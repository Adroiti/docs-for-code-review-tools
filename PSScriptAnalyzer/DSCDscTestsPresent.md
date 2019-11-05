Pattern: Missing tests for DSC

Issue: -

## Description

Every DSC resource module should contain folder `Tests` with tests for every resource. Test scripts should have resource name they are testing in the file name.

## How

To fix a violation of this rule, please make sure Tests directory is present:
* For non-class based resources it should exist at the same folder level as DSCResources folder.
* For class based resources it should be present at the same folder level as resource psm1 file.

Tests folder should contain test script for given resource - file name should contain resource's name.

### Non-class based resource

Let's assume we have non-class based resource with a following file structure:
* xAzure
  * DSCResources
    * MSFT_xAzureSubscription
      * MSFT_xAzureSubscription.psm1
      * MSFT_xAzureSubscription.schema.mof

In this case, to fix this warning, we should add tests in a following way:
* xAzure
  * DSCResources
    * MSFT_xAzureSubscription
      * MSFT_xAzureSubscription.psm1
      * MSFT_xAzureSubscription.schema.mof
  * Tests
    * MSFT_xAzureSubscription_Tests.ps1

### Class based resource

Let's assume we have class based resource with a following file structure:
* MyDscResource
    * MyDscResource.psm1
    * MyDscResource.psd1

In this case, to fix this warning, we should add tests in a following way:
* MyDscResource
    * MyDscResource.psm1
    * MyDscResource.psd1
    * Tests
      * MyDscResource_Tests.ps1

## Further Reading

* [PSScriptAnalyzer - DSCDscTestsPresent](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/DSCDscTestsPresent.md)