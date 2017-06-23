---
title: MIORA API docs

includes:
  - users
  - errors
  - countries
  - cities

search: true
---

# Introduction

Welcome to Miora API docs.

# Authentication 

> To authenticate, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "https://api.miora.io/user/" \
  -H "Authorization: Bearer meowmeowmeow"
```

> Make sure to replace `meowmeowmeow` with your user token.

Some of our methods are only valid with a Auth Token. On these cases yo must send the header Authorization:

`Authorization: Bearer meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with the user token.
</aside>