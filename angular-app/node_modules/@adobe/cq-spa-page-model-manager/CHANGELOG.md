### *1.0.7* - 4 April 2019

* no functional changes

### *1.0.6* - 6 March 2019

* ModelManager#initialze to consistently return the same type of object
* ModelManager#initialze to fire a cq-pagemodel-loaded event

### *1.0.5* - 12 December 2018

* ModelClient fetch: added default credentials for the request

### *1.0.4* - 9 November 2018

* support path ending the jcr:content when getting the data from the ModelStore

### *1.0.3* - 11 October 2018

* Un-found remote model entry point rejection handling
* README update

### *1.0.1* - 28 September 2018

 * **BREAKING CHANGE** API refactoring for a better modularization
 * **BREAKING CHANGE** SSR refactoring
    * Added support for setting apiHost, in order to force absolute url requests on Node server
    * Added support for initializing with an existing model. This is useful when we initialize in the client, the state from the server.
    * Guarding for dispatching & listening events only in browser context. 
    * Fixed race conditions with `init` method when called from `getData`

### Removed

 * unnecessary and misleading event triggering resulting in the Page Editor not to have overlays

## 0.0.24 - 22 June 2018

Public release of `cq-spa-page-model-manager`, which provides:

* support for context path
* **BREAKING CHANGE** change routing method to support History API by default (hash routing support has been removed)

## 0.0.23 - 15 May 2018

Public release of `cq-spa-page-model-manager`, which provides:

 * Support for the latest version of the `com.adobe.cq.export.json.hierarchy` API
    * Support and usage of the `:path` and `:children` fields to identify a page and its child pages
 * Support for URLs containing a context path
    * The `PageModelManager` can now be used in conjunction with URLs including a context path

## 0.0.22 - 20 April 2018

Initial public release of `cq-spa-page-model-manager`, which provides:
 * Updated `PageModelManager` API, now able to manage the model of multiple pages stored in AEM:
    * `getData()`, `addListeners()` and `removeListeners()` expect a config parameter that specifies the `pagePath` and `dataPath`
    * `getData()` supports a `forceReload` parameter
    * `cq-pagemodel-update` event listener expects `pagePath` and `dataPath` in the event data object
 * New `ModelRouter`, which reacts to hash changes and triggers the reload of the corresponding model asynchronously
    * `cq-pagemodel-route-changed` event indicates route changes after successful model update
