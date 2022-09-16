---
title: "PII Web Portal" # MODIFY THIS TITLE
chapter: true
weight: 1 # MODIFY THIS VALUE TO REFLECT THE ORDERING OF THE MODULES
---

# PII Web Portal <!-- MODIFY THIS HEADING -->

## Create a PII Web Portal <!-- MODIFY THIS SUBHEADING -->

### Know Your Customer (KYC)/Anti-Money Laundering (AML)/ID Verification Variables to Define  

* KYC/AML/ID Verification Details  
	* Name  
		* Variable: name  
		* Label: Cardholder Name  
		* Description: The name of the cardholder.  
	* Phone Number  
		* Variable: phone_number  
		* Label: Phone Number  
		* Description: The end-user's phone number.  
	* Social Security Number  
		* Variable: ssn  
		* Label: Social Security Number  
		* Description: The end-user's Social Security Number.  


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
5) The following pictures highlights, with red boxes, the areas to select/modify in steps #2 through #4.

![VGS Dashboard Collect Web](/images/vgs-dashboard-collect-web.jpg)

6) Scroll to the bottom of the page.
7) Under "Next Steps", select "Start with Collect.js Form Builder.
8) Finally, click on "Open Form Builder".
9) The following pictures highlights, with red boxes, the areas to select/modify in steps #6 through #8.

![VGS Dashboard Collect Web Form Builder](/images/vgs-dashboard-collect-web-form-builder.jpg)


### Build the KYC/AML/ID Verification Web Form

1) From the left-hand pane of the VGS Collect.js Form Builder, select "Choose from template".
2) Hit "Apply" next to the "SSN Form" template.
3) Click on VGS Collect.js Form Builder to exit the form template selection.
4) The following pictures highlights, with red boxes, the areas to select/modify in steps #1 through #3.  

![VGS Collect Form Builder Choose From Template](/images/vgs-collect-form-builder-choose-from-template.jpg)  

![VGS Collect Form Builder SSN Form Template](/images/vgs-collect-form-builder-ssn-form-template.jpg)  

4) From the left-hand pane of the VGS Collect.js Form Builder, select "Add new field".
5) Under Field Options on the left-hand side, check the "Field label" box and enter, "Name" in the box provided.
6) enter "name" in the "Enter field name" field.
7) Under Field Options on the right-hand side, hit the "Create" button.
8) The following pictures highlights, with red boxes, the areas to select/modify in steps #4 through #7.  

![VGS Collect Form Builder SSN Form Add Field](/images/vgs-collect-form-builder-ssn-form-add-field.jpg)

![VGS Collect Form Builder SSN Form Add Name](/images/vgs-collect-form-builder-ssn-form-add-name.jpg)

9) From the left-hand pane of the VGS Collect.js Form Builder, select "Add new field".
10) Under Field Options on the left-hand side, check the "Field label" box and enter, "Phone Number" in the box provided.
11) Under Field Options on the right-hand side, enter "phone_number" in the "Enter field name" field.
12) Under Field Options on the right-hand side, hit the "Create" button.
13) The following pictures highlights, with red boxes, the areas to select/modify in steps #9 through #12.  

![VGS Collect Form Builder SSN Form Add Field 2](/images/vgs-collect-form-builder-ssn-form-add-field-2.jpg)

![VGS Collect Form Builder SSN Form Add Phone Number](/images/vgs-collect-form-builder-ssn-form-add-phone-number.jpg)

14) From the right-hand pane of the VGS Collect.js, select "Form Preview".
15) You should now see 3 fields to capture the PII needed for the KYC/AML/ID Verification.  .
16) If desired, you can re-order the form boxes by clicking on the field box in the left-hand panel and dragging it to the desired order position.  
17) From the right-hand pane of the VGS Collect.js Form Builder, select "Get Code".  
18) You will see the following file types:  
        * JS (form.js) = The Javascript code contain the VGS Collect form creation and iFrames defined.  
        * HTML (index.html) - The HTML used to present the form.  
        * CSS (styles.css) - Contains CSS to style the form.  
19) From the right-hand pane of the VGS Collect.js Form Builder, click on the "JS" tab.
20) Scroll to the bottom.  
21) Hit "Download Code" to download the 3 files.  
22) The following pictures highlights, with red boxes, the areas to select/modify in steps #14 through #21.  

![VGS Collect Form Builder SSN Form Download Code](/images/vgs-collect-form-builder-ssn-form-download-code.jpg)

23) Go to the "Download" folder on your local machine and locate the newly downloaded directory starting with "collect-form" and open it.  

24) The following pictures highlights, with red boxes, the areas to select/modify in step #23.  

![VGS Collect Download Folder Collect Form](/images/vgs-collect-download-folder-collect-form.jpg)

25) Edit the "form.js" file.  
26) Replace the '\<Vault ID\>' with your VGS Data Vault ID recorded earlier.  
27) The following pictures highlights, with red boxes, the areas to select/modify in steps #25 and #26.  

![VGS Collect SSN Form.js Edit](/images/vgs-collect-ssn-form-js-edit.jpg)

![VGS Collect SSN Form.js Edit Complete](/images/vgs-collect-ssn-form-js-edit-complete.jpg)

28) Go to the bottom of the "form.js" file and locate the code block below. Note that this is the form submit and denotes the destination API endpoint (/post).  

        document.addEventListener('submit', (e) => {  
          e.preventDefault();  
          **form.submit('/post', { method: 'POST'}, (status, data) => {**  
            document.getElementById('response').innerText = JSON.stringify(data.json, null, ' ');  
          });  
        });  

29) The following pictures highlights, with red boxes, the areas to select/modify in step #28.  

![VGS Collect Payment Form.js Edit Submit](/images/vgs-collect-payment-form-js-edit-submit.jpg)

30) Save the file.  
31) Double-click on the "index.html" file to launch the KYC/AML/ID Verification Web Portal.  
32) The following pictures highlights, with red boxes, the areas to select/modify in step #31.

![VGS PII Web Portal](/images/vgs-pii-web-portal.png)

Please note that you just created a web portal (client-side application) that is descoped from PII-sensitive data.   

Also note that we only leveraged step #1 of the VGS Collect.js Form Builder to create a form. As part of this lab, we are walking through some steps manually. Steps #2 - #4 enable you to style the form (step #2; if planning on leverage in real environment), define the server-side API endpoint to hit (step #3), and automatic creation of the VGS Data Vault and Inbound Route (step #4;). We will manually create an Inbound Route in the next section.  


Congratulations, you have finished this section.  
