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

[[Форматы плагинов]] · [[Экспорт и резервные копии]] · [[Диагностика студии]]
