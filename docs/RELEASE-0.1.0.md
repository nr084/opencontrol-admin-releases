# OpenControl Admin 0.1.0 — early preview

## English

The first public Android preview for administering an existing Kerio Control gateway.

- Multiple gateway profiles with optional encrypted password storage.
- Editable VPN gateway address suggestion.
- Overview, active hosts, network interfaces and read-only traffic rules.
- Sign out one selected host after confirmation.
- Optional background API availability checks and change notifications.
- OpenControl light and dark themes, private certificate fingerprint confirmation.

**Install `OpenControlAdmin-0.1.0.apk`.** The `.aab` asset is intended for distribution tooling. Android 8.0+; current app interface: Russian. Documentation: English and Russian.

If upgrading from the earlier local debug preview, uninstall that preview first because its signing certificate differs. Uninstalling removes its local profiles and credentials.

This is an early preview, not a Google Play release. Traffic-policy editing, direct gateway handoff from the VPN client, continuous metric monitoring and iOS are not available yet. Android controls the timing of background checks.

Validation: optimized APK/AAB builds, unit checks and release lint; real UI screenshots using an isolated Android 15 emulator and synthetic API data. Live API read-only verification was also performed during initial development. Physical-device, OEM background scheduling and destructive-action testing remain pending.

Signing certificate SHA-256:
```text
ee066519d1baea2b1949216f03ed444b4e4d448d288a0ab5d1c3bbfa6d50e144
```

## Русский

Первая публичная Android-версия для администрирования существующего шлюза Kerio Control.

- Несколько профилей с необязательным шифрованным сохранением пароля.
- Редактируемая подсказка адреса VPN-шлюза.
- Обзор, активные узлы, интерфейсы и просмотр правил трафика.
- Завершение сессии одного узла с подтверждением.
- Необязательная фоновая проверка API и уведомления об изменении состояния.
- Светлая и тёмная темы OpenControl, подтверждение отпечатка частного сертификата.

**Устанавливайте `OpenControlAdmin-0.1.0.apk`.** Файл `.aab` предназначен для инструментов распространения. Android 8.0+; текущий интерфейс — русский. Документация — EN/RU.

При переходе с локальной debug-версии сначала удалите её: сертификат подписи отличается. Удаление стирает её локальные профили и сохранённые пароли.

Это предварительная версия, не публикация в Google Play. Редактирование политики, прямая передача шлюза из VPN-клиента, непрерывный мониторинг метрик и iOS пока недоступны. Периодичностью фоновых проверок управляет Android.

Проверены оптимизированные APK/AAB, модульные проверки и release lint; реальные экраны сняты в изолированном эмуляторе Android 15 с вымышленными данными API. На этапе разработки также проверено чтение API частного сервера. Проверки физических устройств, фоновых ограничений производителей и действий, завершающих реальные пользовательские сессии, ещё предстоят.

SHA-256 сертификата подписи приведён выше. Контрольные суммы файлов находятся в `SHA256SUMS.txt`.
