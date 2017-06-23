

# Users

## <span class="put">POST</span> User signup

```shell
curl "https://api.miora.io/user/v2/add" \
-X POST \
-d names="<NAMES>"
-d surnames="<SURNAMES>"
```

Creates auth user's data

### HTTP Request

`POST https://api.miora.io/user/v2/add`

### Parameters

Parameter | Description
--------- | -----------
names | User's first name
surnames | User's last name
email | User's email
password | User's password
genre | User's gender
phone| User's phone 
country_id | User's country id
origin | User's source
address | User's address

<a href="#countries">View list of Countries ID</a>

### Return

Parameter | Description
--------- | -----------
status | 'okay' or 'error'
token | User's auth token
data | User's data


## <span class="put">POST</span> Facebook user signup

```shell
curl "https://api.miora.io/registro/facebook" \
-X POST \
-d user="<USER>"
```

Creates auth user's data

### HTTP Request

`POST https://api.miora.io/registro/facebook`

### Parameters

Parameter | Description
--------- | -----------
user | User's data retrieved from Facebook connection

You need at first to get user's date from Facebook API and then send the returning object to this endpoint. In case the user already exists, the endpoint returns his previously stored data.

### Return

Parameter | Description
--------- | -----------
status | 'okay' or 'error'
token | User's auth token
data | User's data

## <span class="post">POST</span> Authenticate a user

```shell
curl "https://api.miora.io/user/auth" \ 
-X POST \
-d email='sample@miora.io' \
-d password='123456' \
-d origin='widget_fb'
```

### HTTP Request

`POST https://api.miora.io/user/auth`

### Parameters

Parameter | Description
--------- | -----------
email* | User's email
password* | Plain text user's password
origin | utm_source style user's origin

### Return

Parameter | Description
--------- | -----------
status | 'okay' or 'error'

> The above command returns JSON structured like this:

```json
{
  "status": "okay",
  "token": "<TOKEN>",
  "data": { 
    "id": "<USER_ID>",
    "name": "<USER_NAME>"
  } 
}
```

## <span class="post">POST</span> Recover password

```shell
curl "https://api.miora.io/user/recuperar-contrasena" \
-X POST \
-d email='sample@miora.io'
```

### HTTP Request

`POST http://api.miora.io/user/recuperar-contrasena`

Sends a user recovery password e-mail

### Parameters

Parameter | Description
--------- | -----------
email* | User's email

## <span class="post">POST</span> Update Country

```shell
curl "https://api.miora.io/user/update-country" \
-X POST \
-H "Authorization: Bearer meowmeowmeow" \
-d country_id=2
```

Updates auth user's country

### HTTP Request

`POST https://api.miora.io/user/update-country`

### Parameters

Parameter | Description
--------- | -----------
country_id* | Country ID

<a href="#countries">View list of Countries ID</a>

### Return

Parameter | Description
--------- | -----------
status | 'okay' or 'error'
changes | [] (Empty array: no changes detected) or 'country_id' 


## <span class="post">POST</span> Update Device Token

```shell
curl "https://api.miora.io/user/update-device-token" \
-X POST \
-H "Authorization: Bearer meowmeowmeow" \
-d device_token="<TOKEN>"
```

Updates auth user's device token (for sending push notifications, both Android and iOS)

### HTTP Request

`POST https://api.miora.io/user/update-device-token`

### Parameters

Parameter | Description
--------- | -----------
device_token* | Device Token

### Return

Parameter | Description
--------- | -----------
status | 'okay' or 'error'
changes | [] (Empty array: no changes detected) or 'device_token' 

## <span class="put">PUT</span> Update user data

```shell
curl "https://api.miora.io/user/update" \
-X PUT \
-H "Authorization: Bearer meowmeowmeow" \
-d names="<NAMES>"
-d surnames="<SURNAMES>"
```

Updates auth user's data

### HTTP Request

`PUT https://api.miora.io/user/update`

### Parameters

Parameter | Description
--------- | -----------
names | User's first name
surnames | User's last name
genre | User's gender
email | User's email
city_id | User's city_id
phone_mobile | User's phone mobile
phone_landline | User's phone
country_id | User's country id

<a href="#cities">View list of Cities ID</a>
<a href="#countries">View list of Countries ID</a>

### Return

Parameter | Description
--------- | -----------
status | 'okay' or 'error'
changes | Array of changes