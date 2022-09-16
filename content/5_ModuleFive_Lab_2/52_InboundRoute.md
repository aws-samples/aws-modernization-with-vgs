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
5) Under the "HTTP" tab, select the "All" tab.
6) On the right-hand side, click on "Add Route" and select "Inbound route".  
7) The following picture highlights, with red boxes, the areas to select/modify in steps #2 through #6.  

![VGS Dashboard Routes](/images/vgs-dashboard-routes.jpg)  

8) Modify the Upstream Host to point to the simulated customer network, "https://vgs-simulated-customer-network.ngrok.io".
9) Scroll down to filters.  
10) Under "Conditions" in the default filter, note the following settings:  
        * PathInfo matches "/post". This points to your server-side API endpoint destination.  
        * ContentType equals "application/json". This defines the content type of the request.  
11) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
12) Scroll down and select the "Basic" tab below "Tag".  
13) Under "Operation", select "REDACT" to secure sensitive data.  
14) Under "Content Type, select "Json" to identify the content type of the request.  
15) Under "Fields in JSON path", enter "$.phone_number" into field 1.  
16) Scroll down to "Storage" below "Targets".  
17) Click on "Storage" field and select "Persistent".  
18) Under "Alias Format", click the field and select "Account Number - Number Length Preserving (A4) - xxxxxxxxxxxx<last_four>.  
19) Scroll down and hit "Add filter".  
20) The following pictures highlights, with red boxes, the areas to select/modify in steps #8 through #19.  

![VGS Dashboard Inbound Routes Upstream Host](/images/vgs-dashboard-inbound-route-upstream-host-modify.jpg)  

![VGS Dashboard Inbound Routes Phone Number Conditions](/images/vgs-dashboard-inbound-route-redact-phone-number-conditions.jpg)  

![VGS Dashboard Inbound Routes Redact Phone Number Variable](/images/vgs-dashboard-inbound-route-redact-phone-number-variable.jpg)  

21) Scroll down to filters.  
22) Under "Conditions" in the default filter, note the following settings:  
        * PathInfo matches "/post". This points to your server-side API endpoint destination.  
        * ContentType equals "application/json". This defines the content type of the request.  
23) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
24) Scroll down and select the "Basic" tab below "Tag".  
25) Under "Operation", select "REDACT" to secure sensitive data.  
26) Under "Content Type, select "Json" to identify the content type of the request.  
27) Under "Fields in JSON path", enter "$.phone_number" into field 1.  
28) Scroll down to "Storage" below "Targets".  
29) Click on "Storage" field and select "Persistent".  
30) Under "Alias Format", click the field and select "SSN - Format Preserving (A4) - xxx-xx-<last_four>.  
31) Scroll to the bottom and hit "Save" in the bottom, right-hand side.  
32) The following pictures highlights, with red boxes, the areas to select/modify in steps #21 through #31.  

![VGS Dashboard Inbound Routes Redact SSN Conditions](/images/vgs-dashboard-inbound-route-redact-ssn-conditions.jpg)  

![VGS Dashboard Inbound Routes Redact SSN Variable](/images/vgs-dashboard-inbound-route-redact-ssn-variable.jpg)  


Congratulations, you have finished this section.  
