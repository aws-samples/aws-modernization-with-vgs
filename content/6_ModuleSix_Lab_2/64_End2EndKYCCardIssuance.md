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
	 "a_name": "Barrie Hayman",  
	 "b_secured_phone_number": "2273061044",  
	 "c_secured_ssn": "940-14-2185",  
	 "d_id_verified": "Success.",  
	 "e_trust_score": 1000,  
	 "f_trust_score_thresdhold": 930,  
	 "g_secured_card_number": "4000008928664247",  
	 "h_secured_cvc": "tok_sandbox_evKaKkfdF1ePkxgDPqDf8t",  
	 "i_exp_date": "08/2025"  
	}  

5) If the above steps were done correctly, you should see a result similar to the following:  

![VGS End to End KYC/AML/ID Verification & Card Issuance Test](/images/vgs-end-to-end-kyc-aml-id-verification-&-card-issuance-test.png)  


Congratulations, you have finished this lab.  
