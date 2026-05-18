# 🗂️ Підключення до мережевих дисків Media / Stroyova

> **Привіт!** 👋 Ця інструкція допоможе під’єднатися до офісного сервера з **macOS** 🍎 або **Windows** 🪟.  
> Обирайте свій шлях нижче — усе з картинками й готовими адресами для копіювання 📋

---

## 🧭 З чого почати?

| Режим | Коли використовувати |
|--------|-------------------------------|
| 🌍 **Tailscale** · `100.120.130.55` | З дому, кафе, відрядження — де є інтернет |
| 🏢 **Локальна мережа** · `192.168.31.223` | Тільки в офісі, у Wi‑Fi |

| Потрібний диск | Том на сервері |
|----------------|----------------|
| 🎬 **Media** | `media` |
| 🏗️ **Stroyova** | `stroyova` |

> [!TIP]
> **Не впевнені, що обрати?**  
> Працюєте не в офісі → ставте **Tailscale** 🌍. Сидите в офісі → можна **локальну мережу** 🏢 (швидше, без VPN).

---

## 📍 Маршрут інструкції

```
1️⃣ Tailscale  →  2️⃣ Вхід  →  3️⃣ macOS 🍎  або  4️⃣ Windows 🪟  →  ⚡ Ви на сервері
```

---

## 1️⃣ Встановити Tailscale

> [!NOTE]
> Tailscale — це «тунель» до офісу. Без нього віддалений IP `100.120.130.55` не спрацює.

### 🍎 macOS

Завантажте інсталятор:

```text
https://pkgs.tailscale.com/stable/Tailscale-latest-macos.pkg
```

### 🪟 Windows

Завантажте інсталятор:

```text
https://pkgs.tailscale.com/stable/tailscale-setup-latest.exe
```

### 🐧 Linux

Виконайте в терміналі:

```bash
curl -fsSL https://tailscale.com/install.sh | sh
```

### 🔗 Інші системи

```text
https://tailscale.com/download
```

---

## 2️⃣ Увійти в Tailscale

1. ▶️ Запустіть Tailscale.
2. 🔐 Увійдіть через **Google-акаунт** (доступ до сервера видає адміністратор).
3. ✅ Переконайтесь, що статус **Connected** => ви в мережі!

---

## 3️⃣ 🍎 macOS — підключити диск у Finder

### Крок 1 · Відкрити підключення

У Finder: **Go → Connect to Server…** (або натисніть `⌘K`).

![Connect to Server](../office_server_connect/Attachments/2F0DA57E-E4F8-4279-9A9E-A3FE70B5EB54.png)

### Крок 2 · Ввести адресу сервера

#### 🌍 Віддалено (Tailscale)

Скопіюйте й вставте:

```text
smb://100.120.130.55
```

![Tailscale IP](../office_server_connect/Attachments/CC9E185C-CEA7-46A3-B00E-ECFC81AAC57A.png)

#### 🏢 Або в офісі (локальна мережа)

Скопіюйте й вставте:

```text
smb://192.168.31.223
```

![Local IP](../office_server_connect/Attachments/9FCDB689-E7E6-4C09-BB86-B5AB18D99170.png)

### Крок 3 · Обрати том

Оберіть 🎬 **media** або 🏗️ **stroyova**.

![Select volumes](../office_server_connect/Attachments/8888169A-CA4F-47B4-8392-4B20998C0F42.png)

> [!WARNING]
> Обрали не той том? Сервер не пустить — це нормально 😅 Поверніться назад (`⌘K`) і спробуйте інший.

### Крок 4 · Логін і пароль

Введіть **ім’я користувача** і **пароль**, увімкніть **Remember this password** 🔒

![Enter credentials](../office_server_connect/Attachments/A2261424-81E5-495A-9614-3E25E571010D.png)

🎉 Диск з’явиться в боковій панелі Finder!

![Mounted volume](../office_server_connect/Attachments/3FCF92F5-D695-4DE6-88B6-11EC1E92734A.png)

### Крок 5 · Автопідключення

Додайте **Tailscale** і **мережевий диск** у **Login Items** — тоді після увімкнення Mac усе під’єднається само ☕

![Login Items](../office_server_connect/Attachments/3B743A64-92E7-4865-B848-D9CE40D7A289.png)

---

## 4️⃣ 🪟 Windows — підключити диск у Провіднику

### Крок 1 · Відкрити мапінг диска

**Цей комп’ютер** → **Map network drive** (Підключити мережевий диск).

![This PC](../office_server_connect/Attachments/6D2F38BA-571C-405E-9A14-C1084DA89E20.png)

### Крок 2 · Літера диска

За замовчуванням часто **Z:** — можна залишити або обрати іншу 🔤

### Крок 3 · Шлях до папки

Скопіюйте **один** блок нижче 👇

---

#### 🏢 Локальна мережа (тільки в офісі)

| Диск | Шлях |
|------|------|
| 🏗️ Stroyova | див. блок нижче |
| 🎬 Media | див. блок нижче |

**🏗️ Stroyova:**

```text
\\192.168.31.223\stroyova
```

![Map drive — stroyova local](../office_server_connect/Attachments/1F5F8003-2B7D-49F0-B3FD-06BBFBDDADF7.png)

**🎬 Media:**

```text
\\192.168.31.223\media
```

![Map drive — media local](../office_server_connect/Attachments/7A56E716-FBD7-4EAD-9632-98F18F618E77.png)

---

#### 🌍 Tailscale (з будь-якого місця)

**🏗️ Stroyova:**

```text
\\100.120.130.55\stroyova
```

![Map drive — stroyova remote](../office_server_connect/Attachments/A9E6C6B7-FFC4-48F2-8075-CAEB315A5A66.png)

**🎬 Media:**

```text
\\100.120.130.55\media
```

![Map drive — media remote](../office_server_connect/Attachments/B1B027A9-82E9-4E54-9310-524EF5C2AFDC.png)

---

### Крок 4 · Автопідключення

✅ Залиште **Reconnect at sign-in** — після перезавантаження диск під’єднається сам.

### Крок 5 · Логін і пароль

Введіть дані, увімкніть **Remember my credentials** 🔒

![Network credentials](../office_server_connect/Attachments/C85F4A4E-DC76-4BEF-99F3-BB1A282565EA.png)

🎉 Готово! Диск у **Цей комп’ютер → Мережеві розташування**.

![Devices and drives](../office_server_connect/Attachments/522D626A-9C9E-4A24-B65B-6BC5074A9DBD.png)

---

## ⚡ Швидка довідка (копіювати одним кліком)

> [!TIP]
> У **macOS** після `smb://…` на наступному екрані оберіть том. У **Windows** том уже в шляху після `\`.

| Що | 🍎 macOS (`⌘K`) | 🪟 Windows |
|----|-----------------|------------|
| 🌍 Сервер Tailscale | `smb://100.120.130.55` | `\\100.120.130.55\` + том |
| 🏢 Сервер офіс Wi‑Fi | `smb://192.168.31.223` | `\\192.168.31.223\` + том |
| 🏗️ Stroyova віддалено | — | `\\100.120.130.55\stroyova` |
| 🎬 Media віддалено | — | `\\100.120.130.55\media` |
| 🏗️ Stroyova в офісі | — | `\\192.168.31.223\stroyova` |
| 🎬 Media в офісі | — | `\\192.168.31.223\media` |

---

### 🆘 Щось не працює?

| Симптом | Що перевірити |
|---------|----------------|
| 🔴 Не бачу сервер віддалено | Tailscale **Connected**? Спробуйте IP `100.120.130.55` |
| 🔴 Не бачу в офісі | Wi‑Fi офісу? IP `192.168.31.223` |
| 🔴 Відмовлено в доступі | Том **media** / **stroyova** і правильний логін? |
| 🔴 Просить пароль щоразу | Увімкніть «запам’ятати пароль» на кроці логіну |

> [!NOTE]
> Питання до адміна — краще одразу зі скріном помилки 📸

**Успішної роботи з дисками!** 🚀✨
