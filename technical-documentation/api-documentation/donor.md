---
description: Donor Management
---

# Donor

{% swagger method="post" path="/auth/:organisation_id/invite/:campaign_id" baseUrl="https://staging-api.chats.cash/v1" summary="Donor Invitation" %}
{% swagger-description %}
Endpoint to invite donors into a particular campaign.



Authorization Header takes in the Bearer token generated from the login of the NGO&#x20;
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-parameter in="body" name="inviteeEmail" required="true" %}
Email of Donors for invitation
{% endswagger-parameter %}

{% swagger-parameter in="body" name="link" required="false" %}
URL of Donor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="message" required="false" %}
Extra message to Donor
{% endswagger-parameter %}

{% swagger-parameter in="path" name="campaign_id" required="true" %}
ID of campaign
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Invite sent to donor" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal Server Error. Please try again" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/auth/:campaignId/confirm-campaign-invite/:token" baseUrl="https://staging-api.chats.cash/v1" summary="Donor Invitation Confirmation" %}
{% swagger-description %}
Endpoint to confirm the invitation sent to donor(s)


{% endswagger-description %}

{% swagger-parameter in="path" name="campaignId" required="true" %}
ID of campaign for donor to join
{% endswagger-parameter %}

{% swagger-parameter in="path" name="token" required="true" %}
Unique token for each invite confirmation
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="campaign invitation has been confirmed" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal Server Error. Please try again" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/organisations/:organisation_id/campaigns/:campaign_id/crypto_pay" baseUrl="https://staging-api.chats.cash/v1" summary="Campaign Funding by Donor (Crypto)" %}
{% swagger-description %}
This is the crypto option endpoint that allows a donor to fund a campaign.

Authorization Header takes in the Bearer token generated from the login of the Donor
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="path" name="campaign_id" required="true" %}
ID of campaign
{% endswagger-parameter %}

{% swagger-parameter in="body" name="currency" required="true" %}
Crypto type

\[USDT, BTC, XRP, XDP]
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Wallet info received" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal Server Error. Contact Support" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/organisations/request-withdrawal/:organisation_id" baseUrl="https://staging-api.chats.cash/v1" summary="Donor Withdrawal Request" %}
{% swagger-description %}
This is the endpoint that allows a donor to make a withdrawal request. This request is sent to the Admin, who approves or rejects the request.



Authorization Header takes in the Bearer token generated from the login of the Donor&#x20;
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="body" name="campaign_id" required="true" %}
ID of campaign
{% endswagger-parameter %}

{% swagger-parameter in="body" name="donor_organisation_id" required="true" %}
Donor's organisation ID
{% endswagger-parameter %}

{% swagger-parameter in="body" name="reason" %}
Reason for the withdrawal request
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Request sent" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal server error. Contact support" %}

{% endswagger-response %}
{% endswagger %}



{% swagger method="get" path="/organisations/:organisation_id/campaigns/:campaign_id/vendors" baseUrl="https://staging-api.chats.cash/v1" summary="Get all campaign vendors" expanded="false" %}
{% swagger-description %}
This endpoint is used to get all the vendors in a campaign.



Authorization Header takes in the Bearer token generated from the login of the Donor&#x20;
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" type="" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="path" name="campaign_id" required="true" %}
ID of campaign
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Campaign Vendors" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Server Error. Unexpected error occurred" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/organisations/:organisation_id/campaigns/:campaign_id/beneficiaries" baseUrl="https://staging-api.chats.cash/v1" summary="Get all campaign beneficiaries" %}
{% swagger-description %}
This endpoint is used to get all the beneficiaries in a campaign.



Authorization Header takes in the Bearer token generated from the login of the Donor&#x20;
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="path" name="campaign_id" required="true" %}
ID of campaign
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Campaign Beneficiaries" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Server Error. Unexpected error occurred" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/organisation/:organisation_id/campaigns/:campaign_id/beneficiary_age" baseUrl="https://staging-api.chats.cash/v1" summary="Get all campaign beneficiaries by age group" %}
{% swagger-description %}
This endpoint is used to get all campaign beneficiaries by age group.



Authorization Header takes in the Bearer token generated from the login of the Donor&#x20;
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="path" name="campaign_id" required="true" %}
ID of campaign
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Campaign Beneficiaries" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Server Error. Unexpected error. Please retry" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/organisation/:organisation_id/campaigns/:campaign_id/beneficiary_mstatus" baseUrl="https://staging-api.chats.cash/v1" summary="Get all campaign beneficiaries by marital status" %}
{% swagger-description %}
This endpoint is used to get all campaign beneficiaries by age group.



Authorization Header takes in the Bearer token generated from the login of the Donor&#x20;
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-parameter in="path" name="campaign_id" required="true" %}
ID of campaign
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Campaign Beneficiaries" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Server Error. Unexpected error. Please retry" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/organisation/:organisation_id/campaigns/:campaign_id/beneficiary_location" baseUrl="https://staging-api.chats.cash/v1" summary="Get all campaign beneficiaries by location" %}
{% swagger-description %}
This endpoint is used to get all campaign beneficiaries by location.



Authorization Header takes in the Bearer token generated from the login of the Donor&#x20;
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-parameter in="path" name="campaign_id" required="true" %}
ID of campaign
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Campaign Beneficiaries" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Server Error. Unexpected error. Please retry" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/organisation/:organisation_id/campaigns/:campaign_id/beneficiary_balance" baseUrl="https://staging-api.chats.cash/v1" summary="Get all campaign beneficiaries balances" %}
{% swagger-description %}
This endpoint is used to get all campaign beneficiaries' balances.

Authorization Header takes in the Bearer token generated from the login of the Donor&#x20;
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="path" name="campaign_id" required="true" %}
ID of campaign
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Server Error. Unexpected error. Please retry" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/organisations/donations/private_donor/campaigns/all" baseUrl="https://staging-api.chats.cash/v1" summary="Get all campaigns" %}
{% swagger-description %}
This endpoint is used to get all campaigns.



Authorization Header takes in the Bearer token generated from the login of the Donor&#x20;
{% endswagger-description %}

{% swagger-parameter in="query" name="type" required="true" %}
Type of campaign
{% endswagger-parameter %}

{% swagger-parameter in="query" name="OrganisationId" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Request failed. Please try again." %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/organisations/:organisation_id/private/campaigns/:campaign_id" baseUrl="https://staging-api.chats.cash/v1" summary="Get a single campaign" %}
{% swagger-description %}
This endpoint is used to get a campaign by ID.



Authorization Header takes in the Bearer token generated from the login of the Donor
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="path" name="campaign_id" required="true" %}
ID of campaign
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal server error. Contact support" %}

{% endswagger-response %}
{% endswagger %}
