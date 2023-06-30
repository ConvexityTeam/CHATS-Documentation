---
description: Authentication Management
---

# Authentication

{% swagger method="post" path="auth/login" baseUrl="https://staging-api.chats.cash/v1/" summary="Login endpoint into the CHATS platform" expanded="false" %}
{% swagger-description %}
With this endpoint, users can login as an NGO, Donor, Beneficiary, Field Agent. Each of these stakeholder are identified by the RoleID.&#x20;

Here are the following Roles and their IDs:

SuperAdmin: 1, GodMode: 2, NgoAdmin: 3, NgoSubAdmin: 4, FieldAgent: 5, Beneficiary: 7, Donor: 8,
{% endswagger-description %}

{% swagger-parameter in="body" name="email" required="true" %}
The email of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" required="true" %}
The password of the user
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Login successfully" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Invalid login credentials" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="vendors/auth/login" baseUrl="https://staging-api.chats.cash/v1/" summary="Vendor Login" %}
{% swagger-description %}
The Vendor Login endpoint differs from the regular login because of the body params. The body takes in a Vendor ID, alongside password.
{% endswagger-description %}

{% swagger-parameter in="body" name="vendor_id" required="true" %}
Vendor Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" required="true" %}
Vendor Password
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Login Successful" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="Login failed. Please try again later" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/auth/donor-login" baseUrl="https://staging-api.chats.cash/v1" summary="Donor Login" %}
{% swagger-description %}
The Donor Login endpoint.
{% endswagger-description %}

{% swagger-parameter in="body" name="email" required="true" %}
Email of Donor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" required="true" %}
Password of Donor
{% endswagger-parameter %}
{% endswagger %}

{% swagger method="post" path="/admin/auth/login" baseUrl="https://staging-api.chats.cash/v1" summary="Admin Login" %}
{% swagger-description %}
The Admin Login endpoint.
{% endswagger-description %}

{% swagger-parameter in="body" name="email" required="true" %}
Email of Admin
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" required="true" %}
Password of Admin
{% endswagger-parameter %}
{% endswagger %}



{% swagger method="post" path="/auth/password/reset" baseUrl="https://staging-api.chats.cash/v1" summary="Request Password Reset" %}
{% swagger-description %}
This endpoint sends a reset password request to the user who called the endpoint.
{% endswagger-description %}

{% swagger-parameter in="body" name="email" %}
If email is used
{% endswagger-parameter %}

{% swagger-parameter in="body" name="phone" %}
If phone is used
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Token generated" %}

{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Request failed please try again" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="put" path="/auth/password/reset" baseUrl="https://staging-api.chats.cash/v1" summary="Password Reset" %}
{% swagger-description %}
This endpoint resets the password of the user who called the endpoint
{% endswagger-description %}

{% swagger-parameter in="body" name="ref" required="true" %}
Password reset ref from previous step
{% endswagger-parameter %}

{% swagger-parameter in="body" name="otp" required="true" %}
Password Reset OTP
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" required="true" %}
New Password
{% endswagger-parameter %}

{% swagger-parameter in="body" name="confirm_password" required="true" %}
Password Confirmation
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Password changed" %}

{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Reset password request failed. Please try again" %}

{% endswagger-response %}
{% endswagger %}
