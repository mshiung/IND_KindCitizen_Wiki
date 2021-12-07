# KindCitizen Meal Ordering System

## Team Members (CAA 6 Sep 2021)
|Name|Role  |
|--|--|
|Chai Min Shiung  |Supervisor  |
|Leow Zhen Zhen  |Co-Supervisor  |
|Verawaty  |Co-Supervisor  |
|Bernice Tan  |Client/Co-Assessor  |
|Heng Yit Kiat  |Student Developer  |
|Jaedon Lim  |Student Developer  |
|Mah Zi Xin  |Student Developer  |
|Sng Yee Hwee  |Student Developer  |
|Xavier Tay Jia Jie  |Student Developer  |

## Project Objective
![MobileLandingPage.png](/.attachments/MobileLandingPage-a2cac514-2283-4125-8001-09f1a5c7ecc6.png)
- This project is provided by Gmeal Singapore Pte Ltd to School of Design & Media (SDM) and School of Information Technology (SIT) to digitize their meal ordering process involving merchants, contributors and beneficiaries.
- The project will develop a total of 8 front end and backend modules to support the user stories and various workflows.

## System Architecture
![SystemArchitecture.png](/.attachments/SystemArchitecture-9c921dd6-3339-49fd-9709-38bd0e90a813.png)

## Update, 9 Jul 2021
### Timeline
![Software Development 20210303.png](/.attachments/Software%20Development%2020210303-12a7ba49-06b8-456e-91c3-24a75fd1da67.png)

### Status:
- Completed:
  - Development and deployment environment setup on Shopify, Firebase and Azure DevOps.
  - User stories and Adobe XD designs for merchant, contributor and beneficiary pages.
- In Progress:
  - User stories and Adobe XD designs for NGO & KindCitizen Admin pages. (Added requirements above original objectives)
  - Development of merchant, contributor and beneficiary static pages. (Students) 
  - Development of APIs for static pages access to Firebase RDB and Shopify storefront. (Vera / Min Shiung)
  - Account Management including SingPass and other Social Logins e.g. Google, Facebook. (Min Shiung / Vera)

### Issues/Feedback:
- Min Shiung reported that the project is currently in the development phase but the client wants to add 2 new user roles (NGO and KindCitizen Admin) to the requirements.
- AD(PC&T) enquired about the efforts required to handle the new requirements. Min Shiung replied that based on current estimate that it takes 1 period to complete 3 user roles, the team is looking at an additional 1 period (till end P3).
- AD(PC&T) queried if it is possible to complete part 1 with 3 user roles, then work on part 2 for the 2 new user roles. Min Shiung replied that the 2 roles, albeit being missed out during the requirements gathering phase, are still crucial to the project.
- AD(PC&T) then asked if the client is aware that the project will potentially be delayed for another 2 to 3 months. Zhen Zhen replied that the team has conveyed to the client that it is not possible to complete a full working system (with 5 roles) by Sep ’21. She also updated that the client is looking to see some completed workflows in Sep ’21 and a full rollout (with complete UAT) in Nov ’21. The team will continue to liaise with SIDM and the client to finalise the requirement of the new roles.
- Nam Beng enquired about the payment schedule of the project. Min Shiung replied that there are 5 payments scheduled and the first payment (project signoff) has been completed.
James highlighted to the team to closely track the project and the amount of efforts required to work on the new requirements and to discuss them with the client.
- Min Shiung wrapped up the update by showing the Azure DevOps platform and some of the work done by the FYPJ students.

## Update, 30 Sep 2021
### Timeline
![Software Development 20210930.png](/.attachments/Software%20Development%2020210930-1b1926b5-e339-4b59-b756-d77a9bf02038.png)
### Status:
- Completed:
  - User stories and Adobe XD designs for KindCitizen Admin pages. (Added requirements above original objectives)
  - Development of APIs for Merchant static pages access to Firebase RDB and Shopify storefront, enabling user/product onboarding, login, invoicing, QR code scanning.
  - Contributor static pages.
  - Beneficiary static pages.
  - Static login pages including SingPass and other Social Logins e.g. Google, Facebook.
- In Progress:
  - Development of NGO & KindCitizen Admin static pages. (Students)
  - Development of APIs for Contributor, Beneficiary, NGO & KindCitizen Admin static pages access to Firebase RDB and Shopify storefront. (Vera / Min Shiung)
  - Account Management including user onboarding. (Min Shiung / Vera)
  - PayLah!, GrabPay integration. (Min Shiung / Zhen Zhen)
  - Xero integration. (Min Shiung / Zhen Zhen)
  - Mobile app deployment to Google Play and Apple Store. (Min Shiung)

### Issues/Feedback:
- The team had shown some completed workflows to the client and allowed the client to onboard merchants at the end of P2. However, this is insufficient for the client's needs to secure funding and initiate a press release for the project. As a result, the client had requested help to set up a "Plan B", which is an interim Shopify store that resembles the actual system's marketplace for Contributors. The team assigned a student to help with "Plan B" to a point where the client decided to take over the set up on 23 Sep 2021, and told us not to do anything anymore. I have recently visited the "Plan B" store and noticed that nothing has changed since the team left it.
- The team discovered a design flaw that causes excessive downloads from the backend Firebase RDB which has since been rectified. However, an additional funding of $1000 has been requested (and approved by AD(PC&T)) in order to continue with P3.
![FirebaseRDBExcessiveDownload.png](/.attachments/FirebaseRDBExcessiveDownload-76b14816-991a-4658-b2cd-45c5dc401d67.png)