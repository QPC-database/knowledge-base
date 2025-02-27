---
title: "MDVA-34102 Magento patch: inconsistent salable quantity"
labels: 2.3.0,2.3.1,2.3.2,2.3.2-p2,2.3.3,2.3.3-p1,2.3.4,2.3.4-p1,2.3.4-p2,2.3.5,2.3.5-p1,2.3.5-p2,2.3.6,2.3.6-p1,2.4.0,2.4.0-p1,2.4.1,2.4.1-p1,2.4.2,Default Stock,Edit Product,MQP 1.0.18,MQP patches,Magento Commerce,Magento Commerce Cloud,Magento Quality Patches,Product Grid,disabled product,salable quantity
---

The MDVA-34102 Magento patch solves the issue where the quantity of default stock is zero for disabled products on the Product Grid and Edit Product pages in Admin.

This patch is available when the [Magento Quality Patch (MQP) tool](https://support.magento.com/hc/en-us/articles/360047139492) 1.0.18 is installed. The patch ID is MDVA-34102. Please note that the issue is scheduled to be fixed in Magento version 2.4.3.

## Affected products and versions

 **The patch is created for Magento version:** Magento Commerce Cloud 2.3.5-p2

 **Compatible with Magento versions:** Magento Commerce and Magneto Commerce Cloud 2.3.0-2.4.2

>![info]
>
>Note: the patch might become applicable to other versions with new MQP tool releases. To check if the patch is compatible with your Magento version, run `./vendor/bin/magento-patches status` .

## Issue

 <span class="wysiwyg-underline">Steps to reproduce</span> :

1. Setup 2 websites with stores and store views.
1. Create an additional source and stock.
1. Add a simple product:
    * Set **Enable Product** = *No* .
    * Assign two sources with **Source Item Status** = *In Stock* with a quantity greater than zero (Example: **default stock** = *123* and **UK stock** = *123* ).
1. Save the product.
1. Check the **Product Salable Quantity** tab.

 <span class="wysiwyg-underline">Expected results</span> :

Both the default stock = *123* and the UK stock = *123.* The quantity of default stock is showed correctly for disabled products on the Product Grid and Edit Product pages in Admin, as expected.

 <span class="wysiwyg-underline">Actual results</span> :

The default stock = *0* and the UK stock = *123.* 

The quantity of default stock is zero for disabled products on the Product Grid and Edit Product pages in Admin.

## Apply the patch

To apply individual patches use the following links depending on your Magento product:

* Magento Commerce: DevDocs [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching.html) .
* Magento Commerce Cloud: DevDocs [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) .

## Related reading

To learn more about Magento Quality Patches, refer to:

* [Magento Quality Patches released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492) .
* [Check patch for Magento issue with Magento Quality Patches](https://support.magento.com/hc/en-us/articles/360047125252) .

For info about other patches available in MQP tool, refer to the [Patches available in MQP tool](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-MQP-tool-) section.