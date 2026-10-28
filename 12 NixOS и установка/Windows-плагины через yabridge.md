---
type: guide
status: new
updated: 2026-10-28
tags: [music, studio]
---

# Windows-плагины через yabridge

Дополнительный путь, когда нужного эффекта нет в нативном наборе. Основа студии обходится без него.

Нужны совместимые версии Wine и yabridge, Windows-установщик и поддерживаемый DAW формат. Сверяй текущие ограничения в [README yabridge](https://github.com/robbert-vdh/yabridge); не обновляй Wine вслепую перед работой над треком.

После установки совместимой пары пример команд:

```bash
WINEPREFIX="$HOME/.wine-audio" wineboot
WINEPREFIX="$HOME/.wine-audio" wine /absolute/path/installer.exe
yabridgectl add "$HOME/.wine-audio/drive_c/Program Files/Common Files/VST3"
yabridgectl sync
yabridgectl status
```

Путь установщика — заглушка. Для VST2 добавь реальную директорию установки отдельно. В Waveform сканируй созданные обёртки, обычно ~/.vst3/yabridge и ~/.vst/yabridge.

Мост не гарантирует работу защиты, GUI или сохранения состояния каждого продукта. Сначала проверь в отдельном проекте. Для основного набора Graillon, Surge и эффектов нативная сборка предпочтительнее.

## Связи

[Форматы плагинов](%D0%A4%D0%BE%D1%80%D0%BC%D0%B0%D1%82%D1%8B%20%D0%BF%D0%BB%D0%B0%D0%B3%D0%B8%D0%BD%D0%BE%D0%B2.md) · [Экспорт и резервные копии](../13%20%D0%A0%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%20%D0%BD%D0%B0%D0%B4%20%D1%82%D1%80%D0%B5%D0%BA%D0%BE%D0%BC/%D0%AD%D0%BA%D1%81%D0%BF%D0%BE%D1%80%D1%82%20%D0%B8%20%D1%80%D0%B5%D0%B7%D0%B5%D1%80%D0%B2%D0%BD%D1%8B%D0%B5%20%D0%BA%D0%BE%D0%BF%D0%B8%D0%B8.md) · [Диагностика студии](%D0%94%D0%B8%D0%B0%D0%B3%D0%BD%D0%BE%D1%81%D1%82%D0%B8%D0%BA%D0%B0%20%D1%81%D1%82%D1%83%D0%B4%D0%B8%D0%B8.md)
