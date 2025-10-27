# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.5.0] - 2025-10-14

### Added
- New Scheduler UI
- New log explorer page for services built with version 6.0 and above
- New Getting Started page
- Add validation for empty message field (editor) when creating a Campaign

### Changed
- Request scope header is 'X-BEAM-SCOPE' instead of 'X-DE-SCOPE' 
- Improved Analytics page usability

### Fixed
- Bug Analytics if one of the queries fails with a 500 error, all of the graphs get cleared
- Fixed a bug where the current realm’s environment was accessed before it finished loading: Cannot read properties of null (reading 'environment')
- Cannot Archive Realm: Error Claims Microservices Running When None Are Active
- Admin unable to remove federated associations from account
- An issue with the Events Calendar where an event that lasts approximately 24 hours appears to span two days on the calendar
- Error getting event from url query in analytics page
- JSON Parsing Errors in In-App Purchase History View
- Refactor KPI query so that it handles missing views
- PreviewChanges problem while items has null values
- Admin role functionality is suppressed when user is admin in scoped roles but tester globally


## [1.4.0] - 2024-12-04

### Fixed
- Resolved an issue where the login dialog would not submit upon pressing Enter.
- Corrected an error on the Analytics page of the Demo project.
- Fixed the "Load More Data" button in microservice logs to properly append new results to existing ones.
- Addressed premature truncation of JSON data in Analytics fields.
- Fixed a UI bug on the Microservice Docs page.
- Corrected cloud saving dates that displayed erroneously as years above 2600.
- Resolved an issue where the Microservices RAM graph disappeared when hovered over with a large dataset.
- Fixed mismatched timezones between microservice log filtering and the logs themselves.
- Resolved rendering issues in the Game Tree on Safari for macOS.
- Fixed overlapping text on the realm graphic in the realm section.
- Ensured the "Actions" menu in the player inventory items always displays all options.
- Clarified that X-DE-TIMEOUT headers are specified in milliseconds rather than seconds.
- Addressed intermittent issues causing logs for C#MS to stop appearing.

### Added
- Introduced a changelog tracker with a modal popup for developers upon first login to a new version.
- Updated the Realm Tree to display the user's role on each realm card.
- Added safeguards to prevent accidental shutdowns of production microservices.
- Enhanced Player Inventory to support operations on multiple items and currencies simultaneously.
- Adjusted API calls to Content Manifest and Inventory to use a longer x-beam-timeout duration.
- Added visualization for the federation "components" field in the Microservice section manifest.
- Specified X-BEAM-TIMEOUT as 60000 for calls to the realms/customer API to prevent timeouts.
- Enabled a feature to stop and archive all C#MS instances in a realm.
- Improved the local Swagger page to detect if a service is running before attempting a health check.

## [1.3.0] - 2024-06-28

### Changed

- Added role icon on realm card from realm tree.

### Added

- Added dummy data for `Performance & Metrics` in Microservices page from Demo projects.
- Login dialog should submit when you hit Enter

### Fixed

- Logs for C#MS sometimes stop appearing

## [1.2.0] - 2023-05-06

### Changed

- Message Campaigns In-Game Mail campaigns support specifying an optional Category (similar to channel in Announcements).
- Retention table now distinguishes between 0% retention and unavailable data.
- Retention table default date range window now only shows full days and no longer suffers from off by one.
- Message Campaigns for Announcements now properly handle legacy Entitlement Attachments.
- Player Events page will always show rewards.
- Players > Events page now renders the event id as a link which takes you to the corresponding event details page.
- Players > Events page now shows the leaderboard Id that a player has been assigned to (if available) and renders it as a link.
- Events now support changing Event Rewards for currently running events (as well as upcoming events).

### Added

- `Promote Realm` with the production realm as the source is now possible (with a warning displayed).
- Microservices now show “status” when they are deploying.
- Portal users can now disable/enable Microservices and Storage Objects Operate > Microservices section.
- Operations performed by Portal users are now logged in analytics and viewable from Realm > Analytics as a new table called client_portal_audit.
- New `Download Logs` button will export view of logs into a flat file you can download.
- New api & microservice usage graphs segmented by realms and services now available in under Account > API Usage.
- Player Profile will now show external, custom authentication schemes (such as web3 wallet association) under Player Associations alongside social login.

### Fixed

- Clearing an entire leaderboard will no longer result in a 404 Error.
- Removing player from leaderboard in Players > Leaderboards page no longer results in a malformed and failed request.
- Players > Leaderboards section will load dramatically faster for customers with large numbers of leaderboards.
- Fixed missing Microservices Deployment Status.
- Fixed incorrect visualization for Player geolocation.

## [1.1.0] - 2024-01-23

### Fixed

- Player calendar activity appeared one day too early
- Downloading Content from the Portal did not always download the correct data
- Event Calendar view white text on yellow bar background was hard to read
- Player Inventory items with lots used to overflow, now feature a scrollbar
- Player Inventory view sort by items had no effect
- Analytics data query resulted in error when event name contains a hyphen
- Game Tree > Config Defaults context menu was incorrectly placing the customer alias in the cid field
- Downloading analytics data would not always work
- Player Profile Location badges would duplicate when switching pages
- In-Game Mail: sometimes currency list only showed coins and gems even when custom currencies exist
- Rendering of act_time timestamp value in Portal Analytics view was incorrect
- Clicking on the realm id in the game tree didn't take you to realm section
- Promoting Microservices or Redeploying them in the portal could cause loss of data in the manifest (e.g. federated components)

### Added

- Added showing realm alias (if available) API usage dashboard
- Added support for manual entry of date times (without needing date picker)
- Added date-range presets for convenience in specifying date range (e.g. "last 30 days")
- Added support for hiding archived C# Microservices
- Added additional configuration options to Leaderboard creation
- Added server pagination support to Leaderboards
- Added support for re-ordering items in Commerce Catalog

### Changed

- Better error message when supplying an invalid CID at login
- Better JSON Visualization and Editing
- Better visual language for disabled or archived C#MS (gray rather than red)
- Faster loading of analytics dashboard
- Faster history service querying in analytics and other sections
- Archived realms show PID
- MongoDB health metrics request uses "Zulu" timestamps
- Admin navbar section is now expanded by default
- API usage dashboard omits non-billable calls
- No longer possible to archive a realm if you have microservices running in the realm

## [1.0.0] - 2022-12-16

### Changed

- New Demo Project with fully stubbed out data which developers can explore to get a richer sense of capabilities
- New Realm > Analytics allows developers to query analytics events in a player-agnostic way, similar to Player > Analytics section
- New section in Events details page shows Cohort Settings
- New Realm secret field is viewable in the realm tree context menu for sufficiently privileged users
- New “Location” field in Player Profile shows badges indicating the continent, country, state, and whether the country is in the European union if available (also available as player stats)
- Content UI groups private and public content in a single row, with option to view public/private data in the actions menu
- Player Inventory table is sortable by updated-at timestamp
- Trials support specifying stats from other domains and visibilities (not just game.private)
- Diffing of Content in the Portal shows Tags differences
- Removed IP address field from Player profile, which is no longer stored.

### Fixed

- Dashboard: Percent paying number was wrongly calculated
- Dashboard: Revenue table no longer shows oldest date with no data (off by one)
- Dashboard: Fixes and improvements to retention chart
- `Add Entitlement` no longer throws “Unexpected end of JSON input” error on Save.
- `Send Notification` button was absent in “Notify All Players” page even if you are an Admin.
- Create event dialog no longer shows unselected months as “Undefined”
- Realm selection dropdown scrolls properly even when the list is very long
- Real Money Transactions: Items and Currencies are rendered consistently throughout the portal
- Event cloning does not properly clone rewards which are based off of Entitlements

## [0.9.0] - 2022-10-08

### Changed

- Clear and Delete leaderboard actions have been removed from the overview action menu, and are only available when looking at the leaderboard view itself
- Default action when clicking a parent leaderboard is now to expand the row to avoid confusion
- Replaced leaderboard badge colors by monochromatic text-button
- Leaderboard Partitions are now sorted numerically in ascending order
- Realms > Leaderboard now support editing player scores in place
- Event Instance ID is now visible, badged, and copy-pasteable on the Event Details page
- Events creation and details page now supports Group Score Rewards

- Middle click enabled to popup links in new windows
- Message Campaigns: Announcement thumbnail supports selecting an image from the image browser
- Added ability to force redeploy C#MS of any current or previous deployment
- Sidebar expand is now an arrow instead of a dot, and sidebar should be expanded by default

### Fixed

- Message Campaigns: When cloning a campaign, the "sent" field is now properly reset instead of cloned

## [0.8.0] - 2022-09-26

### Changed

- Player > Leaderboards visualization is now visually consistent with Realms > Leaderboards
- Player > Leaderboards action menu allows the removing of a player from leaderboard
- Leaderboard Player IDs are now clickable and copyable, like they are elsewhere in the portal
- Leaderboards table now nests child partitions logically
- Other improvements to the Leaderboard Creation wizard
- Adding or Editing a Leaderboard Entry now offers the option to add entry stats

## [0.7.0] 2022-09-15

### Changed

- Cosmetic & Copy fixes to Players > Leaderboards
- Create timer validation now let's you pass once it triggers
- Player entries can now be removed from the leaderboard

### Fixed

- Leaderboard View is now properly URI-encoding the # symbol in the leaderboard id
- Message Campaign unsupported translations error now prints the whole language name and not just the code
- Message Campaign UI lag fixed for when there are many language settings

## [0.6.0] - 2022-09-08

### Changed

- Trials: It is now more visually obvious how to add “OR” and “AND” conditionals
- Message Campaign table row shows “English (Default)” badge alongside the other languages
- Content Rollback is now possible via the Portal
- Messaging editor supports adding a picture via paste command
- Write access and visibility parameters added to player search by stat.

### Fixed

- You can now Edit User Permissions of newly added users
- Message Campaigns: Fixed how Button Editing Tooltip disappears too quickly
- Join Now link on invites for new game developers/admins added to an account is now fixed
- Punctuation in studio names is now blocked during registration form validation

## [0.5.0] - 2022-08-16

### Changed

- Message Campaign Provide Link feature shows asset details prior to insertion
- Message Campaign upload image supports user-defined tags
- Message Campaigns now have support for auto-translating from the default language to the target languages
- Message campaigns now have an image library you can upload images into that are auto added to a CDN
- You can browse a library of previously uploaded images and insert them into your message campaign

### Fixed

- In-Game Mail campaigns now populate mb_store field with SYSTEM.DB as the default value
- Message Campaign links (buttons and images) which contain special characters now correctly convert to html

## [0.4.0] - 2022-08-02

### Changed

- Message Campaigns can customize button color
- Multilanguage support added for all types of campaigns

### Fixed

- Message Campaign table rows now show the correct localization data in all cases
- Updating a Message Campaign with a new localization language displays correctly
- Individual Event view no longer hangs after clicking to see detail when item rewards are missing properties
- Message Campaign Announcements containing dots in the symbol no longer cause localization settings to be lost and other errors
- Message Campaign announcements which are sourced from Content now properly grey out the `Eject` action menu

## [0.3.0] - 2022-07-21

### Changed

- Message Campaign Text Color is now consistently saved in hexadecimal format
- Message Campaign WYSIWYG button icon has been changed to be more obvious
- Redirect from old route /register to the new route /signup/registration
- Portal player language preference icon should be sourced from account data rather than stat
- Events supports creating and visualizing recurring event schedules
- Timers page now support a visual editor, similar to what we do in the new Message Campaigns and in Unity

### Fixed

- Bug Fix for inserting images in localized text
- Bug Fix for Editing Announcements that were created prior to adding localization support
- Bug Fix for correctly copying and pasting WYSIWYG content (preserving correct html)

### Added

- Add support to announcements for a thumbnail (added to clientData)

## [0.2.0] - 2022-07-14

### Changed

- It is now possible to diff manifests and specific content objects via the Promote dialog in the portal
- Leaderboard creation via the portal now properly handles freeze time
- Player inventory rendering and editing is more intuitive
- Time rendering is now universally rendering as UTC instead of a mix of local time and utc
- Time rendering will attempt to show local time on over tooltip
- Events Live Ops Calendar will now render recurring events as well
- Message Campaign localization settings now get restored when editing a campaign
- Message Campaign localization configurations (i.e. other languages) now show up in pre-publish summary
- Message Campaign localization text now shows up in message campaign table summary
- Content Diff icon now appears next to manifest even when the promote button is toggled off
- Content Diff UI is no longer missing tags comparison
- Content Diff UI should now allow showing and downloading the content of deleted and added objects
- Content Diff now put the "identical" string in a badge, like it does for "Changed" and "Added"

### Fixed

- Fix for Events Calendar rendering error (date parsing exception)

### Added

- Support for localized text
- Support for buttons in the body of announcements and in-game mail (which renders correctly in TextMeshPro)
- Support for multiple images in the body of announcements and in-game mail (which renders correctly in TextMeshPro)
- Support for optional thumbnail image for in-game mail and announcements
- Bug fixes for rich text and bread crumbs
- Support for enabling & disabling microservices directly via the portal

## [0.1.0] - 2022-06-09

### Changed

- Messaging improvement: Announcements can be edited after they are created.
- Navigate directly to Realm from clicking on the Realm card, clicking the three dots opens the realm menu.
- Player Profile realm badges show the human readable realm name.
- Removed SDK version from Getting Started.
- In events you can now see item properties on hover.
- Removed the ability for users to navigate into archived realms.

### Fixed

- Errors when adding a new listing to store in commerce page
- Fixes to how html is rendered in the messaging preview
- Html pasted into the editor will be preserved