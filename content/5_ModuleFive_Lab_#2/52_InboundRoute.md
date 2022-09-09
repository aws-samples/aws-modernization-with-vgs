---
title: "Inbound Route" # MODIFY THIS TITLE
chapter: true
weight: 2 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

# Inbound Route <!-- MODIFY THIS HEADING -->

## Create an Inbound Route to Secure PII-Sensitive Data <!-- MODIFY THIS SUBHEADING -->  

1) If not already logged in, log into your VGS Dashboard (https://dashboard.verygoodsecurity.com).  
2) On the top, left-hand side, just under the organization name, click on the "Vault" tab.  
3) On the left-hand side, under "Vault", click on "Routes".  
4) At the top, just under the "Vault ID", select the "HTTP" tab.  
5) On the right-hand side, click on "Add Route" and select "Inbound route".  
6) The following picture highlights, with red boxes, the areas to select/modify in steps #2 through #5.  

![VGS Dashboard Routes](/images/vgs-dashboard-routes.jpg)  

7) Modify the Upstream Host to point to the simulated customer network, "https://vgs-simulated-customer-network.ngrok".
8) Scroll down to filters.  
9) Under "Conditions" in the default filter, note the following settings:  
        * PathInfo matches "/kyc". This points to your server-side API endpoint destination.  
        * ContentType equals "application/json". This defines the content type of the request.  
10) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
11) Scroll down and select the "Basic" tab below "Tag".  
12) Under "Operation", select "REDACT" to secure sensitive data.  
13) Under "Content Type, select "Json" to identify the content type of the request.  
14) Under "Fields in JSON path", enter "$.phone_number" into field 1.  
15) Scroll down to "Storage" below "Targets".  
16) Click on "Storage" field and select "Persistent".  
17) Under "Alias Format", click the field and select "Account Number - Number Length Preserving (A4) - xxxxxxxxxxxx<last_four>.  
18) Scroll down and hit "Add filter".  
19) The following pictures highlights, with red boxes, the areas to select/modify in steps #7 through #18.  

![VGS Dashboard Inbound Routes Upstream Host](/images/vgs-dashboard-inbound-route-upstream-host.jpg)  

![VGS Dashboard Inbound Routes Phone Number Conditions](/images/vgs-dashboard-inbound-route-redact-phone-number-conditions.jpg)  

![VGS Dashboard Inbound Routes Redact Phone Number Variable](/images/vgs-dashboard-inbound-route-redact-phone-number-variable.jpg)  

20) Scroll down to filters.  
21) Under "Conditions" in the default filter, note the following settings:  
        * PathInfo matches "/kyc". This points to your server-side API endpoint destination.  
        * ContentType equals "application/json". This defines the content type of the request.  
22) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
23) Scroll down and select the "Basic" tab below "Tag".  
24) Under "Operation", select "REDACT" to secure sensitive data.  
25) Under "Content Type, select "Json" to identify the content type of the request.  
26) Under "Fields in JSON path", enter "$.phone_number" into field 1.  
27) Scroll down to "Storage" below "Targets".  
28) Click on "Storage" field and select "Persistent".  
29) Under "Alias Format", click the field and select "SSN - Format Preserving (A4) - xxx-xx-<last_four>.  
30) Scroll to the bottom and hit "Save" in the bottom, right-hand side.  
31) The following pictures highlights, with red boxes, the areas to select/modify in steps #20 through #30.  

![VGS Dashboard Inbound Routes Redact SSN Conditions](/images/vgs-dashboard-inbound-route-redact-ssn-conditions.jpg)  

![VGS Dashboard Inbound Routes Redact SSN Variable](/images/vgs-dashboard-inbound-route-redact-ssn-variable.jpg)  


Congratulations, you have finished this section.  
