
# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [unreleased]
### Added
- Verbose logging capability available in Project Settings
- Exposed cohort requirements for listing content

### Fixed
- Logging back into the Toolbox will remember your Realm selection per game

## [0.14.2]
- no changes

## [0.14.1]
### Fixed
- Facebook SDK won't be referenced unless the Facebook setting is checked in the Account Management Configuration

## [0.14.0] 
### Fixed
- Integration for Unity In-App-Purchasing 3.x.x packages
- Content references will update after a manifest subscription update

### Changed
- Rearranged the Portal button and Account button in Toolbox
- Rearranged the Content Count label in Content Manager
- Password reset codes can use PINs instead of UUIDs

### Added
- WebGL build support
- Multiple content namespaces, both in Editor and Runtime. Must enable in Project Settings
- Facebook Limited Login (iOS) Authentication
- `"portal"` console command, which opens portal to the current player's admin page
- Multi-object editing support for Content Reference selector
- New editor tooling for ISO date strings in Content Objects
- Realm Picker in the top right of Content Manager
- Last publish date in bottom-right of Content Manager
- ISerializationCallbackReceiver support for Content Object serialization
- Async support for `Promise<T>` types
- Added Donate api call method to GroupApi


## [0.13.3]
### Fixed:
- Matchmaking state transition bug 
- Increases heartbeat rate for MatchMaking
  

## [0.13.2]
### Fixed:
- Fixed isHttpError obsolete errors
- Removed use of Social.localUser.id from GameCenter Authentication

### Added:
- Support for GameCenter Authentication on iOS 13.5+


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


## [0.12.0]
(this release was skipped)


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