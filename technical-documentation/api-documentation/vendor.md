---
description: Campaign Management
---

# Vendor

{% swagger method="post" path="/organisations/:organisation_id/campaigns" baseUrl="https://staging-api.chats.cash/v1" summary="Campaign Creation" %}
{% swagger-description %}
Endpoint to create a new campaign by the NGO.



Authorization Header takes in the Bearer token generated from the login of the NGO&#x20;
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-parameter in="body" name="title" required="true" %}
Title of Campaign
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" required="true" %}
Type of Campaign
{% endswagger-parameter %}

{% swagger-parameter in="body" name="description" required="true" %}
Description of Campaign
{% endswagger-parameter %}

{% swagger-parameter in="body" name="budget" required="true" type="Int" %}
Budget of Campaign
{% endswagger-parameter %}

{% swagger-parameter in="body" name="location" required="true" %}
Location of Campaign
{% endswagger-parameter %}

{% swagger-parameter in="body" name="start_date" required="true" %}
Start date of Campaign
{% endswagger-parameter %}

{% swagger-parameter in="body" name="end_date" required="true" %}
End date of Campaign
{% endswagger-parameter %}

{% swagger-parameter in="body" name="is_public" type="bool" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Created Campaign" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Campaign creation failed. Please retry" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="put" path="/organisations/:organisation_id/campaigns/:campaign_id" baseUrl="https://staging-api.chats.cash/v1" summary="Update Existing Campaign" %}
{% swagger-description %}
Endpoint to update the status of an existing campaign.



Authorization Header takes in the Bearer token generated from the login of the NGO&#x20;
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" required="true" %}
Type of Campaign
{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" required="true" type="" %}
Status of campaign
{% endswagger-parameter %}

{% swagger-parameter in="path" name="campaign_id" required="true" %}
ID of campaign
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Campaign updated" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Campaign update failed. Please retry" %}

{% endswagger-response %}
{% endswagger %}



{% swagger method="post" path="/organisations/:organisation_id/campaigns/:campaign_id/fund-campaign" baseUrl="https://staging-api.chats.cash/v1" summary="Fund Cash Campaign" expanded="true" %}
{% swagger-description %}
This is the endpoint to fund the campaign wallet. This is done by the NGO



Authorization Header takes in the Bearer token generated from the login of the NGO&#x20;
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

{% swagger-response status="200: OK" description="Organisation fund to campaign is Processing" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Campaign funding failed. Please retry" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/organisations/:organisation_id/campaigns/:campaign_id/fund" baseUrl="https://staging-api.chats.cash/v1" summary="Disburse Funds to Beneficiaries" %}
{% swagger-description %}
This endpoint allows funds to be distributed to the beneficiaries of a campaign.



Authorization Header takes in the Bearer token generated from the login of the NGO&#x20;
{% endswagger-description %}

{% swagger-parameter in="body" name="token_type" required="true" %}
Type of funds disbursement

\




\


\[papertoken, wallet, smstoken]
{% endswagger-parameter %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="path" name="campaign_id" required="true" %}
ID of campaign
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Campaign fund with beneficiaries is Processing" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Disbursing failed. Please retry" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/organisations/:organisation_id/onboarded/:campaign_id/:replicaCampaignId" baseUrl="https://staging-api.chats.cash/v1" summary="Import Beneficiaries" %}
{% swagger-description %}
This endpoint allows the NGO to import already existing beneficiaries from an existing campaigns to a newly created campaign.



Authorization Header takes in the Bearer token generated from the login of the NGO&#x20;
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="path" name="campaign_id" required="true" %}
ID of campaign
{% endswagger-parameter %}

{% swagger-parameter in="path" name="replicaCampaignId" required="true" %}
The campaign ID you want to duplicate beneficiary
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/organisations/extend-campaign/:organisation_id" baseUrl="https://staging-api.chats.cash/v1" summary="Extend Campaign" %}
{% swagger-description %}
This endpoint extends the existence of a campaign. It is an optional feature for the NGO who decide whether or not to extend a campaign. \
\
Optionally, the NGO can decide to additionally add funds to the campaign. However, if the NGO decides not to extend the campaign, funds are refunded back to the wallet of the NGO.



Authorization Header takes in the Bearer token generated from the login of the NGO
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="body" name="end_date" required="true" %}
Campaign End Date - DD-MM-YYYY
{% endswagger-parameter %}

{% swagger-parameter in="body" name="campaign_id" required="true" %}
ID of the campaign to extend
{% endswagger-parameter %}

{% swagger-parameter in="body" name="location" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="additional_budget" %}
additional budget to fund the campaign with
{% endswagger-parameter %}

{% swagger-parameter in="body" name="description" %}
Description of the extention
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="campaign extended" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Internal server error. Contact support" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/organisations/:organisation_id/campaigns/all" baseUrl="https://staging-api.chats.cash/v1" summary="Get all organisation campaigns" %}
{% swagger-description %}
Endpint to fetch all the campaigns of organisations
{% endswagger-description %}

{% swagger-parameter in="path" name="organisation_id" required="true" %}
ID of organisation
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Bearer <token>
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="All Campaigns" %}

{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Request failed. Please try again" %}

{% endswagger-response %}
{% endswagger %}
