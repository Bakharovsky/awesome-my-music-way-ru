---
type: guide
status: new
updated: 2026-10-28
tags: [music, studio]
---

# Нативные плагины на NixOS

## Порядок выбора

1. Пакет в закреплённом nixpkgs: проверь версию, архитектуру и фактические выходные форматы.
2. Сборка из исходников в derivation: закрепи commit и hash.
3. Упаковка готовой Linux-сборки: могут понадобиться autoPatchelfHook, библиотеки и пути ресурсов.

Пример поиска, а не список гарантированно существующих атрибутов:

```bash
nix search nixpkgs surge
nix search nixpkgs byod
nix search nixpkgs guitarix
```

Registry nixpkgs может отличаться от input твоего flake.lock. Используй найденный и проверенный атрибут в environment.systemPackages либо home.packages своего проекта.

Не считай nix-ld универсальным решением: DAW загружает библиотеки плагинов внутрь процесса, а не только запускает исполняемый файл. Плагин вместе с ресурсами должен быть доступен тому окружению, где работает DAW.

После установки: сканирование → загрузка → сохранение → повторное открытие проекта. Фиксируй результат в [[Паспорт рабочего окружения]].

Источники: [NixOS Audio production](https://wiki.nixos.org/wiki/Audio_production), [Nixpkgs manual](https://nixos.org/manual/nixpkgs/stable/).

## Связи

[[Форматы плагинов]] · [[Сканирование плагинов Waveform]] · [[Диагностика студии]]
