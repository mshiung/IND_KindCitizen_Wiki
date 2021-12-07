# **Set up Project**
Follow [Set up Shopify Theme Project](/Guidelines/Set-up-Shopify-Theme-Project) to set up project\
[Install Theme Kit](https://shopify.dev/themes/tools/theme-kit/getting-started)
## **Theme architecture**
## Layout
The layout directory contains the layout files for a theme, through which template files are rendered.

## Templates
The templates directory contains a theme’s template files, which control what's rendered on each type of page.

## Sections
The sections directory contains a theme’s sections, which are reusable modules of content that merchants can customize. Sections also define the blocks that can be used inside of them.

## Snippets
The snippets directory contains Liquid files that host smaller reusable snippets of code. You can reference these snippets throughout the theme with the Liquid render tag.

## Assets
The assets directory contains all of the assets used in a theme, including image, CSS, and JavaScript files.

## **Templates used for Merchant**

| For | File name  |
|--|--|
| Sign up | page.mSignup.liquid |
| Home |page.mHome.liquid|
| Add Product | page.mProductForm.liquid |
| Edit Product | page.mProductEdit.liquid |
| Invoice | page.mInvoice.liquid |
| Order Summary | page.mOrderSummary.liquid |
| Scan QR Code | page.mScanQR.liquid |
| Enter Code | page.mCodeEnter.liquid |
| Checkout | page.mCheckout.liquid |
| Settings | page.mSettings.liquid |
Most Templates have their own corresponding Section

## **Possible Enhancement**
- Loading speed (Invoice page, currently reload after clicking on view invoice details; Currently retrieve all invoices at once)
- Stricter Form validation (Form error handling)
- Error Handling
- Alert/confirm dialog
- Responsive CSS

## **Possible Changes** 
- invoice timestamp (currently using claimedTimestamp)
- Deleting Product (currently Archive Product instead)
- Removing tags from product form
- Enter Code Manually (currently that code is very long)