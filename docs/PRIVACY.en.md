# Privacy — OpenControl Admin 0.1.0

[Русский](PRIVACY.ru.md) · Updated 14 October 2026

The app communicates directly with the Kerio Control management endpoint you configure. Your administrator username and password are sent to that endpoint over HTTPS to establish an API session. The app uses its session cookie and CSRF token for subsequent requests.

Profiles, usernames and optional saved passwords are encrypted locally with an Android Keystore key. Backup and device transfer are disabled for this data. Session credentials are held in memory. Removing a profile removes its saved password and monitoring state. Uninstalling the app removes its local storage.

The app reads gateway configuration and operational data such as host addresses, user names, interfaces and traffic rules. These are displayed on the device. This version includes no analytics SDK, advertising or developer-operated telemetry endpoint. Background checks connect to the configured gateways; notifications can show a profile name and availability status on the lock screen, depending on Android settings.

VPN address discovery reads available Android network information and may query the optional OpenControl gateway provider. It does not request the VPN user's password.

GitHub hosts this repository, releases and public issue reports under GitHub's own privacy terms. The app does not automatically submit reports. Do not include passwords, tokens, private certificates, internal IP addresses or personal information in public issues.

This document describes the app's current behavior. It is not a statement about your firewall administrator's logging or data retention policies.
