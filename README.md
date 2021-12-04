# bulkfollows-automation
Bulkfollows.com - Automation Software. Using the Bulkfollows API, the software can place orders right from your desktop. 

For checking the order status, you need to add order ID and then click check status. On clicking check status, the text below would be updated. 

When a new order is placed, the bulkfollows api returns the Order ID. This ID is stored in a text file in the current working directory. If you want to check the status of the order, copy that order ID and put it in the Order ID field and click on check status. The `status:` label will be updated with the status. The order usually takes 3 days so you can check the order once in a day and see if the order has completed or not.

> Add your data and let it place orders for you. 


It can also place bulk orders. To generate mass order, you have to Add orders in the format told in the website, i.e., ajsd123|123123|123123; OrderID;Link;Quantity. After this, you can click on Generate Mass Order button.

### Check Order Status Code?

```
    def check_order_status(self, order_id=None):
        if order_id:
            self.ORDER_ID = order_id
        if self.ORDER_ID is None:
            return "No Order Placed."
        order = requests.post(self.API_URL, {'key':self.API_KEY, 'action':'status', 'order':self.ORDER_ID})
        if order.ok:
            _data = json.loads(order.text)
            return f"Total Remaining: {_data['remains']}"
        else:
            return "Order Status Check Failed."
```

Placing Order is very simple via the bulkfollows API.

![front page bulkfollows automation mujeebishaque](https://github.com/mujeebishaque/bulkfollows-automation/blob/main/bin/first.png)

Second Tab of the software for storing the API key. The API key is stored in a text file created in the current working directory.
This tab also shows the current API KEY that's stored in the software and is being used. If you want to save a new API key, get your API key from bulkfollows website. Copy it to clipboard and click save. The software will update the current key and you'll be able to see the new key.

![Second Tab Bulkfollows automation mujeebishaque](https://github.com/mujeebishaque/bulkfollows-automation/blob/main/bin/second.jpg)
