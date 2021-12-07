# Singpass Authentication

## NDI OIDC Authentication Code Flow
The screenshot below describes the NDI OIDC Authentication Code Flow.

![image.png](/.attachments/image-20f2f59c-1924-4ed8-85e3-c3f09377986a.png)

The Client (Relying Party, RP) i.e. KindCitizen needs to implement both the Frontend and Backend for the NDI OIDC authentication.


# Section 1: Frontend

## QR Code Guide

The guide to embed the Singpass QR code into the application is defined here:
https://stg-id.singpass.gov.sg/docs/embedded-auth/js#_introduction

## QR Code display in Shopfiy theme login.liquid

The above guide has been implemented in the login.liquid file in the Shopify themes.

Just beneath the social login buttons i.e. Facebook and Google, you will find the div that houses the QR code which is rendered by a script.

![image.png](/.attachments/image-3f03adae-a259-41b5-8837-3763a66f3afa.png)

The snippet below shows the scripts that render the QR Code as well as set parameters to initialize the authentication session. The highlighted portions below are for production environment.

![image.png](/.attachments/image-34e4eab3-f69e-44c5-8345-752b48e92664.png)

The respective staging and production settings are shown in the table below:

|  | Staging  | Production |
|--|--|--|
| QR Script | https://stg-id.singpass.gov.sg/static/ndi_embedded_auth.js | https://id.singpass.gov.sg/static/ndi_embedded_auth.js |
| clientId | Z1QgkeaV7icc6z4pPTeImHK6fwS3mMXh | DTUj8d1k5bwGfrexXHFaiiqPRAwmbIw1 |
| redirectUri | https://kindcitizen.myshopify.com/apps/kcapi/singpass/stg/redirect | https://kindcitizen.myshopify.com/apps/kcapi/singpass/prd/redirect |

<br>
When the user initiates the authentication by scanning the QR code, they will be redirected to the redirectUri which is hosted on KCAPI (Backend) to continue the authentication flow. The backend authentication flow is explained in "Section 2: Backend".
<br>
<br>
Upon successful Singpass authentication at the backend, the user will be redirected back to the KC login page and automatically logged in with the Beneficiary's credentials embedded in the URL as the parameter "id_token". The format of the Beneficiary's credentials derived from "id_token" is described in "Section 3: Beneficiary Login Credentials (SECRET)".

![image.png](/.attachments/image-565b8f59-6c46-4b43-a6a9-41eeee2eb4ba.png)

<br>
<br>

# Section 2: Backend

Detailed diagram and description of the authentication flow and the NDI - Authorization API Reference can be found here:
https://stg-id.singpass.gov.sg/docs/authorization/api#_introduction

## KCAPI apisingpass.js

3 APIs are currently exposed to Singpass through KCAPI to handle the NDI OIDC Authentication Code Flow.

| S/N | API | Description |
|--|--|--|
| 1| https://kindcitizen.myshopify.com/apps/kcapi/.well-known/keys | API to expose KC's public signing and encryption key. JSON Web Key (JWK) key pairs are generated and only the public keys are exposed. |
| 2| https://kindcitizen.myshopify.com/apps/kcapi/singpass/stg/redirect | API (redirect_uri) to receive the Authorization Code, initiate the Client Assertion and receive the ID Token / Access Token for staging environment. |
| 3| https://kindcitizen.myshopify.com/apps/kcapi/singpass/prd/redirect | API (redirect_uri) to receive the Authorization Code, initiate the Client Assertion and receive the ID Token / Access Token for production environment.

KCAPI uses the jose crypto library https://www.npmjs.com/package/jose to handle JSON Web Key (JWK), JSON Web Token (JWT), JSON Web Signature (JWS) and JSON Web Encryption (JWE) used in the authentication.

## GET /.well-known/keys

JWK keypairs are generated from this website: https://mkjwk.org/

Example JWK Signing Keypair generation:

![image.png](/.attachments/image-9dc32dc2-c759-4b9f-a811-2a29f491c72b.png)

Example JWK Encryption Keypair generation:

![image.png](/.attachments/image-f2c47616-f513-4b17-85ea-3a5ac73f6431.png)

_**Note:** These generated keypairs are currently hardcoded in apisingpass.js, and may not be ideal from a security standpoint as the keys should be refreshed regularly. A unique Key ID (with a timestamp) can be refreshed every 6 months to generate the keypairs. The jose crypto library can be used to generate the keypairs dynamically._

You may verify the generated keypairs using the verifier provided by Singpass by pasting the JSON representation of the JWK: https://api.singpass.gov.sg/library/login/developers/jwks-verifier


## GET /singpass/stg/redirect, GET /singpass/prd/redirect

These are APIs are the redirect URIs that Singpass will call after the QR Code is scanned. Depending on whether the staging or production API is called as defined in the QR Code settings, the following highlighted Singpass APIs will be used in the authentication process. See NDI - Authorization API Reference Section 1 https://stg-id.singpass.gov.sg/docs/authorization/api#_staging_and_production_urls.

![image.png](/.attachments/image-b92afa42-d018-47b2-9c81-0a951fed1436.png)

**Step 1:** An Authorization Code will be received through the URI's query parameter "code", which will be used during Client Assertion when calling the Token Endpoint.

![image.png](/.attachments/image-854d7a0a-e3b7-4364-8d38-d3d1d2550b48.png)

**Step 2:** Call OpenID discovery endpoint to retrieve the latest OpenID endpoints once every hour. The essential endpoints for us are the Issuer URL and the Token Endpoint URL. See NDI - Authorization API Reference Section 3 https://stg-id.singpass.gov.sg/docs/authorization/api#_well_known_endpoints.

![image.png](/.attachments/image-6a15509f-0b78-414d-b259-b794368351c4.png)

**Step 3:** Call Token Endpoint to perform Client Assertion by passing the JWT signed by KC's private signing JWK. See NDI - Authorization API Reference Section 4.1.2 https://stg-id.singpass.gov.sg/docs/authorization/api#_authorization_code_grant_authenticated_with_client_assertion_jwt.

![image.png](/.attachments/image-1e987b10-7827-43fd-aa00-8021e5372c1b.png)

**Step 4:** Retrieve the NRIC from the ID Token returned by the Client Assertion. The ID Token needs to be decrypted using KC's private encryption JWK to obtain the JWS ID Token. The JWS ID Token is then base64 decoded to obtain its claim where the NRIC can be found. See NDI - Authorization API Reference Section 4.1.4 https://stg-id.singpass.gov.sg/docs/authorization/api#_id_token_structure

![image.png](/.attachments/image-194b0847-36c1-4473-840a-b2d093675649.png)

**Step 5:** Redirect the client back to the login page and pass the MD5 hash of the NRIC to be used as the email ID and password for Beneficiary login. **(SECRET)** 

![image.png](/.attachments/image-5e0342aa-d851-4688-b703-0fb152bacb4e.png)

# Section 3: Beneficiary Login Credentials **(SECRET)**

When a new Beneficiary is added using the KCAPI POST /addBeneficiary, a new account is automatically created and activated in Shopify without the need for email activation.

The email ID is the string representation of the first 16 hex values of the Beneficiary's NRIC MD5 hash. 
The password is the string representation of the full hex value of the Beneficiary's NRIC MD5 hash. 
See example in the table below.

| NRIC | MD5 Hash | Email | Password |
|--|--|--|--|
| S1234567A | 61cbec065ae7577b7cc20d88a8b89ffe | 61cbec065ae7577b@kcemail.com | 61cbec065ae7577b7cc20d88a8b89ffe |

