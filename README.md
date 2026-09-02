# Environment Compass

Letta Code mod — read-only ориентация агента в среде выполнения.

## Что делает

Показывает, в каком окружении запущен агент: Desktop (macOS / Windows), платформа, модель, пути и git-статус памяти и рабочей директории.

- среда, модель, режим permission
- HOME, CWD, MEMORY_DIR, переменные окружения
- версия Node.js и Letta (Desktop bundled)
- git-статус репозитория памяти и текущей директории
- рекомендации перед редактированием памяти

Никаких сетевых запросов, никакой записи на диск.

## Установка

```bash
git clone https://github.com/dsv180/environment-compass.git
cd environment-compass
letta install .
```

После установки — `/reload` в активной сессии.

## Использование

- `/env-compass` — команда в чате
- `environment_compass` — инструмент для агента

## Пример

```
Detected environment: Desktop / local Windows
Agent: Вася китаец
Model: openai-compatible/deepseek-v4-flash

Memory: ~/.letta/lc-local-backend/memfs/... (ctx.agent.id)
Branch: main
Status: clean

➡ Репозиторий памяти чистый, можно редактировать.
```

## Происхождение

Этот мод является адаптацией community-разработки **Environment Compass**, изначально продемонстрированной в рамках Letta Mod Challenge (Letta Office Hours). Данный форк адаптирован для кроссплатформенного использования (Windows Desktop + Cloud).

Если вы автор или знаете автора оригинальной версии — напишите, пожалуйста, в issues.

## Совместимость

Desktop macOS (локальный и облачный), Desktop Windows (локальный backend).

## Лицензия

MIT