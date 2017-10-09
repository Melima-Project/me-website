---
layout:     post
title:      Advanced user creation
date:       2017-08-19
categories: [User management]
lang: en 
permalink: /advanced-user-creation/
---

You can read about basic user creation in the [Getting started]({{ site.baseurl }}/getting-started/) guide.

Right now we see two common behaviors:  

- You run Melima for local (physical world) business -  like restaurant, cafe, bakery and etc
- You use Melima as platform to sell things and manage orders through the internet

For the first use-case you need minimum one administrator account to add new products, and separate user accounts for every device (possibly tablet with future Melima Droid version), you run client application on. And by default user can only read products, and create orders. And anonymous users has no read rights at all.  

For the second use case you need re-enable user registration, and make product list readable anonymously, but allow only registered users create orders. Also you possibly need implement captcha and email check, for the registration (and we have plans, to make it easy to add). 

## Enable user registration

Remove from the `model-config.json`

```json
    {
      "accessType": "*",
      "principalType": "ROLE",
      "principalId": "$everyone",
      "permission": "DENY",
      "property": "create"
    },
```

## LoopBack ACLs

Unfortunately LoopBack acls could be hard to understand, but in case, you need custom configuration, you need to use ACLs.  
However, we try to make our default configuration applicable to use, and provide more configuration examples in future.  
For basic ACL adjust tasks you can use ACL generator. You can run it with `lb acl` in Melima root directory.

You could also check LoopBack ACL and authentication docs:  

<https://loopback.io/doc/en/lb3/Controlling-data-access.html>  

<https://loopback.io/doc/en/lb3/tag_authentication.html>










