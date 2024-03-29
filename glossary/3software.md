---
title: QMK и фичи
parent: Механика 101
layout: default
nav_order: 2
---

# QMK и фичи

{: .warning}
> Этот раздел служит чтобы сформировать общие идеи о практическом применении этих вещей.

1. TOC
{:toc}

## QMK

Прошивка или же код, исполняемый клавиатурой. То, что дает ей способность распознавать нажатия и сообщать о них подключенному устройству.

QMK предполагает работу с исходниками. Также, он статичен: исходники редактируются, компилируются и прошиваются на контроллеры. Для внесения изменений в работу клавиатуры процесс повторяется.

Место в контроллере ограничено и каждая фича и слой его занимают. Поэтому есть физические ограничения на функционал, который может уместиться в клавиатуре.

### Via

Надстройка над QMK. На стороне пользователя, позволяет динамически вносить изменения в прошивку через GUI в браузере. Например, назначать клавиши, записывать макро, настраивать подсветку. Однако, Via ограничена по сравнению с тем, что предоставляет работа с исходниками.

### Vial

Альтернатива Via. Другой проект, другая философия, свой форк. Несколько более широкий функционал, чем в Via.

## Фичи

### layers

Они же слои. Их работу можно сравнить с тем, как *Shift*{:.k} взаимодействует с рядом цифр: *9*{:.k} выведет `9`, а *Shift*{:.k}+*9*{:.k} -- `(`.

Все слои на клавиатуре содержат все клавиши и свободно настраиваются.

### mod-tap и homerowmods

Mod-tap позволяет клавише играть роль как обычной клавиши, так и клавиши модификатора. Например, нажатие на *F*{:.k} работает как ожидается, а зажатие превращается в *Ctrl*{:.k}.

Homerowmods -- mod-tap для *Shift*{:.k}, *Ctrl*{:.k}, *Alt*{:.k} и *Super*{:.k} на домашнем ряду. Экономия клавиш, сокращение движений пальцев.

### tap dance

Разные функции в зависимости от вида и количества нажатий на клавишу. Например, одинарное нажатие на *Ь*{:.k} посылает `Ь`, а двойное -- `Ъ`.

### macros

Позволяют записать череду нажатий на разные клавиши и воспроизвести их по нажатию на одну.
