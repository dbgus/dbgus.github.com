---
layout: post
title: 2021-07-20 TIL
subtitle: blockchain이란?
categories: TIL
tags: [TIL, blockchain]
---

## block chain이란?

> **block chain이란 말 그대로 데이터 블럭들이 chain 처럼 연결되어있는 형태를 말한다.**

### append-only
데이터를 추가하려면 블럭 형태의 데이터만 `추가`만 가능하며, 블럭이 추가 될 때에는 이전 블럭과 함께 연결이 됩니다.

모든 데이터는 다른 노드들을 가로질러 축적이 되며 이 때 데이터는 영구적으로 변경이 불가능해진다.
> In other words, blockchain is an immutable and distributed ledger.

### hash
해쉬의 특징은 다음과 같다
```
1. 뭘 넣든 비슷한 길이의 알수 없는 난수가 결과로 출력이 된다
2. 글자가 한글자만 바뀌어도 완전히 다른 결과가 출력이 된다
3. 출력값으로 입력값을 예측할 수 없다.
출처: https://needjarvis.tistory.com/239
```
해쉬는 `단방향`으로 암호화되어 복호화를 쉽게 할 수 없도록 만들어진 값입니다.

#### hash in blockChain
hash가 블록체인에서 사용되는 곳은 위 `append-only`에서 설명한 `다른 노드들...`이 부분에서 힌트를 얻을 수 있다. hashing된 값이 같으려면 동일한 input으로 암호화를 해야지만 같은 출력값을 얻을 수 있습니다. 각 노드별로 평범한 텍스트를 가지고 있고 이 노드들이 수천, 수만, 수억건이 된다면 파악이 힘들어질 것입니다. 새로운 블럭이 들어와 이전 데이터와 chain(연결)되면서 이전 데이터의 hash값을 추가해 가며 마지막 노드에 값이 동일하다면 모든 기록이 동일하다는 것을 알 수 있습니다. 



### 문제점
블록체인은 분산이라는 특성 때문에 대기 시간이 길어지고 처리량이 떨어진다는 문제점이 있습니다. 즉, 확장성에 대한 문제가 있습니다.




```출처
https://blog.liquid.com/what-is-blockchain-technology
https://velog.io/@kihyun/%EB%B8%94%EB%A1%9D%EC%B2%B4%EC%9D%B8
https://needjarvis.tistory.com/239
```