---
title: "Secure Card Security Code" # MODIFY THIS TITLE
chapter: true
weight: 4 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

# Secure Card Security Code <!-- MODIFY THIS HEADING -->

## Use VGS Logs to Secure Card Security Code <!-- MODIFY THIS SUBHEADING -->

1) If not already logged in, log into your VGS Dashboard (https://dashboard.verygoodsecurity.com).  
2) On the top, left-hand side, just under the organization name, click on the "Vault" tab.  
3) On the left-hand side, under "Vault", click on "Logs".  
4) At the top, just under the "Vault ID", select the "HTTP" tab.   
5) In the center of the page, click on the "Load New Requests" button.  
6) Identify a log entry similar to the one pictured below.  

![VGS Payload Logs](/images/vgs-payload-logs.jpg)  

7) Double-click on the log entry. Then, select the "Request" tab followed by the "Body" tab. You should see a log similar to the following:  

![VGS Payload Logs](/images/vgs-single-payload-log-body.jpg)  

8) Notice that the PAN has been aliased. However, the card security code is still in the clear. So, we are still in PCI scope. To fix this issue, click on the "Secure this payload" button on the right-hand side of the log as shown in the following picture:  

![VGS Payload Logs](/images/vgs-single-payload-log-body-secure-this-payload.jpg)  

9) You should see the input variables in the client-side to server-side API call similar to the following picture:  

![VGS Payload Logs](/images/vgs-single-payload-log-secure-cvc.jpg)  

10) To secure the card security code, do the following:  
	* Check the box next to card-security-code (as shown).  
	* In the transformer, enter the following:
		* Operation: Redact  
		* Storage: Volatile  
		* Format: Generic VGS Alias (Default) - tok_sandbox_xxxxxxxxxxxxxxxxxxxxxx  
	* Hit the "Secure this payload" button. 
	* After successful route update message in green, hit the "X" in the top-right of the "Payload Secured" window in order to close it.   

11) The following picture highlights, with red box, provides an example of the "successful route update message in green" that should appear as result from step #10.

![VGS Payload Logs](/images/vgs-single-payload-log-secure-cvc-route-update-msg.jpg)  

 
Congratulations, you have finished this section.  

