# Fine-tuning RuBERT 
## Модели
- Fine-tuning RuBERT на 1000 комментариях из обучающей выборки -> Fine-tuned RuBERT_1000
- Fine-tuning RuBERT на 7000 комментариях из обучающей выборки -> Fine-tuned RuBERT_7000

https://huggingface.co/AnastasiaMML/EconComments-RuBERT-sentiment - модель после fine-tuning на 7000 комментариях

## Файлы:
- Classification_RuBERT_fine-tuning.ipynb - ноутбук с тонкой настройкой (fine-tuning) RuBERT
- Test_{model_name}.xlsx - результаты работы моделей на тестовой выборке из 2000 комментариев
- ec_{model_name}.csv - результаты работы моделей на комментариях к постам экономической тематики (тексты самих комментариев см. в файле ec_comments.zip в папке Data)
- cb_{model_name}.csv - результаты работы моделей на комментариях к постам с упоминанием ЦБ (тексты самих комментариев см. в файле comments_with_cb.csv в папке Data)


