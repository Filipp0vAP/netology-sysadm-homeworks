# Домашнее задание к занятию "3.9. Элементы безопасности информационных систем"

1. Установите Bitwarden плагин для браузера. Зарегестрируйтесь и сохраните несколько паролей.

    ## Ответ
    
    ![Bitwarden](./image.png)
    
    ---
    
2. Установите Google authenticator на мобильный телефон. Настройте вход в Bitwarden акаунт через Google authenticator OTP.
    ## Ответ
    ![2fa](./2fa.png)
    
    ---
    
3. Установите apache2, сгенерируйте самоподписанный сертификат, настройте тестовый сайт для работы по HTTPS.
    ## Ответ
    я немного заморочился и импортировал сертификат в доверенные
    
    (а еще прописал subjectAltName при создании сертификата, потому что без subjectAltName хром не считал его доверенным даже если я его импортировал)
    ![hi](./hi.png)
    
    ---
    
4. Проверьте на TLS уязвимости произвольный сайт в интернете (кроме сайтов МВД, ФСБ, МинОбр, НацБанк, РосКосмос, РосАтом, РосНАНО и любых госкомпаний, объектов КИИ, ВПК ... и тому подобное).
     ## Ответ
     проверил вас :-)
     ![pentest](./pentest.png)
     
     ---
     
5. Установите на Ubuntu ssh сервер, сгенерируйте новый приватный ключ. Скопируйте свой публичный ключ на другой сервер. Подключитесь к серверу по SSH-ключу.
    ## Ответ
    ![ssh](./ssh.png)
    
6. Переименуйте файлы ключей из задания 5. Настройте файл конфигурации SSH клиента, так чтобы вход на удаленный сервер осуществлялся по имени сервера.
    ## Ответ
    ```
    Host vagrant
        HostName 127.0.0.1
        User vagrant
        Port 2222
        IdentityFile C:\Users\filip\.ssh\test
    ```
    
    ![vagrantssh](./vagrantssh.png)
    
7. Соберите дамп трафика утилитой tcpdump в формате pcap, 100 пакетов. Откройте файл pcap в Wireshark.
    
    ![wireshark](./wireshark.png)
 ---
## Задание для самостоятельной отработки (необязательно к выполнению)

8*. Просканируйте хост scanme.nmap.org. Какие сервисы запущены?

9*. Установите и настройте фаервол ufw на web-сервер из задания 3. Откройте доступ снаружи только к портам 22,80,443
    
   ## Ответ
   ```bash
    vagrant@vagrant:~/testssl.sh$ sudo ufw default deny incoming
    allow outgoingDefault incoming policy changed to 'deny'
    (be sure to update your rules accordingly)
    vagrant@vagrant:~/testssl.sh$ sudo ufw default allow outgoing
    Default outgoing policy changed to 'allow'
    (be sure to update your rules accordingly)
    vagrant@vagrant:~/testssl.sh$
    vagrant@vagrant:~/testssl.sh$
    vagrant@vagrant:~/testssl.sh$ sudo ufw allow ssh
    Rules updated
    Rules updated (v6)
    vagrant@vagrant:~/testssl.sh$ sudo ufw allow 22
    Rules updated
    Rules updated (v6)
    vagrant@vagrant:~/testssl.sh$ sudo ufw allow 2222
    Rules updated
    Rules updated (v6)
    vagrant@vagrant:~/testssl.sh$ sudo ufw allow 80
    Rules updated
    Rules updated (v6)
    vagrant@vagrant:~/testssl.sh$ sudo ufw allow 443
    Rules updated
    Rules updated (v6)
    vagrant@vagrant:~/testssl.sh$ sudo ufw allow http
    Rules updated
    Rules updated (v6)
    vagrant@vagrant:~/testssl.sh$ sudo ufw allow https
    Rules updated
    Rules updated (v6)
    vagrant@vagrant:~/testssl.sh$ sudo ufw enable
    Command may disrupt existing ssh connections. Proceed with operation (y|n)? y
    Firewall is active and enabled on system startup
   ```
 ---

## Как сдавать задания

Обязательными к выполнению являются задачи без указания звездочки. Их выполнение необходимо для получения зачета и диплома о профессиональной переподготовке.

Задачи со звездочкой (*) являются дополнительными задачами и/или задачами повышенной сложности. Они не являются обязательными к выполнению, но помогут вам глубже понять тему.

Домашнее задание выполните в файле readme.md в github репозитории. В личном кабинете отправьте на проверку ссылку на .md-файл в вашем репозитории.

Также вы можете выполнить задание в [Google Docs](https://docs.google.com/document/u/0/?tgif=d) и отправить в личном кабинете на проверку ссылку на ваш документ.
Название файла Google Docs должно содержать номер лекции и фамилию студента. Пример названия: "1.1. Введение в DevOps — Сусанна Алиева".

Если необходимо прикрепить дополнительные ссылки, просто добавьте их в свой Google Docs.

Перед тем как выслать ссылку, убедитесь, что ее содержимое не является приватным (открыто на комментирование всем, у кого есть ссылка), иначе преподаватель не сможет проверить работу. Чтобы это проверить, откройте ссылку в браузере в режиме инкогнито.

[Как предоставить доступ к файлам и папкам на Google Диске](https://support.google.com/docs/answer/2494822?hl=ru&co=GENIE.Platform%3DDesktop)

[Как запустить chrome в режиме инкогнито ](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=ru)

[Как запустить  Safari в режиме инкогнито ](https://support.apple.com/ru-ru/guide/safari/ibrw1069/mac)

Любые вопросы по решению задач задавайте в чате учебной группы.

---

