---
title: git 블로그 hexo 사용법
date: 2022-01-23 11:51:58
tags: ['hexo', 'clean-blog', 'theme', 'git-blog']
categories: blog
---

![hexo](/img/page/thumbnail-hexo.png)

## 헥소(HEXO)란?

Hexo 는 Node.js 기반의 정적 블로그 프레임워크 입니다.

### 설치 환경

-   node.js
-   git

### 헥소(HEXO) 설치

```bash
$ npm install hexo-cli -g
```

원하는 디렉토리로 이동하여 헥소 블로그 초기 설치(이 포스팅에선 blog라는 이름으로 초기 설치) 후 해당 디렉토리로 이동하여 노드 모듈 설치

```bash
$ hexo init blog
$ cd blog
$ npm install
```

설치 후 터미널에서 hexo server명령어를 실행해 줍니다.
로컬 서버가 구동되면 http://localhost:4000주소로 접속해 보고 아래 화면이 나온다면 헥소가 정상적으로 설치.

![hexo](/img/page/github-hexo-init-01.png)

### clean-blog 테마 적용

clean-blog 테마를 적용해 보겠습니다.
우선 아래 링크의 clean-blog 저장소로 가서 테마를 다운 받은 뒤 압축을 풀어줍니다.

https://github.com/klugjo/hexo-theme-clean-blog

압축을 풀어주면 hexo-theme-clean-blog-master폴더가 있는데, clean-blog라고 이름을 변경한 뒤 blog폴더의 themes폴더 안에 넣어줍니다. 기존의 landscape(기본 테마)는 사용 안할꺼면 삭제해 줘도 됩니다.

이제 설정 파일에서 테마를 clean-blog로 사용한다고 정해줘야 합니다. hexo폴더 루트 경로에 \_config.yml파일이 헥소 기본 설정파일이며, 여기서 전반적인 사이트 설정을 할 수 있습니다. theme 항목을 clean-blog로 수정해 줍니다.

```
theme: clean-blog
```

수정한 뒤 아래 명령어로 로컬서버를 다시 실행해 보면 테마가 반영된걸 확인 할 수 있습니다.

```bash
$ hexo server
```

### 블로그 작성 하기

헥소 블로그는 터미널에서 아래 명령어로 마크다운을 작성할 포스팅을 만들 수 있습니다.

```bash
$ hexo new post "포스트명"
```

/sources/\_posts/ 경로에 마크다운 파일이 새로 생성되며 이곳에 포스팅을 작성하면 됩니다. 마크다운 문법은 vsCode에서 미리보기를 하며 마크다운 적용 후를 확인하며 작성할수도 있습니다.

### 빌드 및 배포 하기

hexo는 적적 파일을 build하여 github.io에 적적 파일만 배포해야합니다.

저는 main에 적적파일을 배포하고 hexo로 관리하는 포스팅은 develop이라고 branch를 따로 만들었습니다.

지금까지 작성한 파일들을 develop브렌치로 생성한후 아래 명령어로 build를 해보면 정적파일이 생깁니다.

```bash
$ hexo generate
```

이제 내 git 블로그에 배포를 하는 방법은 아래 명령어로 배포 할 수 있습니다.

```bash
$ hexo deploy
```

git 블로그는 반영하는데 1분 정도 소요시간이 있어서 새로고침하여 배포가되었는지 확인 하면 됩니다.

이제 main은 배포하는 정적파일이 쌓이는 branch로 관리되고
develop은 hexo를 사용한 코드를 관리하는 branch로 사용하면 됩니다.

### 줄임말

지금까지 hexo를 사용하는 방법을 알려드렸는데
git 블로그의 프레임워크는 3가지가 있습니다.

#### Jekyll
-   루비 기반
-   현재 가장 인기 있음(깃헙 별 수 제일 많음)
-   한글 레퍼런스도 제일 많음
-   느리다는 제보가 많음(몇 십개의 포스팅 뿐인데도 빌드 하는데 5분씩 걸린다고)
-   윈도우 공식 지원 안됨

#### Hexo
-   자바스크립트(Node.js) 기반
-   한글 레퍼런스 꽤 많음
-   메인 개발자가 손을 놓은 듯
-   개발자가 중국인? 이라 구글링하면 중국어 글이 많이 나옴

#### Hugo
-   Golang 기반
-   빌드 빠름
-   문서화 잘돼있음
-   깃헙 별 수가 헥소보다 많음
-   한글 레퍼런스가 거의 없음

전 nodejs 개발자라 hexo를 사용하긴 했지만 개인적으로 테마와 정보가 많지 않다는점에서 약간은 비추한다...
다음번엔 지킬을 사용하여 만들어보고싶다.

이상 끝.