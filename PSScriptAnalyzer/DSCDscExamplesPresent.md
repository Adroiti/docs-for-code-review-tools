Pattern: Missing examples for DSC

Issue: -

## Description

Every DSC resource module should contain folder `Examples` with sample configurations for every resource. Sample configurations should have resource name they are demonstrating in the title.

## How

To fix a violation of this rule, please make sure Examples directory is present:
* For non-class based resources it should exist at the same folder level as DSCResources folder.
* For class based resources it should be present at the same folder level as resource psm1 file.

Examples folder should contain sample configuration for given resource - file name should contain resource's name.

### Non-class based resource

Let's assume we have non-class based resource with a following file structure:
* xAzure
  * DSCResources
    * MSFT_xAzureSubscription
      * MSFT_xAzureSubscription.psm1
      * MSFT_xAzureSubscription.schema.mof

In this case, to fix this warning, we should add examples in a following way:
* xAzure
  * DSCResources
    * MSFT_xAzureSubscription
      * MSFT_xAzureSubscription.psm1
      * MSFT_xAzureSubscription.schema.mof
  * Examples
    * MSFT_xAzureSubscription_AddSubscriptionExample.ps1
    * MSFT_xAzureSubscription_RemoveSubscriptionExample.ps1

### Class based resource

Let's assume we have class based resource with a following file structure:
* MyDscResource
    * MyDscResource.psm1
    * MyDscResource.psd1

In this case, to fix this warning, we should add examples in a following way:
* MyDscResource
    * MyDscResource.psm1
    * MyDscResource.psd1
    * Examples
      * MyDscResource_Example1.ps1
      * MyDscResource_Example2.ps1

## Further Reading

* [PSScriptAnalyzer - DSCDscExamplesPresent](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/DSCDscExamplesPresent.md)