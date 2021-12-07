## Steps to call KC API using Webhook.

1. From your Shopify admin, go to **Settings** > **Notifications**.
1. Scroll down to the **Webhooks** section.

1. Click the **Create Webhook** button. A new window should appear.

1. From the first drop-down, select the "**Event**".

1. From the second drop-down, choose the format in which you would like Shopify to send this information to you. In this case, select **JSON**.

1. Under URL, enter the URL where you would like data to be stored. In this case, enter the **full URL of KC API** which you would like to call.

1. Click **Add Webhook**. Your webhook should now appear under the "Webhooks" section.

1. You also have the ability to test your webhook, to make sure the information you want is being sent to the correct URL. To do this click the send test notification link. Verify at the URL that you specified that this works.


<br/>More references:
- [Creating/Deleting Webhook](https://help.shopify.com/en/manual/orders/notifications/webhooks)

- [Test Webhook](https://shopify.dev/tutorials/manage-webhooks)
<br/>under "Testing webhooks" section.

- [View Responses from Webhook](https://shopify.dev/docs/admin-api/rest/reference/events/webhook)
<br/>under "List of supported webhook events and topics" section.
