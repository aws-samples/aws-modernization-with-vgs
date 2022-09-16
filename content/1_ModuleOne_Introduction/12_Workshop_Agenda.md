---
title: "Workshop Agenda" # MODIFY THIS TITLE IF APPLICABLE
chapter: true
weight: 2 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES IF APPLICABLE
---

# Workshop Agenda <!-- MODIFY THIS HEADING IF APPLICABLE -->
* Review of prerequisites *(5 minutes)*  
* Brief overview of the VGS Dashboard *(5 minutes)*  
* Lab 1: End to End Payments with VGS Data Security *(60 minutes)*  
	* Demonstrate creating a web form with VGS Collect iFrames to secure and descope PCI-sensitive data 
	* Attendees create their own web form with VGS Collect iFrames to secure and descope PCI-sensitive data
	* Demonstrate creation of an inbound route (VGS Reverse (HTTP) Proxy)  
	* Attendees create their own inbound route (VGS Reverse (HTTP) Proxy) to descope the server-side from the PCI-sensitive data  
	* Demonstrate upstream host change in inbound route to point to a simulated server-side environment and configuration of 2 outbound routes (VGS Forward (HTTP) Proxy) to reveal PCI-sensitive data to the following payment service providers:  
		* Checkout.com for Payment Processing
		* Stripe for Payment Processing
	* Attendees modify their upstream host in the inbound route to point to a simulated server-side environment and configuration of 2 outbound routes (VGS Forward (HTTP) Proxy) to reveal PCI-sensitive data to the following payment service providers  
* Lab 2: KYC and Card Issuing with VGS Data Vault *(40 minutes)*
	* Demonstrate creating a web form with VGS Collect iFrames to secure and descope PII-sensitive data  
 	* Attendees create their own web form with VGS Collect iFrames to secure and descope PII-sensitive data  
 	* Demonstrate creation of an inbound route to descope the server-side from PII-sensitive data  
	* Attendees create their own inbound route to descope the server-side from PII-sensitive data  
	* Demonstrate configuration of 1 outbound route to reveal PII-sensitive data to Prove (KYC/AML/ID Verification) and 1 outbound route to reveal PII-sensitive data to Stripe and redact PCI-sensitive data returning from Stripe (Card Issuance).  
	* Attendees configure 1 outbound route to reveal PII-sensitive data to Prove (KYC/AML/ID Verification) and 1 outbound route to reveal PII-sensitive data to Stripe and redact PCI-sensitive data returning from Stripe (Card Issuance).  
* Questions, Answers, Extra Time, and Wrap-up *(10 minutes)*   


{{% notice info %}}
<p style='text-align: left;'>
</p>
{{% /notice %}}

