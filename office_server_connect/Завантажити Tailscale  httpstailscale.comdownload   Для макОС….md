# Завантажити Tailscale  [https://tailscale.com/download](https://tailscale.com/download)   Для макОС — [https://pkgs.tailscale.com/stable/Tailscale-latest-macos.pkg](https://pkgs.tailscale.com/stable/Tailscale-latest-macos.pkg)  Для вінди – [https://pkgs.tailscale.com/stable/tailscale-setup-latest.exe](https://pkgs.tailscale.com/stable/tailscale-setup-latest.exe)   
**Для лінукса — curl -fsSL https://tailscale.com/install.sh | sh **  
  
  
**Залогінітись в аплікацію  Логін через ГуглАкк  Логін в гугл та в сервер вам має надати адміністратор **  
  
Підключити диск в файндер (медія або стройова)  
![© Downlande](Attachments/2F0DA57E-E4F8-4279-9A9E-A3FE70B5EB54.png)  
Заходимо в Finder -> Go -> Connect to Sever… (або шорткат cmd+K)  
![smb://100.120.130.55](Attachments/CC9E185C-CEA7-46A3-B00E-ECFC81AAC57A.png)  
Вводимо IP серверу з Tailscale — для віддаленого доступу   
[smb://100.120.130.55](smb://100.120.130.55)  
  
АБО  
  
![smb://192.168.31.223](Attachments/9FCDB689-E7E6-4C09-BB86-B5AB18D99170.png)  
Вводимо локальне IP — для доступу лише в межах WiFi офісу   
  
[smb://192.168.31.223](smb://192.168.31.223)  
  
![Select the volumes you want to mount on](Attachments/8888169A-CA4F-47B4-8392-4B20998C0F42.png)  
Обираємо диск до якого потрібен доступ (у випадку якщо оберете не той — ваш обліковий запис не пустить вас, повернетесь на попередній крок)   
  
![Enter your name and password for the server](Attachments/A2261424-81E5-495A-9614-3E25E571010D.png)  
Вводимо юзернейм+пароль та клікаємо запамʼятати цей пароль   
  
   
![> a Macintosh HD](Attachments/3FCF92F5-D695-4DE6-88B6-11EC1E92734A.png)  
Диск зʼявиться у вас в розділі з усіма томами   
  
Для подальшого автоматичного підʼєднання додайте цей диск та аплікацію Tailscale в обʼєкти логіну   
![< > ) Login Items & Extensions](Attachments/3B743A64-92E7-4865-B848-D9CE40D7A289.png)  
  
Підключити диск в провідник (медія/стройова)  
 В провіднику обрати розділ “Цей ПК”   
![This po](Attachments/6D2F38BA-571C-405E-9A14-C1084DA89E20.png)  
Та обрати функцію “Map network drive”  
  
У наступному вікні обрати літеру для диску (по базовм налаштуванням це буде Z:)   
  
![+ * Map Network Drive](Attachments/7A56E716-FBD7-4EAD-9632-98F18F618E77.png)  
Ввести  \\192.168.31.223\stroyova   
для локального підʼєднання до диску стройової (доступ лише в межах WiFi офісу)   
![+ ® Map Network Drive](Attachments/1F5F8003-2B7D-49F0-B3FD-06BBFBDDADF7.png)  
Ввести  \\192.168.31.223\media   
для локального підʼєднання до диску медійки (доступ лише в межах WiFi офісу)   
  
![+ * Map Network Drive](Attachments/A9E6C6B7-FFC4-48F2-8075-CAEB315A5A66.png)  
Ввести  \\100.120.130.55\stroyova   
для підʼєднання до диску стройової через Tailscale (доступ у будь-якій точці де є інтренет)   
  
![+ * Map Network Drive](Attachments/B1B027A9-82E9-4E54-9310-524EF5C2AFDC.png)  
Ввести  \\100.120.130.55\media   
для підʼєднання до диску стройової через Tailscale (доступ у будь-якій точці де є інтренет)   
  
Автоматично буде стояти флажок “Reconnect at sign-in” — це не змінюйте, аби без зайвого клопоту підʼєднуватись після перезавантажень ПК  
  
![enter network credentials](Attachments/C85F4A4E-DC76-4BEF-99F3-BB1A282565EA.png)  
Після цих налаштувань введіть свій юзернейм+пароль та поставте флажок “Remember my credentials”  
  
![v Devices and drives](Attachments/522D626A-9C9E-4A24-B65B-6BC5074A9DBD.png)  
  
Отак в розділі “”Цей ПК” буде виглядати ваш мережевий диск  
  
