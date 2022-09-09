---
title: "PAN Alias Test" # MODIFY THIS TITLE
chapter: true
weight: 3 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

# PAN Alias Test <!-- MODIFY THIS HEADING -->

## Turn on VGS Payload Logging (Only available in sandbox vaults)  

1) If not already logged in, log into your VGS Dashboard (https://dashboard.verygoodsecurity.com).  
2) On the top, left-hand side, just under the organization name, click on the "Vault" tab.  
3) On the left-hand side, under "Vault", click on "Logs".  
4) At the top, just under the "Vault ID", select the "HTTP" tab.  
5) Below the HTTP tab, click on the "Recording payloads" button.  


## Run a PAN Alias Test  

1) Launch the Card Payment Web Portal previously created. You should see something similar to the following:

![VGS VGS Card Payment Web Portal](/images/vgs-card-payment-web-portal.png)  
 
2) In the card payment fields, enter the following:  
	* Cardholder Name: <Your Name or Test Name> (e.g. Charlie Business)  
	* Card number: 4111 1111 1111 1111  
	* Expiration Date: 03 / 30  
	* Card Security Code: 737  
	* Amount: 1  
3) Hit "Submit" to run the test.  
4) Confirm the PAN alias in the payment request response:  
	{  
	 "amount": "1",  
	 "card-expiration-date": "03 / 30",  
	 **"card-number": "4111118052331111"**,  
	 "card-security-code": "737",  
	 "cardholder-name": "Charlie Business"  
	}  
5) If the above steps were done correctly, you should see a result similar to the following:  

![VGS VGS PAN Alias Test](/images/vgs-pan-alias-test.png)  
 
6) Notice that we haven't completely descoped the server-side from the PCI-sensitive data as the Card Security Code is still in the clear. This is because we only defined one filter to redact the PAN in the Inbound Route. We will correct this issue in the next section.  

Congratulations, you have finished this section.  
