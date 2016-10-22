# NLTK - примеры

## Упрощение тегов частей речи

```python
from nltk.tag import map_tag
simplify = lambda x: [(word, map_tag('en-ptb', 'universal', tag)) 
                      for word, tag in x]
```

## Предобработка - токенизация и выделение частей речи

```python
from nltk.tokenize import word_tokenize, sent_tokenize
from nltk.tag import pos_tag
sents = sent_tokenize(text)
sents = [word_tokenize(s) for s in sents]
sents = [pos_tag(s) for s in sents]
```

