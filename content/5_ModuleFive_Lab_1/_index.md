---
title: "Self-paced Lab #1"
chapter: true
weight: 5
---

# Lab #1  
## End to End Payments to 2 PSP(s) with VGS Data Vault  

In this lab, we will learn how to integrate and configure VGS into a payments ecosystem in order to secure PCI-sensitive data and descope the network from the PCI-sensitive data while maintaining the ability to operate on the PCI-sensitive data.  

When dealing with card-not-present, online transaction, and PCI, PCI rules require that the Primary Account Number (PAN) and card security code (CVC/CVV) be secured. VGS not only secures the PCI-sensitive data but also descopes networks completely from the PCI-sensitive data. By decoping from PCI-sensitive data, VGS helps companies simplify and accelerate their journey to PCI compliance.  

This lab will walk partcipants through the following steps:  

1) Building a web portal/client-side application with VGS Collect iFrames to capture the PCI-sensitive data and descope the client-side application from the PCI-sensitive data.  
2) Configuration of an inbound route (VGS Reverse Proxy) to secure the PCI-sensitive data and descope the server-side appllications from the PCI-sensitive data.  
3) Test to confirm that the PAN was secured.  
4) Configuration to secure the card security code.   
5) Test to confirm that the CVC/CVV was secured.  
6) Modification of the data flow to include a simulated customer network/server-side.  
7) Configuration of outbound routes (VGS Forward Proxy) to reveal the PCI-sensitive data to 3rd-party payemnt services providers to execute payment transasctions. Along with the VGS Reverse Proxy, the VGS Forward Proxy descopes the server-side applications from the PCI-sensitive data.    
8) Complete end to end test of payment requests to two payment service providers.  

Let's get started...  


{{% notice warning %}}
The examples and sample code provided in this workshop are intended to be consumed as instructional content. These will help you understand how various AWS services can be architected to build a solution while demonstrating best practices along the way. These examples are not intended for use in production environments.
{{% /notice %}}
