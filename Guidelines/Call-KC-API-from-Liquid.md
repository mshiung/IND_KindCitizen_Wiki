# On Liquid file, add following codes to call KC API using AJAX.

Take note that some values may change, depending on which KC APIs you are going to call.
<br/>- **name of KC API**, e.g. ***.myshopify.com/apps/kcapi<font color="red">/showCurrentDateTime</font>' _(see highlighted in <font color="red">red</font>)_
<br/>- request data
<br/>- response data


```
<script>
    jQuery(window).load(function(){
      data = {};
      jQuery.ajax({
        type: 'POST',
        url: 'https://kindcitizen.myshopify.com/apps/kcapi/showCurrentDateTime',
        data: data,
        dataType: 'json',
        success: function(data) {
          $.each( data, function(i, item) {
            alert(item);
            // do something with your data here
          });
        },
        error:function(request, status, error){
          alert(request.responseText);
        }
      });
    }); 
</script>
```


