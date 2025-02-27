---
title: MDVA-28357 SKU search in Advanced Search page doesn't work
labels: 2.3.0,2.3.1,2.3.2,2.3.2-p2,2.3.3,2.3.3-p1,2.3.4,2.3.4-p2,2.3.5-p1,2.3.5-p2,2.3.6,2.4.0,2.4.0-p1,Advanced search,MQP 1.0.8,MQP patches,Magento Commerce,Magento Commerce Cloud,search,support tools
---

The MDVA-28357 solves the issue where search by a product SKU in the Advanced Search page does not lead to the relevant product displaying in search results. This patch is available when the [Magento Quality Patch (MQP) tool](https://support.magento.com/hc/en-us/articles/360047139492) v.1.0.8 is installed. Please note that the issue is fixed in Magento version 2.4.1.

## Affected products and versions

* This patch was designed for Magento Commerce 2.3.4-p2.
* The patch is also compatible with Magento Commerce and Magento Commerce Cloud 2.3.0 to 2.3.5-p2, and 2.4.0 to 2.4.0-p1.

>![info]
>
>Note: the patch might become applicable to other versions with new MQP tool releases. To check if the patch is compatible with your Magento version, run `./vendor/bin/magento-patches status` .

## Issue

In advanced search, searching using a SKU queries the SKU field using a wildcard. But a wildcard can only be used with `sku.keyword` , so this does not return the expected product.

 <span class="wysiwyg-underline">Steps to reproduce</span> 

1. Go to Advanced Search page.
1. Search by a SKU number.

 <span class="wysiwyg-underline">Actual result</span> Error message displays: *We can't find any items matching these search criteria. Modify your search* .

 <span class="wysiwyg-underline">Expected result</span> One product item displays with a message: *1 item were found using the following search criteria*  *SKU: XX-XXXX* 

## Apply the patch

For instructions on how to apply an MQP patch, use the following links depending on your Magento product:

* Magento Commerce: DevDocs [Apply patches using Magento Quality Patches Tool](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching/mqp.html) .
* Magento Commerce Cloud: DevDocs [Upgrades and Patches > Apply patches](https://devdocs.magento.com/cloud/project/project-patch.html) .

## Related reading

To learn more about Magento Quality Patches, refer to:

* [Magento Quality Patches released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492) .
* [Check if patch is available for your Magento issue using Magento Quality Patches](https://support.magento.com/hc/en-us/articles/360047125252) .

For info about other patches available in MQP tool, refer to the [Patches available in MQP tool](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-MQP-tool-) section.