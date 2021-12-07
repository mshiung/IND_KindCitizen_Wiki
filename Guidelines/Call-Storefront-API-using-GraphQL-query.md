# On Liquid file, add following codes to call Shopify Storefront API using GraphQL query.

Take note that some values may change, depending on which GraphQL queries you are going to call.
<br/>GraphQL App has been setup, so **no action is required**. Just learn how to use following codes.

More references:
- [GraphQL queries](https://shopify.dev/concepts/graphql/queries)
- [Storefront API reference](https://shopify.dev/docs/storefront-api/reference)
<br/>

```
<script>
function apiCall(query) {
  return fetch('https://kindcitizen.myshopify.com/api/graphql.json', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/graphql',
      //"Access-Control-Origin": "*",
      'X-Shopify-Storefront-Access-Token': "09518c3f83f8ed7c026f824bedc4ae88"
    },
    "body": query
  }).then(response => response.json());
}
  
function getProducts() {
  const query = `{
    products(first: 2) {
      edges {
        node {
          title
          description
          images(first: 1) {
            edges {
              node {
                altText
                transformedSrc(maxWidth: 400, maxHeight: 400)
              }
            }
          }
        }
      }
    }
  }`;
  return apiCall(query);
}
  
$(document).ready(function() {
  const $app = $('#app');
  
  getProducts().then(response => {
 
    $app.append("<div class='products'></div>");
     
    const $products = $('.products');
 
    response.data.products.edges.forEach(product => {
       
      const template = `<div class="product">
            <h2>${product.node.title}</h2>
            <img alt="${product.node.images.edges[0].node.altText}" src="${product.node.images.edges[0].node.transformedSrc}">
            <p>${product.node.description}</p>
              </div>`;
     
       
      $products.append(template);
    });
  });  
  
});  
</script>
<div id="app">
	<h1 class="page-title">Shopify Custom Storefront App</h1>
</div>
```


