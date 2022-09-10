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
5) On the right-hand side, click on "Add Route" and select "Outbound route".  
6) The following picture highlights, with red boxes, the areas to select/modify in steps #2 through #5.  

![VGS Dashboard Routes](/images/vgs-dashboard-routes.jpg)  

7) Under Upstream Host, review the setting pointing to Checkout.com's base API endpoint (https://api.sandbox.checkout.com).  
8) Scroll down to filters.  
9) Under "Conditions" in the default filter, note the following settings:  
        * PathInfo matches "/tokens". This points to your server-side API endpoint destination.  
        * ContentType equals "application/json". This defines the content type of the request.  
10) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
11) Scroll down and select the "Basic" tab below "Tag".  
12) Under "Operation", select "REVEAL" to reveal the sensitive data alias.  
13) Under "Content Type, select "Json" to identify the content type of the request.  
14) Under "Fields in JSON path", enter "$.number" into field 1.  
15) Scroll down to "Storage" below "Targets".   
16) Click on "Storage" field and select "Persistent".  
17) Under "Alias Format", click the field and select "Payment Card - Format Preserving, Luhn Valid (6T4).  
18) The following pictures highlights, with red boxes, the areas to select/modify in steps #7 through #18.  

![VGS Dashboard Outbound Routes Upstream Host](/images/vgs-dashboard-outbound-route-upstream-host-checkout.jpg)  

![VGS Dashboard Outbound Routes Reveal PAN Conditions](/images/vgs-dashboard-outbound-route-reveal-pan-conditions-checkout.jpg)  

![VGS Dashboard Outbound Routes Reveal PAN Variable](/images/vgs-dashboard-outbound-route-reveal-pan-variable-checkout.jpg)  

19) Scroll down and hit "Add filter" to add the next filter.  
20) Under "Conditions" in the default filter, note the following settings:  
        * PathInfo matches "/tokens". This points to your server-side API endpoint destination.  
        * ContentType equals "application/json". This defines the content type of the request.  
21) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
22) Scroll down and select the "Basic" tab below "Tag".  
23) Under "Operation", select "REVEAL" to reveal the sensitive data alias.  
24) Under "Content Type, select "Json" to identify the content type of the request.  
25) Under "Fields in JSON path", enter "$.cvc" into field 1.  
26) Scroll down to "Storage" below "Targets".  
27) Click on "Storage" field and select "Volatile".  
28) Under "Alias Format", click the field and select "Generic VGS Alias (Default) - tok_sandbox_xxxxxxxxxxxxxxxxxxxxxx".  
29) Scroll to the bottom and hit "Save" in the bottom, right-hand side.  
30) The following pictures highlights, with red boxes, the areas to select/modify in steps #19 through #29.  

![VGS Dashboard Outbound Routes Reveal Card Security Code Conditions](/images/vgs-dashboard-outbound-route-reveal-card-security-code-conditions-checkout.jpg)  

![VGS Dashboard Outbound Routes Reveal Card Security Code Variable](/images/vgs-dashboard-outbound-route-reveal-card-security-code-variable-checkout.jpg)  


### 3rd-party PSP (Stripe)  

1) If not already logged in, log into your VGS Dashboard (https://dashboard.verygoodsecurity.com).  
2) On the top, left-hand side, just under the organization name, click on the "Vault" tab.  
3) On the left-hand side, under "Vault", click on "Routes".  
4) At the top, just under the "Vault ID", select the "HTTP" tab.  
5) On the right-hand side, click on "Add Route" and select "Outbound route".  
6) The following picture highlights, with red boxes, the areas to select/modify in steps #2 through #5.  

![VGS Dashboard Routes](/images/vgs-dashboard-routes.jpg)  

7) Under Upstream Host, review the setting pointing to Checkout.com's base API endpoint (https://api.stripe.com).  
8) Scroll down to filters.  
9) Under "Conditions" in the default filter, note the following settings:  
        * PathInfo matches "/tokens". This points to your server-side API endpoint destination.  
        * ContentType equals "application/json". This defines the content type of the request.  
10) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
11) Scroll down and select the "Basic" tab below "Tag".  
12) Under "Operation", select "REVEAL" to reveal the sensitive data alias.  
13) Under "Content Type, select "Json" to identify the content type of the request.  
14) Under "Fields in JSON path", enter "$.number" into field 1.  
15) Scroll down to "Storage" below "Targets".  
16) Click on "Storage" field and select "Persistent".  
17) Under "Alias Format", click the field and select "Payment Card - Format Preserving, Luhn Valid (6T4).  
18) The following pictures highlights, with red boxes, the areas to select/modify in steps #7 through #17.  

![VGS Dashboard Outbound Routes Upstream Host](/images/vgs-dashboard-outbound-route-upstream-host-stripe.jpg)

![VGS Dashboard Outbound Routes Reveal PAN Conditions](/images/vgs-dashboard-outbound-route-reveal-pan-conditions-stripe.jpg)

![VGS Dashboard Outbound Routes Reveal PAN Variable](/images/vgs-dashboard-outbound-route-reveal-pan-variable-stripe.jpg)

19) Scroll down and hit "Add filter" to add the next filter.  
20) Under "Conditions" in the default filter, note the following settings:  
        * PathInfo matches "/tokens". This points to your server-side API endpoint destination.  
        * ContentType equals "application/json". This defines the content type of the request.  
21) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
22) Scroll down and select the "Basic" tab below "Tag".  
23) Under "Operation", select "REVEAL" to reveal the sensitive data alias.  
24) Under "Content Type, select "Json" to identify the content type of the request.  
25) Under "Fields in JSON path", enter "$.cvc" into field 1.  
26) Scroll down to "Storage" below "Targets".  
27) Click on "Storage" field and select "Volatile".  
28) Under "Alias Format", click the field and select "Generic VGS Alias (Default) - tok_sandbox_xxxxxxxxxxxxxxxxxxxxxx".  
29) Scroll to the bottom and hit "Save" in the bottom, right-hand side.  
30) The following pictures highlights, with red boxes, the areas to select/modify in steps #19 through #29.  

![VGS Dashboard Outbound Routes Reveal Card Security Code Conditions](/images/vgs-dashboard-outbound-route-reveal-card-security-code-conditions-stripe.jpg)  

![VGS Dashboard Outbound Routes Reveal Card Security Code Variable](/images/vgs-dashboard-outbound-route-reveal-card-security-code-variable-stripe.jpg)  


Congratulations, you have finished this section.  
