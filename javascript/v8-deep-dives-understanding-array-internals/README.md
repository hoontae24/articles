---
title: "[번역] V8 Deep Dives: Array 내부 파헤치기"
description:
date: 2021-12-22
category: javascript
tags: [javascript, v8, array]
---

![V8 Array](./img/v8-array.png)

> 이 글은 아래의 원문을 번역한 글입니다. 오역이 있을 수 있으니, 영어에 능하신 분은 원문을 읽으시는 것을 추천드립니다. \
> 원문: [[V8 Deep Dives] Understanding Array Internals](https://itnext.io/v8-deep-dives-understanding-array-internals-5b17d7a28ecc)

이 시리즈의 [이전 편](https://itnext.io/v8-deep-dives-understanding-map-internals-45eb94a183df)에서 ES6에서 도입된 표준 내장 객체(_standard collections_)인 Map과 Set에 대해 살펴보았습니다. 이번에는 JavaScript 배열에 대해 살펴볼 것입니다.

본질적으로 리스트와 비슷한 객체인 배열은 언어의 핵심 기능 중 하나이고, 모든 자바스크립트 개발자는 배열로 작업한 확실한 경험을 가지고 있습니다. 이 글은 배열의 API를 이해시키는 것이 아니라 메모리 구조, 크기 제한, 기타 세부 구현 등 V8의 JS Array 내부 구현의 다양한 측면을 간략하게 살펴보는 것을 목표로 합니다.

또한 혼란스럽지 않도록, 앞으로의 내용에서는 V8이 64비트 시스템에서 실행된다고 가정하겠습니다.

**TL;DR**을 좋아하는 분들은 요약이 있는 이 글의 마지막 섹션으로 건너뛸 수도 있습니다.

주의: 면책 조항. 아래 작성된 내용은 Node.js(정확히는 [@49342fe](https://github.com/nodejs/node/commit/49342fe6f2ca6cedd5219d835a0a810e6f03cdd7)) 최신 개발 버전과 함께 번들로 제공되는 V8 8.9에 명세된 구현 세부 정보입니다. V8 버전에 따라 구현 세부 정보는 변경될 수 있기 때문에 스펙을 벗어나는 동작을 기대해서는 안 됩니다.
