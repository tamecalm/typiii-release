# TYPIII

**Fast-finger game testing userbot for Telegram**

[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS%20%7C%20Android-blue)]()
[![License](https://img.shields.io/badge/license-MIT-green)]()

## What is TYPIII?

TYPIII is a Telegram userbot designed to test anticheat systems in fastest-finger games. It automatically detects game prompts like `🎯 type: rice` and instantly responds with the keyword.

## Downloads

Download the latest release from the [**Releases Page**](../../releases/latest).

| Platform | Architecture | Filename |
|----------|--------------|----------|
| Windows | 64-bit | `typiii-windows-amd64.exe` |
| Windows | 32-bit | `typiii-windows-386.exe` |
| Linux | 64-bit | `typiii-linux-amd64` |
| Linux | 32-bit | `typiii-linux-386` |
| macOS | Intel | `typiii-macos-amd64` |
| macOS | Apple Silicon | `typiii-macos-arm64` |
| Android/Termux | ARM64 | `typiii-android-arm64` |
| Android/Termux | ARM32 | `typiii-android-arm` |

> **Note:** After downloading, Linux/macOS/Android users need to make the file executable with `chmod +x <filename>`

## Quick Start

### 1. Get Telegram API Credentials
- Visit [my.telegram.org](https://my.telegram.org)
- Go to "API Development Tools"
- Create an app to get your `API ID` and `API Hash`

### 2. Download & Run

**Windows:**
```
typiii-windows-amd64.exe
```

**Linux/macOS:**
```bash
chmod +x typiii-linux-amd64
./typiii-linux-amd64
```

**Android (Termux):**
```bash
chmod +x typiii-android-arm64
./typiii-android-arm64
```

### 3. Configure
Enter when prompted:
- API ID
- API Hash  
- Phone number (e.g., `+1234567890`)
- Target chat ID or username (e.g., `@gamechat` or `-1001234567890`)

### 4. Authenticate
- Enter the verification code sent to your Telegram
- Enter 2FA password if enabled
- Session saves automatically for future use

## Features

- ✅ **Instant Detection** - Detects `🎯 type: <word>` patterns instantly
- ✅ **Auto-Reply** - Sends the keyword automatically
- ✅ **Session Persistence** - Login once, run forever
- ✅ **2FA Support** - Works with two-factor authentication
- ✅ **Proxy Support** - SOCKS5, SOCKS4, HTTP proxy with authentication
- ✅ **Custom Patterns** - Define your own regex detection patterns
- ✅ **Plugin System** - Extensible architecture for custom handlers
- ✅ **Interactive TUI** - Real-time status bar with live stats
- ✅ **Statistics** - Track detections, replies, errors, keyword frequency
- ✅ **File Logging** - All events logged to `logs/` folder
- ✅ **Cross-Platform** - Windows, Linux, macOS, Android
- ✅ **No Dependencies** - Single binary, no installation needed
- ✅ **Colored Logs** - Easy to read console output

## How It Works

```
[12:34:56] INFO Logging to: logs/typiii_2024-11-25.log
[12:34:56] INFO Starting Telegram client...
[12:34:57] SUCCESS Session loaded - Already authorized
[12:34:57] INFO Listening for messages in chat: @gamechat

[12:35:10] 🎯 Keyword detected: rice
[12:35:10] ✓ Auto-reply sent: rice

^C
[12:40:00] INFO Session stats: Uptime: 5m 4s | Scanned: 42 | Detected: 3 | Sent: 3 | Errors: 0
[12:40:00] SUCCESS Userbot stopped gracefully
```

## Proxy Configuration

TYPIII supports connecting through a proxy. When prompted during setup:

```
Enable proxy? (y/N): y
Proxy type (socks5/socks4/http) [socks5]: socks5
Proxy host (IP or hostname): 127.0.0.1
Proxy port: 1080
Username (leave empty if none): 
```

**Supported proxy types:**
- **SOCKS5** - Recommended, supports authentication
- **SOCKS4** - Legacy support
- **HTTP** - HTTP CONNECT tunnel

Proxy settings are saved in `session/config.json` for future runs.

## Custom Patterns

You can define custom regex patterns to detect different message formats:

```
Customize detection patterns? (y/N): y

Current patterns:
  1. [enabled] type_emoji: (?i)🎯\s*type\s*:\s*(\S+)
  2. [enabled] type_plain: (?i)^type\s*:\s*(\S+)

Add custom pattern? (y/N): y
Pattern name: my_pattern
Regex pattern (use parentheses for capture group): (?i)answer:\s*(\w+)
Capture group number [1]: 1
✓ Pattern added: my_pattern
```

**Default patterns:**
- `type_emoji` - Matches `🎯 type: word`
- `type_plain` - Matches `type: word`

Patterns are saved in `session/config.json` and can be edited directly.

## Finding Your Chat ID

**Public groups/channels:** Use `@username`

**Private groups:**
1. Forward a message from the group to [@userinfobot](https://t.me/userinfobot)
2. Use the ID shown (e.g., `-1001234567890`)

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Permission denied | Run `chmod +x <filename>` |
| Colors not showing | Run `export TERM=xterm-256color` |
| Session not saving | Check write permissions in current directory |
| Not detecting messages | Verify chat ID and ensure account is in the chat |

## Security

⚠️ **Use a burner Telegram account** - Userbots may trigger Telegram's spam detection.

See [SECURITY.md](SECURITY.md) for security guidelines.

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for version history.

## Roadmap

See [ROADMAP.md](ROADMAP.md) for planned features and development priorities.

## License

MIT License - Use at your own risk.

---

**Disclaimer:** This tool is for educational and testing purposes only. The developers are not responsible for any misuse or account restrictions.
