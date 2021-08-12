# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.13.2]
### Added:
- GameCenter authentication support to iOS 13.5+ using teamPlayerId

### Fixed:
- GameCenter authentication no longer uses Social.localuser.id to properly generate Authentication Token for various 2019.4+ releases
- isHttpError replaced with Result.ProtocolError


## [0.13.1]
### Fixed:
- GameCenter SDK errors with non-iOS il2cpp builds

## [0.13.0]
### Fixed:
* Fixed possible null reference exception in MustReferenceContent validation attribute

### Added
* GameCenter sdk Authentication Support
* Adds an optional field, activeListingLimit to Store Content

### Changed
* Switched MatchmakingService API to point to our new backend matchmaking service.

## [0.11.0]
### Changed
- Console Configurations ToggleKey will be reset to BackQuote.

### Fixed
- Fixed Promise multithread safety.
- Fixed ContentRef property drawer showing invalid references when deleted.
- Fixed MustReferenceContent validation  for lists of Content References.

### Added
- Support for the new Unity Input Manager System.
- Added OnUserLoggingOut event available from API. The event fires before a user switches account.
- Doc Url to package.json.
- Event phase validation. Events can no longer have zero phases. This may lead to disappearing Event Phases if your Beamable version is mismatched.
- Switched MatchmakingService API to point to our new backend matchmaking service.
