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

После установки: сканирование → загрузка → сохранение → повторное открытие проекта. Фиксируй результат в [Паспорт рабочего окружения](../09%20%D0%9C%D0%BE%D0%B8%20%D0%B7%D0%B0%D0%BC%D0%B5%D1%82%D0%BA%D0%B8/%D0%9F%D0%B0%D1%81%D0%BF%D0%BE%D1%80%D1%82%20%D1%80%D0%B0%D0%B1%D0%BE%D1%87%D0%B5%D0%B3%D0%BE%20%D0%BE%D0%BA%D1%80%D1%83%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F.md).

Источники: [NixOS Audio production](https://wiki.nixos.org/wiki/Audio_production), [Nixpkgs manual](https://nixos.org/manual/nixpkgs/stable/).

## Связи

[Форматы плагинов](%D0%A4%D0%BE%D1%80%D0%BC%D0%B0%D1%82%D1%8B%20%D0%BF%D0%BB%D0%B0%D0%B3%D0%B8%D0%BD%D0%BE%D0%B2.md) · [Сканирование плагинов Waveform](%D0%A1%D0%BA%D0%B0%D0%BD%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%20%D0%BF%D0%BB%D0%B0%D0%B3%D0%B8%D0%BD%D0%BE%D0%B2%20Waveform.md) · [Диагностика студии](%D0%94%D0%B8%D0%B0%D0%B3%D0%BD%D0%BE%D1%81%D1%82%D0%B8%D0%BA%D0%B0%20%D1%81%D1%82%D1%83%D0%B4%D0%B8%D0%B8.md)
