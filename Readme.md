# Домашние задания по курсу [LLM Driven Development](https://otus.ru/lessons/llm-driven-development/?ysclid=md1rqcx0o786174870) от OTUS

### ИТОГИ

### 1) Подготовка данных для дообучения LoRA
Использовала [synthetic-data-kit](https://github.com/meta-llama/synthetic-data-kit).  
- Подготовка данных о товарах  
- Разбиение на части для поэтапной генерации QA-пар  
- Генерация вопросов и ответов  
- Преобразование QA-пар в формат для дообучения  
- Формирование датасета сообщений: `system → user → assistant`  

**Пример формата данных:**
```json
{
  "messages": [
    {"role": "system", "content": "You are a helpful assistant."},
    {"role": "user", "content": "What is the price of the item called 'Polka Style 30x4.4x12.7 cm'?"},
    {"role": "assistant", "content": "$599"}
  ]
}
```

### 2) Дообучение LoRA на Qwen2-0.5B-Instruct
Ранг матриц (r) = 16  
Всего 1 эпоха  

### 3) Результаты работы модели после LoRA
Модель корректно отвечает на вопросы о товарах: точно указывает цены, размеры, вес и возможности кастомизации. Исходная модель давала общие, неточные ответы и часто добавляла лишние пояснения.

