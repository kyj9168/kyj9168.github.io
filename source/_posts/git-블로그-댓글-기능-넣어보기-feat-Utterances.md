---
title: git 블로그 댓글 기능 넣어보기 (feat. Utterances)
date: 2022-01-23 12:29:52
tags: ['Utterances', 'git-blog']
categories: blog
---
Utterances를 사용하면 Github 저장소의 Issue로 댓글을 관리할 수 있다.

개발 블로그 특성상, 내 블로그에 접근하는 사람들은 Github 계정이 있을 가능성이 높으니까 사용하기 좋을 것 같다.

### 설치

먼저 Github App에서 Utterances를 설치해야한다.
아래 url을 들어가면 install 버튼이 보일 것이다.
https://github.com/apps/utterances

Install 버튼을 누르면 저장소를 선택하는 화면이 나온다.

![install](/img/page/install-2.png)

보통 블로그는 private로 관리하기 때문에 public으로 댓글을 받을 저장소를 하나 생성한다.

본인은 blog-comments라는 저장소를 생성하였다.

저장소를 선택하였다면 이제 설정을 해보자.

### 설정 
![install](/img/page/install-3.png)

repo : 에 계정명과 댓글 저장소명을 작성하고

본인은 Issue title contains page pathname을 선택하였다.
(이걸 선택해야 포스팅 별로 댓글 관리가 가능하다.)

아래에서 테마를 설정하고 생성된 스크립트를 각자 본인의 git blog 프레임 워크의 page 단위에 붙여넣기 하면 완료.

![install](/img/page/install-4.png)
오 잘된다.
