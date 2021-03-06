---
layout: post
title:  Enterprise Serial Bus 1.1 Usable User is now available in the Alpha version.
date:   2018-04-03 11:15:51 +0200
categories: FastData Reactive Play
---

<h1>Enterprie Serial Bus 1.1 Usable User is now available in the Alpha version.</h1>

<p>Theoretically, we have to write tests for selected controllers, but you can already use Api version 1.1 Alpha. Api is based on the basic assumptions of reactive programming, such as the use of actors from the Akka package. We invite you to test and submit comments and transfer donations. If the subsidies exceed 5,000 usd, we will go fully on Fast Data.</p>

<h2>Usage</h2>

<p><code>git clone https://github.com/silenceonthewire/com.silenceonthewire.esb.git<code></p>
<p><code>cd com.silenceonthewire.esb<code></p>
<p><code>sbt run<code></p>

<h2>How to use this version?</h2>

<h3>Companies actions</h3>

<p>While working on our api, we assumed that to create a user, you have to create at least one company. Therefore, as the first element we explain activities on companies.</p>

<h4>Add new company</h4>

<p>There is a newCompany.json file in the com.silenceonthewire.esb/test-data/company directory. This file is sent to the server by the command:</p>

<p><code>curl -H "Content-Type: application/json" -X POST -d @newCompany.json http://localhost:9000/api/v1/users/company/add<code></p>

<p>And we get the answer:</p>

<p><code>{"id": 1522759308539, "createdAt": 1522759308539, "updatedAt": 1522759308539, "name": "Example Company", "phone": "123456789", "taxNumber": "1234567890", "email": "company @ example.com "," address ":" street 1 "," city ":" city "," state ":" state "," country ":" country "," postalCode ":" 11-111 "," users "[]}<code></p>

<h4>Update company</h4>

<p>There is a currentCompany.json file in the com.silenceonthewire.esb/test-data/company directory. This file is sent to the server by the command:</p>

<p><code>curl -H "Content-Type: application/json" -X PUT -d @currentCompany.json http://localhost:9000/api/v1/users/company/update<code></p>

<p>And we get the answer:</p>

<p><code>{"id":1522759308539,"createdAt":1522759308539,"updatedAt":1522760348933,"name":"Example Company","phone":"123456789","taxNumber":"1234567890","email":"company@example.com","address":"street 1","city":"city","state":"state","country":"country","postalCode":"11-111","users":[]}<code></p>

<h4>Delete company</h4>

<p>To delete company we send the following request:</p>

<p><code> curl -H "Content-Type: application/json" -X DELETE http://localhost:9000/api/v1/users/company/delete/1522759308539<code></p>

<p>If the removal succeeds, the system will return the data of the deleted company:</p>

<p><code>{"id":1522759308539,"createdAt":1522759308539,"updatedAt":1522760348933,"name":"Example Company","phone":"123456789","taxNumber":"1234567890","email":"company@example.com","address":"street 1","city":"city","state":"state","country":"country","postalCode":"11-111","users":[]}<code></p>

<h4>Get company by id</h4>

<p>To get the company by the id number, send the following request:</p>

<p><code>curl http://localhost:9000/api/v1/users/company/getById/1522760698755<code></p>

<p>if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522760698755,"createdAt":1522760698756,"updatedAt":1522760698756,"name":"Example Company","phone":"123456789","taxNumber":"1234567890","email":"company@example.com","address":"street 1","city":"city","state":"state","country":"country","postalCode":"11-111","users":[]}<code></p>

<h4>Get company by name</h4>

<p>To get the company by the name, send the following request:</p>

<p><code>curl http://localhost:9000/api/v1/users/company/getByName/ExampleCompany<code></p>

<p>if the request succeeds, the system will be returned:</p>
.bundle
.sass-cache
Gemfile.lock
*.gem

<p><code>{"id":1522760698755,"createdAt":1522760698756,"updatedAt":1522760698756,"name":"Example Company","phone":"123456789","taxNumber":"1234567890","email":"company@example.com","address":"street 1","city":"city","state":"state","country":"country","postalCode":"11-111","users":[]}<code></p>

<h4>Get company by tax number</h4>

<p>To get company by the tax numner, send the following request:</p>

<p><code>curl http://localhost:9000/api/v1/users/company/getByTaxNumber/1234567890<code></p>

<p>if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522760698755,"createdAt":1522760698756,"updatedAt":1522760698756,"name":"Example Company","phone":"123456789","taxNumber":"1234567890","email":"company@example.com","address":"street 1","city":"city","state":"state","country":"country","postalCode":"11-111","users":[]}<code></p>

<h4>Get company by email</h4>

<p>To get company by the email, send the following request:</p>

<p><code>curl http://localhost:9000/api/v1/users/company/getByEmail/company@example.com<code></p>

<p>if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522760698755,"createdAt":1522760698756,"updatedAt":1522760698756,"name":"Example Company","phone":"123456789","taxNumber":"1234567890","email":"company@example.com","address":"street 1","city":"city","state":"state","country":"country","postalCode":"11-111","users":[]}<code></p>

<h4>Get company by phone</h4>

<p>To get company by the phone, send the following request:</p>

<p><code>curl http://localhost:9000/api/v1/users/company/getByPhone/123456789<code></p>

<p>if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522761344385,"createdAt":1522761344385,"updatedAt":1522761344385,"name":"ExampleCompany","phone":"123456789","taxNumber":"1234567890","email":"company@example.com","address":"street 1","city":"city","state":"state","country":"country","postalCode":"11-111","users":[]}<code></p>

<h4>Get all companies</h4>

<p>To get all companies, send the following request:</p>

<p><code> curl http://localhost:9000/api/v1/users/company/all<code></p>

<p>if the request succeeds, the system will be returned:</p>

<p><code>[{"id":1522761344385,"createdAt":1522761344385,"updatedAt":1522761344385,"name":"ExampleCompany","phone":"123456789","taxNumber":"1234567890","email":"company@example.com","address":"street 1","city":"city","state":"state","country":"country","postalCode":"11-111","users":[]}]<code></p>

<h3>Users actions</h3>

<p>User management is the second part of the api. It allows you to quickly create, edit, find and delete users.</p>

<h4>Create new user</h4>

<p>If you can add user, send the following request:</p>

<p><code>curl -H "Content-Type: application/json" -X POST -d @newUser.json http://localhost:9000/api/v1/users/user/add<code></p>

<p>if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522772875674,"createdAt":1522772875674,"updatedAt":1522772875674,"firstName":"jonh","lastName":"Doe","email":"john1@doe.com","phone":"12345167689","isAdmin":true,"admin":true},{"id":1522772977796,"createdAt":1522772977796,"updatedAt":1522772977796,"firstName":"jonh","lastName":"Doe","email":"john@doe.com","phone":"1235167689","isAdmin":true,"admin":true}<code></p>

<h4>Update user</h4>

<p>If you can update user, send the following request:</p>

<p><code> curl -H "Content-Type: application/json" -X PUT -d @currentUser.json http://localhost:9000/api/v1/users/user/edit/1522772875674<code></p>

<p>And if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522772875674,"createdAt":1522772875674,"updatedAt":1522773478050,"firstName":"jonh","lastName":"Doe","email":"john322343@doe.com","phone":"12334325167689","isAdmin":true,"admin":true}<code></p>

<h4>Get user by id</h4>

<p>If you can get user by id, you must send this request:</p>

<p><code>curl http://localhost:9000/api/v1/users/user/getById/1522772875674<code></p>

<p>And if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522772875674,"createdAt":1522772875674,"updatedAt":1522773478050,"firstName":"jonh","lastName":"Doe","email":"john322343@doe.com","phone":"12334325167689","isAdmin":true,"admin":true}<code></p>

<h4>Get user by phone</h4>

<p>If you can get user by id, you must send this request:</p>

<p><code>curl http://localhost:9000/api/v1/users/user/getByPhone/12334325167689<code></p>

<p>And if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522772875674,"createdAt":1522772875674,"updatedAt":1522773478050,"firstName":"jonh","lastName":"Doe","email":"john322343@doe.com","phone":"12334325167689","isAdmin":true,"admin":true}<code></p>

<h4>Get user by email</h4>

<p>If you can get user by id, you must send this request:</p>

<p><code>curl http://localhost:9000/api/v1/users/user/getByEmail/john322343@doe.com<code></p>

<p>And if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522772875674,"createdAt":1522772875674,"updatedAt":1522773478050,"firstName":"jonh","lastName":"Doe","email":"john322343@doe.com","phone":"12334325167689","isAdmin":true,"admin":true}<code></p>

<h4>Get all users</h4>

<p>If you can get all users, you must send this request:</p>

<p><code>curl http://localhost:9000/api/v1/users/user/all<code></p>

<p>And if the request succeeds, the system will be returned:</p>

<p><code>[{"id":1522772875674,"createdAt":1522772875674,"updatedAt":1522773478050,"firstName":"jonh","lastName":"Doe","email":"john322343@doe.com","phone":"12334325167689","isAdmin":true,"admin":true},{"id":1522772977796,"createdAt":1522772977796,"updatedAt":1522772977796,"firstName":"jonh","lastName":"Doe","email":"john@doe.com","phone":"1235167689","isAdmin":true,"admin":true}]<code></p>

<h4>Get user by phone and password</h4>

<p>If you can get user by phone and password, you must send this request:</p>

<p><code>curl -H "Content-Type: application/json" -X POST -d @phoneAndPassword.json http://localhost:9000/api/v1/users/user/getByPhoneAndPassword<code></p>

<p>And if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522776276728,"createdAt":1522776276728,"updatedAt":1522776276728,"firstName":"jonh","lastName":"Doe","email":"john@doe.com","phone":"1235167689","isAdmin":true,"admin":true}<code></p>

<h4>Get user by email and password</h4>

<p>If you can get user by email and password, you must send this request:</p>

<p><code>curl -H "Content-Type: application/json" -X POST -d @emailAndPassword.json http://localhost:9000/api/v1/users/user/getByEmailAndPassword<code></p>

<p>And if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522776276728,"createdAt":1522776276728,"updatedAt":1522776276728,"firstName":"jonh","lastName":"Doe","email":"john@doe.com","phone":"1235167689","isAdmin":true,"admin":true}<code></p>

<h4>Delete user</h4>

<p>If you can get delete user, you must send this request:</p>

<p><code>curl -H "Content-Type: application/json" -X DELETE http://localhost:9000/api/v1/users/user/delete/1522776276728<code></p>

<p>And if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522776276728,"createdAt":1522776276728,"updatedAt":1522776276728,"firstName":"jonh","lastName":"Doe","email":"john@doe.com","phone":"1235167689","isAdmin":true,"admin":true}<code></p>

<h3>Account actions</h3>

<p>User accounts are the last element. It contains some very simple operations. I already explain.</p>

<h4>Create account</h4>

<p>If you can get create account, you must send this request:</p>

<p><code>curl -H "Content-Type: application/json" -X POST -d @newAccount.json http://localhost:9000/api/v1/users/account/create<code></p>

<p>And if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522783057798,"createdAt":1522783057798,"updatedAt":1522783057798,"user":null,"taxNumber":"21434","ssn":"43546547","address":"Street 1","city":"city","state":"state","country":"country","postalCode":"23334"}<code></p>

<h4>Get by id</h4>

<p>If you can get account by id, you must send this request:</p>

<p><code>curl http://localhost:9000/api/v1/users/account/id/1522783057798<code></p>

<p>And if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522783057798,"createdAt":1522783057798,"updatedAt":1522783057798,"user":null,"taxNumber":"21434","ssn":"43546547","address":"Street 1","city":"city","state":"state","country":"country","postalCode":"23334"}<code></p>


<h4>Get by tax number</h4>

<p>If you can get account by id, you must send this request:</p>

<p><code>curl http://localhost:9000/api/v1/users/account/taxNumber/21434<code></p>

<p>And if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522783057798,"createdAt":1522783057798,"updatedAt":1522783057798,"user":null,"taxNumber":"21434","ssn":"43546547","address":"Street 1","city":"city","state":"state","country":"country","postalCode":"23334"}<code></p>


<h4>Get by ssn</h4>

<p>If you can get account by ssn, you must send this request:</p>

<p><code>curl http://localhost:9000/api/v1/users/account/bySsn/43546547<code></p>

<p>And if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522783057798,"createdAt":1522783057798,"updatedAt":1522783057798,"user":null,"taxNumber":"21434","ssn":"43546547","address":"Street 1","city":"city","state":"state","country":"country","postalCode":"23334"}<code></p>

<h4>Get by user</h4>

<p>If you can get account by user, you must send this request:</p>

<p><code>curl http://localhost:9000/api/v1/users/account/byUser/1522831550466<code></p>

<p>And if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522783057798,"createdAt":1522783057798,"updatedAt":1522783057798,"user":null,"taxNumber":"21434","ssn":"43546547","address":"Street 1","city":"city","state":"state","country":"country","postalCode":"23334"}<code></p>

<h4>Update account</h4>

<p>If you can update account, you must send this request:</p>

<p><code>curl -H "Content-Type: application/json" -X PUT -d @currentAccount.json http://localhost:9000/api/v1/users/account/update<code></p>

<p>And if the request succeeds, the system will be returned:</p>

<p><code>{"id":1522783057798,"createdAt":1522783057798,"updatedAt":1522786151443,"user":{"id":1522782031521,"createdAt":1522782031521,"updatedAt":1522782031521,"firstName":"jonh","lastName":"Doe","email":"john@doe.com","phone":"1235167689","isAdmin":true,"admin":true},"taxNumber":"df21434","ssn":"435465rte47","address":"Street 1","city":"city","state":"state","country":"country","postalCode":"23334"}<code></p>

<h3>What's next?</h3>

<p>As I have already mentioned, we will reach the full Fast Data if the amount of your shares exceeds 5,000 usd. Then we'll break into Apache Kafka and Cassandra's base.</p>

<p>Additionally, remember that you can already post orders related to FastData, I am more interested in freelancing than full-time job. Calculations using artificial intelligence? There is no welding. Rewriting the existing application interface to something deadly fast is also not a problem.</p>

<p>What's next with this project? First of all, I want to stabilize all available api this week. And then I want to write files management with the OCR system, so I can not do without Tesserac and Elastic Search. Greetings and look forward to the news.</p>
