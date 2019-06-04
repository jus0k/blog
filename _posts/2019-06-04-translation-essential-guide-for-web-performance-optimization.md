---
layout: post
title: "[번역] 웹 성능 최적화를 위한 필수 가이드 - 1부: 이미지 최적화"
---

이 글은 [UX Planet](https://uxplanet.org/)에 [Nick Babich](https://uxplanet.org/@101)가 올린 [Essential Guide for Web Performance Optimization
Part 1: Optimizing Images](https://uxplanet.org/essential-guide-for-web-performance-optimization-1b883d638a1?fbclid=IwAR3C95-22_pEvc_rgr_IFzjNuyOcemO-mRsnbbAmUMUafvb97bAPB8hCg3U)를 번역한 글입니다.

<br>

***

<br>
# 웹 성능 최적화를 위한 필수 가이드 - 1부: 이미지 최적화
웹 성능은 까다로운 주제입니다. 느린 로딩 속도를 일으키는 요인들은 굉장히 많습니다. 이번 아티클에서는, 이미지라는 요인에 대해 초점을 맞춰 이야기하고자 합니다.
이미지는 여전히 웹에서 가장 큰 원인 중 하나입니다. 이미지는 보통 큰 파일 사이즈를 가지고 있기 때문에, 이미지를 로드하는 것은 엄청난 양의 대역폭을 사용합니다.

> HTTP 아카이브에 따르면, 웹 페이지를 가져오기 위해 전송되는 데이터의 60%는 JPEG, PNG 및 GIF로 구성된 이미지입니다.

이미지를 최적화하면 눈에 띄게 웹 페이지를 로딩을 향상시킴으로써, 사용자의 만족도를 향상시키는 결과를 가져옵니다.  
<br>
## 이미지를 최적화 해야 하는지 어떻게 알 수 있나요?  
[웹사이트 속도 테스트 이미지 분석 도구](https://webspeedtest.cloudinary.com/)를 사용해서 사이트를 검사하면, 이미지를 더 잘 최적화하는 방법들을 알려줄 것입니다.

![1](https://user-images.githubusercontent.com/43605468/58860906-2c94e180-86e8-11e9-99bd-0a23287493e2.png)
*Medium의 이미지 분석 결과*

이제, 실제 규칙에 대해 알아봅시다.  

<br>
### 1.  페이지 당 총 이미지 수 줄이기
구글에 의하면, 이미지는 페이지 전환에서 2번째로 높은 예측변수입니다. 많은 경우에서, 페이지가 가지고 있는 이미지의 수와 로딩 시간의 직접적인 연관성을 파악할 수 있습니다.

![2](https://user-images.githubusercontent.com/43605468/58860910-2f8fd200-86e8-11e9-89b1-e0a13ec91f9d.png)
*Source: Google research from 2016*  

<br>
### 2. 이미지 압축
이미지 파일 크기가 작을수록, 사용자에게 더 좋은 네트워크 경험을 제공할 수 있습니다. [Squoosh](https://squoosh.app/)는 최적의 압축 수준에서 이미지를 최적화하는데 도움을 줍니다. 이 도구는 이미지의 퀄리티를 보존하면서, 눈에 띄게 이미지 크기를 줄일 수 있습니다.  

<br>
### 3. PNG, JPEG, SVG 파일의 크기 줄이기
다음과 같이 이미지 형식에 따라 최적화하세요.
- JPEG: [MozJPEG](https://github.com/mozilla/mozjpeg) 나 [Guetzli](https://github.com/google/guetzli) 를 통해 JPEG를 실행하세요. Mozila에 따르면, JPEG 파일 크기를 최대 10% 까지 줄일 수 있다고 합니다.
- PNG: [Pingo](http://css-ig.net/pingo)에서 PNG 최적화를 도와줄 수 있습니다.
- SVG: 벡터 그래픽은 [SVGO](https://www.npmjs.com/package/svgo)를 사용하세요.  

<br>
### 4. 이미지 크기를 적절하게 지정하기
이미지 크기를 조정하는 것은 브라우저(특히, 모바일 환경에서)에 큰 부담이 가는 작업입니다. 그러므로, 불필요한 이미지 크기 조정 비용을 줄이려고 노력하세요. [Responsive Image Breakpoints Generator](https://www.responsivebreakpoints.com/)를 사용해서 적절한 크기의 이미지를 만드세요.

![3](https://user-images.githubusercontent.com/43605468/58860916-31599580-86e8-11e9-9e5d-04361c3364ef.png)

이상적으로는 이 과정을 자동화해야 합니다. [Cloudinary](https://cloudinary.com/) 나 [Imgix](https://www.imgix.com/) 서비스는 이런 점을 도와줄 수 있습니다.

[imaging-heap](https://github.com/filamentgroup/imaging-heap)를 사용해서 반응형 마크업의 효율을 확인할 수 있습니다. 이 간단한 커멘드 라인 도구는 뷰포트 크기와 디바이스 픽셀 비율 간의 효율성을 보여줍니다.

![4](https://user-images.githubusercontent.com/43605468/58860919-33bbef80-86e8-11e9-93a8-e9178fb7e832.png)
*[imaging-heap](https://github.com/filamentgroup/imaging-heap) 결과물*  

<br>
### 5. 사용하지 않는 이미지 삭제하기
사용하지 않는 에셋을 정리하세요. CSS의 *display:none* 속성을 검색해서 이러한 이미지를 찾아낼 수 있습니다.
또한, 기본적으로 로딩되지만, 표시되지 않을 수도 있는 이미지(예를 들어 케러셀 슬라이더에 있는 이미지)를 찾아내세요.  

<br>
### 6. 지연 로딩 (Lazy loading)
지연 로딩은 사용자가 이미지를 볼 필요를 느낄 때 까지, 브라우저에서 이미지의 로딩을 지연시키는 웹 성능 패턴입니다. 일반적으로, 이미지 로딩은 스크롤(사용자가 페이지에 적절한 부분에 닿을 때, 이미지가 비동기적으로 필요에 의해 로드 되는 것) 할 때 실행됩니다.

![5](https://user-images.githubusercontent.com/43605468/58860923-3585b300-86e8-11e9-8b09-bb830020e8da.png)

지연 로딩은 아직 브라우저 자체에서 기본적으로 지원되지 않습니다. 하지만 Javascript 라이브러리를 사용해서 이 기능을 추가할 수 있습니다. 이를 위해 [lazysizes](https://github.com/aFarkas/lazysizes)나 [yall.js](https://github.com/malchata/yall.js)를 사용할 수 있습니다.  

<br>
### 7. 무거운 GIF 이미지 없애기
페이지에서 애니메이션 GIF 이미지를 사용하면 렌더링 성능과 대역폭에 문제가 발생합니다. 큰 애니메이션 GIF 이미지를 추가하는 대신, [AV1](https://en.wikipedia.org/wiki/AV1) 또는 [WebM](https://www.webmproject.org/) 비디오를 사용해보세요.  

<br>
### 8. CDN 선택하기
얼마나 많은 이미지를 가지고 있는지에 따라, CDN에 푸시할 수 있습니다. 그러나 CDN이 압축 및 변환을 수행하는지 다시 한 번 체크해보세요.  

<br>
## 이미지 최적화를 위한 툴
이 아티클에서 언급한 툴은 아래에서 가져온 것입니다.  
[Image Optimization | UXPRO](https://uxpro.cc/toolbox/web-design/image-optimization/)  
[Performance Testing | UXPRO](https://uxpro.cc/toolbox/web-design/performance-testing/)