---
layout:     post
title:      "Getting started"
subtitle:   "Getting started with Melima"
date:       2017-08-18
categories: Introduction
lang: en 
permalink: /getting-started/
---

Check [Prerequirements](https://github.com/Melima-Project/me-core#prerequirements) and [Installation](https://github.com/Melima-Project/me-core#installation) first.

## Database creation

Example for PostgresSQL:  

```sql
sudo su - postgres
psql
CREATE DATABASE restaurant;
CREATE USER restaurantuser WITH ENCRYPTED PASSWORD '2GCadoCs9tsTVfYV';
ALTER DATABASE restaurant OWNER TO restaurantuser;
```

  > *Login details for datasource example configuration used, **use your own!***

## Connecting new datasource

By default [loopback-connector-postgresql](https://github.com/strongloop/loopback-connector-postgresql) used, and you can check `me-core/server/datasources.json` file with example configuration defined.
    
```json
{
  "postgresql": {
    "host": "localhost",
    "port": 5432,
    "url": "",
    "database": "restaurant",
    "password": "2GCadoCs9tsTVfYV",
    "name": "postgresql",
    "user": "restaurantuser",
    "connector": "postgresql"
  }
}
```

If you want connect any other popular database, check [database connectors](http://loopback.io/doc/en/lb3/Database-connectors.html) documentation. You also, may need adjust modules `dataType` and model-config.


## Creating users

You can register new user via Melima Administration Interface (MAI) or create new users manually. By default new users registration is disabled, and you need to create users manually.  
You can create `createuser.js` file with following contents in `me-core/server/boot` directory.

```javascript
  'use strict';
  module.exports = function(createusers) {

      createusers.models.User.create([{
          email: 'user@example.local',
          password: 'yourpassword1'
      }, {
          email: 'admin@example.local',
          password: 'yourpassword2'
      }], function(err, users) {
          console.log(err, users);
          createusers.models.Role.create({
              name: 'Product'
          }, function(err, product) {
              console.log(err, product);
              product.principals.create({
                  principalType: createusers.models.RoleMapping.USER,
                  principalId: users[0].id
              }, function(mainproduct) {
                  console.log(err, mainproduct);
                  createusers.models.Role.create({
                      name: 'Order'
                  }, function(err, order) {
                      console.log(err, order);
                      order.principals.create({
                          principalType: createusers.models.RoleMapping.USER,
                          principalId: users[1].id
                      }, function(mainorder) {
                          console.log(err, mainorder);
                      });
                  });
              });
          });
      });
  };
```

This will create two users `user@example.local` with user rights and `admin@example.local` with administrator privileges.

***Administrator*** account used to create and edit new products, and has ability to update or finalize orders.  
And ***user accounts*** used to create orders, and have only read access to the product list.

After you created `createuser.js` file, you can start Melima Core with `node .` command from the root directory. And you should see new users creation messages in terminal emulator output.  
You can use `Control + C` to close Melima Core as for now, and delete `createuser.js`.

  > *Check [Advanced user creation]() for more information.*

## Using Melima Web

You can get Melima Web from our [github repository](https://github.com/Melima-Project/me-web).

### Development or testing

You can serve Melima Web from Melima Core `client` directory. You just need to copy index.html and js folder inside `client` directory.  
Just start Melima Core with `node .` as normal.

  > *By default Melima Core starts on 3000 port and you can access it locally via `http://127.0.0.1:3000`*

### Production

You can use your favorite web-server, but we recommend you to stick with Nginx.

Recommended Nginx repositories:

<https://nginx.org/en/linux_packages.html#mainline> 

<https://github.com/cryptofuture/nginx-hda-bundle/>  

<https://launchpad.net/%7Ehda-me/+archive/ubuntu/nginx-stable>


