---
title: "Card Security Code Alias Test" # MODIFY THIS TITLE
chapter: true
weight: 5 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

# Card Security Code Alias Test <!-- MODIFY THIS HEADING -->

## Run a Card Security Code Alias Test  

1) Return to the Card Payment Web Portal. You should see something similar to the following:  

![VGS VGS PAN Alias Test](/images/vgs-pan-alias-test.png)  

2) In the card payment fields, enter the following:  
        * Cardholder Name: <Your Name or Test Name> (e.g. Charlie Business)  
        * Card number: 4111 1111 1111 1111  
        * Expiration Date: 03 / 30  
        * Card Security Code: 737  
        * **Amount: 2**  
3) Hit "Submit" to run the test.  
4) Confirm the PAN alias in the payment request response:  
        {  
         "amount": "2",  
         "card-expiration-date": "03 / 30",  
         **"card-number": "4111118052331111"**,  
         **"card-security-code": "tok_sandbox_bt1okrcfHzkEkcErBaet2m"**,  
         "cardholder-name": "Charlie Business"  
        }  
5) If the above steps were done correctly, you should see a result similar to the following:  

![VGS VGS PAN Alias Test](/images/vgs-card-security-code-alias-test.png)  

Please note that you have now descoped the server-side from the inbound PCI-sensitive data.  

 
Congratulations, you have finished this section.  
