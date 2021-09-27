---
title: 리액트에서 CSS-in-JS는 어떻게 동작할까?
description: 자바스크립트를 이용하여 스타일을 적용할 수 있는 CSS-in-JS가 리액트에서 어떻게 동작하는지 알아보겠습니다.
date: 2021-09-26
category: react
tags: [react, css-in-js]
---

![CSS-in-JS on REACT](./img/css-in-js-on-react.png)

[팀 버너스리](https://namu.wiki/w/팀%20버너스리)가 고안한 [웹](https://namu.wiki/w/월드%20와이드%20웹?from=웹)이 등장한 이래로 많은 웹 서비스 기술들이 생기고 사라졌습니다. 하지만 여전히 [HTML](https://namu.wiki/w/HTML)은 우리에게 중요한 기술로 남아 있습니다. 또한 CSS 역시 웹 문서의 스타일을 꾸미기 위해 사용하는 강력한 기술입니다. 웹 개발자라면 HTML과 CSS로 이루어진 웹 문서에 대한 이해가 필수적일 것입니다. React, Vue 등 많은 프론트엔드 기술이 있지만 이것들 역시 더 효과적이고 매력적인 웹 문서(또는 웹 페이지)를 만들기 위한 도구일 뿐입니다.

저 역시 프론트엔드 개발에서 React를 주로 사용하지만 HTML과 CSS, Javascript를 이용한 가장 기본적인 부분을 알아야 할 필요를 느낄 때가 많습니다. React를 사용하더라도 CSS를 적용하는 방법은 다양합니다. 그 중 저는 [MUI](https://mui.com), [Styled-components](https://styled-components.com) 등의 라이브러리를 사용하면서 CSS-in-JS를 주로 다루었습니다. 자바스크립트를 통해 동적인 CSS를 생성할 수 있는 **CSS-in-JS**는 어떤 방식으로 CSS를 적용할까요?

> 이번 예시 코드는 `React`에서 동작하는 `CSS-in-JS`를 살펴봅니다. 하지만 핵심 원리가 `React`에 의존하지는 않습니다.

## 1. CSS-in-JS

> Cascading Style Sheets (CSS) is a stylesheet language used to describe the presentation of a document written in HTML or XML. ([MDN](https://developer.mozilla.org/en-US/docs/Web/CSS))

CSS는 스타일 시트 언어입니다. 프로그래밍 언어가 아니기에 정적으로 동작합니다. 그래서 순수 CSS를 이용하여 복잡한 웹 페이지의 모든 스타일을 적용하고 관리하기란 꽤나 귀찮은 일이 아닐 수 없습니다. 그런 CSS를 보완하기 위해 여러 기술이 생겨났습니다. Sass, Less, Stylus 등의 CSS 전처리기 방식과 JSS, styled-components, emotion 등의 CSS-in-JS 방식 등이 있습니다.

CSS-in-JS 방식은 말 그대로 자바스크립트로 작성한 CSS입니다. JS를 통해 생성되기 때문에 runtime에서 시트가 생성, 관리되며 프로그래밍 언어의 동적 특징을 이용할 수 있습니다. 또한 몇몇 라이브러리는 Sass 등의 중첩 CSS 문법을 사용할 수도 있습니다.

## 2. Libraries

### 2.1 conditional styles

#### 2.1.1 react-jss - class based styles (미리 모든 시트를 만들어둔다)

#### 2.1.2 react-jss - props based styles (각각의 컴포넌트를 각각의 시트에 매핑하고 각각의 시트를 변경시킨다)

#### 2.1.3 styled-components (변경될 때 마다 필요한 시트를 생성한다.)
