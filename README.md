# CGIM2 Weathers (rel. 1.0) for IX-Ray Platform

## Overview

This is an official adaptation of the CGIM2 weather mod for the IX-Ray platform. The pack adds several completely new weather cycles and creates a summer atmosphere in the game

## Remarks

> [!WARNING]
>
> Supported only on __IX-Ray Platform__!
>
> Not compatible with other weather mods! Before installing, delete user.ltx

## Requirements

Installation:

1. Install Shadow of Chernobyl, Clear Sky, or Call of Pripyat
2. Install a matching IX-Ray build with platform-aware addons and CoP-format weather support
3. Extract the addon archive into the game folder, preserving all four modules in `ixr_addons/ixray-cgim2/`
4. Start the game and play

Link to the current __IX-Ray__ [release](https://github.com/ixray-team/ixray-1.6-stcop/releases/latest)

## Modules

| Directory | Platform | Contents |
| --- | --- | --- |
| `cgim-common` | `soc`, `cs`, `cop` | Shared textures, CoP-format weather cycles and effects, sun settings, graph groups, renderer defaults |
| `cgim-soc` | `soc` | Dynamic weather manager, outdoor graph assignments, and native SoC ambient/thunderbolt adapters |
| `cgim-cs` | `cs` | Clear Sky dynamic weather graph and introductory weather conditions |
| `cgim-cop` | `cop` | Call of Pripyat weather periods and surge settings |

The engine discovers nested `addon.init` files, mounts the common module first through `depends: cgim-common`, and selects the matching platform module automatically. Keep the common module together with the platform module; textures and weather keyframes are stored only once.

SoC selects shared CoP-format cycles dynamically: weather groups last for the configured number of game hours, weighted cycles change hourly, and a one-hour transition separates groups. The current group, cycle, and timers persist in actor pstor across saves and level changes. Underground weather remains native, scripted weather effects take priority, and the weather-manager save packet keeps its native format. The SoC adapters contain native sound, particle, and thunderbolt definitions in the CoP config layout and use only SoC assets. Disable the old `cgim-origin` addon before using this version.

## Contributors

### IX-Ray Team

- Drombeys
- Hozar2002

### CGIM Team

- zhoracementov

## License

Сontents of this repository are licensed under terms of the __CC BY-NC-SA 4.0__ license unless otherwise specified. See [this](./LICENSE.txt) file for details

## Обзор

Это официальная адаптация погодного мода CGIM2 под платформу IX-Ray. Пак добавляет несколько полностью новых погодных циклов и создаёт в игре летнюю атмосферу

## Примечаниe

> [!WARNING]
>
> Поддерживается только на __IX-Ray Platform__!
>
> Не совместимо с другими погодными модами! Перед установкой удалите user.ltx

## Рекомендации

Установка:

1. Установить «Тень Чернобыля», «Чистое небо» или «Зов Припяти»
2. Установить сборку IX-Ray для выбранной игры с поддержкой платформ в аддонах и погоды формата ЗП
3. Распаковать архив в папку с игрой, сохранив все четыре модуля в `ixr_addons/ixray-cgim2/`
4. Запустите игру и играйте

Ссылка на текущую версию __IX-Ray__ [релиз](https://github.com/ixray-team/ixray-1.6-stcop/releases/latest)

## Структура модулей

| Папка | Платформа | Содержимое |
| --- | --- | --- |
| `cgim-common` | `soc`, `cs`, `cop` | Общие текстуры, циклы и эффекты погоды формата ЗП, солнца, группы графов и настройки рендера |
| `cgim-soc` | `soc` | Динамический погодный менеджер, привязки графа наземных локаций ТЧ и адаптеры родных звуков и молний |
| `cgim-cs` | `cs` | Граф динамической погоды ЧН и условия погоды вступления |
| `cgim-cop` | `cop` | Периоды погоды ЗП и настройки выбросов |

Движок находит вложенные `addon.init`, загружает общий модуль первым благодаря `depends: cgim-common` и автоматически выбирает модуль нужной платформы. Общий модуль обязателен; текстуры и погодные кадры хранятся в единственном экземпляре.

В ТЧ общие циклы формата ЗП выбираются динамически: длительность групп задаётся общим графом в игровых часах, циклы внутри группы меняются каждый час с учётом весов, между группами включается часовая переходная погода. Группа, цикл и таймеры сохраняются в штатном хранилище актёра между загрузками и переходами по локациям. Подземелья используют родную погоду, сюжетные погодные эффекты имеют приоритет. Формат блока сохранения погодного менеджера ТЧ остаётся штатным. Адаптеры содержат штатные определения звуков, частиц и молний ТЧ в структуре конфигов ЗП и используют ресурсы ТЧ. Перед использованием отключите старый аддон `cgim-origin`.

## Контрибьюторы

### Команда IX-Ray

- Drombeys
- Hozar2002

### Команда CGIM

- zhoracementov

## Лицензия

Содержимое этого репозитория лицензировано в соответствии с условиями лицензии __CC BY-NC-SA 4.0__, если не указано иное. Подробности см. в файле [здесь](./LICENSE.txt)
