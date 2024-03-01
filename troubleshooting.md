---
title: Решение проблем
nav_order: 9
layout: default
---

# Решение проблем

1. TOC
{:toc}

### При подключении клавиатура не реагирует на нажатия, не отображается в Via, дисплеи не горят, подсветка горит красным

Это более чем вероятно решится другим кабелем. Даже если Вы уверены, что у Вас хороший кабель, попробуйте другой. Был случай, когда сплит не работал с кабелем от GMMK. Почему -- до сих пор не ясно.

### Via не распознает клавиатуру и выдает ошибку на Linux, но на Windows все нормально

Дело в udev. Чтобы дать текущему пользователю доступ ко всем hidraw устройствам, выполните:

```
export USER_GID=`id -g`; sudo --preserve-env=USER_GID sh -c 'echo "KERNEL==\"hidraw*\", SUBSYSTEM==\"hidraw\", MODE=\"0660\", GROUP=\"$USER_GID\", TAG+=\"uaccess\", TAG+=\"udev-acl\"" > /etc/udev/rules.d/92-viia.rules && udevadm control --reload && udevadm trigger'
```

Источник: [https://get.vial.today/manual/linux-udev.html](https://get.vial.today/manual/linux-udev.html#generalized-via-udev-rule).

### Клавиатура не определяется на [vial.rocks](https://vial.rocks/)

По умолчанию я не прошиваю клавиатуры с Vial, только с Via. Для поддержки Vial необходима [перепрошивка]({% link guide/4flash.md %}).

# Моей проблемы нет выше

Напишите мне на сайте, где был оформлен заказ.
