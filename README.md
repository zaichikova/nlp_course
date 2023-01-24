# Распознавание ключевых навыков кандидатов в текстах вакансий
В работе рассматривается подход к извлечению ключевых навыков кандидатов из текстов вакансий на русском языке с помощью решения задачи распознавания именованных сущностей.

## Dataset

В рамках данной работы с ресурса HeadHunter собраны вакансии по запросу «Программист» для региона «Россия» через специальный API. Процесс загрузки вакансий реализован в файле 'Download_vac_hh.ipynb'

Затем отбирались вакансий с отсутствием информации в поле «key skills» и применялись процедуры
удаления html тегов, удаления стоп-слов из библиотеки nltk и токенизация из библиотеки razdel.

Для обучения и тестирования модели было случайным образом отобрано 20 вакансий из 297 и произведена ручная разметка ключевых навыков в вакансиях. В результате разметки было сформировано 172 предложения,
11 из которых были направлены для тестирования, 11 для валидации и 150 для обучения. Данные для обучения расположены в архиве 'dataset.rar'.


## Models

В качестве модели использовалась W2NER. Файлы для запуска модели находятся в архиве 'W2NER-main.zip'
Парметры модели находятся в файле /config/example.json
Данные для обучения необходимо расположить в папке /data/example


## Обучение модели

>> python main.py --config ./config/example.json

## Библиотеки

```
- numpy (1.21.4)
- torch (1.12.1)
- gensim (4.1.2)
- transformers (4.13.0)
- pandas (1.3.4)
- scikit-learn (1.0.1)
- prettytable (2.4.0)
```
## Результаты

Precision = 0.83
Recall = 0.51
F1 = 0.58

## Authors
Зайчикова Анастасия
