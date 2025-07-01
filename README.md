# DSLogic-spi_tpm-Clevis-decoder
Модифицированный протокольный декодер для DSView (DSLogic), позволяющий перехватывать и распознавать данные Clevis на шине SPI-TPM.

## Описание

DSView — это GUI для приборов DreamSourceLab (логические анализаторы, осциллографы и т.д.), построенный на базе открытого проекта sigrok.  
Все декодеры протоколов реализованы в виде модулей Python и загружаются DSView из библиотеки `libsigrokdecode`.  
Данный репозиторий содержит два расширения родного декодера SPI-TPM:

- **pd(ClevisKey).py**  
  Извлекает только ключ Clevis.
- **pd(ClevisKey+ClevisJSON).py**  
  Дополнительно извлекает полный JSON-объект, где хранится ключ. Рекомендуется к использованию.

## Установка

1. Закройте DSView, если он запущен.
2. Перейдите в папку с декодерами:
   - **Windows**: `C:\Program Files\DSView\decoders\spi_tpm`
   - **Linux**: `/usr/local/share/libsigrokdecode4DSL/decoders/spi_tpm`
3. Сделайте резервную копию родного `pd.py`.
4. Скопируйте из этого репозитория один из кастомных декодеров:
   - `pd1.0(ClevisKey).py`
   - `pd1.1(ClevisKey+ClevisJSON).py`
5. Переименуйте выбранный файл в `pd.py`.

## Ссылки

- Оригинальный декодер SPI-TPМ:  
  https://github.com/ghecko/libsigrokdecoder_spi-tpm/blob/main/pd.py
- Документация sigrok по написанию декодеров:  
  https://sigrok.org/wiki/Protocol_decoder_HOWTO
