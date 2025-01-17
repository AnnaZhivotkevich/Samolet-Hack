# Samolet-Hack
# Проект: Автоматическое определение скидок в телефонных разговорах
# Команда
Moivres
# Участники команды:
Владимир Галкин\
Артемий Мосин\
Анна Животкевич\
Илья Поддуба\
Константин Корнилов
# Описание задачи
Компания "Самолет" ежемесячно обрабатывает сотни тысяч телефонных звонков, существенная часть из которых переходит во встречи и покупки. Важным фактором, влияющим на принятие решения клиентом, является предложенная компанией скидка. Наша задача - разработать алгоритм, способный анализировать транскрибированные тексты телефонных разговоров и определять, была ли предложена скидка клиенту, а также выявлять размер этой скидки.
# Использованные инструменты и технологии
Python\
PyTorch\
SpaCy\
Transformers (Hugging Face)\
Scikit-learn\
Flask (для создания API)
# Обучение модели 
Для обучения модели запустите main.py:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
python main.py
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
# Инференс
Для инференса загрузите в директорию файл gt_test.csv и запустите:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
python inference.py
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
# Инструкция для использования api
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Шаг 1: Перестановка виртуального окружения

–Чтобы все работало, на всякий случай переустановите виртуальное окружение:

rm -rf .venv

–Создайте новое виртуальное окружение:

python3 -m venv .venv
source .venv/bin/activate

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Шаг 2: Установка зависимостей

–Установите зависимости при помощи файла `requirements.txt`:

pip install -r requirements.txt

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Структура директории:


pythonProject/
│
├── model/
│   ├── config.json
│   ├── model.safetensors
│   ├── special_tokens_map.json
│   ├── tokenizer.json
│   ├── tokenizer_config.json
│   └── vocab.txt
│   
│
├── app.py
├── download_model.py
├── requirements.txt
├── test.txt
└── .venv/


Шаг 3: Запуск сервера

Теперь запустите сервер (просто запустите app.py удобным способом).

После запуска сервер будет доступен по адресу `http://127.0.0.1:5001`.

- Для проверки состояния сервера: `http://127.0.0.1:5001/`.

- Для отправки предсказания:



curl -X POST http://127.0.0.1:5001/predict -H "Content-Type: application/json" -d '{"text": "Hello, this is a test."}'



Если все настроено правильно, сервер должен вернуть JSON.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
# Docker образ
Содержит только модель, не содержит api\
Чтобы скачать Docker образ, запустите
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
docker pull ghcr.io/ob3r/hack:latest
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
