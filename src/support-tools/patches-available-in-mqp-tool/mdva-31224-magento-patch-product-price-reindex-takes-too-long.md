---
title: "MDVA-31224 Magento patch: Product price reindex takes too long"
labels: 2.3.3,2.3.3-p1,2.3.4,2.3.4-p2,MQP 1.0.7,MQP patches,Magento Commerce,Magento Commerce Cloud,price,product,reindex,support tools,time
---

The MDVA-31224 patch solves the issue when product price reindex takes too long to complete or never completes. This patch is available when the [Magento Quality Patch (MQP) tool](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching.html#mqp) v.1.0.7 is installed.

## Affected products and versions

* The patch was designed for Magento Commerce Cloud 2.3.3.
* The patch is also compatible with Magento Commerce and Magento Commerce Cloud 2.3.3 - 2.3.4-p2.

>![info]
>
>Note: the patch might become applicable to other versions with new MQP tool releases. To check if the patch is compatible with your Magento version, run `./vendor/bin/magento-patches
    status` 

## Issue

Product price reindex takes too long to complete or never completes.

 <span class="wysiwyg-underline">Steps to reproduce:</span> 

1. Create 6000 bundled products with 15 options.
1. Create 1 bundled product with 30 options.
1. Run price reindex from CLI:     `bin/magento indexer:reindex catalog_product_price`     

 <span class="wysiwyg-underline">Expected results:</span> 

Product price reindex takes 1.5 hours or more to complete.

 <span class="wysiwyg-underline">Actual results:</span> 

Product price reindex takes a short time (a minute or two) to complete.

## Apply the patch

To apply individual patches use the following links depending on your Magento product:

* Magento Commerce: DevDocs [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching.html) .
* Magento Commerce Cloud: DevDocs [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) .

## Related reading

To learn more about Magento Quality Patches, refer to:

* [Magento Quality Patches released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492) .
* [Check if patch is available for your Magento issue using Magento Quality Patches](https://support.magento.com/hc/en-us/articles/360047125252) .

For info about other patches available in MQP tool, refer to the [Patches available in MQP tool](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-MQP-tool-) section.