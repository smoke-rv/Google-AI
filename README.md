# Google AI - ADK Agents

Цей проєкт містить агентів, створених за допомогою Google ADK (Agent Development Kit).

## Налаштування

### 1. Створення .env файлів

Кожен агент потребує файл `.env` для налаштування API ключів.

**Для кожної директорії агента** (my_first_agent, True_Fake, QA_expert):

1. Скопіюйте `.env.example` → `.env`
2. Замініть `your_google_api_key_here` на ваш справжній Google API ключ

```bash
# Приклад для my_first_agent
cd my_first_agent
cp .env.example .env
# Відредагуйте .env та додайте ваш API ключ
```

### 2. Отримання Google API Key

1. Перейдіть до [Google AI Studio](https://aistudio.google.com/apikey)
2. Створіть або скопіюйте API ключ
3. Додайте його в файл `.env`

### 3. Запуск агентів

```bash
# Запустити веб-інтерфейс для всіх агентів
adk web
```

## Структура проєкту

```
Google AI/
├── my_first_agent/          # Перший агент
│   ├── .env                 # API ключі (НЕ в Git)
│   ├── .env.example         # Шаблон для .env
│   └── root_agent.yaml
├── True_Fake/               # Агент перевірки фактів
│   ├── .env
│   ├── .env.example
│   └── root_agent.yaml
└── QA_expert/               # Агент для аналізу Office документів
    ├── .env
    ├── .env.example
    ├── root_agent.yaml
    └── tools/
        └── office_reader.py
```

## ⚠️ Безпека

**ВАЖЛИВО:** Файли `.env` містять конфіденційні API ключі і **НЕ повинні** бути в Git!

- ✅ `.env.example` - в Git (без реальних ключів)
- ❌ `.env` - НЕ в Git (додано в `.gitignore`)

## Агенти

### my_first_agent
Базовий агент для початку роботи з ADK.

### True_Fake
Агент для перевірки фактів. Аналізує текст, витягує твердження та перевіряє їх через Google Search.

### QA_expert
Агент для аналізу Microsoft Office документів (.docx, .xlsx, .pptx). Витягує текст та відповідає на питання.
