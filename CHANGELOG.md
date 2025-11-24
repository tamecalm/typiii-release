# Changelog

All notable changes to TYPIII will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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
| 1.0.0 | 2024-11-24 | Initial release |

---

## Upcoming Features (Planned)

- [ ] Configuration file support (config.json)
- [ ] Multiple chat monitoring
- [ ] Custom response delay
- [ ] Regex pattern customization
- [ ] Statistics and logging to file
- [ ] Proxy support

---

## Reporting Issues

Found a bug? Please open an issue with:
1. Your platform (Windows/Linux/macOS/Android)
2. Steps to reproduce
3. Expected vs actual behavior
4. Console output (if applicable)
