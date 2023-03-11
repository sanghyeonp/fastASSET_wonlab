# fastASSET Wonlab version

 기존 `fastASSET` README는 [here](./README_ori.md).

원래 `ASSET`이라는 R package가 Bioconductor에서 제공을 함 ([here](https://bioconductor.org/packages/release/bioc/html/ASSET.html)).  
하지만, 이 package에서 제공하는 ASSET을 돌릴 수 있는 function은 `h.traits()` 인데, 이녀석은 computationally slow 하다는 것이 단점.  
그래서, `https://github.com/gqi/fastASSET` 여기에서, `fast_asset()`이라는 function을 만듬.  
*(지금은 기존 ASSET R package에 이 `fast_asset()` function이 incorporate 되어있음.) -> 하지만 github에 있는 version으로 다운로드 받는 걸 추천. 왜냐하면 R package로 다운로드 받으면 example data가 없는데, GitHub version 다운로드 받으면 `data`폴더에 example data가 있음.*  

`fast_asset()`은 더 빨라질 수 있었던 이유가:  
- effective sample size를 direct하게 input으로 넣을 수 있어서. (`h.traits()`은 number of case, control 각각 넣어서 따로 계산을 해주는 process가 필요함.)

Wonlab 용 `fast_asset()` -> `fast_asset_wonlab()`을 따로 만든 이유:
- `fast_asset()`이 two-sided test만 할 수 있도록 고정되어있음.
- `ASSET`을 활용한 Meta-analysis를 할 수 없게 코드가 짜져있음.

---
## 설치하기

```
devtools::install_github("sanghyeonp/fastASSET_wonlab")
```

---
## 새로운 function 만들고 적용 방법
Step 1. Function 만들고  
Step 2. Function에 대한 roxygen comment를 달고  
Step 3. Root package directory에서 R 세션 실행 후  
Step 4. 아래 commend 실행  
```
library(devtools)
document()
```
Step 5. Git push to repository  
Step 6. Install!

---
Reference:
- Qi, G., Chhetri, S. B., Ray, D., Dutta, D., Battle, A., Bhattacharjee, S.\*, & Chatterjee, N.\* (2022). Genome-Wide Large-Scale Multi-Trait Analysis Characterizes Global Patterns of Pleiotropy and Unique Trait-Specific Variants. bioRxiv.
