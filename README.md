# Indicator of public confidence in the Central Bank based on sentiment analysis
Данный репозиторий посвящён построению индикатора доверия к ЦБ посредством сентимент-анализа комментариев социальной сети.
В нём осуществляется сравнение различных подходов к решению поставленной задачи сентимент-анализа (классического ML, классических NN и LLMs).

Методология описана в статье: *Matevosova, A. (2025). Modelling Trust in the Central Bank Using Sentiment Analysis. Russian Journal of Money and Finance, 84(1), pp. 3–25.*


## Data
Данная папка содержит итоговые данные, используемые в расчётах
#### Файлы
- ec_comments.zip - собранные из групп СМИ в социальной сети ВКонтакте комментарии к постам экономической тематики
- comments_with_cb.csv - собранные из групп СМИ в социальной сети ВКонтакте комментарии к постам с упоминанием ЦБ
- marked_data.xlsx - набор размеченных комментариев: из собранных комментариев были случайным образом выбраны 10000 комментариев, которые затем были вручную размечены. Каждый комментарий отнесён к одному из трёх классов по эмоциональному окрасу: негативный (-1), нейтральный (0), позитивный (1)

## Data: comments on economic posts
Данная папка содержит результаты сбора комментариев к постам экономической тематики в социальной сети ВКонтакте

Рассматриваемые группы СМИ: aif_ru, expert_ru, izvestia, kommersant, mk_ru, rbc, ria, tassagency, vedomosti, vesti
#### Файлы
- Сomment_parser_for_posts_on_economic_topics.ipynb - код для сбора комментариев к постам экономической тематики в ВК
- post_id - папка, которая содержит id отобранных постов экономической тематики для каждой группы СМИ
- {group_name}_ec_comments_all.csv - собранные комментарии к постам экономической тематики для group_name

## Data: comments on posts mentioning the Central Bank
Данная папка содержит результаты сбора комментариев к постам с упоминанием ЦБ в социальной сети ВКонтакте

Рассматриваемые группы СМИ: aif_ru, expert_ru, izvestia, kommersant, mk_ru, rbc, ria, tassagency, vedomosti, vesti
#### Файлы
- Сomment_parser_for_posts_on_economic_topics.ipynb - код для сбора комментариев к постам с упоминанием ЦБ в ВК
- post_id - папка, которая содержит id отобранных постов с упоминанием ЦБ для каждой группы СМИ
- {group_name}_comments_with_cb_all.csv - собранные комментарии к постам с упоминанием ЦБ для group_name

## Indicators
Данная папка содержит результаты построения индикатора доверия к ЦБ на основе различных моделей сентимент-анализа
#### Файлы
- Indicator.ipynb - ноутбук для построения индикатора на основе результатов сентимент-анализа
- Annual - папка, в которой содержатся результаты построения индикаторов с годовой частотой
- Monthly - папка, в которой содержатся результаты построения индикаторов с ежемесячной частотой
- Daily - папка, в которой содержатся результаты построения индикаторов с ежедневной частотой
- Relevance_and_Stability - папка, в которой содержатся результаты проверки стабильности индикатора и его релевантности (посредством сопоставления с чистым доверием на основе опросов ФОМ)
#### В таблицах:
- indicator - основной индикатор доверия к ЦБ, построенный при использовании конкретной модели сентимент-анализа. Он использует способ формирования единого показателя тональности = Ppos-Pneg (основной способ)
- indicator2 - альтернативный способ расчёта индикатора на основе меток классов

## Models
В данной папке рассматриваются различные модели для этапа сентимент-анализа комментариев
### Models/Сlassical_machine_learning_models, Models/Classical_neural_networks, Models/RuBERT_fine-tuning
- Classical_ML.ipynb - ноутбук с финальными ML моделями
- Classical_NN.ipynb - ноутбук с финальными моделями нейронных сетей
- Classification_RuBERT_fine-tuning.ipynb - ноутбук с тонкой настройкой (fine-tuning) RuBERT
- Test_{model_name}.xlsx - результаты работы моделей на тестовой выборке из 2000 комментариев
- ec_{model_name}.csv - результаты работы моделей на комментариях к постам экономической тематики (тексты самих комментариев см. в файле ec_comments.zip в папке Data)
- cb_{model_name}.csv - результаты работы моделей на комментариях к постам с упоминанием ЦБ (тексты самих комментариев см. в файле comments_with_cb.csv в папке Data)

Модель EconComments-RuBERT-sentiment: https://huggingface.co/AnastasiaMML/EconComments-RuBERT-sentiment - модель RuBERT после fine-tuning на 7000 комментариях

### Models/YGPT
- YandexGPT_Pro_Classifier.ipynb - ноутбук: взаимодействие с моделью
- YGPT_test.xlsx - ответы модели на тестовой выборке из 2000 комментариев
- YGPT_result_of_test.ipynb - ноутбук: результаты тестировани модели на тестовой выборке из 2000 комментариев

### Models/DeepSeek-r1-distill-qwen-7b
- DeepSeek-R1-Distill-Qwen-7B.ipynb - ноутбук: взаимодействие с моделью
- DeepSeek_test.xlsx - ответы модели на тестовой выборке из 2000 комментариев
- DeepSeek_result_of_test.ipynb - ноутбук: результаты тестировани модели на тестовой выборке из 2000 комментариев


