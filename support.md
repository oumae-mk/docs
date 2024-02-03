---
title: Поддержка
layout: default
nav_order: 3
---

# Поддержка

1. TOC
{:toc}

## Типовые проблемы

> При подключении клавиатура не реагирует на нажатия, не отображается в Via, дисплеи не горят, подсветка горит красным...
>
> В 99% случаев дело в USB кабеле. Был случай, когда сплит не работал с кабелем от GMMK. Почему -- до сих пор не ясно.
{: .note .question}

{: .note .question}
> Via не распознает клавиатуру и выдает ошибку на Linux, но на Windows все нормально...
>
> Дело в udev. Чтобы дать текущему пользователю доступ ко всем hidraw устройствам, выполните:
>
> ```
> export USER_GID=`id -g`; sudo --preserve-env=USER_GID sh -c 'echo "KERNEL==\"hidraw*\", SUBSYSTEM==\"hidraw\", MODE=\"0660\", GROUP=\"$USER_GID\", TAG+=\"uaccess\", TAG+=\"udev-acl\"" > /etc/udev/rules.d/92-viia.rules && udevadm control --reload && udevadm trigger'
> ```
>
> Источник: [https://get.vial.today/manual/linux-udev.html](https://get.vial.today/manual/linux-udev.html#generalized-via-udev-rule).

{: .note .question}
> Захожу на [https://vial.rocks/](https://vial.rocks/), клавиатура не определяется...
>
> По умолчанию я не прошиваю клавиатуры с Vial, только с Via. Для поддержки Vial необходима [перепрошивка]({% link guide/3flash.md %}).

## Моей проблемы нет выше

Напишите мне на сайте, где был оформлен заказ.

<!-- ## Формат обращения -->
<!---->
<!-- Ответьте на вопросы ниже и пришлите мне ответы: -->
<!---->
<!-- 1.  -->
