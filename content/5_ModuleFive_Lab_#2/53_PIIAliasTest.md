---
title: "PII Alias Test" # MODIFY THIS TITLE
chapter: true
weight: 3 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

# Run a PII Alias Test <!-- MODIFY THIS HEADING -->

## Turn on VGS Payload Logging (Only available in sandbox vaults)

1) If not already logged in, log into your VGS Dashboard (https://dashboard.verygoodsecurity.com).
2) On the top, left-hand side, just under the organization name, click on the "Vault" tab.
3) On the left-hand side, under "Vault", click on "Logs".
4) At the top, just under the "Vault ID", select the "HTTP" tab.
5) Below the HTTP tab, click on the "Recording payloads" button.


## Run a PII Alias Test

1) Launch the PII Web Portal previously created. You should see something similar to the following:

![VGS VGS PII Web Portal](/images/vgs-pii-web-portal.png)

2) In the card payment fields, enter the following:
	* Name: <Your Name or Test Name> (e.g. Barrie Hayman)  
	* Phone Number: 2001041044  
	* SSN: 541-58-2185  
3) Hit "Submit" to run the test.  
4) Confirm the Phone Number & SSN aliases in the PII request response:  
	{  
	 "name": "Barrie Hayman",  
	 "phone-number": "7550301044",  
	 "ssn": "992-24-2185"  
	}  
5) If the above steps were done correctly, you should see a result similar to the following:  

![VGS VGS PII Alias Test](/images/vgs-pii-alias-test.png)

Please note that you just descoped the server-side from the inbound PII-sensitive data.  


Congratulations, you have finished this section.  


