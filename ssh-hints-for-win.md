# Создание и использование SSH-ключей в Windows

## Создание SSH-ключа

Откройте терминал и введите:
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
где ***your_email@example.com*** - ваш e-mail.
Далее будут заданы вопросы (где будут располагаться ключи, пароль, подтверждение пароля) для ответа на которые рекомендую просто нажать `Enter`:

![SSH for Win](./img/01.png "SSH-key for Windows")

После этого введите в терминале для запуска ssh-агента:
```bash
eval "$(ssh-agent -s)"
```

![SSH for Win](./img/02.png "SSH-key for Windows")

И последний шаг введите в терминале:
```bash
ssh-add ~/.ssh/id_ed25519
```

![SSH for Win](./img/03.png "SSH-key for Windows")

## Добавление ключа в GitHub.

Перейдите в папку `C:\Users\"NickName"\.ssh`, где ***NickName*** - ваш аккаунт Windows. Откройте в любом текстовом редакторе (блокнот) файл `id_ed25519.pub`. Начинаться он должен примерно так: `ssh-ed25519 `. Скопируйте в буфер обмена все его содержимое (Ctrl+A -> Ctrl+C).

Откройте GitHub и откройте `Settings`:

![SSH for Win](./img/04.png "SSH-key for Windows")

Потом перейдите в раздел `SSH and GPG keys`:

![SSH for Win](./img/05.png "SSH-key for Windows")

Нажмите на кнопку `New SSH key`:

![SSH for Win](./img/06.png "SSH-key for Windows")

В поле `Title` введите любое название для ключа, а в поле `Key` вставьте ключь (Ctrl+V) который вы скопировали из файла `id_ed25519.pub`. Нажмите на кнопку `Add SSH key`.

![SSH for Win](./img/07.png "SSH-key for Windows")

На вашу почту должно прийти письмо с подтверждением добавления ключа.

При первом обращении к GitHub в терминале у вас спросят хотите ли продолжить, введите `yes` и нажмите `enter`:

![SSH for Win](./img/08.png "SSH-key for Windows")