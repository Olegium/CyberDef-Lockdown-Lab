## CyberDef-Lockdown-Lab

# Вопросы

<img width="800" height="1204" alt="image" src="https://github.com/user-attachments/assets/d43aefe4-0eda-44ed-9e5d-fcae8b0ff74c" />


загрузили pcapng file видим что источник запросов 10.0.2.4 

<img width="1649" height="751" alt="image" src="https://github.com/user-attachments/assets/32fc6317-9d15-4836-b3fb-cc6a858057b2" />

<img width="1137" height="33" alt="image" src="https://github.com/user-attachments/assets/586a842d-c10b-455c-8670-fc7473e2a1a7" />

SMB (Server Message Block) - протокол Windows для доступа к файлам и папкам по сети. Когда злоумышленник сканирует общие ресурсы на сервере, он отправляет запросы Tree Connect - это запрос на подключение к конкретной общей папке (share).

по smb ничего не нашли

<img width="1421" height="320" alt="image" src="https://github.com/user-attachments/assets/18051703-96f6-44fc-a43b-f5e0c3739f35" />

нашли tree connect через поиск есть 2 каталога

\\10.0.2.15\Documents
\\10.0.2.15\IPC$

<img width="1914" height="864" alt="image" src="https://github.com/user-attachments/assets/d61b25f6-150c-47e4-b6e6-c0b3856776b0" />

находим подозрительный файл file 

<img width="1757" height="189" alt="image" src="https://github.com/user-attachments/assets/8d4c498d-ec36-4e6e-bac2-733eb733163c" />

код 5 создание нового файла 

<img width="1747" height="312" alt="image" src="https://github.com/user-attachments/assets/b9b1c4cc-a6c3-48bb-9723-082071caa539" />

Обычно, когда ты подключаешься к серверу (например, по SSH или RDP), ты (клиент) инициируешь соединение к серверу. Это прямое подключение. Брандмауэры (фаерволы) по умолчанию блокируют такие входящие подключения извне на нестандартные порты.

Обратная оболочка работает наоборот:
Злоумышленник загружает вредоносный файл (shell.aspx) на сервер.
Файл выполняется на сервере (IIS).
Сервер (жертва) сам инициирует исходящее подключение к компьютеру злоумышленника.

ищем все соединения которые только начали 3-рукопожатия

<img width="1502" height="242" alt="image" src="https://github.com/user-attachments/assets/c818dffa-7bef-4afe-b2e8-6e0a495fb5fe" />

Вопросы

<img width="707" height="1120" alt="image" src="https://github.com/user-attachments/assets/108dd0db-25dd-4120-93d0-a4a624094908" />

Volatility — это главный инструмент в мире цифровой криминалистики (Digital Forensics) для анализа оперативной памяти (RAM).

мы загрузили все данные работы оперативной паямти  и нашли адресс ядра

<img width="1009" height="429" alt="image" src="https://github.com/user-attachments/assets/aefe1a12-88fb-4880-956c-fef6d85afb65" />

Мы нашли файл который имеет автозапуск .exe и это вызвало подозрения 

<img width="1039" height="417" alt="image" src="https://github.com/user-attachments/assets/4048ae04-853e-40bc-9634-5a962658bce9" />

Смотрим СЕССИИ с ip злоумышленника находим файл

<img width="1106" height="92" alt="image" src="https://github.com/user-attachments/assets/fea24c29-0a15-4606-a5a9-f25032f10abb" />
