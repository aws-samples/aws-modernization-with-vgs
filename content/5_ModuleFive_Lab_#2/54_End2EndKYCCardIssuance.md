---
title: "End to End KYC & Card Issuance Test" # MODIFY THIS TITLE
chapter: true
weight: 5 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

# End to End KYC & Card Issuance Test <!-- MODIFY THIS HEADING -->

## Run End to End KYC & Card Issuance Test  

1) Launch the PII Web Portal previously created. You should see something similar to the following:  

![VGS VGS PII Web Portal](/images/vgs-pii-web-portal.png)  

2) In the card payment fields, enter the following:  
        * Name: <Your Name or Test Name> (e.g. Barrie Hayman)  
        * Phone Number: 2001041044  
        * SSN: 541-58-2185  
3) Hit "Submit" to run the test.  
4) Confirm the results:  
	{  
	 "a_name": "Charlie Business",  
	 **"b_phone_number": "7550301044",**  
	 **"c_ssn": "992-24-2185",**  
	 **"d_id_verified": "True",**  
	 **"e_trust_score": "1000",**  
	 **"f_secure_card_number": "5454548983585454",**  
	 **"g_secure_card_cvc": "tok_sandbox_kj13GDN4bEgKPaR6qa6fZR",**  
	 "h_card_exp": "3/30",  
	}  
5) If the above steps were done correctly, you should see a result similar to the following:  

![VGS End to End KYC/AML/ID Verification & Card Issuance Test](/images/vgs-end-to-end-kyc-aml-id-verification-&-card-issuance-test.png)  


Congratulations, you have finished this lab.  
