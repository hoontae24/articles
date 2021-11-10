---
title: Typed Array
description:
date: 2021-11-06
category: javascript
tags: [javascript, arraybuffer, typedarray]
---

프로그래밍에 있어 빠질 수 없는 자료구조 중 하나는 바로 "배열"일 것입니다. 자바스크립트에는 "Array"라는 전역 객체로 배열을 사용할 수 있습니다. (_"Array"를 번역하면 "배열"이지만_) 실제로 자바스크립트의 Array는 일반적으로 컴퓨터과학에서 다루는 "[배열](https://ko.wikipedia.org/wiki/배열)"과는 다릅니다. JS Array는 기본적으로 객체 타입이며, 연속적인 데이터 저장을 보장하지 않습니다.

JIT 컴파일러를 사용하는 V8과 같은 엔진에서는 개선된 부분이 있지만, 연속성과 고정 타입을 늘 강제할 수는 없습니다. 만약 파일이나 이미지 등의 바이너리 데이터를 다룬다면 연속적인 데이터 구조를 사용하는 것이 성능에 도움이 될 수 있습니다. 그러한 문제들을 위해 ArrayBuffer와 TypedArray를 사용하면 해결할 수 있습니다.

## ArrayBuffer

> 버퍼(buffer)는 데이터를 한 곳에서 다른 한 곳으로 전송하는 동안 일시적으로 그 데이터를 보관하는 메모리의 영역이다.

**ArrayBuffer**의 의미적인 이해를 돕기 위해 **Buffer**의 뜻을 검색해봤습니다. Buffer와 Array가 결합된 ArrayBuffer는 "연속적인 데이터를 보관하는 메모리의 영역"정도로 이해할 수 있습니다. MDN에서는 "바이트로 구성된 배열"이라고 표현하고 있습니다.

하지만 ArrayBuffer는 데이터를 직접 다루는 기능을 제공하지 않습니다. TypedArray나 DataView 등의 객체를 이용하여 ArrayBuffer에 할당된 공간을 특정 타입의 데이터로 읽거나 쓸 수 있습니다. (_마치 ArrayBuffer는 종이, 다른 도구는 펜과 잉크 같은 역할이라고나 할까요..._)

```js
const buffer = new ArrayBuffer(8);
console.log(buffer.byteLength); // output: 8
```

위 코드와 같이 `ArrayBuffer(8)` 생성자를 이용해 고정된 길이(8)를 가진 객체를 직접 생성할 수 있습니다.

```js
const src =
  "https://www.google.com/images/branding/googlelogo/2x/googlelogo_color_272x92dp.png";

fetch(src)
  .then((res) => res.arrayBuffer())
  .then((buffer) => console.log(buffer.byteLength)); // output: 13504
```

이미지를 바이너리로 다룰 때, ArrayBuffer를 이용할 수 있습니다. 간단히 예제로 구글 홈페이지의 로고를 `fetch` API로 가져와 `ArrayBuffer`로 변환하는 코드입니다. 이미지 데이터의 버퍼 길이와 실제 구글 로고의 용량을 비교해보면 같은 것을 볼 수 있습니다. 실제 데이터의 용량만큼 ArrayBuffer가 생성됩니다.

```js
const src =
  "https://www.google.com/images/branding/googlelogo/2x/googlelogo_color_272x92dp.png";

fetch(src)
  .then((res) => res.arrayBuffer())
  .then((buffer) => {
    const blob = new Blob([buffer]);
    const dataUrl = window.URL.createObjectURL(blob);
    const img = document.createElement("img");
    img.src = dataUrl;
    document.body.appendChild(img);
  });
```

위 예제처럼 ArrayBuffer에 담긴 데이터를 이용해 Blob으로 변환해 이용할 수도 있습니다. 구글 메인 페이지에서 개발자도구로 실행해보세요. 실제로 ArrayBuffer를 위처럼 사용하지는 않지만 데이터가 저장되는 공간을 다루는 ArrayBuffer를 다양하게 활용할 수 있을 것입니다.

## TypedArray

## Examples for Threejs
