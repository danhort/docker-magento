# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.8.0] - 2021-05-27
### Added
- Ioncube to PHP 4
### Fixed
- Added sed command to replace utf8mb4_0900_ai_ci to prevent errors in db import

## [0.7.1] - 2021-04-19
### Added
- Fixed symlinking external vendor module

## [0.7.0] - 2021-04-19
### Added
- Added external composer extensions volume + symlink command

## [0.6.0] - 2021-04-07
### Added
- Git to PHP 7.4
### Changed
- Update composer to v2 in PHP 7.4

## [0.5.8] - 2021-03-12
### Changed
- Replace zcat with gunzip for macOS compatibility
- Update db-import command to recreate database table
### Fixed
- Change user in db-dump command

## [0.5.7] - 2021-01-14
### Fixed
- Fix composer removal error

## [0.5.6] - 2021-01-13
### Fixed
- Makefile missing space

## [0.5.5] - 2021-01-10
### Changed
- Changed master references to main in readme

## [0.5.4] - 2021-01-10
### Fixed
- Downgrade composer to version 1 (Magento does not support composer 2)

## [0.5.3] - 2020-12-18
### Fixed
- Makefile db import and export bug

## [0.5.2] - 2020-11-10
### Added
- patch library ro PHP7.4 

## [0.5.1] - 2020-11-10
### Fixed
- Makefile conflict error

## [0.5.0] - 2020-10-30
### Added
- Varnish
- Ioncube to PHP 7.3 container
- Add base_static_url and base_media_url and elastic host to env.php sample
- Add fastcgi_buffer_size to nginx
- Added PHP 7.4
### Changed
- Updated elasticsearch to 7.6
### Removed
- Remove unused bin script

## [0.4.0] - 2020-05-19
### Added
- npm to PHP 7.0, 7.1, 7.2 and 7.3
- npm and grunt commands to makefile

## [0.3.0] - 2020-05-18
### Fixed
- Swapped clear-assets src path with env path
### Changed
- Removed www from env sample default urls
### Added
- config file update method to update bin script

## [0.2.0] - 2020-05-06
### Added
- PHP7.3

## [0.1.0] - 2020-04-29
### Changed
- The update command now checks for the latest tag
- The magento-docker bash tool now initiates the latest tag

## [0.0.1] - 2020-04-29
### Added
- This CHANGELOG file to hopefully serve as an evolving example of a
  standardized open source project CHANGELOG.

[Unreleased]: https://github.com/danhort/docker-magento/compare/0.8.0...HEAD
[0.8.0]: https://github.com/danhort/docker-magento/compare/0.7.1...0.8.0
[0.7.1]: https://github.com/danhort/docker-magento/compare/0.7.0...0.7.1
[0.7.0]: https://github.com/danhort/docker-magento/compare/0.6.0...0.7.0
[0.6.0]: https://github.com/danhort/docker-magento/compare/0.5.8...0.6.0
[0.5.8]: https://github.com/danhort/docker-magento/compare/0.5.7...0.5.8
[0.5.7]: https://github.com/danhort/docker-magento/compare/0.5.6...0.5.7
[0.5.6]: https://github.com/danhort/docker-magento/compare/0.5.5...0.5.6
[0.5.5]: https://github.com/danhort/docker-magento/compare/0.5.4...0.5.5
[0.5.4]: https://github.com/danhort/docker-magento/compare/0.5.3...0.5.4
[0.5.3]: https://github.com/danhort/docker-magento/compare/0.5.2...0.5.3
[0.5.2]: https://github.com/danhort/docker-magento/compare/0.5.1...0.5.2
[0.5.1]: https://github.com/danhort/docker-magento/compare/0.5.0...0.5.1
[0.5.0]: https://github.com/danhort/docker-magento/compare/0.4.0...0.5.0
[0.4.0]: https://github.com/danhort/docker-magento/compare/0.3.0...0.4.0
[0.3.0]: https://github.com/danhort/docker-magento/compare/0.2.0...0.3.0
[0.2.0]: https://github.com/danhort/docker-magento/compare/0.1.0...0.2.0
[0.1.0]: https://github.com/danhort/docker-magento/compare/0.0.1...0.1.0
[0.0.1]: https://github.com/danhort/docker-magento/releases/tag/0.0.1
