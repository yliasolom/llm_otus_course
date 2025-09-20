# Домашние задания по курсу [LLM Driven Development](https://otus.ru/lessons/llm-driven-development/?ysclid=md1rqcx0o786174870) от OTUS

# ИТОГИ

1) Подготовка данных для дообучения LoRA: использовала https://github.com/meta-llama/synthetic-data-kit. Подготовка данных о товарах, разбиение на части для поэтапной генерации QA-пар, генерация вопросов и ответов, преобразование QA-пар в формат для дообучения и формирование датасета сообщений: system → user → assistant. Пример формата данных:

{
  "messages": [
    {"role": "system", "content": "You are a helpful assistant."},
    {"role": "user", "content": "What is the price of the item called 'Polka Style 30x4.4x12.7 cm'?"},
    {"role": "assistant", "content": "$599"}
  ]
}

2) Дообучение LoRA на Qwen2-0.5B-Instruct: ранг матриц (r) = 16, всего 1 эпоха.

3) Результаты работы модели после LoRA: модель корректно отвечает на вопросы о товарах, точно указывает цены, размеры, вес и возможности кастомизации, в отличие от исходной модели, которая давала общие, неточные ответы и часто добавляла лишние пояснения.

