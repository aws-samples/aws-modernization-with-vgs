---
title: "Outbound Routes" # MODIFY THIS TITLE
chapter: true
weight: 7 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

# Outbound Routes <!-- MODIFY THIS HEADING -->

## Create Outbound Routes to Each PSP

### 3rd-party PSP (Checkout.com)  

1) If not already logged in, log into your VGS Dashboard (https://dashboard.verygoodsecurity.com).  
2) On the top, left-hand side, just under the organization name, click on the "Vault" tab.  
3) On the left-hand side, under "Vault", click on "Routes".  
4) At the top, just under the "Vault ID", select the "HTTP" tab.  
5) Just under the "HTTP" tab, click on "All".
6) On the right-hand side, click on "Add Route" and select "Outbound route".  
7) The following picture highlights, with red boxes, the areas to select/modify in steps #2 through #6.  

![VGS Dashboard Routes](/images/vgs-dashboard-outbound-route-checkout.jpg)  

8) Under Upstream Host, review the setting pointing to Checkout.com's base API endpoint (https://api.sandbox.checkout.com).  
9) Scroll down to filters.  
10) Under "Conditions" in the default filter, note the following settings:  
        * PathInfo matches "/tokens". This points to your server-side API endpoint destination.  
        * ContentType equals "application/json". This defines the content type of the request.  
11) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
12) Scroll down and select the "Basic" tab below "Tag".  
13) Under "Operation", select "REVEAL" to reveal the sensitive data alias.  
14) Under "Content Type, select "Json" to identify the content type of the request.  
15) Under "Fields in JSON path", enter "$.number" into field 1.  
16) Scroll down to "Storage" below "Targets".   
17) Click on "Storage" field and select "Persistent".  
18) Under "Alias Format", click the field and select "Payment Card - Format Preserving, Luhn Valid (6T4).  
19) The following pictures highlights, with red boxes, the areas to select/modify in steps #8 through #18.  

![VGS Dashboard Outbound Routes Upstream Host](/images/vgs-dashboard-outbound-route-upstream-host-checkout.jpg)  

![VGS Dashboard Outbound Routes Reveal PAN Conditions](/images/vgs-dashboard-outbound-route-reveal-pan-conditions-checkout.jpg)  

![VGS Dashboard Outbound Routes Reveal PAN Variable](/images/vgs-dashboard-outbound-route-reveal-pan-variable-checkout.jpg)  

20) Scroll down and hit "Add filter" to add the next filter.  
21) Under "Conditions" in the default filter, note the following settings:  
        * PathInfo matches "/tokens". This points to your server-side API endpoint destination.  
        * ContentType equals "application/json". This defines the content type of the request.  
22) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
23) Scroll down and select the "Basic" tab below "Tag".  
24) Under "Operation", select "REVEAL" to reveal the sensitive data alias.  
25) Under "Content Type, select "Json" to identify the content type of the request.  
26) Under "Fields in JSON path", enter "$.cvc" into field 1.  
27) Scroll down to "Storage" below "Targets".  
28) Click on "Storage" field and select "Volatile".  
29) Under "Alias Format", click the field and select "Generic VGS Alias (Default) - tok_sandbox_xxxxxxxxxxxxxxxxxxxxxx".  
30) Scroll to the bottom and hit "Save" in the bottom, right-hand side.  
31) The following pictures highlights, with red boxes, the areas to select/modify in steps #20 through #30.  

![VGS Dashboard Outbound Routes Reveal Card Security Code Conditions](/images/vgs-dashboard-outbound-route-reveal-card-security-code-conditions-checkout.jpg)  

![VGS Dashboard Outbound Routes Reveal Card Security Code Variable](/images/vgs-dashboard-outbound-route-reveal-card-security-code-variable-checkout.jpg)  


### 3rd-party PSP (Stripe)  

1) If not already logged in, log into your VGS Dashboard (https://dashboard.verygoodsecurity.com).  
2) On the top, left-hand side, just under the organization name, click on the "Vault" tab.  
3) On the left-hand side, under "Vault", click on "Routes".  
4) At the top, just under the "Vault ID", select the "HTTP" tab.  
5) Just under the "HTTP" tab, select "Outbound".  
6) On the right-hand side, click on "Add Route".  
7) The following picture highlights, with red boxes, the areas to select/modify in steps #2 through #6.  

![VGS Dashboard Routes](/images/vgs-dashboard-outbound-route-stripe.jpg)  

8) Under Upstream Host, review the setting pointing to Checkout.com's base API endpoint (https://api.stripe.com).  
9) Scroll down to filters.  
10) Under "Conditions" in the default filter, note the following settings:  
        * PathInfo matches "(.*)". This points to your server-side API endpoint destination. In this case, we use a wildcard to identify any Stripe API endpoint.   
11) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
12) Scroll down and select the "Basic" tab below "Tag".  
13) Under "Operation", select "REVEAL" to reveal the sensitive data alias.  
14) Under "Content Type, select "Form" to identify the content type of the request.  
15) Under "Fields in FormData", enter "card[number]" into field 1.  
16) Scroll down to "Storage" below "Targets".  
17) Click on "Storage" field and select "Persistent".  
18) Under "Alias Format", click the field and select "Payment Card - Format Preserving, Luhn Valid (6T4).  
19) The following pictures highlights, with red boxes, the areas to select/modify in steps #8 through #18.  

![VGS Dashboard Outbound Routes Upstream Host](/images/vgs-dashboard-outbound-route-upstream-host-stripe.jpg)

![VGS Dashboard Outbound Routes Reveal PAN Conditions](/images/vgs-dashboard-outbound-route-reveal-pan-conditions-stripe.jpg)

![VGS Dashboard Outbound Routes Reveal PAN Variable](/images/vgs-dashboard-outbound-route-reveal-pan-variable-stripe.jpg)

20) Scroll down and hit "Add filter" to add the next filter.  
21) Under "Conditions" in the default filter, note the following settings:  
        * PathInfo matches "(.*)". This points to your server-side API endpoint destination. In this case, we use a wildcard to identify any Stripe API endpoint.   
22) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
23) Scroll down and select the "Basic" tab below "Tag".  
24) Under "Operation", select "REVEAL" to reveal the sensitive data alias.  
25) Under "Content Type, select "Form" to identify the content type of the request.  
26) Under "Fields in FormData", enter "card[cvc] into field 1.  
27) Scroll down to "Storage" below "Targets".  
28) Click on "Storage" field and select "Volatile".  
29) Under "Alias Format", click the field and select "Generic VGS Alias (Default) - tok_sandbox_xxxxxxxxxxxxxxxxxxxxxx".  
30) Scroll to the bottom and hit "Save" in the bottom, right-hand side.  
31) The following pictures highlights, with red boxes, the areas to select/modify in steps #20 through #30.  

![VGS Dashboard Outbound Routes Reveal Card Security Code Conditions](/images/vgs-dashboard-outbound-route-reveal-card-security-code-conditions-stripe.jpg)  

![VGS Dashboard Outbound Routes Reveal Card Security Code Variable](/images/vgs-dashboard-outbound-route-reveal-card-security-code-variable-stripe.jpg)  


Congratulations, you have finished this section.  
