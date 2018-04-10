---
layout: post
title:  Company api is available now!
date:   2018-04-10 11:15:51 +0200
categories: FastData Reactive Play
---
We have recently written api for applications that currently only support company data. How to use it?

<h2>Company type</h2>

<p>The company type is to be defined by a company type. How should you handle it?</p>

<p>This repository is available here: <a href="https://github.com/silenceonthewire/com.silenceonthewire.companies">https://github.com/silenceonthewire/com.silenceonthewire.companies</a>.

<h3>Add new type</h3>

<p>To add a new business type, please submit the following query:</p>

<code>curl -H "Content-Type: application/json" -X POST -d '{"id":"1","name":"xyz", "description": "hello", "timestamp": "timestamp"}' http://localhost:59603/api/type</code>

<h3>Update type</h3>

<p>To update a business type, please submit the following query:</p>

<code>curl -H "Content-Type: application/json" -X PUT -d '{"id":"1","name":"xyz", "description": "hello", "timestamp": "timestamp"}' http://localhost:59603/api/type</code>

<h3>Delete type</h3>

<p>To delete a business type, please submit the following query:</p>

<code>curl -H "Content-Type: application/json" -X PUT http://localhost:59603/api/type/1</code>

<h3>Get all business types</h3>

<p>To get all  business types, please submit the following query:</p>

<code>curl http://localhost:59603//api/type</code>

<h3>Get current business type</h3>

<p>To get current company, please submit the following query:</p>

<code>curl http://localhost:59603//api/type/1</code>

<h2>Company</h2>

The company defines contact company data.

<h3>Add new company</h3>

<p>To add a new comapany, please submit the following query:</p>

<code>curl -H "Content-Type: application/json" -X POST -d'{"id":"1","typeId":"1", "name":"xyz", "phone": "2222", "email":"email@example.com", "taxNumber": "3435435", "street": "street", "city": "city", "state": "state", "country": "country", "postalCode":"3454", "createdAt": "09/04/2018", "updatedAt": "09/04/2018"}' http://localhost:52592/api/company</code>

<h3>Update company</h3>

<p>To update a company, please submit the following query:</p>

<code>curl -H "Content-Type: application/json" -X PUT -d'{"id":"1","typeId":"1", "name":"xyz", "phone": "2222", "email":"email@example.com", "taxNumber": "3435435", "street": "street", "city": "city", "state": "state", "country": "country", "postalCode":"3454", "createdAt": "09/04/2018", "updatedAt": "09/04/2018"}' http://localhost:52592/api/company</code>

<h3>Delete company</h3>

<p>To delete a company, please submit the following query:</p>

<code>curl -H "Content-Type: application/json" -X DELETE http://localhost:52592/api/company/1</code>

<h3>Get all companies</h3>

<p>To get all companies, please submit the following query:</p>

<code>curl http://localhost:59603//api/company</code>

<h3>Get current company</h3>

<p>To get current company, please submit the following query:</p>

<code>curl http://localhost:59603//api/type/1</code>


