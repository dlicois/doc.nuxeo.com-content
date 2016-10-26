---
title: Upgrade from LTS 2015 following Fast Tracks
review:
    comment: ''
    date: '2015-12-01'
    status: ok
labels:
    - multiexcerpt
tabbed_page: true
toc: true
confluence:
    ajs-parent-page-id: '3343538'
    ajs-parent-page-title: Upgrading the Nuxeo Platform
    ajs-space-key: NXDOC
    ajs-space-name: Nuxeo Platform Developer Documentation
    canonical: Upgrade+from+LTS+2015+following+Fast+Tracks
    canonical_source: >-
        https://doc.nuxeo.com/display/NXDOC/Upgrade+from+LTS+2015+following+Fast+Tracks
    page_id: '31032752'
    shortlink: sIXZAQ
    shortlink_source: 'https://doc.nuxeo.com/x/sIXZAQ'
    source_link: /display/NXDOC/Upgrade+from+LTS+2015+following+Fast+Tracks
tree_item_index: 200
history:
    -
        author: Solen Guitter
        date: '2016-07-28 13:05'
        message: dd Server + JSF UI = equivalent of CA
        version: '31'
    -
        author: Solen Guitter
        date: '2016-07-19 09:12'
        message: ''
        version: '30'
    -
        author: Solen Guitter
        date: '2016-07-12 08:27'
        message: ''
        version: '29'
    -
        author: Anahide Tchertchian
        date: '2016-07-11 17:03'
        message: 'NXDOC-840: JSF optims'
        version: '28'
    -
        author: Anahide Tchertchian
        date: '2016-07-11 12:45'
        message: ''
        version: '27'
    -
        author: Anahide Tchertchian
        date: '2016-07-08 17:19'
        message: 'NXDOC-840: JSF optims doc'
        version: '26'
    -
        author: Anahide Tchertchian
        date: '2016-07-08 15:24'
        message: 'NXDOC-840: start documenting JSF perfs optims'
        version: '25'
    -
        author: Solen Guitter
        date: '2016-07-06 13:04'
        message: ''
        version: '24'
    -
        author: Solen Guitter
        date: '2016-07-06 13:00'
        message: ''
        version: '23'
    -
        author: Arnaud Kervern
        date: '2016-07-06 09:48'
        message: ''
        version: '22'
    -
        author: Arnaud Kervern
        date: '2016-07-06 09:45'
        message: ''
        version: '21'
    -
        author: Solen Guitter
        date: '2016-07-04 16:20'
        message: ''
        version: '20'
    -
        author: Arnaud Kervern
        date: '2016-07-04 15:12'
        message: ''
        version: '19'
    -
        author: Solen Guitter
        date: '2016-07-04 14:51'
        message: ''
        version: '18'
    -
        author: Arnaud Kervern
        date: '2016-07-04 14:45'
        message: ''
        version: '17'
    -
        author: Solen Guitter
        date: '2016-04-20 08:00'
        message: ''
        version: '16'
    -
        author: Manon Lumeau
        date: '2016-04-19 15:33'
        message: ''
        version: '15'
    -
        author: Antoine Taillefer
        date: '2016-04-18 09:06'
        message: ''
        version: '14'
    -
        author: Solen Guitter
        date: '2016-04-13 08:50'
        message: ''
        version: '13'
    -
        author: Solen Guitter
        date: '2016-04-13 08:15'
        message: ''
        version: '12'
    -
        author: Solen Guitter
        date: '2016-04-04 10:06'
        message: ''
        version: '11'
    -
        author: Solen Guitter
        date: '2016-04-04 10:06'
        message: Add related documentation links
        version: '10'
    -
        author: Solen Guitter
        date: '2016-04-04 09:54'
        message: ''
        version: '9'
    -
        author: Solen Guitter
        date: '2016-04-04 09:43'
        message: ''
        version: '8'
    -
        author: Solen Guitter
        date: '2016-04-04 09:41'
        message: ''
        version: '7'
    -
        author: Solen Guitter
        date: '2016-04-04 09:40'
        message: ''
        version: '6'
    -
        author: Solen Guitter
        date: '2016-04-04 09:39'
        message: ''
        version: '5'
    -
        author: Solen Guitter
        date: '2016-04-04 09:38'
        message: ''
        version: '4'
    -
        author: Solen Guitter
        date: '2016-04-04 09:26'
        message: ''
        version: '3'
    -
        author: Arnaud Kervern
        date: '2016-04-01 15:50'
        message: ''
        version: '2'
    -
        author: Arnaud Kervern
        date: '2016-04-01 15:47'
        message: ''
        version: '1'

---
# From LTS 2015 to 8.1

## Installation and Configuration

### Parameters to Update

<div class="table-scroll"><table class="hover"><tbody><tr><th colspan="1">Parameter</th><th colspan="1">Modification</th><th colspan="1">Reference</th></tr><tr><td colspan="1">`nuxeo.s3storage.bucket.prefix`</td><td colspan="1">**Moved** to `nuxeo.s3storage.bucket_prefix`</td><td colspan="1">[NXP-18565](https://jira.nuxeo.com/browse/NXP-18565)</td></tr><tr><td colspan="1">`nuxeo.vcs.ddlmode`</td><td colspan="1">**New default value** to `execute` (previously: `compat`)</td><td colspan="1">[NXP-17396](https://jira.nuxeo.com/browse/NXP-17396)</td></tr></tbody></table></div>

## Code Changes

### Deprecated APIs

{{! multiexcerpt name='upgrade-8.1-api-Environment.getHome'}}

Calls to `Environment.getHome()` might need to be replaced with `Environment.getRuntimeHome()` or `Environment.getServerHome()` to ensure that you are using the correct home path in your code. See [NXP-18667](https://jira.nuxeo.com/browse/NXP-18667).

{{! /multiexcerpt}}

### Addons

#### Nuxeo Live Connect

{{! multiexcerpt name='upgrade-8.1-live-connect'}}

Several changes in `BatchUpdateBlobProvider` break compatibility with custom code created on LTS 2015 or before. We removed two public methods only used internally:

*   `getPageProviderNameForUpdate()`
*   `getBlobProviderId()`

The code of `BatchUpdateBlobProvider#processDocumentsUpdate()` was moved to an abstract class `AbstractLiveConnectBlobProvider` which provides a default implementation above interface.

To upgrade your code:

1.  Make your classes to extend `AbstractLiveConnectBlobProvider` which provides implementation of `BatchUpdateBlobProvider`.
2.  Remove call to `getBlobProvider()` or implement it in your custom code. See [NXP-18660](https://jira.nuxeo.com/browse/NXP-18660).

{{! /multiexcerpt}}

&nbsp;

#### Nuxeo Multi Tenant

{{! multiexcerpt name='upgrade-8.1-multi-tenant'}}

&nbsp;We removed `multi_tenant_user.xsd` and `multi_tenant_group.xsd` schemas. The `tenantId` field is now part of default `user.xsd` and `group.xsd` schemas. See&nbsp;[NXP-18496](https://jira.nuxeo.com/browse/NXP-18496).

{{! /multiexcerpt}}

## Complementary Information

*   [Upgrade notes for 8.1](https://jira.nuxeo.com/issues/?jql=project%20in%20%28NXP%2C%20NXCM%29%20AND%20resolution%20%3D%20Fixed%20AND%20fixVersion%20IN%20%28%228.1%22%20%29%20AND%20%28%22Impact%20type%22%20%3D%20%22API%20change%22%20OR%20%22Upgrade%20notes%22%20is%20not%20EMPTY%29%20ORDER%20BY%20component%20DESC%2C%20key%20DESC)
*   [Release notes for 8.1](http://nuxeo.github.io/releasenotes/8.1/)

# From 8.1 to 8.2

## Configuration

<div>

### New Parameters

</div>

<div class="table-scroll"><table class="hover"><tbody><tr><th colspan="1">Parameter</th><th colspan="1">Description</th><th colspan="1">Reference</th></tr><tr><td colspan="1">

`nuxeo.automation.properties.value.trim`

</td><td colspan="1">

Force Automation properties value to be trimmed (default:`false`)

</td><td colspan="1">

[NXP-19170](https://jira.nuxeo.com/browse/NXP-19170)

</td></tr></tbody></table></div>

<div>

###
Notes

</div>

{{! multiexcerpt name='upgrade-8.2-hidden-stacktraces'}}

Stacktraces are now hidden per default in error pages. Activate the `dev mode` (`org.nuxeo.dev=true`) to get them back.

{{! /multiexcerpt}}

## Code Changes&nbsp;

### Deleted APIs

{{! multiexcerpt name='upgrade-8.2-api-REST-group'}}

REST endpoint `/group/{groupname}` no longer marshall members (users and groups) per default. To keep them present in the response, use `fetch.group=memberUsers` and/or `fetch.group=memberGroups` properties in the request. See: [NXP-19112](https://jira.nuxeo.com/browse/NXP-19112).

{{! /multiexcerpt}}

### <span style="color: rgb(0,0,0);">Deleted Features</span>

{{! multiexcerpt name='upgrade-8.2-remove-annotations'}}

Annotations were removed from Nuxeo Platform 8.2\. A new integration of annotations will be implemented for the pdf.js previewer before Nuxeo Platform LTS 2016.

{{! /multiexcerpt}}

### <span style="color: rgb(0,0,0);">JSF Performance Optimization Changes
</span>

{{! multiexcerpt name='JSF-optimizations'}}

Nuxeo 8.2 and Nuxeo 7.10-HF12 hold changes optimizing performance of JSF pages rendering and processing).

These improvements rely on:

1.  Optimizations of variables exposure in the context
2.  Optimizations of pluggable actions rendering
3.  Optimizations of document listings rendering

Some helpers have also been defined to help analyzing what element is taking time when rendering a page, see [How to Debug Slow Page Rendering]({{page page='how-to-debug-slow-page-rendering'}}).

Optimizations 1 and 2 should not have any impact on existing templates, maybe except on edge cases. If the misbehavior is affecting a tag `nxu:set`, the boolean attribute `useAlias=true` can be used to get back the old behavior.

Optimization 3 can have an impact on custom widget templates when used inside document listings, as some variables may not be available in the same context: `c:set`, `c:if` tags are resolved at build time, they should be replaced by other JSF tags using the `rendered` attribute, resolved at render time.

{{#> callout type='info' }}

On 7.10-HF12, optimizations are disabled by default. You can add the following contribution to your application to enable them: [enable-jsf-optims-config.xml](https://jira.nuxeo.com/secure/attachment/53920/enable-jsf-optims-config.xml).

{{/callout}}

Reference JIRA issue: [NXP-17690](https://jira.nuxeo.com/browse/NXP-17690)

{{! /multiexcerpt}}

### <span style="color: rgb(0,0,0);">Complementary Information</span>

*   [Upgrade notes for 8.2](https://jira.nuxeo.com/issues/?jql=project%20in%20%28NXP%2C%20NXCM%29%20AND%20resolution%20%3D%20Fixed%20AND%20fixVersion%20IN%20%28%228.2%22%20%29%20AND%20%28%22Impact%20type%22%20%3D%20%22API%20change%22%20OR%20%22Upgrade%20notes%22%20is%20not%20EMPTY%29%20ORDER%20BY%20component%20DESC%2C%20key%20DESC)
*   [Release notes for 8.2](http://nuxeo.github.io/releasenotes/8.2/)

# From 8.2 to 8.3

## Distribution Changes

### <span style="color: rgb(0,0,0);font-size: 16.0px;line-height: 1.5625;">UI Dedicated Package
</span>

{{! multiexcerpt name='upgrade-8.3-jsf-ui'}}

The Nuxeo Platform distribution has been refactored to separate server-side features and the user interface. As a consequence the user interface is now available in a Nuxeo Package called [Nuxeo JSF UI](https://connect.nuxeo.com/nuxeo/site/marketplace/package/nuxeo-jsf-ui). This package should be installed on the new base distribution of the platform, called Nuxeo Server. Using Nuxeo Server with the Nuxeo JSF UI is the equivalent of the previous CAP distribution.

```bash
$ nuxeoctl mp-install nuxeo-jsf-ui
```

{{! /multiexcerpt}}

## <span style="color: rgb(0,0,0);">Code Changes</span>

### Nuxeo and iframe

{{! multiexcerpt name='upgrade-8.3-code-iframe'}}

Nuxeo is now sending the `X-FRAME-OPTIONS` header with `SAMEORIGIN` value. It restricts Nuxeo to be embedded in an iframe from the same origin.

You can disable it using:

```xml
<require>org.nuxeo.ecm.platform.web.common.requestcontroller.service.RequestControllerService.defaultContrib</require>

<extension target="org.nuxeo.ecm.platform.web.common.requestcontroller.service.RequestControllerService"
    point="responseHeaders">
  <header name="X-Frame-Options" enabled="false"/>
</extension>
```

This is required for the addon [Nuxeo for Salesforce](https://connect.nuxeo.com/nuxeo/site/marketplace/package/nuxeo-salesforce).

See [NXP-19629](https://jira.nuxeo.com/browse/NXP-19629) for details.

{{! /multiexcerpt}}

### Deprecated APIs

{{! multiexcerpt name='upgrade-8.3-api-coreSession_methods'}}

The following methods are deprecated in order to introduce same methods with a `var args` argument `CopyOption`.

*   `CoreSession#copy(DocumentRef, DocumentRef, String)`

*   `CoreSession#copy(List<DocumentRef>, DocumentRef)`

*   `CoreSession#copyProxyAsDocument(DocumentRef, DocumentRef, String)`

*   `CoreSession#copyProxyAsDocument(List<DocumentRef>, DocumentRef)`

See [NXP-19740](https://jira.nuxeo.com/browse/NXP-19740) for details.

{{! /multiexcerpt}}

### WorkManager

{{! multiexcerpt name='upgrade-8.3-code-workManager'}}

The `canceled` and `completed` states are removed from the work's API. So you can't get results from completed works anymore. Instead you should store results by means of the `transient store`.
The previous way of querying for queue's counter has been deprecated by a the new API `org.nuxeo.ecm.core.work.api.WorkManager.getMetrics(String)` which provides you with the consistent set of counters.

See [NXP-19160](https://jira.nuxeo.com/browse/NXP-19160) for details.

{{! /multiexcerpt}}

### REST Workflow

{{! multiexcerpt name='upgrade-8.3-code-RESTWorkflow'}}

The `url` property of a workflow blob has been moved to the `data` property. See [NXP-19640](https://jira.nuxeo.com/browse/NXP-19640) for details.

The `url` property of a blob is now following the correct pattern. Previously `../[thumbnail:thumb:thumbnail/retrievedFile.png](http://thumbnailthumbthumbnail)` is now `../[thumb:thumbnail/retrievedFile.png](http://thumbthumbnail)`.See [NXP-18239](http://jira.nuxeo.com/browse/NXP-18239) for details.

{{! /multiexcerpt}}

&nbsp;

## Optimizations

<div>

### Nuxeo Drive

{{! multiexcerpt name='upgrade-8.3-optims-drive'}}

The permission checks done when adapting a document to a `FileSystemItem` are optimized by default with the `org.nuxeo.drive.permissionCheckOptimized` property of the `ConfigurationService` set to `true`.

The previous behavior can be re-activated using:

```xml
<extension target="org.nuxeo.runtime.ConfigurationService" point="configuration">
  <property name="org.nuxeo.drive.permissionCheckOptimized">false</property>
</extension>
```

See [NXP-19441](https://jira.nuxeo.com/browse/NXP-19441) for details.

{{! /multiexcerpt}}

## Nuxeo Packages

### Deprecated Packages

{{! multiexcerpt name='upgrade-8.3-NuxeoPackages-webMobile'}}

`nuxeo-web-mobile` has been deprecated in order to let some place to the new standalone [Nuxeo Application](https://itunes.apple.com/en/app/nuxeo/id1103802613?ls=1&mt=8), available on iOS.

{{! /multiexcerpt}}

### New Packages

{{! multiexcerpt name='upgrade-8.3-NuxeoPackages-jsfui'}}

The&nbsp; [Nuxeo JSF UI](https://connect.nuxeo.com/nuxeo/site/marketplace/package/nuxeo-jsf-ui) package lets you install the old Nuxeo UI based on JSF technologies.

{{! /multiexcerpt}}

## <span style="color: rgb(0,0,0);">Complementary Information</span>

*   [Upgrade notes for 8.3](https://jira.nuxeo.com/issues/?jql=project%20in%20%28NXP%2C%20NXCM%29%20AND%20resolution%20%3D%20Fixed%20AND%20fixVersion%20IN%20%28%228.3%22%20%29%20AND%20%28%22Impact%20type%22%20%3D%20%22API%20change%22%20OR%20%22Upgrade%20notes%22%20is%20not%20EMPTY%29%20ORDER%20BY%20component%20DESC%2C%20key%20DESC)
*   [Release notes for 8.3](http://nuxeo.github.io/releasenotes/8.3/)

</div>

{{> end_of_tabs }}

&nbsp;

* * *

&nbsp;

<div class="row" data-equalizer data-equalize-on="medium"><div class="column medium-6">{{#> panel heading='Related Documentation'}}

*   [Upgrade from LTS 2015 to 8.3]({{page page='upgrade-from-lts-2015-to-83'}})
*   [Upgrading the Nuxeo Platform]({{page page='upgrading-the-nuxeo-platform'}})

{{/panel}}</div><div class="column medium-6">

&nbsp;

</div></div>