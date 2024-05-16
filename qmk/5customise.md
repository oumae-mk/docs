---
layout: default
title: Кастомизация
nav_order: 4
parent: QMK
---

# Кастомизация

1. TOC
{:toc}

Немного о том, как отредактировать исходники прошивки чтобы поменять в ней что-то, что недоступно в Via и Vial.

Релевантные пути:

```
qmk_firmware/keyboards/<клавиатура>
qmk_firmware/keyboards/<клавиатура>/keymap/<раскладка>
```

{: .warning }
> Помните, что каждая фича и слой занимают место в контроллере -- оно ограничено.

### rules.mk

Файл правил, которые позволяют легко включать и отключать фичи QMK. Достаточно просто назначить на нее `yes` или `no`. Например, строчка `OLED_ENABLE = no` отключит поддержку дисплеев.

Некоторые из доступных правил:

| Правило | Пояснение |
| :-: | ------- |
| `RGBLIGHT_ENABLE` | Подсветка.
| `MOUSEKEY_ENABLE` | [Управление мышью](https://github.com/qmk/qmk_firmware/blob/master/docs/feature_mouse_keys.md): передвижение указателя, клавиши мыши.
| `EXTRAKEY_ENABLE` | Медиа клавиши: системная громкость/яркость дисплея на стороне ОС.
| `OLED_ENABLE` | OLED дисплеи на клавиатуре.
| `NKRO_ENABLE` | N-key rollover. |
| `COMBO_ENABLE`| [Комбо](https://github.com/qmk/qmk_firmware/blob/master/docs/feature_combo.md). Например, *F*{:.k} + *J*{:.k} нажимают *Esc*{:.k}.
| `QMK_SETTINGS` | Соотв. вкладка в Vial.

**TODO: ограниченное кол-во эндпойнтов и места в контроллерах, а также KEYBOARD_SHARED_EP**

Подробнее в [документации](https://github.com/qmk/qmk_firmware/blob/master/docs/config_options.md#the-rulesmk-file QMK) QMK (англ.)

### Как поменять мастер половинку

Просто замените `#define MASTER_LEFT` на `#define MASTER_RIGHT` в файле `config.h`.

### Как изменить кол-во слоев

В файле `config.h`, измените само количество:

```
#define DYNAMIC_KEYMAP_LAYER_COUNT 6
```

В файле `keymap.c`, добавьте недостающие слои. Можно просто скопировать любой и изменить индекс:

```
const uint16_t PROGMEM keymaps[][MATRIX_ROWS][MATRIX_COLS] = {
  [0] = LAYOUT_split_3x6_3(
       KC_TAB,    KC_Q,    KC_W,    KC_E ...
  ),

  [1] = LAYOUT_split_3x6_3(
       KC_TAB,    KC_1,    KC_2,    KC_3 ...
  ),

  [2] = LAYOUT_split_3x6_3(
       KC_TAB, KC_EXLM,   KC_AT, KC_HASH ...
  ),

  [3] = LAYOUT_split_3x6_3(
        QK_BOOT, XXXXXXX, XXXXXXX, XXXXXXX ...
+ ),
+
+ [4] = LAYOUT_split_3x6_3(
+       QK_BOOT, XXXXXXX, XXXXXXX, XXXXXXX ...
+ ),
+
+ [5] = LAYOUT_split_3x6_3(
+       QK_BOOT, XXXXXXX, XXXXXXX, XXXXXXX ...
  )
};
```
