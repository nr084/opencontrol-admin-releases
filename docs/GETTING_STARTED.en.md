# Getting started

[English](GETTING_STARTED.en.md) · [Русский](GETTING_STARTED.ru.md) · [Home](../README.en.md)

## Install

Download `OpenControlAdmin-0.3.apk` from [the release page](https://github.com/nr084/opencontrol-admin-releases/releases/tag/v0.3). Allow installation from your browser or file manager when Android asks. Use the accompanying SHA-256 file to verify the download if needed.

If you installed the earlier **debug-signed** local preview, uninstall it first: Android does not allow an in-place update with a different signing certificate. Uninstalling removes local profiles and saved credentials. Future releases signed with the same production key can update this signed release.

The `.aab` file is a distribution bundle, not an installable APK. The app is not currently listed on Google Play.

## Add a gateway

On **Обзор** (Overview), tap **Добавить** (Add). Enter a name, management address, administrator username and password. You can paste an address ending in `/admin/`; the app normalizes the API path. HTTPS is required. The default port is 4081.

With an active VPN, an address may be suggested automatically. **Verify it before connecting.** It is derived from available VPN network information and can be wrong with a different VPN or a nonstandard subnet. Direct gateway handoff requires a future OpenControl client update.

Enable **Сохранить пароль** (Save password) only if you want the app to retain it. Tap **Сохранить** (Save) to keep the profile or **Подключить** (Connect) to save and connect.

## Certificate trust

Normal HTTPS connections use system trust. A private certificate may require confirmation: compare the displayed SHA-256 fingerprint with a trusted copy from your administrator. Once confirmed, the app pins that certificate for the profile.

When a pinned certificate changes, connection is blocked. Verify the replacement independently, edit the profile and select **Сбросить доверие сертификату** (Reset certificate trust), then reconnect. Do not reset trust simply to silence an unexpected warning.

Version 0.3 lets you explicitly allow an expired certificate in the trust prompt. The exception is scoped to the profile and exact fingerprint; it does not accept a different certificate. Revoke it in the profile editor. Changing the endpoint or resetting trust clears the exception.

## Navigate

| Russian label | Meaning |
| --- | --- |
| Обзор | Profiles and gateway overview |
| Узлы | Active hosts, user sessions and traffic totals |
| Сеть | Network interfaces |
| Правила | Read-only traffic policy |
| Обновить | Refresh the current snapshot |
| Завершить сессию | Sign out the selected host; confirmation required |
| Выйти | Disconnect the administration session |

## Background checks

Enable **Фоновая проверка** (Background check) in a profile with a saved password, and allow notifications on Android 13+. The app opens a short API session to test login availability. It notifies when status changes or the first check fails, rather than on every successful check.

Android uses a periodic interval of about 15 minutes but can delay checks in Doze or under battery restrictions. A VPN-only gateway still needs a working VPN. Force-stopping the app disables jobs until it is opened again. No CPU, bandwidth threshold or tunnel-specific monitoring is included in 0.1.0.

## Troubleshooting

- **Cannot connect:** verify VPN, management address, port and network access to the firewall.
- **Access denied:** check the account's administration rights. Different sections may require different permissions.
- **Session expired:** reconnect from Overview.
- **No background notifications:** check the profile toggle, saved password and Android notification permission. Delivery timing is controlled by Android.
- **Screenshot is blank:** production builds protect the window from screen capture. Repository screenshots are captured by a test runner in an isolated emulator using synthetic data.

The developer does not supply corporate server access or accounts. Keep support reports free of credentials and internal network data.


