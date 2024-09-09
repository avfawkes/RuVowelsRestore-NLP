# RuVowelsRestore-NLP
LM для восстановления гласных в тексте

![RuVowelRestore-title](https://github.com/user-attachments/assets/1e63fb63-fccb-47ef-a03b-6c972403ad5b)

### Описание/ Description
Создание модели для восстановления пропущенных гласных в тексте. Практическое применение сомнительно, но было полезно при знакомстве с NLP. Задача была решена дообучением модели перевода с украинского на русский на датасете с вырезанными гласными. Это показалось самым простым решением, т.к. синтаксис языков схож и было предположение, что можно обойтись без обучения токенизатора и это не сильно скажется на качестве работы и количестве токенов. В итоге результат удовлетворительный, наверняка можно его улучшить даже этим подхом, если взять датасет побольше, но это уже затруднительно на бесплатных GPU. Если знаете, как сделать лучше, дайте, пожалуйста, знать в [`обсуждении`](https://github.com/avfawkes/RuVowelsRestore-NLP/issues/new/choose)

- [HuggingFace Hub model repo](https://huggingface.co/avfawkes/marian-finetuned-to-restore-ru-vowels) - репозиторий модели в HuggingFace Hub

- [train.ipynb](https://github.com/avfawkes/RuVowelsRestore-NLP/blob/main/train.ipynb) - ноутбук дообучения модели. Также можно посмотреть на [Kaggle](https://www.kaggle.com/code/avfawkes/ruvowelsrestore)

- [HuggingFace Helsinki-NLP/opus-mt-uk-ru](https://huggingface.co/Helsinki-NLP/opus-mt-uk-ru) - модель, которую дообучал

- [HuggingFace Helsinki-NLP/opus-100](https://huggingface.co/datasets/Helsinki-NLP/opus-100) - датасет

### Инференс/ Inference

- [HuggingFace Space](https://huggingface.co/spaces/avfawkes/ru-vowels-restore) - инференс модели в HuggingFace Space с помощью gradle. Отвечает медленно, так как он бесплатный без GPU.

Либо так:

```
from transformers import pipeline

pipe = pipeline("translation", model="avfawkes/marian-finetuned-to-restore-ru-vowels")
pipe('Кгд  прхл в дрвн, ббшк бл чнь рд мн вдть.')
```
