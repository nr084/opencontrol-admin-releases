# OpenControl Admin 0.2

## Русский

Исправлены два случая, о которых сообщили пользователи:

- **Просроченный сертификат.** При подключении приложение показывает срок окончания и SHA-256. Можно явно разрешить просроченный сертификат: исключение сохраняется только для конкретного отпечатка в выбранном профиле и применяется также к фоновым проверкам. Другой сертификат и сертификат, срок действия которого ещё не наступил, по-прежнему отклоняются. Исключение можно отключить в редакторе профиля; сброс доверия или смена адреса его удаляют.
- **Названия служб в правилах.** Вместо `RuleSelectedEntities` отображаются выбранные службы, включая Ipsec services, Kerio Vpn и OpenVPN services. Исправлено чтение массива `service.entries` из Kerio API.

Устанавливайте **OpenControlAdmin-0.2.apk** поверх подписанной версии 0.1.0: ключ подписи прежний, профили сохраняются. AAB предназначен для распространения, а не прямой установки. Для старой локальной debug-версии потребуется удаление перед установкой подписанного APK.

Как подключиться с просроченным сертификатом: откройте профиль → «Подключить» → сверьте отпечаток → отметьте «Разрешить просроченный сертификат» → «Доверять сертификату».

Проверки: модульные тесты чтения служб, миграции профилей и TLS; реальное тестовое HTTPS-соединение с синтетическим просроченным сертификатом; запрет передачи запроса до подтверждения и отказ при неверном отпечатке. Выполнены сборка оптимизированных APK/AAB, проверка подписи и Android Lint. Проверка этих изменений на ваших двух шлюзах и на физическом телефоне не выполнялась.

## English

Two reported issues are fixed:

- **Expired certificates.** The connection prompt now shows expiry and SHA-256, and offers an explicit exception tied to this profile and exact certificate fingerprint. Background checks use the same setting. Changed certificates and not-yet-valid certificates remain rejected. You can revoke the exception in the profile editor; resetting trust or changing the endpoint clears it.
- **Named services in traffic rules.** Selected services such as Ipsec services, Kerio Vpn and OpenVPN services are shown instead of `RuleSelectedEntities`. The renderer now reads Kerio's `service.entries` array.

Install **OpenControlAdmin-0.2.apk** over the signed 0.1.0 release. The signing key is unchanged and profiles are retained. The AAB is a distribution bundle. An old local debug-signed build must be uninstalled before installing this signed APK.

For an expired certificate: connect, verify the fingerprint, select the expired-certificate exception, then confirm trust.

Validation covers rule rendering, old-profile migration, TLS policy and a real local HTTPS handshake with a synthetic expired certificate, including rejection before any request is sent and rejection of a mismatched fingerprint. Optimized builds, signature checks and Android Lint were run. The changes were not tested on your two gateways or a physical phone.

Signing certificate SHA-256:
```text
ee066519d1baea2b1949216f03ed444b4e4d448d288a0ab5d1c3bbfa6d50e144
```

Версии далее увеличиваются с шагом 0.1: 0.2 → 0.3 → 0.4.
