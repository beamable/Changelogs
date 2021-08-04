# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## (Unreleased)
### Fixed
- Fixes Beamable integration for the latest Unity In-App-Purchasing 3.x.x packages

### Added
- Add Content Manifest publish date to Content Manager window
- New console command which opens web portal to the player page of the current player 
- Support for Content multi object editing in the Inspector view
- New editor tooling for selecting date strings
- GameCenter Authentication Support
- Add RealmPicker component to Content Manager V2
- Add "publish under new manifest" button and manifest dropdown in Content Manager
- Adds an optional field, activeListingLimit to Store Content
- Facebook Limited Login support on iOS 
- Added support for multiple content manifests

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