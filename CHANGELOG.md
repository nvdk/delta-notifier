# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.2.0] (2026-10-26)
### Changed
- Upgrade base image to `nvdk/mu-javascript-template:2.0.0-beta.3`:
  - runs on Node.js 24 on a slim base image
  - runs as an arbitrary non-root user (e.g. OpenShift)
  - `/config` may be mounted read-only (e.g. a Kubernetes ConfigMap); overrides are applied in `$TMPDIR` (default `/tmp`) at startup, so with a read-only root filesystem a writable volume must be mounted on `/tmp`
- Merge upstream mu-semtech/delta-notifier 0.4.1

### Fixed
- Rules with different regex values for the same match key were grouped together, so only the first regex was evaluated and matches were sent to all of those rules
- Rules without `options` no longer crash on incoming deltas
- Default maildelivery rule uses `callback.url` instead of `callback.uri`

## [1.1.0] (2026-02-12)
### Added
- Prometheus metrics endpoint (`/metrics`) exposing delta throughput, notification rates, latency histograms, and pending bundle counts
- Support for regex values in match specifications (e.g. match on patterns instead of exact URIs)
- Graceful shutdown handler via `beforeExit`

### Changed
- Upgrade mu-javascript-template base image to 1.9.1
- Use mu errorHandler for consistent error responses

## [1.0.0] (2025-12-02)
### Added
- Error handling improvements
- Better logging for failed requests
- Add option to send only matches to receiving services

### Changed
- Load environment variables from correct path
- Optimize process.env lookups to only occur once
- Filter effectiveInsert and effectiveDelete operations
- Optimize filtering performance
- Ensure unique indexes are set on services

### Fixed
- Only send changesets when there are changes left after filtering

## [0.4.0] (2024-05-22)

### Initial release features
- Delta notification system for mu.semte.ch microservices
- Configurable rules and normalization
- Bundle request handling
- Request folding and matching capabilities

