# RuVowelsRestore-NLP
LM для восстановления гласных в тексте

![RuVowelRestore-title](https://github.com/user-attachments/assets/1e63fb63-fccb-47ef-a03b-6c972403ad5b)

https://huggingface.co/avfawkes/marian-finetuned-to-restore-ru-vowels

https://huggingface.co/spaces/avfawkes/ru-vowels-restore

https://www.kaggle.com/code/avfawkes/ruvowelsrestore

```
from transformers import pipeline

pipe = pipeline("translation", model="avfawkes/marian-finetuned-to-restore-ru-vowels")
pipe('Кгд  прхл в дрвн, ббшк бл чнь рд мн вдть.')
```
