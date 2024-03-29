# 선택자 우선 순위(Selector_Priority)

## 적용 순서에 따른 우선 순위 규칙

---

1. 같거나 서로 다른 선택자 방식으로 동일 요소에게 동일 속성을 뒤쪽에서 다른 값으로 재정의할 수 있다.
2. 서로 나누어진 CSS 코드인 경우 HTML 문서에 적용되는 순서에 따라 뒤쪽에서 동일 요소에게 동일 요소에게 동일 속성을 재정의 할 수 있다.
3. 선택자의 종류에 따른 우선 순위 큐칙(1항보다 우선)

- 주요 단일 선택자 방식에서 `id`, `class`, `tag` 순의 우선 순위
- 우선 순위 규칙에 의해 경우에 따라 뒤쪽에서 동일 속성을 재정의 할 수 없다.

4. 결합 관계 (복합 선택자 패턴)의 경우는 결합되는 선택자 방식의 정해진 점수를 합산하여 우선 순위를 정한다.
5. `!important`를 사용하여 가장 우선적으로 적용이 가능하다.

## 복합 선택자 패턴에서의 우선 적용 순위 규칙

---

| **선택자 방식**  |       **적용 예**        | **선택자 우선 순위** | **혼용 방식의 점수 산정** |       **비고**        |
| :--------------: | :----------------------: | :------------------: | :------------------------ | :-------------------: |
|    !important    | 속성:적용 값 !improtant; | 속성 기준 가장 우선  | 속성 기준 가장 우선       |  속성 기준 가장 우선  |
|  인라인 스타일   |         style=""         |          1           | 요소 기준 가장 우선       |  요소 기준 가장 우선  |
|    ID 선택자     |        #selector         |          2           | 100                       | #header > .logo > a{} |
|   CLASS 선택자   |        .selector         |          3           | 10                        | #header > .logo > a{} |
| 속성 기반 선택자 |       a[href*="#"]       |          3           | 10                        | #header > .logo > a{} |
|   가상 클래스    |         a:hover          |          3           | 10                        | #header > .logo > a{} |
|    가상 요소     |       span::after        |          3           | 10                        | #header > .logo > a{} |
|   태그 선택자    |            a             |          4           | 1                         | #header > .logo > a{} |
|   전체 선택자    |            \*            |          5           | 0                         | #header > .logo > a{} |
