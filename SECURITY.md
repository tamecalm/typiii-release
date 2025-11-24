# Security Policy

## Overview

TYPIII is a Telegram userbot that requires access to your Telegram account. This document outlines security considerations and best practices.

## ⚠️ Important Warnings

### Use a Burner Account
**Always use a secondary/burner Telegram account for testing.**

Reasons:
- Telegram may flag automated behavior as spam
- Your account could be temporarily or permanently restricted
- Userbots violate Telegram's Terms of Service

### Credential Safety
- **Never share your API ID and API Hash**
- **Never share your session files**
- **Never commit credentials to version control**

## How Your Data is Handled

### What TYPIII Stores Locally

| Data | Location | Purpose |
|------|----------|---------|
| Session data | `./session/session.json` | Maintains login state |
| API credentials | Runtime only | Authentication with Telegram |

### What TYPIII Does NOT Do
- ❌ Does not transmit your credentials to any third party
- ❌ Does not store your password
- ❌ Does not log message content (only keywords)
- ❌ Does not have any analytics or telemetry
- ❌ Does not connect to any server other than Telegram

## Session File Security

The `session.json` file contains your authenticated session. **Treat it like a password.**

### Protecting Your Session
```bash
# Set restrictive permissions (Linux/macOS)
chmod 600 ./session/session.json
chmod 700 ./session/
```

### If Your Session is Compromised
1. Immediately terminate all sessions in Telegram:
   - Settings → Devices → Terminate All Other Sessions
2. Delete the `./session/` folder
3. Change your Telegram password
4. Re-authenticate with TYPIII

## API Credentials

### Obtaining Credentials Safely
1. Only get credentials from [my.telegram.org](https://my.telegram.org)
2. Never use credentials from third-party sources
3. Each app should have its own API credentials

### Credential Rotation
If you suspect your API credentials are compromised:
1. Go to [my.telegram.org](https://my.telegram.org)
2. Delete the compromised app
3. Create a new app with fresh credentials

## Network Security

### What Connections TYPIII Makes
- Connects only to Telegram's MTProto servers
- Uses Telegram's standard encryption
- No proxy or VPN required (but supported by Telegram)

### Firewall Considerations
TYPIII needs outbound access to:
- `*.telegram.org` (ports 80, 443, 5222)
- Telegram DC IP ranges

## Binary Verification

### Verifying Downloads
Always download from the official repository. Compare checksums if provided.

```bash
# Linux/macOS - Generate SHA256
sha256sum typiii-linux-amd64

# Windows (PowerShell)
Get-FileHash typiii-windows-amd64.exe -Algorithm SHA256
```

## Responsible Use

### Do
- ✅ Use for testing your own anticheat systems
- ✅ Use with accounts you own
- ✅ Respect rate limits
- ✅ Stop if you receive warnings from Telegram

### Don't
- ❌ Use to spam or harass
- ❌ Use in chats without permission
- ❌ Use to gain unfair advantages in real games
- ❌ Distribute modified versions with malware

## Reporting Security Issues

If you discover a security vulnerability:

1. **Do not** open a public issue
2. Contact the maintainer privately
3. Provide detailed reproduction steps
4. Allow reasonable time for a fix before disclosure

## Disclaimer

This software is provided "as is" without warranty. Users are responsible for:
- Compliance with Telegram's Terms of Service
- Any consequences of using this software
- Securing their own credentials and sessions

---

**Remember:** Security is a shared responsibility. Use TYPIII responsibly and protect your credentials.
