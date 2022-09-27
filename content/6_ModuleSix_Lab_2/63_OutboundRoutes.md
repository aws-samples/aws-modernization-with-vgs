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
5) Under the "HTTP" tab, select the "All" tab.
6) On the right-hand side, click on "Add Route" and select "Outbound route".
7) The following picture highlights, with red boxes, the areas to select/modify in steps #2 through #6.

![VGS Dashboard Routes](/images/vgs-dashboard-outbound-route.jpg)

8) Under Upstream Host, modify the Upstream Host to point to Prove's base API endpoint (https://api.staging.payfone.com).  
9) Scroll down to "Filters".
10) Under "Conditions" in the default filter, set an OR condition with the following settings:
        * PathInfo matches "/identity/v2". This points to your server-side API endpoint destination.  
	or  
        * PathInfo matches "/identity/verify/v2". This points to your server-side API endpoint destination.  
	or  
        * PathInfo matches "/trust/v2". This points to your server-side API endpoint destination.  
11) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
12) Scroll down and select the "Basic" tab below "Tag".  
13) Under "Operation", select "REVEAL" to reveal the sensitive data alias.  
14) Under "Content Type, select "Json" to identify the content type of the request.  
15) Under "Fields in JSON path", enter "$.phone_number" into field 1.  
16) Scroll down to "Storage" below "Targets".
17) Click on "Storage" field and select "Persistent".
18) Under "Alias Format", click the field and select "Account Number - Number Length Preserving (A4) - xxxxxxxxxxxx<last four>.  
19) The following pictures highlights, with red boxes, the areas to select/modify in steps #8 through #18.

![VGS Dashboard Outbound Routes Upstream Host Prove](/images/vgs-dashboard-outbound-route-upstream-host-prove.jpg)

![VGS Dashboard Outbound Routes Reveal Phone Number Conditions Prove](/images/vgs-dashboard-outbound-route-reveal-phone-number-conditions-prove.jpg)

![VGS Dashboard Outbound Routes Reveal Phone Number Variable Prove](/images/vgs-dashboard-outbound-route-reveal-phone-number-variable-prove.jpg)

20) Scroll down and hit "Add filter" to add the next filter.  
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
26) Under "Fields in JSON path", enter "$.ssn" into field 1.  
27) Scroll down to "Storage" below "Targets".
28) Click on "Storage" field and select "Persistent".
29) Under "Alias Format", click the field and select "SSN - Format Preserving (A4) - xxx-xx-<last four>.  
30) Scroll to the bottom and hit "Save" in the bottom, right-hand side.
31) Check for successful route update message in green. 
32) The following pictures highlights, with red boxes, the areas to select/modify in steps #20 through #31.

![VGS Dashboard Outbound Routes Reveal SSN Conditions Prove](/images/vgs-dashboard-outbound-route-reveal-ssn-conditions-prove.jpg)

![VGS Dashboard Outbound Routes Reveal SSN Variable Prove](/images/vgs-dashboard-outbound-route-reveal-ssn-variable-prove.jpg)

![VGS Dashboard Outbound Routes Save Confirm Prove](/images/vgs-dashboard-outbound-route-save-confirm-prove.jpg)  


### 3rd-party (Card Issuance)
1) On the top, left-hand side, just under the organization name, click on the "Vault" tab.
2) On the left-hand side, under "Vault", click on "Routes".
3) At the top, just under the "Vault ID", select the "HTTP" tab.
4) Under the "HTTP" tab, select the "Outbound" tab.
5) Scroll down to the outbound route with UPSTREAM set to "api.stripe.com".   
6) On the right-hand side, click on "Manage".  
7) The following picture highlights, with red boxes, the areas to select/modify in steps #1 through #6.

![VGS Dashboard Routes](/images/vgs-dashboard-outbound-route-card-issuance-stripe.jpg)

8) Under Upstream Host, review the setting pointing to Stripe's base API endpoint (https://api.stripe.com).  
9) Scroll down to the bottom of the page.  
10) Hit "Add filter" to add the next filter.  
11) Under "Conditions" in the default filter, set the following:  
        * PathInfo matches "/v1/issuing/cardholders". This points to your server-side API endpoint destination.  
12) Phase: "On request". This defines the API phase. In this case, this filter will trigger on API call response.  
13) Scroll down and select the "Basic" tab below "Tag".  
14) Under "Operation", select "REVEAL" to reveal the sensitive data alias.  
15) Under "Content Type, select "Json" to identify the content type of the request.  
16) Under "Fields in JSON path", enter "$.phone_number" into field 1.  
17) Scroll down to "Storage" below "Targets".
18) Click on "Storage" field and select "Persistent".
19) Under "Alias Format", click the field and select "Account Number - Number Length Preserving (A4) - xxxxxxxxxxxx<last four>.  
20) The following pictures highlights, with red boxes, the areas to select/modify in steps #8 through #19.

![VGS Dashboard Outbound Routes Upstream Host Stripe Card Issuance](/images/vgs-dashboard-outbound-route-upstream-host-stripe-card-issuance.jpg)

![VGS Dashboard Outbound Route Card Issuance Add Filter Stripe](/images/vgs-dashboard-outbound-route-card-issuance-add-filter-stripe.jpg)

![VGS Dashboard Outbound Routes Reveal Phone Number Conditions Stripe Card Issuance](/images/vgs-dashboard-outbound-route-reveal-phone-number-conditions-stripe-card-issuance.jpg)

![VGS Dashboard Outbound Routes Reveal Phone Number Variable Stripe Card Issuance](/images/vgs-dashboard-outbound-route-reveal-phone-number-variable-stripe-card-issuance.jpg)

21) Scroll down and hit "Add filter" to add the next filter.  
22) Under "Conditions" in the default filter, set the following:
        * PathInfo matches "/v1/issuing/cards/(.*)". This points to your server-side API endpoint destination.  
23) Phase: "On response". This defines the API phase. In this case, this filter will trigger on API call response.  
24) Scroll down and select the "Basic" tab below "Tag".  
25) Under "Operation", select "REDACT" to secure the sensitive data.  
26) Under "Content Type, select "Json" to identify the content type of the request.  
27) Under "Fields in JSON path", enter "$.number" into field 1.  
28) Scroll down to "Storage" below "Targets".
29) Click on "Storage" field and select "Persistent".
30) Under "Alias Format", click the field and select "Payment Card - Format Preserving, Luhn Valid (6T4)".  .  
31) The following pictures highlights, with red boxes, the areas to select/modify in steps #21 through #30.

![VGS Dashboard Outbound Routes Redact PAN Conditions Stripe Card Issuance](/images/vgs-dashboard-outbound-route-redact-pan-conditions-stripe-card-issuance.jpg)

![VGS Dashboard Outbound Routes Redact PAN Variable Stripe Card Issuance](/images/vgs-dashboard-outbound-route-redact-pan-variable-stripe-card-issuance.jpg)

32) Scroll down and hit "Add filter" to add the next filter.  
33) Under "Conditions" in the default filter, set an OR condition with the following settings:
        * PathInfo matches "/v1/issuing/cards/(.*)". This points to your server-side API endpoint destination.  
34) Phase: "On response". This defines the API phase. In this case, this filter will trigger on initial API call.  
35) Scroll down and select the "Basic" tab below "Tag".  
36) Under "Operation", select "REDACT" to secure the sensitive data.  
37) Under "Content Type, select "Json" to identify the content type of the request.  
38) Under "Fields in JSON path", enter "$.cvc" into field 1.  
39) Scroll down to "Storage" below "Targets".  
40) Click on "Storage" field and select "Volatile".  
41) Under "Alias Format", click the field and select "Generic VGS Alias (Default) - tok_sandbox_xxxxxxxxxxxxxxxxxxxxxx.  
42) Scroll to the bottom and hit "Save" in the bottom, right-hand side.  
43) Check for successful route update message in green.
44) The following pictures highlights, with red boxes, the areas to select/modify in steps #32 through #43.

![VGS Dashboard Outbound Routes Redact CVC Conditions Stripe Card Issuance](/images/vgs-dashboard-outbound-route-redact-cvc-conditions-stripe-card-issuance.jpg)

![VGS Dashboard Outbound Routes Redact CVC Variable Stripe Card Issuance](/images/vgs-dashboard-outbound-route-redact-cvc-variable-stripe-card-issuance.jpg)

![VGS Dashboard Outbound Routes Save Confirm Stripe Card Issuance](/images/vgs-dashboard-outbound-route-redact-save-confirm-stripe-card-issuance.jpg)


Congratulations, you have finished this section.  
