# Updates on KC APIs


## <font color="purple">5 Nov 2021</font>
**/getBeneficiaryItemsJustAdded**
<br/>- For beneficiary to view 'Items Just Added' on specific category page. Input 'category' is required.
<br/>- *"Coming Soon: display for Beneficiary's home page."*

**/getBeneficiaryNewMerchants**
<br/>- For beneficiary to view 'New Merchants' on Beneficiary's home page and specific category page. Input 'category' is required.
<br/>- Options for 'category' attribute input:
<br/>&nbsp;&nbsp;&nbsp;&nbsp;>> Use input 'home' for Beneficiary's home page.
<br/>&nbsp;&nbsp;&nbsp;&nbsp;>> Use other category values for Beneficiary's respective category page.

**/getBeneficiaryHealthyPicks**
<br/>- For beneficiary to view 'Healthy Picks'. No input is required.

**/getBeneficiaryLocalPicks**
<br/>- For beneficiary to view 'Local Picks'. No input is required.

**/addProduct**
<br/>- Removed output attributes: "title", "body_html", "tags".
<br/>- Added output attribute: "productName". Use this to replace "title" output attribute.
<br/>- Use "productDescription" to replace "body_html" output attributes.

**/updateProduct**
<br/>- Removed output attributes: "title", "body_html", "tags".
<br/>- Added output attribute: "productName". Use this to replace "title" output attribute.
<br/>- Use "productDescription" to replace "body_html" output attributes.
<br/>- Removed required fields to input product **title** and **image**.

**/getProductDetails**
<br/>- Removed output attributes: "title", "body_html", "tags".
<br/>- Added output attribute: "productName". Use this to replace "title" output attribute.
<br/>- Use "productDescription" to replace "body_html" output attributes.

**/setMerchantProfile**
<br/>- Added required field to input merchant **reviewRating**. If there is no review rating, please enter 0 or "" as the input.


<br/>

## <font color="purple">3 Nov 2021</font>
**/getContributorNewMerchants**
<br/>- Added option for input 'category' as 'home' to be displayed at Contributor's home page.
<br/>- This API will replace existing **/getMerchantsNew** soon!

**/getContributorTopDemand**
<br/>- For contributor to view 'Top Demand' at Contributor's home page. No input is required.
<br/>- This API will replace existing **/getProductsTopDemand** soon!

<br/>

## <font color="purple">1 Nov 2021</font>
**/getContributorFeaturedMerchants**
<br/>- For contributor to view 'Featured Merchants'. Input 'category' is required.

**/getContributorNewMerchants**
<br/>- For contributor to view 'New Merchants'. Input 'category' is required.

**/getContributorHealthyPicks**
<br/>- For contributor to view 'Healthy Picks'. No input is required.

**/getContributorLocalPicks**
<br/>- For contributor to view 'Local Picks'. No input is required.

<br/>

## <font color="purple">25 Oct 2021</font>
**/getMerchantsNew**
<br/>- Added merchant's review rating.

**/getMerchantsByCategory**
<br/>- Added merchant's review rating.

**/getMerchantsWithPromotions**
<br/>- Added merchant's review rating.

<br/>

## <font color="purple">11 Oct 2021</font>
**/getOrdersNEW**
<br/>- Data is returned based on order number. This data is for specific merchant.
<br/>- This API will replace existing **/getOrders** soon!

**/getClaimVouchersByCategory**
<br/>- Data is returned for Beneficiary to browse active claimVouchers.


<br/>

## <font color="purple">9 Oct 2021</font>
**Webhook Create Order**
<br/>- This process is transparent to Contributor. No action is required.

<br/>

## <font color="purple">29 Sep 2021</font>
**/getProductsByMerchant**
<br/>- By default (i.e. if no '_status_' is sent during request), only active products will be returned.
<br/>- To retrieve products with specific status, following are the options for 'status' input:
<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; '<font color="green">active</font>' - to retrieve active products
<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; '<font color="green">draft</font>' - to retrieve draft products
<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; '<font color="green">archived</font>' - to retrieve archived products
<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; '<font color="green">ad</font>' - to retrieve active & draft products (So far, only Merchant requires this option!)

**/getMerchantsWithPromotions**
<br/>- Included 'merchantStoreName' info.

**/getProductCategoryOptions**
<br/>- Removed. Please use '/getProductCategoryOptionsNEW' as replacement.

**/addProduct**
<br/>- Removed 'tags' input during request.
<br/>- No 'base64Images' data will be returned.

**/updateProduct**
<br/>- Removed 'tags' input during request.
<br/>- No 'base64Images' data will be returned.

~~ =.= ~~
<br/>


