---
title: "MDVA-33632 Magento patch: out of stock product reorder exception"
labels: 2.3.0,2.3.1,2.3.2,2.3.2-p2,2.3.3,2.3.3-p1,2.3.4,2.3.4-p1,2.3.4-p2,2.3.5,2.3.5-p1,2.3.5-p2,2.3.6,2.3.6-p1,MQP 1.0.15,MQP patches,Magento Commerce,Magento Commerce Cloud,Magento Quality Patches,exception,out of stock,product,reorder
---

The MDVA-33632 Magento patch solves the issue where an exception is thrown when trying to reorder an out of stock product.

This patch is available when the [Magento Quality Patch (MQP) tool](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching.html#mqp) 1.0.15 is installed. Please note that the issue is scheduled to be fixed in Magento version 2.4.3.

## Affected products and versions

 **The patch is created for Magento version:** Magento Commerce Cloud 2.3.6

 **Compatible with Magento versions:** Magento Commerce Cloud and Magento Commerce 2.3.0 - 2.3.6-p1

>![info]
>
>Note: the patch might become applicable to other versions with new MQP tool releases. To check if the patch is compatible with your Magento version, run `./vendor/bin/magento-patches status` .

## Issue

 <span class="wysiwyg-underline">Steps to reproduce</span> :

1. Create a configurable product with one option (Example: **color** = *red* ) and set **qty** = *1* .
1. Create a customer, and place an order with this product, which at that moment will become **qty** = *0* .
1. Go to Admin, and try to reorder the previous order.

 <span class="wysiwyg-underline">Expected results</span> :

The customer gets the " *This product is out of stock.* " message for an out of stock product, as expected.

 <span class="wysiwyg-underline">Actual results</span> :

The customer gets the " *This product is out of stock.* " message, and `var/log/exception.log` contains a similar exception:

```php
[2020-12-09 00:17:36] report.CRITICAL: This product is out of stock. {"exception":"[object] (Magento\\Framework\\Exception\\LocalizedException(code: 0): This product is out of stock. at /vendor/magento/module-quote/Model/Quote.php:1711)"} []
```

## Apply the patch

To apply individual patches use the following links depending on your Magento product:

* Magento Commerce: DevDocs [Software Update Guide > Apply Patches](https://devdocs.magento.com/guides/v2.4/comp-mgr/patching.html) .
* Magento Commerce Cloud: DevDocs [Upgrades and Patches > Apply Patches](https://devdocs.magento.com/cloud/project/project-patch.html) .

## Related reading

To learn more about Magento Quality Patches, refer to:

* [Magento Quality Patches released: a new tool to self-serve quality patches](https://support.magento.com/hc/en-us/articles/360047139492) .
* [Check patch for Magento issue with Magento Quality Patches](https://support.magento.com/hc/en-us/articles/360047125252) .

For info about other patches available in MQP tool, refer to the [Patches available in MQP tool](https://support.magento.com/hc/en-us/sections/360010506631-Patches-available-in-MQP-tool-) section.