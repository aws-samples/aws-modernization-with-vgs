---
title: "Outbound Routes" # MODIFY THIS TITLE
chapter: true
weight: 4 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

# Create Outbound Routes to 3rd-parties <!-- MODIFY THIS HEADING -->

## Create Outbound Routes to Each 3rd-party   

### 3rd-party (KYC/AML/ID Verification)

1) If not already logged in, log into your VGS Dashboard (https://dashboard.verygoodsecurity.com).
2) On the top, left-hand side, just under the organization name, click on the "Vault" tab.
3) On the left-hand side, under "Vault", click on "Routes".
4) At the top, just under the "Vault ID", select the "HTTP" tab.
5) On the right-hand side, click on "Add Route" and select "Outbound route".
6) The following picture highlights, with red boxes, the areas to select/modify in steps #2 through #5.

![VGS Dashboard Routes](/images/vgs-dashboard-routes.jpg)


7) Under Upstream Host, review the setting pointing to Prove's base API endpoint (https://api.staging.payfone.com).
8) Scroll down to filters.
9) Under "Conditions" in the default filter, set an OR condition with the following settings:
        * PathInfo matches "/identity/v2". This points to your server-side API endpoint destination.  
	or  
        * PathInfo matches "/identity/verify/v2". This points to your server-side API endpoint destination.  
	or  
        * PathInfo matches "/trust/v2". This points to your server-side API endpoint destination.  
10) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
11) Scroll down and select the "Basic" tab below "Tag".  
12) Under "Operation", select "REVEAL" to reveal the sensitive data alias.  
13) Under "Content Type, select "Json" to identify the content type of the request.  
14) Under "Fields in JSON path", enter "$.phone_number" into field 1.  
15) Scroll down to "Storage" below "Targets".
16) Click on "Storage" field and select "Persistent".
17) Under "Alias Format", click the field and select "Account Number - Number Length Preserving (A4) - xxxxxxxxxxxx<last four>.  
18) The following pictures highlights, with red boxes, the areas to select/modify in steps #7 through #17.

![VGS Dashboard Outbound Routes Upstream Host Prove](/images/vgs-dashboard-outbound-route-upstream-host-prove.jpg)

![VGS Dashboard Outbound Routes Reveal Phone Number Conditions Prove](/images/vgs-dashboard-outbound-route-reveal-phone-number-conditions-prove.jpg)

![VGS Dashboard Outbound Routes Reveal Phone Number Variable Prove](/images/vgs-dashboard-outbound-route-reveal-phone-number-variable-prove.jpg)

19) Scroll down and hit "Add filter".  
20) Scroll down to filters.
21) Under "Conditions" in the default filter, set an OR condition with the following settings:
        * PathInfo matches "/identity/v2". This points to your server-side API endpoint destination.  
	or  
        * PathInfo matches "/identity/verify/v2". This points to your server-side API endpoint destination.  
	or  
        * PathInfo matches "/trust/v2". This points to your server-side API endpoint destination.  
22) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
23) Scroll down and select the "Basic" tab below "Tag".  
24) Under "Operation", select "REVEAL" to reveal the sensitive data alias.  
25) Under "Content Type, select "Json" to identify the content type of the request.  
26) Under "Fields in JSON path", enter "$.phone_number" into field 1.  
27) Scroll down to "Storage" below "Targets".
28) Click on "Storage" field and select "Persistent".
29) Under "Alias Format", click the field and select "SSN - Format Preserving (A4) - xxx-xx-<last four>.  
30) The following pictures highlights, with red boxes, the areas to select/modify in steps #19 through #29.

![VGS Dashboard Outbound Routes Reveal SSN Conditions Prove](/images/vgs-dashboard-outbound-route-reveal-ssn-conditions-prove.jpg)

![VGS Dashboard Outbound Routes Reveal SSN Variable Prove](/images/vgs-dashboard-outbound-route-reveal-ssn-variable-prove.jpg)


### 3rd-party (Card Issuance)
1) On the top, left-hand side, just under the organization name, click on the "Vault" tab.
2) On the left-hand side, under "Vault", click on "Routes".
3) At the top, just under the "Vault ID", select the "HTTP" tab.
4) On the right-hand side, click on "Add Route" and select "Outbound route".
5) The following picture highlights, with red boxes, the areas to select/modify in steps #1 through #4.

![VGS Dashboard Routes](/images/vgs-dashboard-routes.jpg)

6) Under Upstream Host, review the setting pointing to Prove's base API endpoint (https://api.stripe.com).
7) Scroll down to filters.
8) Under "Conditions" in the default filter, set the following:
        * PathInfo matches "/v1/issuing/cardholders". This points to your server-side API endpoint destination.  
9) Phase: "On request". This defines the API phase. In this case, this filter will trigger on API call response.  
10) Scroll down and select the "Basic" tab below "Tag".  
11) Under "Operation", select "REVEAL" to reveal the sensitive data alias.  
12) Under "Content Type, select "Json" to identify the content type of the request.  
13) Under "Fields in JSON path", enter "$.phone_number" into field 1.  
14) Scroll down to "Storage" below "Targets".
15) Click on "Storage" field and select "Persistent".
16) Under "Alias Format", click the field and select "Account Number - Number Length Preserving (A4) - xxxxxxxxxxxx<last four>.  
17) Scroll down and hit "Add filter".  
18) Scroll down to filters.
19) The following pictures highlights, with red boxes, the areas to select/modify in steps #6 through #18.

![VGS Dashboard Outbound Routes Upstream Host Stripe Card Issuance](/images/vgs-dashboard-outbound-route-upstream-host-stripe-card-issuance.jpg)

![VGS Dashboard Outbound Routes Reveal Phone Number Conditions Stripe Card Issuance](/images/vgs-dashboard-outbound-route-reveal-phone-number-conditions-stripe-card-issuance.jpg)

![VGS Dashboard Outbound Routes Reveal Phone Number Variable Stripe Card Issuance](/images/vgs-dashboard-outbound-route-reveal-phone-number-variable-stripe-card-issuance.jpg)

20) Under "Conditions" in the default filter, set the following:
        * PathInfo matches "/v1/issuing/cards". This points to your server-side API endpoint destination.  
        * ContentType equals "application/json". This defines the content type of the request.
21) Phase: "On response". This defines the API phase. In this case, this filter will trigger on API call response.  
22) Scroll down and select the "Basic" tab below "Tag".  
23) Under "Operation", select "REDACT" to secure the sensitive data.  
24) Under "Content Type, select "Json" to identify the content type of the request.  
25) Under "Fields in JSON path", enter "$.number" into field 1.  
26) Scroll down to "Storage" below "Targets".
27) Click on "Storage" field and select "Persistent".
28) Under "Alias Format", click the field and select "Payment Card - Format Preserving, Luhn Valid (6T4)".  .  
29) Scroll down and hit "Add filter".  
30) Scroll down to filters.
31) The following pictures highlights, with red boxes, the areas to select/modify in steps #20 through #30.

![VGS Dashboard Outbound Routes Redact PAN Conditions Stripe Card Issuance](/images/vgs-dashboard-outbound-route-redact-pan-conditions-stripe-card-issuance.jpg)

![VGS Dashboard Outbound Routes Redact PAN Variable Stripe Card Issuance](/images/vgs-dashboard-outbound-route-redact-pan-variable-stripe-card-issuance.jpg)

32) Under "Conditions" in the default filter, set an OR condition with the following settings:
        * PathInfo matches "/v1/issuing/cards". This points to your server-side API endpoint destination.  
        * ContentType equals "application/json". This defines the content type of the request.
33) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
34) Scroll down and select the "Basic" tab below "Tag".  
35) Under "Operation", select "REDACT" to secure the sensitive data.  
36) Under "Content Type, select "Json" to identify the content type of the request.  
37) Under "Fields in JSON path", enter "$.cvc" into field 1.  
38) Scroll down to "Storage" below "Targets".  
39) Click on "Storage" field and select "Volatile".  
40) Under "Alias Format", click the field and select "Generic VGS Alias (Default) - tok_sandbox_xxxxxxxxxxxxxxxxxxxxxx.  
41) Scroll to the bottom and hit "Save" in the bottom, right-hand side.  
42) The following pictures highlights, with red boxes, the areas to select/modify in steps #32 through #41.

![VGS Dashboard Outbound Routes Redact CVC Conditions Stripe Card Issuance](/images/vgs-dashboard-outbound-route-redact-cvc-conditions-stripe-card-issuance.jpg)

![VGS Dashboard Outbound Routes Redact CVC Variable Stripe Card Issuance](/images/vgs-dashboard-outbound-route-redact-cvc-variable-stripe-card-issuance.jpg)


Congratulations, you have finished this section.  
