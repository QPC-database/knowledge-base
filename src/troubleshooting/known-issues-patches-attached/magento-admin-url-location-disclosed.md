---
title: Magento Admin URL location disclosed
labels: 2.x.x,Admin URL disclosed,Magento Commerce,Magento Commerce Cloud,known issues,patch,troubleshooting
---

This article provides a patch for the Magento 2 security issue where the URL location of a Magento Admin panel can be disclosed. Knowing the URL location could make it easier to automate attacks.

### Affected versions:

* Magento Commerce Cloud 2.X.X
* Magento Commerce 2.X.X
* Magento Open Source  2.X.X

## Issue

An issue has been discovered in Magento Open Source and Magento Commerce that can be used to disclose the URL location of a Magento Admin panel. While there is currently no reason to believe this issue would lead to a compromise directly, knowing the URL location could make it easier to automate attacks.

## Solution

To fix the issue, please apply the patch attached to this article. To download it, scroll down to the end of the article and click the file name, or click the following link:

* Download [PRODSECBUG-2432\_EE\_2.1.17\_composer.patch](assets/PRODSECBUG-2432_EE_2.1.17_composer.patch.zip) - for versions 2.1.13-2.1.17, Magento Commerce, Magento Open Source
* Download [PRODSECBUG-2432\_EE\_2.2.8\_composer.patch](assets/PRODSECBUG-2432_EE_2.2.8_composer.patch.zip) - for versions 2.2.0-2.2.8, all editions
* Download [PRODSECBUG-2432\_EE\_2.3.1\_composer.patch](assets/PRODSECBUG-2432_EE_2.3.1_composer.patch.zip) - for versions 2.3.0-2.3.1, all editions

If you do see a patch for your product/version, please upgrade to the latest security release and then apply the patch.

Magento strongly recommends applying the patch as soon as possible, even if you have not experienced any symptoms of an attack.

## How to apply the patch

See [How to apply a composer patch provided by Magento](https://support.magento.com/hc/en-us/articles/360028367731) for instructions.

## Other security recommendations

Magento also strongly recommends that merchants deploy tools to secure their admin panel, including two-factor authentication, VPN, IP AllowListing, and more. For detailed information, see the following blogs and documentation:

* [5 Immediate Actions to Protect Against Brute Force Attacks](https://magento.com/security/best-practices/5-immediate-actions-protect-against-brute-force-attacks)
* [Protect Your Magento Installation Password Guessing New Update](https://magento.com/security/best-practices/protect-your-magento-installation-password-guessing-new-update)
* [Security Best Practices](https://magento.com/security/best-practices/security-best-practices)
* Adding and Configuring Two-Factor Authentication in Magento for [2.1.x](https://docs.magento.com/m2/2.1/ce/user_guide/stores/security-two-factor-authentication.html) , [2.2.x](https://docs.magento.com/m2/2.2/ce/user_guide/stores/security-two-factor-authentication.html) , and [2.3.x](https://docs.magento.com/m2/ce/user_guide/stores/security-two-factor-authentication.html) 

## Attached files
