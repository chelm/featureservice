# Change Log
All notable changes to this project will be documented in this file.
This project adheres to [Semantic Versioning](http://semver.org/).

## [1.6.2] - 2019-11-05
### Unreleased 
* Throw `TypeError` when URL is not a FeatureServer or MapServer with optional layer

## [1.6.1] - 2018-11-28
### Changed
* Double check pagination support with a request for the second page

## [1.6.0] - 2018-06-19
### Added
* Check for an option `outSR` and if provided use it to transform data; if no outSR option default to `outSR=4326`

## [1.5.13] - 2018-01-31
### Fixed
* Parse out html at the end of an otherwise valid response

## [1.5.12] - 2017-12-29
### Changed
* Z value is requested when paging

## [1.5.11] - 2016-10-23
### Fixed
* Use options.size to restrict max

## [1.5.10] - 2016-10-23
### Changed
* Don't use forever agent on http requests

## [1.5.9] - 2016-10-20
### Changed
* Use request library instead of hand-rolled http(s) requests

## [1.5.8] - 2016-10-16
### Changed
* Don't set min max OIDs for a single page request

## [1.5.7] - 2016-04-07
### Changed
* Remove unneeded try/catch

## [1.5.6] - 2016-04-06
### Fixed
* Get correct objectID range even when field names are unexpectedly capitalized

## [1.5.5] - 2016-03-31
### Changed
* Exposed `getObjectIdRange` as public function

### Fixed
* Corrected bug in statistics paging strategy

## [1.5.4] - 2016-03-30
### Fixed
* Don't throw exception when passed in layer is of type numeric

## [1.5.3] - 2016-03-23
### Changed
* A passed-in layer will always override what's in the url

## [1.5.2] - 2016-03-03
### Fixed
* Get the object id field if it's explicitly in info properties
* resultOffset strategy was reversed

## [1.5.1] - 2016-03-02
### Changed
* Don't use resultOffset for services not hosted on ArcGIS Online, it's not reliable
* Decode streaming server response

## [1.5.0] - 2016-02-28
### Added
* Service Info, Layer Info, and Metadata are memoized
* Can call `info`, `layerInfo`, and `metadata` without a callback when info is memoized

### Changed
* Concurrency is set during paging process
* URL parsing for services is more precise

## [1.4.6] - 2016-01-20
### Fixed
* Guard against missing ObjectID field when trying to page
* Remove unused dep

## [1.4.5] - 2016-01-13
### Changed
* Throttle concurrency down on every 2 failed requests
* Throttle concurrency up on every 10 successful requests

## [1.4.4] - 2016-01-07
### Fixed
* Removed bad reference to `this`

## [1.4.3] - 2016-01-04
### Changed
* Concurrency is throttled when encountering errors in the paging queue
### Fixed
* Urls and Layers are parsed correctly on service init

## [1.4.2] - 2015-10-13
### Changed
* Removed callback from parse try statement

## [1.4.1] - 2015-10-13
### Fixed
* Removed log statement that was causing the process to crash

## [1.4.0] - 2015-10-12
### Added
* Backoff time for failed requests can now be set as an option
* `service.info` returns information about the feature or map service

### Changed
* Return the page that was successfully completed when getting features
* Response parsing has been moved to its own function and the callback is no longer wrapped in a try/catch

### Fixed
* No longer failing to parse multi-chunk feature service responses that are not compressed

## [1.3.1]
### Fixed
* Log retry urls correclty

## [1.3.0]
### Added
* Allow a logger to be passed in through options.logger when initializing a new service

### Fixed
* Don't throw exception when there is no error in the json returned from server
* Catch non-json responses explicitly
* Don't use zlib methods unsupported in node 0.10.* in testing
* Error timestamps are all written in same case

## [1.2.7] - 2015-09-03
### Fixed
* Correct logic for correcting against poorly instantiated FeatureServices

## [1.2.6] - 2015-09-02
### Fixed
* Don't set a layer id with a query string
* Don't set a url with a query string

## [1.2.5] - 2015-09-02
### Fixed
* Uncaught error when `json.error` doesn't exist in `FeatureService.layerInfo`

## [1.2.4] - 2015-09-01
### Changed
* Restrict max record count to 5000 or less

### Fixed
* Pages generated from statistics use the correct layer when index > 0

## [1.2.3] - 2015-08-31
### Fixed
* Do not exclude object ids === 0 when building pages

## [1.2.2] - 2015-08-26
### Changed
* Errors after timeouts conform to standard
* Errors on metadata requests conform to standard

### Fixed
* Requests are ended correctly after timeouts

## [1.2.1] - 2015-08-17
### Changed
* All requests accept gzip or deflate compressed
* Requests are decoded async (for compatibility with node < 0.11.12)

### Fixed
* Pages are built correctly for layers with an index > 0

## [1.2.0] - 2015-08-11
### Fixed
* Pages based on object ids are now formed correctly

### Changed
* All errors returned to the requestor are standardized

## [1.1.1] - 2015-08-10
### Fixed
* Build dist for changes

## [1.1.0] - 2015-08-10
### Added
* New fixtures and integration tests for paging
* Support for paging layers from server version 10.0
* New fixtures and tests for decoding

### Changed
* Refactored paging strategy
* Moved feature request decoding into isolated function

### Fixed
* Catch errors that come on 200 responses
* Errors are reported correctly up the chain
* Retries for all errors

## [1.0.0] - 2015-08-07
### Added
* New function gets objectID from service info

### Changed
* Moved to koopjs github organization

### Fixed
* detach http/https modules from FeatureService instances

## [0.2.0] - 2015-08-06
### Added
* Feature requests time out

### Changed
* Timeout set at 90 seconds

### Fixed
* Reference to non-existent functions

## [0.1.0] - 2015-08-05
### Added
* Feature service requests time out after 5 minutes of inactivity by default

### Changed
* TCP sockets are kept alive

## [0.0.4] - 2015-07-29
### Fixed
* request method was calling the callback twice when it wrapped a callback in a try/catch
* passing min and max to statsUrl for creating stats in pages method

## [0.0.3] - 2015-07-28
### Fixed
* A change made in v0.0.2 broke pagination. Its now fixed and a test for pages was added.

## [0.0.2] - 2015-07-27
### Added
* A method for making statistics calls to a service
* Support for using the module in the browser

### Changed
* http requests are all routed through the core http/https libs now

## [0.0.1] - 2015-07-22
### Added
* Code for requesting data from FeatureServices
* Tests on most methods

[1.6.1]: https://github.com/koopjs/featureservice/compare/v1.6.0...v1.6.1
[1.6.0]: https://github.com/koopjs/featureservice/compare/v1.5.13...v1.6.0
[1.5.13]: https://github.com/koopjs/featureservice/compare/v1.5.12...v1.5.13
[1.5.12]: https://github.com/koopjs/featureservice/compare/v1.5.11...v1.5.12
[1.5.11]: https://github.com/koopjs/featureservice/compare/v1.5.10...v1.5.11
[1.5.10]: https://github.com/koopjs/featureservice/compare/v1.5.9...v1.5.10
[1.5.9]: https://github.com/koopjs/featureservice/compare/v1.5.8...v1.5.9
[1.5.8]: https://github.com/koopjs/featureservice/compare/v1.5.7...v1.5.8
[1.5.7]: https://github.com/koopjs/featureservice/compare/v1.5.6...v1.5.7
[1.5.6]: https://github.com/koopjs/featureservice/compare/v1.5.5...v1.5.6
[1.5.5]: https://github.com/koopjs/featureservice/compare/v1.5.4...v1.5.5
[1.5.4]: https://github.com/koopjs/featureservice/compare/v1.5.3...v1.5.4
[1.5.3]: https://github.com/koopjs/featureservice/compare/v1.5.2...v1.5.3
[1.5.2]: https://github.com/koopjs/featureservice/compare/v1.5.1...v1.5.2
[1.5.1]: https://github.com/koopjs/featureservice/compare/v1.5.0...v1.5.1
[1.5.0]: https://github.com/koopjs/featureservice/compare/v1.4.6...v1.5.0
[1.4.6]: https://github.com/koopjs/featureservice/compare/v1.4.5...v1.4.6
[1.4.5]: https://github.com/koopjs/featureservice/compare/v1.4.4...v1.4.5
[1.4.4]: https://github.com/koopjs/featureservice/compare/v1.4.3...v1.4.4
[1.4.3]: https://github.com/koopjs/featureservice/compare/v1.4.2...v1.4.3
[1.4.2]: https://github.com/koopjs/featureservice/compare/v1.4.1...v1.4.2
[1.4.1]: https://github.com/koopjs/featureservice/compare/v1.4.0...v1.4.1
[1.4.0]: https://github.com/koopjs/featureservice/compare/v1.3.1...v1.4.0
[1.3.1]: https://github.com/koopjs/featureservice/compare/v1.3.0...v1.3.1
[1.3.0]: https://github.com/koopjs/featureservice/compare/v1.2.7...v1.3.0
[1.2.7]: https://github.com/koopjs/featureservice/compare/v1.2.6...v1.2.7
[1.2.6]: https://github.com/koopjs/featureservice/compare/v1.2.5...v1.2.6
[1.2.5]: https://github.com/koopjs/featureservice/compare/v1.2.4...v1.2.5
[1.2.4]: https://github.com/koopjs/featureservice/compare/v1.2.3...v1.2.4
[1.2.3]: https://github.com/koopjs/featureservice/compare/v1.2.2...v1.2.3
[1.2.2]: https://github.com/koopjs/featureservice/compare/v1.2.1...v1.2.2
[1.2.1]: https://github.com/koopjs/featureservice/compare/v1.2.0...v1.2.1
[1.2.0]: https://github.com/koopjs/featureservice/compare/v1.1.1...v1.2.0
[1.1.1]: https://github.com/koopjs/featureservice/compare/v1.1.0...v1.1.1
[1.1.0]: https://github.com/koopjs/featureservice/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/koopjs/featureservice/compare/v0.2.0...v1.0.0
[0.2.0]: https://github.com/koopjs/featureservice/compare/v0.1.0...v0.2.0
[0.1.0]: https://github.com/koopjs/featureservice/compare/v0.0.4...v0.1.0
[0.0.4]: https://github.com/koopjs/featureservice/compare/v0.0.3...v0.0.4
[0.0.3]: https://github.com/koopjs/featureservice/compare/v0.0.2...v0.0.3
[0.0.2]: https://github.com/koopjs/featureservice/compare/v0.0.1...v0.0.2
[0.0.1]: https://github.com/koopjs/featureservice/releases/tag/v0.0.1
