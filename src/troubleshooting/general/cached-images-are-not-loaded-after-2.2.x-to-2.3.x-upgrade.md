---
title: Cached images are not loaded after 2.2.X to 2.3.X upgrade
labels: 2.2.x,2.3.x,404,Magento Commerce Cloud,Pro,cache,images,troubleshooting
---

This article provides the solution for the issue with cached images not being displayed after upgrading from Magento Commerce Cloud 2.2.X to 2.3.X.

### Affected versions and editions:

* Magento Commerce Cloud 2.2.X, 2.3.X, Pro Plan

## Issue

After Magento is upgraded from 2.2.X to 2.3.X, the cached product images are not available, a 404 page is displayed instead.

The issue is caused by the incorrect Nginx configuration set in `.magento.app.yaml` : `index.php` (or none) is used for the `"/media"` location instead of `passthru: /get.php` .

## Solution

1. Check your `.magento.app.yaml` configuration file, at the `"/media"` location. The correct configuration looks like following:    ```yaml    "/media":      root: "pub/media"      allow: true      scripts: false      expires: 1y      passthru: "/get.php"    ```    
1. If `passthru` is not set to `"/get.php"` and `expires` is not set, take the following steps.
1. Correct the configuration file.
    * Starter Plan: correct the file yourself and push the changes.
    * Pro Plan:
    * Integration: correct the file yourself and push the changes.
    * Staging and Production: correct the file yourself, push the changes, and create a [Magento Support ticket](https://support.magento.com/hc/en-us/articles/360019088251) to have it applied.
    

1. Enable Fastly image optimization in the Magento Admin (Fastly must be configured prior), as described in<https://devdocs.magento.com/guides/v2.3/cloud/cdn/fastly-image-optimization.html>

If the configuration is correct, but you are still experiencing the issue, continue investigation or contact [Magento Support](https://support.magento.com/hc/en-us/articles/360019088251) .

 