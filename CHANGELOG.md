# Elasticraft Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/) and this project adheres to [Semantic Versioning](http://semver.org/).

## 0.4.6
### Changed
- Do not index elements that do not have transformers.

### Fixed
- When publishing drafts, they didn't get uris. Now they do.
- Return values in ElasticraftService
- Indexing drafts via CLI

## 0.4.5
### Fixed
- Index when reverting to older version of entry

## 0.4.4
### Fixed
- Debug error

## 0.4.3
### Fixed
- Uncought error in settings page

## 0.4.2 - 2018-01-14
### Fixed
- Clean up console controller

## 0.4.1 - 2018-01-03
### Fixed
- Edit entry widget styling for Craft RC3

## 0.4.0 - 2017-12-21
### Added
- Cookie for logged in users for use in front end as admin link

### Changed
- Indexing drafts.

## 0.3.8 – 2017-11-29
### Fixed
- Fix drafts.

## 0.3.7 – 2017-11-27
### Added
- Index drafts.

## 0.3.6 - 2017-11-17
### Fixed
- postDate and expiryDate is needed for filtering entrie.

## 0.3.5 - 2017-11-10
### Added
- Utility button to remove stale and failed jobs from queue, to allow other jobs to start.

### Fixed
- Made main plugin file DRY-er.
- Made elastic jobs and service safer.
- Updated dependencies.

## 0.3.4 - 2017-09-13
### Added
- New option to reindex all elements, and in the same operation deleting stale documents in Elasticsearch, effectively recreating the index with no down time.

### Fixed
- Ignore 404 errors in some service methods, handle them in others.

## 0.3.3 - 2017-09-13
### Changed
- Now adding dates to all ElasticDocuments.

## 0.3.2 - 2017-09-12
### Fixed
- Optimize indexing.
- Make widget in entry edit page more informative. Now lets editor know status of Elasticsearch if entry is not found.
- Throw errors in elasticService to make bug hunting easier.

## 0.3.1 - 2017-09-10
### Fixed
- Make plugin more robust if no hosts are configured.
- Make settings actually work.

## 0.3.0 - 2017-09-08
### Changed
- Breaking: document type is now set to `element` for all elements. To access section handles – for entries – or handles – for globals, use ``_source.type.keyword` instead of `_type`.

### Added
- Console command for reindexing to Elasticsearch.
- Example page transformers and short description in README.
- Add stuff to settings page.

### Removed
- Removed widget for now.
- Removed debug tools from utility page.

### Fixed
- Only show last indexed date widget if entry has an associated pagetransformer.

## 0.2.3 - 2017-09-07
### Fixed
- Recreate index now works better and indexes globals as well
- Code cleanup

## 0.2.2 - 2017-09-05
### Added
- Translation files for nb (not complete)
- Document counts by type added to utility page
- dfo\elasticraft\controllers\DefaultController::recreateIndex()
- dfo\elasticraft\controllers\DefaultController::getDocumentCount()
- (private) dfo\elasticraft\controllers\DefaultController::_deleteIndex()
- (private) dfo\elasticraft\controllers\DefaultController::_indexAllElements()

### Fixed
- Saving entry with matrix fires `EVENT_AFTER_SAVE_ELEMENT` for each matrix block. To not add unnecessary jobs, the check for if the element is of a type that should be indexed must be done before adding job.
- The widget added in `0.2.1` had an extra `</div>`. Now removed.
- A little cleanup

### Removed
- dfo\elasticraft\controllers\DefaultController::getIndexStats()
- dfo\elasticraft\controllers\DefaultController::deleteIndex()
- dfo\elasticraft\controllers\DefaultController::indexAllElements()

## 0.2.1 - 2017-09-04
### Added
- Widget with the date and time of the last indexing when editing an entry

### Fixed
- Error in mapping example in `config.php`

## 0.2.0 - 2017-08-31
### Changed
- New handling of dates

## 0.1.0 - 2017-07-03
### Added
- Initial release
