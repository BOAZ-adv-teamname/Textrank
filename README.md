# Textrank

### 사용법
* data: 문장 분리된 리스트 
``` python
import kss
kss.split_sentences(x)
```
* tr.loadSents()의 data 부분에 문장을 넣으면 `ratio`만큼 textrank로 요약된 문장 추출됨

``` python
tr = TextRank()
tagger = Mecab()
stopword = set([('있', 'VV'), ('하', 'VV'), ('되', 'VV') ])
tr.loadSents(data, lambda sent: filter(lambda x:x not in stopword and x[1] in ('NNG', 'NNP', 'VV', 'VA'), tagger.pos(sent)))
tr.build()
ranks = tr.rank()
tr.summarize(ratio = 0.33)
```

* 출처: https://bab2min.tistory.com/570
