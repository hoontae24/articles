---
title: Typed Array
description:
date: 2021-11-04
category: javascript
tags: [javascript, data structure, array]
---

<!--
- Array save data sequentially each item type is same

- ArrayBuffer
- DataView
  - TypedArray
 -->

한 블로그의 포스팅을 보던 중, 관심이 생기는 문구를 봤습니다. "[javascript의-배열이-실제로는-배열이-아닌-이유](https://evan-moon.github.io/2019/06/15/diving-into-js-array/#javascript의-배열이-실제로는-배열이-아닌-이유)"라는 말이었습니다. 잠깐동안 "이게 무슨 말이지?"라고 생각하다가 글의 내용을 계속해서 읽었는데, 그 내용은 자바스크립트의 **배열**이 실제로 연속적인 구조를 가지지 않는다는 것이었습니다. 내용을 이해하는 것이 크게 어렵지는 않았지만 평소 자바스크립트로 개발을 하면서도 고려하지 않던 부분이었습니다. 정확히 말하면 일반적인 배열의 인터페이스를 제공하기 때문에 배열로 여기며 사용했고, Low Level 관점에서 실제 구현이 어떠한지는 고려하지 않았습니다.

배열은 개발자들이 많이 사용하는 자료구조 중에서 빼 놓을 수 없는 타입입니다. 자주 사용하는만큼 배열처럼 동작하지 않는 자바스크립트의 배열은 어떻게 다른지 궁금해졌습니다. _'아주 저수준의 구현까지는 아니더라도 원리를 이해하고 코드의 질을 향상시키고 성능 이점을 고려할 수 있는 정도의 지식은 가져야하지 않을까'_. 이 글에서는 자바스크립트 Array와 배열처럼 다룰 수 있게 해주는 ArrayBuffer에 대해 살펴보겠습니다.

## Array is object

## ArrayBuffer

## TypedArray
