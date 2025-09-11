# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- Error handling improvements
- Better logging for failed requests

### Changed
- Load environment variables from correct path
- Optimize process.env lookups to only occur once
- Filter effectiveInsert and effectiveDelete operations
- Optimize filtering performance
- Ensure unique indexes are set on services

### Fixed
- Only send changesets when there are changes left after filtering
- Add option to send only matches to receiving services

## [0.4.0] - Current Release

### Initial release features
- Delta notification system for mu.semte.ch microservices
- Configurable rules and normalization
- Bundle request handling
- Request folding and matching capabilities