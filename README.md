# Passwords for Windows

A single-file, offline password manager inspired by the macOS Passwords app. Runs in any modern browser (Edge, Chrome) — no install, no server, no account.

- **Encryption:** PBKDF2-SHA256 (600,000 iterations) -> AES-256-GCM using the browser's Web Crypto. The vault never leaves your device.
- **Sections:** All, Codes (TOTP 2FA), Wi-Fi, Security (reused / weak / optional leak check), Recently Deleted.
- **Backup & transfer:** encrypted backup files, CSV import/export (Apple and Chrome formats).
- **Not included:** passkeys, family sharing, cross-device sync.

Your vault is stored in the browser's local storage for the site's origin. **Save encrypted backups regularly** (Settings -> Save encrypted backup); clearing site data deletes the vault.

The optional leak check sends only the first 5 characters of a SHA-1 hash of each password to `api.pwnedpasswords.com` (k-anonymity).

## Windows Wi-Fi passwords
A web page cannot read them. Run `tools/Export-WiFi-Passwords.ps1` as administrator, then import the CSV (Settings -> Import CSV) and delete it.

## Deploy
Static site: `index.html` is the whole app. `vercel.json` adds security headers.
