# **Set up Project**
Click on [Set up Shopify Theme Project](https://dev.azure.com/NanyangPoly/IND_KindCitizen/_wiki/wikis/IND_KindCitizen_WIKI/3870/Set-up-Shopify-Theme-Project) to set up project         
Theme ID: "123094270113"
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
# Templates for Contributor 
Contributor templates have a "c" in front of them.
| Purpose  | File name |
|--|--|
| Home  | page.cHome.liquid |
| Favourite | page.cFavourite.liquid |
| Notifications | page.cNotifications.liquid |
| Profile | page.cProfile.liquid |
| Profile: History of contribution | page.cProfileContribution.liquid |
| Profile: Account Information | page.cProfileAccount.liquid |
| Profile: Get Help | page.cProfileHelp.liquid |
| Category: Food | page.cCategories.liquid |
| Food: Halal | page.cHalal.liquid |
| Food: Vegan | page.cVegan.liquid |
| Food: Wholegrain | page.cWholegrain.liquid |
| Food: Fast Food | page.cFastfood.liquid |
| Food: Dessert | page.cDessert.liquid |
| Food: Rice | page.cRice.liquid |
| Food: Noodles | page.cNoodles.liquid |
| Food: Spicy | page.cSpicy.liquid |
| Shop detail | page.cShopView.liquid |
| Item detail | page.cFoodView.liquid |
| Cart | cart.liquid |
| Cart message | page.cCheckout.liquid |

# Sections for Contributor

| Purpose  | File name |
|--|--|
| Header | header.liquid |

# User stories completed
- Homepage (UI, API)
- Favourites page (UI)
- Notifications page (UI)
- Profile page (UI)
- Profile account information page (UI)
- Food category page (UI, API)
- Food subcategory pages (UI, API)
- Shop detail page (UI)
- Food detail page(UI, API)
- Cart (UI)
- Cart message (UI)



# Expected user stories to be completed
Food category featured merchants carousel
- Implement API 

API items to be added into shopify cart
- Add button to add API item into shopify cart
- Shopify cart shows added API items (name, quantity, price)
- Message variable for contributors to add a kindness message shown in page.cCheckout.liquid, to be added into shopify cart form through line items

Show shop details through /getMerchantProfile API

# Enhancement
- Loading speed for carousels 
- Language usage

# Feedback
- Unable to show shop details through /getMerchantProfile API


