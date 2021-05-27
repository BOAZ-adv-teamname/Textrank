# Textrank

### 사용법
tr.loadSents()의 data 부분에 문장을 넣으면 textrank로 요약된 문장 추출됨

``` python
tr = TextRank()
tagger = Mecab()
stopword = set([('있', 'VV'), ('하', 'VV'), ('되', 'VV') ])
tr.loadSents(data, lambda sent: filter(lambda x:x not in stopword and x[1] in ('NNG', 'NNP', 'VV', 'VA'), tagger.pos(sent)))
tr.build()
ranks = tr.rank()
tr.summarize(0.2)
```

* 출처: https://bab2min.tistory.com/570
