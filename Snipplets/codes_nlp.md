```python
# Biblioteca nlpnet
import nlpnet
nlpnet.set_data_dirt('pos-pt/')
tagger = nlpnet.POSTagger()
tagger.tag('A rã arranha a aranha e a aranha arranha a rã.')
```

```python
# Biblioteca do spacy para usar POS
doc2 = nlp(u'A rã arranha a aranha e a aranha arranha a rã.')
tokens2 = [token for token in doc2]
[(token.orth_, token.pos_) for token in doc2]
```
