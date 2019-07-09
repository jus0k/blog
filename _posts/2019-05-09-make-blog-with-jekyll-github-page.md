---
layout: post
category: Development
title: "Jekyll + Github Page로 블로그 만들기"
---
블로그를 해야겠다 싶어서 몇 가지 서비스를 알아봤다. 브런치는 뭔가 쫌... 작가 신청도 해야하고 막 올리기에 부담이 되는 느낌이다. 전에 디자인 테이블을 듣다가 [끊임없이 배우는 디자이너]([https://www.designspectrum.org/designtable-s1e19](https://www.designspectrum.org/designtable-s1e19)) 에서 들었던 Jekyll 을 사용해서 만들어야겠다고 생각했다. 간단하게 만들 수 있을 줄 알았는데, 이것저것 찾아보다 보니 헷갈려서 시간이 꽤나 걸렸다. 

Local에서 Jekyll을 설치하고 만들어서 Github에 올리는 방법과, Github에서 원하는 테마를 찾아 내 저장소에 Fork 하고 거기서 수정하는 방법이 있었다. 어찌어찌 하다보니 만들긴 했는데 중간 과정이 짬뽕되서 무엇이 정확한 방법인지 헷갈린다 ㅜㅜ

단순하게 로컬에서 .md 파일로 포스트를 바로 github에 올리는 방법은 테마의 레포지토리를 Fork 하면 되기 때문에 jekyll을 따로 설치하지 않아도 되는 것 같다. 하지만 로컬에서 .md파일을 보면서 작성하고, 테마를 수정하려면 jekyll을 설치해야 한다.

어쨌든, 나는 [Tale]([https://github.com/chesterhow/tale](https://github.com/chesterhow/tale)) 테마를 이용해서 블로그를 만들었고, 포트폴리오 페이지도 따로 프로젝트 주소가 있기 때문에 기본 주소가 아닌 프로젝트 주소로 페이지를 만들었다. 과정을 정리해보려고 한다. 