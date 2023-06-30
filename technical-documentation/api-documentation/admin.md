---
description: Admin Management
---

# Admin



{% swagger method="get" path="/admin/ngos" baseUrl="https://staging-api.chats.cash/v1" summary="Get all NGOs" expanded="false" %}
{% swagger-description %}
This endpoint is used to get all NGOs.



Authorization Header takes in the Bearer token generated from the login of the Admin&#x20;
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" type="" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="NGOs retrieved" %}

{% endswagger-response %}

{% swagger-response status="404: Not Found" description="Internal Server Error" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/admin/vendors" baseUrl="https://staging-api.chats.cash/v1" summary="Get all Vendors" %}
{% swagger-description %}
This endpoint is used to get all Vendors.



Authorization Header takes in the Bearer token generated from the login of the Admin&#x20;
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Vendors retrieved" %}

{% endswagger-response %}

{% swagger-response status="404: Not Found" description="Internal Server Error" %}

{% endswagger-response %}
{% endswagger %}



{% swagger method="get" path="/admin/beneficiaries" baseUrl="https://staging-api.chats.cash/v1" summary="Get all beneficiaries" %}
{% swagger-description %}
This endpoint is used to get all beneficiaries

Authorization Header takes in the Bearer token generated from the login of the Admin&#x20;
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Beneficiaries retrieved" %}

{% endswagger-response %}

{% swagger-response status="404: Not Found" description="" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/admin/campaigns" baseUrl="https://staging-api.chats.cash/v1" summary="Get all campaigns" %}
{% swagger-description %}
This endpoint is used to get all campaigns



Authorization Header takes in the Bearer token generated from the login of the Admin&#x20;
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Campaign retrieved" %}

{% endswagger-response %}

{% swagger-response status="404: Not Found" description="Internal error occured. Please try again" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="admin/donors" baseUrl="https://staging-api.chats.cash/v1" summary="Get all donors" %}
{% swagger-description %}
This endpoint is used to get all donors



Authorization Header takes in the Bearer token generated from the login of the Admin&#x20;
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Donors retrieved" %}

{% endswagger-response %}

{% swagger-response status="404: Not Found" description="Server Error. Unexpected error. Please retry" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/admin/withdrawal-requests" baseUrl="https://staging-api.chats.cash/v1" summary="Get all donors' withdrawal requests" %}
{% swagger-description %}
This endpoint is used to get all donors' withdrawal requests.



Authorization Header takes in the Bearer token generated from the login of the Admin&#x20;
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Donor withdrawal requests" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal server error. Contact support" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/admin/approve-reject-request/:organisation_id" baseUrl="https://staging-api.chats.cash/v1" summary="Approve / reject Donor's withdrawal request" %}
{% swagger-description %}
This endpoint is used to approve the withdrawal request



Authorization Header takes in the Bearer token generated from the login of the Admin&#x20;
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-parameter in="body" name="campaign_id" required="true" %}
ID of campaign
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" required="true" %}
The approval type



\[approve, reject]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="request_id" required="true" %}
ID or request
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal server error. Contact support" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/admin/update-status" baseUrl="https://staging-api.chats.cash/v1" summary="Update User status" %}
{% swagger-description %}
This endpoint is used to update the status of a user.



Authorization Header takes in the Bearer token generated from the login of the Admin&#x20;
{% endswagger-description %}

{% swagger-parameter in="body" name="userId" required="true" %}
Id of user
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" required="true" %}
status type&#x20;

\[activated, suspended]
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="User status updated" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal server error. Contact support" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/admin/vendor-transactions/:vendor_id" baseUrl="https://staging-api.chats.cash/v1" summary="Vendor Transactions" %}
{% swagger-description %}
This endpoint is used to get the transaction of a vendor.



Authorization Header takes in the Bearer token generated from the login of the Admin&#x20;
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-parameter in="path" name="vendor_id" required="true" %}
ID of vendor
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="vendor transactions retrieved" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal server error. Contact support" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/admin/register-beneficiary" baseUrl="https://staging-api.chats.cash/v1" summary="Beneficiary Registration" %}
{% swagger-description %}
This endpoint enables an Admin to register a new Beneficiary



Authorization Header takes in the Bearer token generated from the login of the Admin&#x20;
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-parameter in="body" name="first_name" required="true" %}
First name of Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="first_name" required="true" %}
Last name of Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" required="true" %}
Email of Beneficiary
{% endswagger-parameter %}

{% swagger-parameter in="body" name="phone" required="true" %}
Phone of Beneficiary
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Beneficiary registered successfully" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal server error. Please try again later." %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/admin/register-vendor" baseUrl="https://staging-api.chats.cash/v1" summary="Vendor Registration" %}
{% swagger-description %}
This endpoint enables an Admin to register a new Vendor



Authorization Header takes in the Bearer token generated from the login of the Admin&#x20;
{% endswagger-description %}

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

{% swagger-parameter in="body" name="phone" required="true" %}
Phone of Vendor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="location" required="true" %}
Location of Vendor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="address" required="true" %}
Address of Vendor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="store_name" required="true" %}
Store name of Vendor
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Vendor Account Created" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal Server Error. Contact Support" %}

{% endswagger-response %}
{% endswagger %}
