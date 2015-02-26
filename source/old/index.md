---
title: Proxyclick API Reference

language_tabs:
  - shell
  - python
  - php

toc_footers:
  - <a href='https://api.proxyclick.com/v1/docs'>Documentation Powered by Proxyclick</a>

includes:
  - meeting
  - visitor
  - ticket
  - company	
  - errors

---

# Introduction

Welcome to the Proxyclick API! You can use our API to access Proxyclick API endpoints.

You can view code examples (in Shell, Python and PHP) in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Summary

This part will explain shortly how the API needs to be consumed


# Authentication

This section describes the authentication needed to be able to use the api

Proxyclick expects for the access token to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer <accessToken>`

<aside class="notice">
You must replace `<accessToken>` with your personal access token.
</aside>

<aside class="success">Remember — a happy kitten is an authenticated kitten!</aside>

<aside class="warning">If you're not using an administrator API key, note that some kittens will return 403 Forbidden if they are hidden for admins only.</aside>



