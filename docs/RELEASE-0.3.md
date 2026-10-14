# OpenControl Admin 0.3

## Русский

Исправлена строка «Сервисы» во вкладке «Правила»: службы, заданные протоколом и портом, теперь отображаются как **TCP 995**, **UDP 53**, а не «Условие: 6» или «Условие: 17».

Поддерживаются одиночные порты, диапазоны (`TCP 1000–2000`), списки (`UDP 53, 123`), исключения и сравнения (`TCP ≠ 443`, `TCP > 1024`, `UDP < 1024`), а также любой порт. Именные службы, например HTTPS и Kerio VPN, по-прежнему показываются по имени, в том числе вместе с явными портами в одном правиле.

Устанавливайте **OpenControlAdmin-0.3.apk** поверх подписанной версии 0.2: ключ подписи прежний, профили сохраняются. AAB не предназначен для прямой установки.

Проверки: модульные тесты отображения правил, профилей и TLS, оптимизированная сборка APK/AAB, Android Lint и проверка подписей. Проверка на физическом телефоне и на шлюзах пользователя для этого выпуска не проводилась. Изменение касается отображения; правила на шлюзе не изменяются.

## English

Fixed the Services row in Rules: explicit protocol/port entries now appear as **TCP 995** or **UDP 53**, instead of a raw protocol number.

Supports single ports, ranges, lists, exclusions, greater-than/less-than conditions and any port. Named services such as HTTPS and Kerio VPN still display their names, including rules mixing named services and explicit ports.

Install **OpenControlAdmin-0.3.apk** over the signed 0.2 release. The signing key is unchanged and saved profiles are retained. The AAB is not a directly installable APK.

Validation covers rule rendering, profile and TLS unit tests, optimized APK/AAB builds, Android Lint and signatures. This release was not tested on a physical phone or the user's gateways. This is a display fix; gateway rules are not modified.

Signing certificate SHA-256:
```text
ee066519d1baea2b1949216f03ed444b4e4d448d288a0ab5d1c3bbfa6d50e144
```