---
description: User Management/Authentication
---

# User

{% swagger method="post" path="/auth/ngo-register" baseUrl="https://staging-api.chats.cash/v1" summary="NGO Registration" expanded="false" %}
{% swagger-description %}
Registration endpoint of NGO
{% endswagger-description %}

{% swagger-parameter in="body" name="organisation_name" required="true" %}
The name of Organisation
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" required="true" %}
The email of the organisation representative
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" required="true" %}
Password
{% endswagger-parameter %}

{% swagger-parameter in="body" name="website_url" %}

{% endswagger-parameter %}

{% swagger-response status="201: Created" description="NGO and User registered successfully" %}

{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="An Organisation with such name or website url already exist" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/auth/verify-email/" baseUrl="https://staging-api.chats.cash/v1" summary="NGO Email Verification" %}
{% swagger-description %}
Email verificaiton endpoint for NGO
{% endswagger-description %}

{% swagger-parameter in="body" name="confirmationCode" required="true" %}
Confirmation Code of the Email Verification
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/ngos/:organisation_id/members" baseUrl="https://staging-api.chats.cash/v1" summary="Organisation Member Registration" %}
{% swagger-description %}
Endpoint to register Orgamisation Members. These types of members, include: \[admin, subadmin, fieldagent]



Authorization Header takes in the Bearer token generated from the login of the NGO&#x20;
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-parameter in="body" name="first_name" required="true" %}
First name of Organisation Member
{% endswagger-parameter %}

{% swagger-parameter in="body" name="last_name" required="true" %}
Last name of Organisation Member
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" required="true" %}
Email of the Organisation Member
{% endswagger-parameter %}

{% swagger-parameter in="body" name="phone" required="true" %}
Phone number of Organisation Member
{% endswagger-parameter %}

{% swagger-parameter in="body" name="role" required="true" %}
Type of Organisation Member. Includes: 

\




\


\[admin, subadmin, fieldagent]
{% endswagger-parameter %}
{% endswagger %}

{% swagger method="post" path="/organisations/:organisation_id/vendors" baseUrl="https://staging-api.chats.cash/v1" summary="Vendor Registration by NGO" %}
{% swagger-description %}
Endpoint to register Vendors by NGOs.



Authorization Header takes in the Bearer token generated from the login of the NGO&#x20;
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-parameter in="body" name="first_name" required="true" %}
First name of Vendor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="last_name" required="true" %}
Last name of Vendor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" required="true" %}
Email of Vendor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="store_name" required="true" %}
Store name of Vendor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="location" required="true" %}
Store location of Vendor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" required="true" %}
Store address of Vendor
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Vendor Account Created" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal server error. Contact support" %}

{% endswagger-response %}
{% endswagger %}



{% swagger method="post" path="/ngos/:organisation_id/beneficiaries" baseUrl="https://staging-api.chats.cash/v1" summary="Beneficiary Registration By Field Agent" expanded="true" %}
{% swagger-description %}
This is the endpoint to register beneficiaries by a Field agent. These types of beneficiaries are presumed not to have smart phones to register themselves.&#x20;



Authorization Header takes in the Bearer token generated from the login of Field Agent&#x20;
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" type="" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="body" name="campaign" required="true" %}
The campaign to register the Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="first_name" required="true" %}
First name of Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="last_name" required="true" %}
Last name of Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" %}
Email of Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="phone" required="true" %}
Phone of Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gender" required="true" %}
Gender of Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" required="true" %}
Address of Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="location" required="true" %}
Location of Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="dob" required="true" %}
Date of Birth of Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="profile_pic" required="true" %}
Photo of Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pin" required="true" %}
Campaign pin of the Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nfc" %}

{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Account Onboarded Successfully" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/auth/self-registration" baseUrl="https://staging-api.chats.cash/v1" summary="Beneficiary Self Registration" %}
{% swagger-description %}
This endpoint enables the self registraion of beneficiaries. These types of beneficiaries are presumed to have smart phones to register themselves.&#x20;


{% endswagger-description %}

{% swagger-parameter in="body" name="first_name" required="true" %}
First name of Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="last_name" required="true" %}
Last name of Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" required="true" %}
Email of Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="phone" required="true" %}
Phone number of Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="gender" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="profile_pic" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="state" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="country" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="coordinates" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Account Onboarded Successfully" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="On-boarding failed. Please try again later" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/auth/donor-register" baseUrl="https://staging-api.chats.cash/v1" summary="Donor Registration" %}
{% swagger-description %}
This is the endpoint that registers Donors. Prior to a registration, a donor is sent an invite to join a campaign. Refer to the Donor page, for the invitation endpoint, before, calling this endpoint.
{% endswagger-description %}

{% swagger-parameter in="body" name="organisation_name" required="true" %}
Name of Donor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" required="true" %}
Email of Donor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" required="true" %}
Password of Donor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="website_url" %}
Website URL of Donor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="campaignId" required="true" %}
ID of campaign for Donor to join
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Donor and User registered successfully" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal Server Error, Contact Support" %}

{% endswagger-response %}
{% endswagger %}
