# Changelog
All notable changes to Audit.NET and its extensions will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/).

## [12.1.6] - 2018-06-04
### Modified
- Audit.NET.Udp: Fix #129. Allow specifying host name on the Udp Configuration as an alternative to the IP address. 

## [12.1.5] - 2018-06-02
### Added
- Audit.NET.EventLog.Core: Created this new assembly/package to output events to the windows eventlog when targeting net core 2.0.
 
### Modified
- Audit.EntityFramework and Audit.EntityFramework.Core: Fix #128 to be compatible with new EF Core 2.1 lazy loading feature.
- Audit.NET: Removing Microsoft.Windows.Compatibility dependency from Audit.NET package

## [12.1.4] - 2018-05-25
### Added
- Audit.Mvc and Audit.Mvc.Core: Adding request and response bodies to the logs, optional via IncludeRequestBody and IncludeResponseBody properties on the action filter attribute.

## [12.1.3] - 2018-05-15
### Modified
- Audit.NET.AzureDocumentDB: Fix #126: AzureDocumentDb not respecting the global JsonSettings.

## [12.1.2] - 2018-05-15
### Modified
- Audit.Core: Fix bug #126: FileDataProvider not respecting JsonSettings. Exposed JsonSettings as a property of the FileDataProvider and fixed async methods.

## [12.1.1] - 2018-05-14
### Modified
- Audit.EntityFramework: Fix bug on SaveAsync for EntityFrameworkDataProvide. Related to #122.

## [12.1.0] - 2018-05-08
### Added
- Audit.WebApi: Adding `AuditApiGlobalFilter` a configurable global filter as an alternative
to decorate the controllers with `AuditApiAttribute`.

## [12.0.7] - 2018-05-05
### Modified
- Audit.WebApi: Adding `IncludeResponseBodyFor` and `ExcludeResponseBodyFor` property on `AuditApiAttribute` 
to allow conditionally Including/Excluding the Response Body from the log, only when certain Http Status codes are returned.


## [12.0.6] - 2018-05-04
### Modified
- Audit.Core: Adding `AuditDisabled()` method to fluent configuration API.
- Audit.WebApi: Bypassing the filter when audit is globally disabled.
- Audit.Mvc: Bypassing the filter when audit is globally disabled.

## [12.0.5] - 2018-05-02
### Modified
- Audit.WebApi: Adding context wrapper interface IContextWrapper and injection mechanism for Audit.WebApi on full framework. Related to #124.

## [12.0.4] - 2018-04-30
### Modified
- Audit.NET.AzureDocumentDB: Allowing builders to pass the connection string, database and collection.
- Audit.NET.Elasticsearch: Fixing project URL reference on nuget package.

## [12.0.3] - 2018-04-30
### Added
- Audit.NET.Elasticsearch: New Elasticsearch data provider

### Modified
- Audit.NET.AzureDocumentDB: Cosmos DB provider enhancements by _ovidiu [AT] ovidiudiaconescu.com_. Caching azure client and allow passing the connection policy.
- Audit.WebApi: (#124) Making GetRequestBody protected virtual

## [12.0.2] - 2018-04-27
### Modified
- Audit.EntityFramework: Fix #120 exposing internal properties EventEntry.Entry (GetEntry) and EntityFrameworkEvent.DbContext (GetDbContext) on model objects.
- Audit.EntityFramework: Fix #122 allow exlude entities via the audit entity action. Now the AuditEntityAction can be a Func that return a boolean indicating whether to include the entity.


## [12.0.1] - 2018-04-24
### Added
- Audit.Core: Exposing the global JSON serializer settings as a Configuration option to allow changing the serialization behavior for audit events.
 
## [12.0.0] - 2018-04-22
### Added
- Audit.Core: Added a global audit switch off `Configuration.AuditDisabled`.
- Audit.Core: Added `NullDataProvider` as an anternative to disable the audit logging.


## [11.2.0] - 2018-04-11
### Changed
- Audit.NET.MongoDB: Fix #114 - MongoDB Dataprovider Date serialization. Changing serialization mechanism to store the .NET DateTime as mongo datetime.

## [11.1.0] - 2018-04-08
### Added
- Audit.EntityFramework: Added built-in mechanism to Ignore columns and Override column values on the audit logs.

### Changed
- Audit.EntityFramework: (Core) fix PrimaryKeys, ForeignKeys and ColumnValues to log the column name instead of the property name.


## [11.0.8] - 2018-03-25
### Changed
- Audit.EntityFramework - Fix [#106]: DbEntityValidationException causes AuditEntityAction StackOverflowException.

## [11.0.7] - 2018-03-19
### Changed
- Audit.NET.AzureDocumentDB - Fix [#103]: Added FeedOptions argument to DocumentDb QueryEvents.
- Audit.EntityFramework - Fix [#104]: Multiple foreing key using the same field as key, causing audit to fail.

## [11.0.6] - 2018-03-07
### Changed
- Audit.WebApi and Audit.Mvc - Fix [#102]: NULL validation on HttpContext.Connection.RemoteIpAddress 


## [11.0.5] - 2018-02-18
### Changed
- Audit.WebApi. Fix [#99]: Output not including body value when type was Microsoft.AspNetCore.Mvc.JsonResult

## [11.0.4] - 2018-02-14
### Added
- Audit.WebApi: Added GetCurrentAuditScope(this HttpContext httpContext) extension to get the web api audit scope directly from an HttpContext

### Changed
- Audit.NET.Postgres: Fix the insert command for the Postgres provider (#98)

## [11.0.3] - 2018-02-12
### Added
- Added request body for AspNet Core Web API 2 via IncludeRequestBody property.

## [11.0.2] - 2018-02-09
### Added
- Adding NETSTANDARD2.0 support to Audit.NET 

### Changed
- EventLog data provider available on NETCORE 2.0
- EventLog new MessageBuilder property to allow customizing the logged message
- Audit.DynamicProxy: allow setting the creation policy.
- Fixed [#97](https://github.com/thepirat000/Audit.NET/issues/97): WebAPI missing response body when the response was a type inherited from ObjectResult, etc. 

## [11.0.1] - 2018-01-28
### Changed
- Audit.MySql: refactor by _bgrainger [AT] gmail.com_ to use MySqlConnector instead of MySql.Data to support real async calls.

## [11.0.0] - 2018-01-14
### Added
- Async support to the AuditScope and all the data providers.
- Async support for Audit.EntityFramework, Audit.WCF, Audit.WebAPI and Audit.MVC extensions.
- Data retrieval methods for most of the data providers.
- New Custom Action OnEventSaved triggered right after the event is saved.

## [10.0.3] - 2017-12-28
### Changed
- Audit.EntityFramework: bug fixing [#92](https://github.com/thepirat000/Audit.NET/issues/92)

## [10.0.2] - 2017-12-25
### Added
- New Audit.NET.log4net extension to log events with Apache log4net.


