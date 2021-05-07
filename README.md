# Textrank

아직까지 문장이 길고 전처리 완전하게 되지 않아 아래 부분이 잘 계산되지 않음  
현재느 score = 3으로 고정해두었는데 이후에는 이 부분 수정해가면서 봐도 좋을 것 같음
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
