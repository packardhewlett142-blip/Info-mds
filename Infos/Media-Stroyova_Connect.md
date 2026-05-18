# Підключення до мережевих дисків Media / Stroyova

Інструкція для доступу до офісного сервера з macOS або Windows. Є два варіанти підключення:

| Режим | Коли використовувати |
|--------|----------------------|
| **Tailscale** (IP `100.120.130.55`) | З будь-якого місця, де є інтернет |
| **Локальна мережа** (IP `192.168.31.223`) | Тільки в офісі, у Wi‑Fi мережі |

---

## 1. Встановити Tailscale

**macOS** — завантажте інсталятор:

```text
https://pkgs.tailscale.com/stable/Tailscale-latest-macos.pkg
```

**Windows** — завантажте інсталятор:

```text
https://pkgs.tailscale.com/stable/tailscale-setup-latest.exe
```

**Linux** — виконайте в терміналі:

```bash
curl -fsSL https://tailscale.com/install.sh | sh
```

Або оберіть пакет на сторінці:

```text
https://tailscale.com/download
```

---

## 2. Увійти в Tailscale

1. Запустіть Tailscale.
2. Увійдіть через **Google-акаунт** (логін у Google і доступ до сервера має видати адміністратор).
3. Переконайтесь, що статус підключення **Connected**.

---

## 3. macOS — підключити диск у Finder

### Крок 1. Відкрити підключення до сервера

У Finder: **Go → Connect to Server…** (або `⌘K`).

![Connect to Server](../office_server_connect/Attachments/2F0DA57E-E4F8-4279-9A9E-A3FE70B5EB54.png)

### Крок 2. Ввести адресу сервера

**Віддалено (Tailscale)** — скопіюйте й вставте:

```text
smb://100.120.130.55
```

![Tailscale IP](../office_server_connect/Attachments/CC9E185C-CEA7-46A3-B00E-ECFC81AAC57A.png)

**Або в офісі (локальна мережа)** — скопіюйте й вставте:

```text
smb://192.168.31.223
```

![Local IP](../office_server_connect/Attachments/9FCDB689-E7E6-4C09-BB86-B5AB18D99170.png)

### Крок 3. Обрати том

Оберіть потрібний диск (**media** або **stroyova**). Якщо обрати не той том — доступ буде відхилено; поверніться на попередній крок.

![Select volumes](../office_server_connect/Attachments/8888169A-CA4F-47B4-8392-4B20998C0F42.png)

### Крок 4. Авторизація

Введіть **ім’я користувача** і **пароль**, увімкніть **Remember this password**.

![Enter credentials](../office_server_connect/Attachments/A2261424-81E5-495A-9614-3E25E571010D.png)

Диск з’явиться в боковій панелі Finder поруч з іншими томами.

![Mounted volume](../office_server_connect/Attachments/3FCF92F5-D695-4DE6-88B6-11EC1E92734A.png)

### Крок 5. Автопідключення після входу в систему

Додайте **Tailscale** і **мережевий диск** у **Login Items** (Системні налаштування → Загальні → Об’єкти входу).

![Login Items](../office_server_connect/Attachments/3B743A64-92E7-4865-B848-D9CE40D7A289.png)

---

## 4. Windows — підключити диск у Провіднику

### Крок 1. Відкрити мапінг диска

У Провіднику відкрийте **Цей комп’ютер** → **Map network drive** (Підключити мережевий диск).

![This PC](../office_server_connect/Attachments/6D2F38BA-571C-405E-9A14-C1084DA89E20.tiff)

### Крок 2. Обрати літеру диска

За замовчуванням часто пропонується **Z:** — можна залишити або змінити.

### Крок 3. Ввести шлях до папки

Скопіюйте **один** із шляхів нижче (залежно від режиму та потрібного диска).

#### Локальна мережа (тільки в офісі)

**Stroyova:**

```text
\\192.168.31.223\stroyova
```

![Map drive — stroyova local](../office_server_connect/Attachments/1F5F8003-2B7D-49F0-B3FD-06BBFBDDADF7.png)

**Media:**

```text
\\192.168.31.223\media
```

![Map drive — media local](../office_server_connect/Attachments/7A56E716-FBD7-4EAD-9632-98F18F618E77.png)

#### Tailscale (з будь-якого місця)

**Stroyova:**

```text
\\100.120.130.55\stroyova
```

![Map drive — stroyova remote](../office_server_connect/Attachments/A9E6C6B7-FFC4-48F2-8075-CAEB315A5A66.png)

**Media:**

```text
\\100.120.130.55\media
```

![Map drive — media remote](../office_server_connect/Attachments/B1B027A9-82E9-4E54-9310-524EF5C2AFDC.png)

### Крок 4. Автопідключення

Залиште увімкненим **Reconnect at sign-in** — диск підключатиметься після перезавантаження без додаткових дій.

### Крок 5. Авторизація

Введіть **ім’я користувача** і **пароль**, увімкніть **Remember my credentials**.

![Network credentials](../office_server_connect/Attachments/C85F4A4E-DC76-4BEF-99F3-BB1A282565EA.png)

Готовий диск з’явиться в **Цей комп’ютер → Мережеві розташування**.

![Devices and drives](../office_server_connect/Attachments/522D626A-9C9E-4A24-B65B-6BC5074A9DBD.png)

---

## Швидка довідка (копіювати одним кліком)

| Що | macOS (Finder, ⌘K) | Windows (Map network drive) |
|----|--------------------|-----------------------------|
| Сервер (Tailscale) | `smb://100.120.130.55` | `\\100.120.130.55\` + ім’я тома |
| Сервер (офіс Wi‑Fi) | `smb://192.168.31.223` | `\\192.168.31.223\` + ім’я тома |
| Том Stroyova (віддалено) | — | `\\100.120.130.55\stroyova` |
| Том Media (віддалено) | — | `\\100.120.130.55\media` |
| Том Stroyova (локально) | — | `\\192.168.31.223\stroyova` |
| Том Media (локально) | — | `\\192.168.31.223\media` |

**Примітка:** у macOS після `smb://…` на наступному екрані оберіть том **media** або **stroyova**. У Windows ім’я тома вже вказане в шляху після `\`.
