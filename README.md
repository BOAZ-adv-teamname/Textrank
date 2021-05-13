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

아직까지 문장이 길고 전처리 완전하게 되지 않아 아래 부분이 잘 계산되지 않음  
현재는 score = 3으로 고정해두었는데 추후에 이 부분 수정해야함
``` python
def summarize(self, ratio = 0.333):
        r = self.rank()
        ks = sorted(r, key=r.get, reverse=True)
        # score = int(len(r)*ratio)

        # 문장 수
        # if score < 3 : 
        #    score = len(r) 
        #elif score >= 3:
        #    score = 3
        #else:
        #    pass
        score = 3
```

* 출처: https://bab2min.tistory.com/570
