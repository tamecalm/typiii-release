# Changelog

All notable changes to TYPIII will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.3.0] - 2024-11-25

### Added
- **Custom Regex Patterns**: Define your own detection patterns
- Multiple patterns support (match any pattern)
- Pattern enable/disable toggle
- Configurable capture groups
- Patterns saved to config file

### Changed
- Handler now uses pattern.Config instead of hardcoded regex

---

## [1.2.0] - 2024-11-25

### Added
- **Statistics Tracking**: Track messages scanned, keywords detected, replies sent, errors
- **File Logging**: All events logged to `logs/typiii_YYYY-MM-DD.log`
- **Stats Export**: Session stats saved to `logs/stats.json` on exit
- Keyword frequency tracking (top keywords)
- Session uptime tracking

### Changed
- Stats summary displayed on graceful shutdown

---

## [1.1.0] - 2024-11-25

### Added
- **Proxy Support**: SOCKS5, SOCKS4, and HTTP CONNECT proxy support
- Proxy configuration saved to config file
- Optional proxy authentication (username/password)

### Changed
- Configuration now prompts for proxy settings

---

## [1.0.0] - 2024-11-24

### Added
- Initial release of TYPIII userbot
- MTProto-based Telegram client using gotd/td library
- Automatic detection of game prompts (`🎯 type: <keyword>`)
- Instant auto-reply with detected keyword
- Session persistence in `./session/` folder
- Phone number authentication with verification code
- Two-factor authentication (2FA) support
- Colored console logging with timestamps
- Cross-platform support:
  - Windows (amd64)
  - Linux (amd64)
  - macOS (arm64)
  - Android/Termux (arm64, arm)
- Flexible pattern matching:
  - Case-insensitive detection
  - Handles extra spaces (`Type :  rice`)
  - Works with or without emoji (`type: rice` or `🎯 type: rice`)
- Support for multiple chat ID formats:
  - Username (`@chatname`)
  - Numeric ID (`-1001234567890`)
  - Raw channel ID
- Automatic access hash caching for channels
- Graceful shutdown with Ctrl+C

### Security
- Session files stored locally (not transmitted)
- No hardcoded credentials
- API credentials entered at runtime

---

## Version History Summary

| Version | Date | Description |
|---------|------|-------------|
| 1.3.0 | 2024-11-25 | Custom regex pattern support |
| 1.2.0 | 2024-11-25 | Statistics tracking and file logging |
| 1.1.0 | 2024-11-25 | Proxy support (SOCKS5/SOCKS4/HTTP) |
| 1.0.0 | 2024-11-24 | Initial release |

---

## Upcoming Features (Planned)

- [x] ~~Proxy support~~ (Added in v1.1.0)
- [x] ~~Statistics and logging to file~~ (Added in v1.2.0)
- [x] ~~Regex pattern customization~~ (Added in v1.3.0)
- [ ] Multiple chat monitoring
- [ ] Custom response delay

---

## Reporting Issues

Found a bug? Please open an issue with:
1. Your platform (Windows/Linux/macOS/Android)
2. Steps to reproduce
3. Expected vs actual behavior
4. Console output (if applicable)
