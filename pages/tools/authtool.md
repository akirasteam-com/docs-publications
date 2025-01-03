Author: Loïc V.
Date: 15/12/2024

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
<script src="https://api.akirasteam.com/auth2/integration.js"></script>
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
```php
<?php
session_start();

error_reporting(E_ALL);
ini_set('display_errors', 1);

$token = $_GET['token'] ?? null;
$app_id = $_GET['app_id'] ?? null;

if (!$token || !$app_id) {
    die('Missing token or app_id');
}

$api_url = "https://api.akirasteam.com/auth2/?action=validate_token&token=" . urlencode($token) . "&app_id=" . urlencode($app_id);

$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, $api_url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$response = curl_exec($ch);

if (curl_errno($ch)) {
    $error_msg = curl_error($ch);
    curl_close($ch);
    die('Failed to connect to API: ' . $error_msg);
}

curl_close($ch);

$data = json_decode($response, true);

if (!$data || $data['status'] !== 'success') {
    die('Invalid token or app_id');
}

$_SESSION['user_id'] = $data['data']['user']['id'];
$_SESSION['user_email'] = $data['data']['user']['email'];

header('location: panel.php');
exit();
?>
```
