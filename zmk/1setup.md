---
layout: default
title: Подготовка
nav_order: 2
parent: ZMK
---
# Подготовка

1. TOC
{:toc}

{: .warning}
> Этот раздел содержит процесс, полагающийся на GUI (почти все происходит в браузере, никакой коммандной строки). Если Вы предпочитаете работать с исходниками, то я рекомендую настроить build env по [докам ZMK](https://zmk.dev/docs/development/setup).

## Github Actions

Один из способов работы с ZMK -- через Github Actions. Это позволяет компилировать прошивку на Github, без необходимости установки какого-либо ПО.

1. Создайте аккаунт на [github.com](https://github.com).
2. Форкните мой репо для Вашей клавиатуры:
    - [Corne](https://github.com/tsbohc/zmk-config-corne) (MX/Choc)
    - [Lily58pro](https://github.com/tsbohc/zmk-config-lily58) (MX/Choc)
    - [TOTEM](https://github.com/tsbohc/zmk-config-totem)
3. Убедитесь, что в настройках репо, в разделе *Actions* -- *General*, активно *Allow all actions and reusable workflows*.

## Keymap Editor

Браузерный GUI для редактирования раскладки ZMK от [nickcoutsos](https://github.com/nickcoutsos/). Это не аналог Via или Vial -- изменения не применяются сразу. Однако, простора для кастомизации в нем на порядок больше.

1. Перейдите по ссылке [nickcoutsos.github.io/keymap-editor/](https://nickcoutsos.github.io/keymap-editor/)
2. В качестве источника выберите Github. Нажмите "Login with GitHub" и авторизируйтесь.

    ![](source.png)

3. Нажмите "Add Repository".

    ![](select.png)

4. Выберите репо, которое Вы форкнули ранее. Не выбирайте вариант "Все репозитории".

    ![](configure.png)

5. И наконец, мы в редакторе с:

    ![](editor.png)
