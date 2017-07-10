

# Bookings

## <span class="put">POST</span> Create Cart

```shell
curl "https://api.miora.io/cart/create" \
-X POST \
-d user_id=<USER_ID>
-d origin="<ORIGIN>"
-d extra="<EXTRA>"
```

Creates user's cart

### HTTP Request

`POST https://api.miora.io/cart/create`

### Parameters

Parameter | Description
--------- | -----------
user_id | User's ID
origin | Cart's source
extra | Cart's extra data

### Return

Parameter | Description
--------- | -----------
status | 'okay' or 'error'
cart_id | User's cart ID


## <span class="put">POST</span> Process Cart

```shell
curl "https://api.miora.io/cart/process" \
-X POST \
-d cart_id=<CART_ID>
-d data=<DATA>
-d payment="<PAYMENT>"
-d bewe_data={bewe_data}
```

Process user's cart using given gateway

Cart "data" format:

```json
{
  "gateway": "<GATEWAY>",
  "gateway_provider": "<GATEWAY_PROVIDER>", 
  "phone": "<PHONE_NUMBER>", 
  "comments": "<COMMENTS>", 
  "coupon_id": "<COUPON_ID>", 
  "wallet": "true|false>"
}
```

Gateway possible values are:

offline
braintree
payu
stripe
sabadell
transbank
paypal

Gateway_provider possible values are:

payu (Payu's web gateway)
credit-card
credit-card-token
venue
paypal

If Wallet is set to "true", it will use the money inside user's current wallet. 

Phone number is mandatory if the user doesn't have a previously stored phone number.

### HTTP Request

`POST https://api.miora.io/cart/process`

### Return

Parameter | Description
--------- | -----------
status | 'okay' or 'error'
errors | String with errors on processing order.