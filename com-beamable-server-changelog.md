# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## (unreleased)
### Added
- Added the ability to use dependency injection to provide custom services to a Microservice instance. Configure your services with a static method marked with the ConfigureServices attribute that takes one input parameter of type IServiceBuilder.

## [0.13.0]
### Added
- Added a difference check at Microservice Deployment time, so that microservices that have not changed are not reuploaded.
- Added a RealmConfig service to available Services. This can be used to read protected realm settings.

## [0.11.0]
### Changed
- Changed response serialization from Microservice. Use UseLegacySerialization to maintain old behaviour.

### Added
- Added a cache for content fetches. 
- Added Doc Url to package.json.
- Added Open API 3.0 auto-generative documentation.
- Added AdminOnlyCallable version of ClientCallable that requires caller to have full scopes.
- Added requiredScopes field to ClientCallable that requires caller to have required scopes.

### Fixed
- Fixes leaderboard and stat fetching cache errors.
- Fixes null reference bug when passing null to [ClientCallable] arrays.