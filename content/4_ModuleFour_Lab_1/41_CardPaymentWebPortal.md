---
title: "Card Payment Web Portal" # MODIFY THIS TITLE
chapter: true
weight: 1 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

# Card Payment Web Portal <!-- MODIFY THIS HEADING -->

## Create a Card Payment Web Portal <!-- MODIFY THIS SUBHEADING -->

### Card Payment Variables to Define

* Card Details  
	* Cardholder Name  
		* Variable: cardholder-name  
		* Label: Cardholder Name  
		* Description: The name of the cardholder.  
	* Card Number  
		* Variable: card-number  
		* Label: Card number  
		* Description: The Primary Account Number (PAN).  
	* Card Expiration Date  
		* Variable: card-expiration-date  
		* Label: Expiration Date  
		* Description: The card expiration date.  
	* Card Security Code  
		* Variable: card-security-code  
		* Label: Card Security Code  
		* Description: The card security code.  
	* Amount  
		* Variable: amount  
		* Label: Amount  
		* Description: The amount of the payment  


### Record the VGS Data Vault ID  
1) Log into your VGS Dashboard (https://dashboard.verygoodsecurity.com).  
2) On the top, left-hand side, just under the organization name, click on the "Vault" tab.  
3) On the top, left-hand side, just below the "Vault" tab, record/copy your VGS "Vault ID".  
4) The following picture highlights, with red boxes, the areas to select/modify in steps #2 and #3.  

![VGS Dashboard Routes](/images/vgs-dashboard-copy-vault-id.jpg)  

### Access the VGS Collect.js Form Builder  

1) If not already logged in, log into your VGS Dashboard (https://dashboard.verygoodsecurity.com). 

2) Go to the Developer dropdown (top, right-hand side of VGS Dashboard).  
3) Select "VGS Collect".  
4) Click on the "Web" tab below "VGS Collect" title at the top.  
5) The following picture highlights, with red boxes, the areas to select/modify in steps #2 through #4.  

![VGS Dashboard Collect Web](/images/vgs-dashboard-collect-web.jpg)  

5) Scroll to the bottom of the page.  
6) Under "Next Steps", select "Start with Collect.js Form Builder.  
7) Finally, click on "Open Form Builder".  
8) The following picture highlights, with red boxes, the areas to select/modify in steps #5 through #7.  

![VGS Dashboard Collect Web Form Builder](/images/vgs-dashboard-collect-web-form-builder.jpg)  

### Build the Card Payment Web Form  

1) From the left-hand pane of the VGS Collect.js Form Builder, select "Choose from template".  
2) Hit "Apply" next to the "Payment Form" template.   
3) Click on VGS Collect.js Form Builder to exit the form template selection.  
4) The following picture highlights, with red boxes, the areas to select/modify in steps #1 through #3.  

![VGS Collect Form Builder Payment Form Template](/images/vgs-collect-form-builder-payment-form-template.jpg)    

5) From the left-hand pane of the VGS Collect.js Form Builder, select "Add new field".  
6) Under Field Options on the left-hand side, check the "Field label" box and enter, "Amount" in the box provided.  
7) Under Field Options on the right-hand side, enter "amount" in the "Enter field name" field.  
8) Under Field Options on the right-hand side, hit the "Create" button.  
9) The following picture highlights, with red boxes, the areas to select/modify in steps #5 through #8.  

![VGS Collect Form Builder Payment Form Add Field](/images/vgs-collect-form-builder-payment-form-add-field.jpg)  

![VGS Collect Form Builder Payment Form Add Amount](/images/vgs-collect-form-builder-payment-form-add-amount.jpg)  

10) From the right-hand pane of the VGS Collect.js, select "Form Preview".  
11) You should now see 5 fields to capture the card payment.  
12) From the right-hand pane of the VGS Collect.js Form Builder, select "Get Code".  
13) You will see the following file types:  
	* JS (form.js) = The Javascript code contain the VGS Collect form creation and iFrames defined.
	* HTML (index.html) - The HTML used to present the form.  
	* CSS (styles.css) - Contains CSS to style the form.  
14) From the right-hand pane of the VGS Collect.js Form Builder, click on the "JS" tab.
15) Scroll to the bottom.  
16) Hit "Download Code" to download the 3 files.  
17) The following picture highlights, with red boxes, the areas to select/modify in steps #12 and #16.  

![VGS Collect Form Builder Payment Form Download Code](/images/vgs-collect-form-builder-payment-form-download-code.jpg)  

18) Go to the "Download" folder on your local machine and locate the newly downloaded directory starting with "collect-form" and open it.  
19) Edit the "form.js" file.  
20) The following pictures highlights, with red boxes, the areas to select/modify in steps #18 and #19.

![VGS Collect Download Folder Collect Form](/images/vgs-collect-download-folder-collect-form.jpg)  

21) Replace the '\<Vault ID\>' with your VGS Data Vault ID recorded earlier.  
22) The following pictures highlights, with red boxes, the areas to select/modify in step #21.

![VGS Collect Payment Form.js Edit](/images/vgs-collect-payment-form-js-edit.jpg)  

23) Go to the bottom of the "form.js" file. The following code block and highlighted area is the form submit and denotes the destination API endpoint:  

![VGS Collect Payment Form.js Edit Submit](/images/vgs-collect-payment-form-js-edit-submit.jpg)  

24) Save the file.  
25) Double-click on the "index.html" file to launch the Card Payment Web Portal.  
26) The following picture provides an illustration of the Card Payment Web Portal launched in step #26.  

![VGS Card Payment Web Portal](/images/vgs-card-payment-web-portal.png)  

 
Please note that you just created a web portal (client-side application) that is descoped from the PCI-sensitive data.
  
Also note that we only leveraged step #1 of the VGS Collect.js Form Builder to create a form. As part of this lab, we are walking through some steps manually. Steps #2 - #4 enable you to style the form (step #2; if planning on leverage in real environment), define the server-side API endpoint to hit (step #3), and automatic creation of the VGS Data Vault and Inbound Route (step #4;). We will manually create an Inbound Route in the next section.  
  
  
Congratulations, you have finished this section.  
