---
title: "End to End Card Payment Test" # MODIFY THIS TITLE
chapter: true
weight: 8 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

# End to End Card Payment Test <!-- MODIFY THIS HEADING -->

## Run End to End Card Payment Test  

1) Return to the Card Payment Web Portal. You should see something similar to the following:

![VGS VGS Card Payment Web Portal](/images/vgs-card-security-code-alias-test.png)  

2) In the card payment fields, enter the following:  
        * Cardholder Name: <Your Name or Test Name> (e.g. Charlie Business)  
        * Card number: 4111 1111 1111 1111  
        * Expiration Date: 03 / 30  
        * Card Security Code: 737  
        * **Amount: 52**  
3) Hit "Submit" to run the test.  
4) Confirm the PAN alias in the payment request response:  
	{    
	 "a_name": "Charlie Business",  
	 **"b_secure_card_number": "4111118052331111",**  
	 **"c_secure_card_cvc": "tok_sandbox_tGo1cfJm9o8UGocoKX4L5c",**  
	 "d_card_exp": "3/30",  
	 **"e_amount": 52,**  
	 "f_currency": "USD",  
	 "g_bin_type": "",  
	 **"h_card_brand": "Visa",**  
	 "i_card_type": "credit",  
	 "j_issuing_country": "",  
	 **"k_psp": "Checkout",**  
	 **"l_psp_payment_token": "",**  
	 **"m_status": "Authorized"** 
	}  	
5) If the above steps were done correctly, you should see a result similar to the following:

![VGS VGS PAN Alias Test](/images/vgs-end-to-end-card-payment-test-checkout.png)

6) In the card payment fields, enter the following:  
        * Cardholder Name: <Your Name or Test Name> (e.g. Charlie Business)  
        * **Card number: 5454 5454 5454 5454**  
        * Expiration Date: 03 / 30  
        * **Card Security Code: 234**  
        * **Amount: 152**  
7) Hit "Submit" to run the test.  
8) Confirm the PAN alias in the payment request response:  
	{  
	 "a_name": "Charlie Business",  
	 **"b_secure_card_number": "5454548983585454",**  
	 **"c_secure_card_cvc": "tok_sandbox_sRkAuqm81eLEyo33TAQhsX",**  
	 "d_card_exp": "3/30",  
	 **"e_amount": 152,**  
	 "f_currency": "USD",  
	 "g_bin_type": "",  
	 **"h_card_brand": "Mastercard",**  
	 "i_card_type": "credit",  
	 "j_issuing_country": "",  
	 **"k_psp": "Stripe",**  
	 **"l_psp_payment_token": "",**  
	 **"m_status": "succeeded"**  
	}  
9) If the above steps were done correctly, you should see a result similar to the following:

![VGS VGS PAN Alias Test](/images/vgs-end-to-end-card-payment-test-stripe.png)  


Please note that because you control and own the end-users' data, you are able to route to whoever you want. In this lab, we setup an end to end card payment flow. We were able to do card brand routing. We routed Visa cards through Checkout.com and Mastercard cards through Stripe. You can do something similar with other variables like card type, currency, and amount.  


Congratulations, you have finished this lab.  
