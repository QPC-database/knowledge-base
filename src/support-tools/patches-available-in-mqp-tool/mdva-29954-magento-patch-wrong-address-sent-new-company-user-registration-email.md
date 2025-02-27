---
title: "MDVA-29954 Magento patch: wrong address sent new company user registration email"
labels: 2.3.0,2.3.1,2.3.2,2.3.2-p2,2.3.3,2.3.3-p1,2.3.4,2.3.4-p2,2.3.5,2.3.5-p1,2.3.5-p2,2.4.0,2.4.1,B2B features,Companies Admin,MQP 1.0.8,MQP patches,Magento Commerce,Magento Commerce Cloud,Magento Quality Patches,New Company Registration Request,email address,sender email,user
---

The MDVA-29954 patch solves the issue where the "New Company Registration Request" and "You've been linked to a company" emails are sent from the wrong email address. This patch is available when the [Magento Quality Patch (MQP) tool](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching.html#mqp) v.1.0.8 is installed. Please note that the issue is scheduled to be fixed in Magento version 2.4.2.

## Affected products and versions

* The patch was designed for Magento Commerce 2.3.3.
* The patch is also compatible with Magento Commerce and Magento Commerce Cloud 2.3.0 - 2.3.5-p2, 2.4.0, and 2.4.1.

>![info]
>
>Note: the patch might become applicable to other versions with new MQP tool releases. To check if the patch is compatible with your Magento version, run `./vendor/bin/magento-patches status` .

## Issue

 <span class="wysiwyg-underline">Prerequisites</span> :

Install Magento with B2B, with **B2B Features** and **Company** enabled.

 <span class="wysiwyg-underline">Steps to reproduce:</span> 

1. Click on the **Create Account** dropdown on the storefront, and select **Create New Company Account** .
1. Fill in the required fields, and register the account.
1. Enable the **Company** from the backend ( **Customer > Companies** ).
1. Check the email address that you used for registration.
1. Set the **Company Admin password** by following the emailed instructions.
1. Log in to the frontend with the **Company Admin password** .
1. Create a new **Company User** in **My Account > Company Users > Add New User** .
1. Go to **Stores > Configurations > General-Store Email Addresses > General Contact** , and check **Sender Email** .
1. Go to the email that you used to register the **New User** in Step 7.

 <span class="wysiwyg-underline">Expected results:</span> 

The "You've been linked to a company" email is sent from an email address with the same value as for the **Sender Email** in Step 8, as expected.

 <span class="wysiwyg-underline">Actual results:</span> 

The "You've been linked to a company" email is sent from the **Companies Admin** email.

## Apply the patch

To apply individual patches use the following links depending on your Magento product:

* Magento Commerce: DevDocs [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching.html) .
* Magento Commerce Cloud: DevDocs [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) .

## Related reading

To learn more about Magento Quality Patches, refer to:

* [Magento Quality Patches released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492) .
* [Check if patch is available for your Magento issue using Magento Quality Patches](https://support.magento.com/hc/en-us/articles/360047125252) .

For info about other patches available in MQP tool, refer to the [Patches available in MQP tool](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-MQP-tool-) section.