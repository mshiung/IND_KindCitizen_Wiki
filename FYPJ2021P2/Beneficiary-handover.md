# **Set up Project**
Click on [Set up Shopify Theme Project](https://dev.azure.com/NanyangPoly/IND_KindCitizen/_wiki/wikis/IND_KindCitizen_WIKI/3870/Set-up-Shopify-Theme-Project) to set up project         
Theme ID: "123691073697"

# Theme Directories

## Layout 
The layout directory contains the layout files for a theme, where template files are rendered.

## Templates 
The templates directory contains a theme’s template files, which controls what's rendered on each type of page.

## Sections
The sections directory contains a theme’s sections, that are reusable modules of content customized by merchants. Sections also define the blocks that can be used inside of them.

## Snippets 
The snippets directory contains Liquid files that host smaller reusable snippets of code. Snippets can be referred throughout the theme with the Liquid render tag.

## Assets
The assets directory contains all of the assets used in a theme, including image, CSS, and JavaScript files.

## Config 
The config directory contains the config files for a theme, which are related to theme settings.

## Locales
The locales directory contains the locale files for a theme, which are used to provide translated content.

# Templates for Beneficiary 
Contributor templates have a "b" in front of them.
| Purpose  | File name |
|--|--|
| Home  | page.bHome.liquid |
| Token | page.bToken.liquid |
| Item-In-Your-Area | page.bShopCollectionView.liquid |
| Wishlist | page.bWishlist.liquid |
| Notifications | page.bNotifications.liquid |
| Notifications : Food Share | page.bbFoodShare.liquid |
| Wallet | page.bWallet.liquid |
| Claim | page.bFoodClaim.liquid |
| QRCODE | page.bShowQR.liquid |
| Profile | page.bProfile.liquid |
| Help | page.bHelp.liquid |
| Category: Food | page.bFoodNavigate.liquid |
| Shop detail | page.bShopView.liquid |
| Item detail | page.bFoodView.liquid |
| Cart | page.bcart.liquid |

# User stories completed


# Expected user stories to be completed


# Enhancement


# what enhances need to continue 
- change api - add to cart (change api from products api to voucher api)
- remove product api in bWallet page when voucher datas are ready
- change api - bFoodClaim (change api from products api to voucher api)
- ShopView page - image of Kindness
- shop in your area - use API, currently hard codes
- beneficiary ID hard coded in. needs  a function to dynamically change ID according to beneficiary
- tags are hard coded now, there is example codes commented out to check if tags exist. might need to improve on it.
- wishlist needs to check for product status to make sure it is available to be placed on the items just added carousel.
- desktop css for bToken, bShopView, bFoodView, bCart
- footer for bFoodView and bCart (add to cart button and confirm checkout button) shown on mobile but not on desktop. change css class and style.
- localStorage clear when logout.

# Feedback