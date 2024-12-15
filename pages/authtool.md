# AuthTool Documentation

AuthTool is a powerful authentication tool that allows you to easily integrate secure login features into your application.

## Introduction

AuthTool provides a simple and secure solution for managing user authentication in your applications. It supports multiple authentication methods and offers easy integration with your backend.

## Getting Started

To get started with AuthTool, follow these steps:

### 1. Application Registration

1. Register your application on the AkirasTeam platform.
2. Obtain your `app_id` and `redirect_uri`.

### 2. Integration of the AuthTool Script

Include the AuthTool script in your application:

```html
<script src="https://api.akirasteam.com/auth/integration.js"></script>
```

### 3. Adding the AuthTool Element

Add the following HTML element to your login page:

```html
<span id="akiras-auth" app_id="YOUR_APP_ID" redirect_uri="YOUR_REDIRECT_URI"></span>
```

### 4. Customization

Customize the appearance and behavior of the AuthTool button according to your needs.

## Callback Implementation

After the user logs in, they will be redirected to your specified redirect_uri with a token. Here is how to handle the callback in PHP and JavaScript:

PHP
