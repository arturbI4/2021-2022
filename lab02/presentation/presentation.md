---
## Front matter
lang: ru-RU
title: Лабораторная работа №2
author: |
	Карымшаков А.А. - студент группы НФИбд-03-18
date: 10.02.2022

## Formatting
toc: false
slide_level: 2
theme: metropolis
header-includes: 
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
aspectratio: 43
section-titles: true
---

# Установка и конфигурация операционной системы на виртуальную машину"

## Прагматика выполнения

- Атрибуты являются важным компонентом файловой системы, поскольку позволяют проверять права доступа для пользователей.

## Цель выполнения лабораторной работы

- Получение практических навыков работы в консоли с атрибутами файлов, закрепление теоретических основ дискреционного разграничения доступа в современных системах с открытым кодом на базе ОС Linux.

## Задачи выолнения работы

- Создать учетную запись пользователя guest.
- Войти в терминал, используя созданную учетную запись, и выполнить ряд команд.
- Заполнить таблицу "Установленные права и разрешенные действия"
- Заполнить таблицу "Минимальные права для совершения операций"

## Результаты выполнения лабораторной работы

- В установленной при выполнении предыдущей лабораторной работы операционной системе была создана учётная запись пользователя guest и был произведен вход в нее (рис -@fig:001, рис -@fig:002)

![Создание учетной записи guest](image/1.png){ #fig:001 width=70% }

##

![Вход в систему от имени пользователя guest](image/3.png){ #fig:002 width=70% }

##

- Вошел в терминал, используя созданную учетную запись, и выполнил ряд команд. (рис -@fig:003)

![Определение текущей директории. Переход в домашнюю директорию](image/4.png){ #fig:003 width=70% }

##

- Была заполнена таблица "Установленные права и разрешенные действия" (рис -@fig:005)

![Фаргмент таблицы "Установленные права и разрешенные действия"](image/14.png){ #fig:005 width=70% }

##

- Была заполнена таблица "Минимальные права для совершения операций" (рис -@fig:006)

![Таблица "Минимальные права для совершения операций"](image/15.png){ #fig:006 width=70% }

##

Таким образом, получил практические навыки работы в консоли с атрибутами файлов, закрепил теоретические основы дискреционного разграничения доступа в современных системах с открытым кодом на базе ОС Linux.