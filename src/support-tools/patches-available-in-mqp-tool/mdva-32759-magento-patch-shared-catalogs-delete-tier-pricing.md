---
title: "MDVA-32759 Magento patch: shared catalogs delete tier pricing"
labels: 2.3.0,2.3.1,2.3.2,2.3.2-p2,2.3.3,2.3.3-p1,2.3.4,2.3.4-p1,2.3.4-p2,2.3.5,2.3.5-p1,2.3.5-p2,2.3.6,2.4.0,2.4.0-p1,2.4.1,2.4.1-p1,2.4.2,B2B features,MQP 1.0.15,MQP patches,Magento Commerce,Magento Commerce Cloud,Magento Quality Patches,advanced pricing,price,product,shared catalog,tier pricing
---

The MDVA-32759 Magento patch solves the issue where shared catalogs delete existing tier pricing.

This patch is available when the [Magento Quality Patch (MQP) tool](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching.html#mqp) 1.0.15 is installed. Please note that the issue is scheduled to be fixed in Magento version 2.4.3.

## Affected products and versions

 **The patch is created for Magento version:** Magento Commerce Cloud 2.3.4-p2

 **Compatible with Magento versions:** Magento Commerce Cloud and Magento Commerce 2.3.0 - 2.4.2

>![info]
>
>Note: the patch might become applicable to other versions with new MQP tool releases. To check if the patch is compatible with your Magento version, run `./vendor/bin/magento-patches status` .

## Issue

 <span class="wysiwyg-underline">Prerequisites</span> :

Install Magento with B2B, with **B2B Features** enabled.

 <span class="wysiwyg-underline">Steps to reproduce</span> :

1. Go to **Stores > Configuration > B2B Features > Enable Company** and **Shared Catalog** .
1. Run `bin/magento cron:run` .
1. Create a simple product, click on **Advanced Pricing** , and add **Catalog and Tier price** , and then save it.
1. Go to **Catalog > Shared Catalog > Set Pricing and Structure** , click on **Configure** , and from that drop-down menu, deselect all options and save.
1. Run `bin/magento cron:run` .
1. Open the above created product, and check advanced pricing.

 <span class="wysiwyg-underline">Expected results</span> :

The tier prices should not be removed from the products after removing all products from the public shared catalog, as expected.

 <span class="wysiwyg-underline">Actual results</span> :

The tier prices get removed after removing all products from the public shared catalog.

 
## Apply the patch

To apply individual patches use the following links depending on your Magento product:

* Magento Commerce: DevDocs [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching.html) .
* Magento Commerce Cloud: DevDocs [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) .

## Related reading

To learn more about Magento Quality Patches, refer to:

* [Magento Quality Patches released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492) .
* [Check patch for Magento issue with Magento Quality Patches](https://support.magento.com/hc/en-us/articles/360047125252) .

For info about other patches available in MQP tool, refer to the [Patches available in MQP tool](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-MQP-tool-) section.