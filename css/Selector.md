# 선택자 (Selector)

#### **CSS 선택자**는 CSS 규칙을 적용할 요소를 정의합니다.

## 기본 선택자

---

**1. 전체 선택자 (Universal Selector)**
`*`을 사용하여 모든 요소를 선택합니다.

```
* {
 color: green;
}
<!-- 모든 요소의 색을 green으로 만든다. -->
```

**2. 유형 선택자 (Type Selector)**
주어진 노드 이름을 가진 모든 요소를 선택합니다. ex) `h1`, `p`, `span`, `div`, `li`

```
li {
 color: blue;
}
<!-- 모든 'li'요소의 색을 blue로 만든다. -->
```

**3. ID 선택자 (ID Selector)**
`#`을 사용합니다. ID 특성에 따라 요소를 선택합니다. 문서 내에는 주어진 ID를 가진 요소는 하나만 존재해야합니다

```
#special {
 color: pink;
}
<!-- 'ID' 속성의 값이 special인 요소의 색을 pink로 만든다. -->
```

**4. 클래스 선택자 (Class Selector)**
`.`을 사용하여 주어진 `class` 특성을 가진 모든 요소를 선택합니다.

```
.red {
 color: yellow;
}
<!-- class 속성의 값이 red인 요소의 색을 yellow로 만든다. -->
```

**5. 특성 선택자 (Attribute)**
`[]`을 사용하요 주어진 특성을 가진 모든 요소를 선택합니다.

```
a[href] {
  color: purple;
}
<!-- 'a' tag중에 herf 속성 값을 가진 요소들을 purple로 만든다. -->
```

## 복합 선택자

---

1. **일치 선택자 (Basic Combinator)**
   두 가지 조건을 동시에 만족하는 요소를 선택한다.

```
span.ABC {
  color: blue;
}
<!-- span태그의 class 속성의 값이 ABC인 요소의 색을 blue 로 만든다. -->
```

**2. 자식 선택자 (Child Combinator)**
`>`를 사용하여 자식 요소를 선택한다.

```
ul>.ABC {
  color: blue;
}
<!-- ul태그의 '자식요소' 중 class 속성의 값이 ABC인 요소의 색을 파란색으로 만든다. -->
```

**3. 하위 선택자 (Descendant Combinator)**
`띄어쓰기`를 사용하여 하위 요소를 선택한다.

```
div .ABC {
  color: blue;
}
<!-- div태그의 '하위 요소' 중 class 속성의 값이 ABC인 요소의 색을 파란색으로 만든다. -->
```

**4.인접 형제 선택자 (Adjacent Sibling Combinator)**
`+`를 사용하여 주어진 요소의 다음 형제 요소를 선택한다.

예를 들어 아래와 같은 코드가 있다.

```
<ul>
  <li>토마토</li>
  <li>사과</li>
  <li class="orange>오렌지</li>
  <li>복숭아</li>
  <li>포도</li>
</ul>
```

이때 다음은 orange클래스의 다음 형제요소인 복숭아를 선택하게 된다.

```
.orange+li {
  color: blue;
}
<!-- 복숭아의 색을 파랗게 만든다. -->
```

**5. 일반 형제 선택자 (General Sibling Combinator)**
`~`를 사용하여 주어진 모든 요소의 다음 형제 요소를 선택한다.

예를 들어아래와 같은 코드가 있다.

```
<ul>
  <li>토마토</li>
  <li>사과</li>
  <li class="orange>오렌지</li>
  <li>복숭아</li>
  <li>포도</li>
</ul>
```

이때 다음은 orange클래스의 다음 형제요소인 복숭아와 포도를 선택하게 된다.

```
.orange~li {
  color: blue;
}
<!-- 복숭아와 포도의 색을 파랗게 만든다. -->
```
