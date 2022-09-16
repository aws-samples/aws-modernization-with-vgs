---
title: "Self-paced Lab #2"
chapter: true
weight: 5
---

# Self-paced Lab #2
<br>

## Know Your Customer (KYC)/Anti-Money Laundering (AML)/ID Verification & Card Issuance  

In this lab, we will learn how to integrate and configure VGS into a network and payments ecosystem in order to secure PII-sensitive and PCI-sensitive data and descope the network from the PII-sensitive and PCI-sensitive data while maintaining the ability to operate on the sensitive data.  

For KYC/AML/ID Verification, the collection of PII from the end-user is necessary. VGS helps customers collect the PII-senstive data, secure the PII-sensitive data, and keep the PII-senstive data off of their networks.  

When dealing with card-not-present, card issuing, and PCI, PCI rules require that the Primary Account Number (PAN) and card security code (CVC/CVV) be secured. VGS not only secures the PCI-sensitive data but also descopes networks completely from the PCI-sensitive data. By decoping from PCI-sensitive data, VGS helps companies simplify and accelerate their journey to PCI compliance.  

This lab will walk partcipants through the following steps:

1) Building a web portal/client-side application with VGS Collect iFrames to capture the PII-sensitive data and descope the client-side application from the PII-sensitive data.
2) Configuration of an inbound route (VGS Reverse Proxy) to secure the PII-sensitive data and descope the server-side appllications from the PII-sensitive data.
3) Configuration of outbound routes (VGS Forward Proxy). The first outbound route is to reveal the PII-sensitive data to a 3rd-party KYC/AML/ID Verification vendor to verify the end-user's identity and receive a Trust Score for the end-user. The second outbound route is to reveal PII-sensitive data to the card issuer and redact PCI-sensitive data coming back from the card issuer. Along with the VGS Reverse Proxy, the VGS Forward Proxy descopes the server-side applications from the PCI-sensitive data.
4) Complete an end to end test of KYC/AML/ID Verification and Card Issuance data flow.

* While not part of this lab, VGS also has VGS Show/VGS Mobile Show to securely present sensitive data (e.g. PCI-senstiive data) to end-users while descoping the client-side application from the sensitive data. 

Let's get started...  
