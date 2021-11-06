---
title: Typed Array
description:
date: 2021-11-06
category: javascript
tags: [javascript, arraybuffer, typedarray]
---

프로그래밍에 있어 빠질 수 없는 자료구조 중 하나는 바로 "배열"일 것입니다. 자바스크립트에는 "Array"라는 전역 객체로 배열을 사용할 수 있습니다. (_"Array"를 번역하면 "배열"이지만_) 실제로 자바스크립트의 Array는 일반적으로 컴퓨터과학에서 다루는 "[배열](https://ko.wikipedia.org/wiki/배열)"과는 다릅니다. 엔진의 구현에 따라 다르지만 JS Array는 기본적으로 객체이며, 연속적인 데이터 저장을 보장하지 않습니다.

JIT 컴파일러를 사용하는 V8과 같은 엔진에서는 개선된 부분이 있지만, 연속성과 고정 타입을 늘 강제할 수는 없습니다. 만약 파일이나 이미지 등의 바이너리 데이터를 다룬다면 연속적인 데이터 구조를 사용하는 것이 성능에 도움이 될 수 있습니다. 그러한 문제들을 위해 ArrayBuffer와 TypedArray를 사용하면 해결할 수 있습니다.

## ArrayBuffer

## TypedArray

## Examples for Threejs
