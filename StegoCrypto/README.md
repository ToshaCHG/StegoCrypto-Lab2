# StegoCrypto - Лабораторная работа №2

## Описание
В данной лабораторной работе реализованы и исследованы три метода стеганографии (LSB-встраивания) с использованием шифрования AES для защиты скрываемого сообщения.

## Зависимости
Для работы скрипта требуются следующие библиотеки Python:
* numpy
* pillow
* pycryptodome
* scikit-image
* matplotlib

## Установка зависимостей
Выполните в терминале (или в ячейке Colab):
pip install numpy pillow pycryptodome scikit-image matplotlib

## Запуск
1. Загрузите файл `src/lab2.ipynb` в Google Colab или Jupyter Notebook.
2. Убедитесь, что исходные изображения (`gradient.jpg`, `checkerboard.jpg`) находятся в корневой директории.
3. Запустите все ячейки кода по порядку.

## Параметры по умолчанию
В коде заданы следующие параметры:
* `MESSAGE` = "Hello, this is a secret message for the lab!" (встраиваемый текст)
* `PASSWORD` = "SuperSecretPassword123" (пароль для генерации ключа шифрования)
* Уровни заполнения (Payload): 1% и 5%.

## Пример обычного LSB
Для встраивания открытого текста используется функция:
`embed_lsb_sequential(cover, message_bytes)`

## Пример гибридного режима (Encryption + LSB)
1. Шифрование сообщения:
`encrypted_data = encrypt_message(message, password)`
2. Встраивание зашифрованных данных:
`stego_enc = embed_lsb_sequential(cover, encrypted_data)`

## Пример извлечения и расшифрования
1. Извлечение байтов из LSB:
`extracted_bytes = extract_lsb_sequential(stego_img)`
2. Расшифрование:
`decrypted_text = decrypt_message(extracted_bytes, password)`