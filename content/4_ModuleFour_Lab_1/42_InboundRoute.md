---
title: "Inbound Route" # MODIFY THIS TITLE
chapter: true
weight: 2 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

# Inbound Route <!-- MODIFY THIS HEADING -->

## Create an Inbound Route to Secure PCI-Sensitive Data 

1) If not already logged in, log into your VGS Dashboard (https://dashboard.verygoodsecurity.com).
2) On the top, left-hand side, just under the organization name, click on the "Vault" tab.
3) On the left-hand side, under "Vault", click on "Routes".  
4) At the top, just under the "Vault ID", select the "HTTP" tab.  
5) On the right-hand side, click on "Add Route" and select "Inbound route". 
6) The following picture highlights, with red boxes, the areas to select/modify in steps #2 through #5.

![VGS Dashboard Routes](/images/vgs-dashboard-routes.jpg)  

7) Under Upstream Host, review the setting pointing to the VGS Sandbox Echo Server (https://echo.apps.verygood.systems). The upstream host identifies where to forward the API call after the sensitive data is secured/aliased. In this step, we are setting the upstream host to a cloud echo server that will return whatever it receives to the client-side application.  
8) Scroll down to filters.  
9) Under "Conditions" in the default filter, note the following settings:  
	* PathInfo matches "/post". This points to your server-side API endpoint destination.  
	* ContentType equals "application/json". This defines the content type of the request.
10) Phase: "On request". This defines the API phase. In this case, this filter will trigger on initial API call.  
11) Scroll down and select the "Basic" tab below "Tag".  
12) Under "Operation", select "REDACT" to secure sensitive data.
13) Under "Content Type, select "Json" to identify the content type of the request.  
14) Under "Fields in JSON path", enter "$.card-number" into field 1.  
15) Scroll down to "Storage" below "Targets".  
16) Click on "Storage" field and select "Persistent". Persistent storage means that the sensitive data will be stored permanently unless a delete request is received to remove it. PCI rules allow VGS to store the PAN for its customers. Our customers then oeprate on the PAN alias. 
17) Under "Alias Format", click the field and select "Payment Card - Format Preserving, Luhn Valid (6T4).  
18) Scroll to the bottom and hit "Save" in the bottom, right-hand side.
19) The following pictures highlights, with red boxes, the areas to select/modify in steps #7 through #18.  

![VGS Dashboard Inbound Routes Upstream Host](/images/vgs-dashboard-inbound-route-upstream-host.jpg)  

![VGS Dashboard Inbound Routes Conditions](/images/vgs-dashboard-inbound-route-conditions.jpg)  

![VGS Dashboard Inbound Routes Redact Variable](/images/vgs-dashboard-inbound-route-redact-variable.jpg)  


Congratulations, you have finished this section.  
