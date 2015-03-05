---
title: Proxyclick API Reference

language_tabs:
  - shell
  
toc_footers:
  - <a href='https://api.proxyclick.com/v1/docs'>Documentation Powered by Proxyclick</a>
  - <a href='https://www.proxyclick.com/api-access-request'>Request API access</a>

includes:
  - authentication	
  - meeting
  - visit
  - visitor
  - company	
  - errors
  - version

---

# Introduction

Welcome to the Proxyclick API! You can use our API to access Proxyclick API endpoints.

You can view code examples (in Shell, Python and PHP) in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.


# Summary

This part will explain shortly how the API needs to be consumed.

All API requests must be sent over HTTPS.
JSON is used in all responses : API data is JSON encoded with UTF-8.

The API also uses common approaches for the following

Function | Description
-------- | -----------
Data | API data is JSON encoded with UTF-8. API JSON is either a single object or a list of objects.
Authorization |	Access control made by access token.
Errors | 4xx and 5xx responses returning JSON with error codes, see [errors](#errors)
HTTP | Methods are used in accordance with HTTP (GET, POST, PUT, DELETE and PATCH verbs are used but not for every URIs.) and resources are identified using URIs. All API requests are sent over HTTPS.

The API is versioned - see [version](#version) for more details. 




