---
layout: post
title:  "Sublime Text 3 - Git 연동하기(feat.2틀간의 삽질)"
date:   2019-03-16 
categories : unknown
---
  
  
  
  
개인적으로 Sublime Text를 좋아한다.  
웹서핑중 sublime text와 Git을 연동해서 사용하시는 분들이 있는걸 발견하고 나도 해보자 싶어 해봤다.  
2틀간의 삽질을 했지만 과정이 공부가 많이 됐다.  
나중에 다시 볼 기회가 생기면 보기위한 기록용 포스팅.. sublime text가 생소한 분들도 있지않을까 싶어 설치부터 캡쳐했다.. 음 시작!


![imgp01](./images/post/sublimetext3-git/01.png)
* Google에 Sublime Text 3 를 검색한다. Download - Sublime Text 클릭

img 02
* Sublime Text Download 페이지로 이동된다. 본인 OS에 맞는걸 클릭하면 된다. 난 윈도우 사용자이므로 .. Windows 64 bit 클릭

img03	
* 설치파일이 다운로드되면 더블클릭하여 실행한다. 실행하시겠습니까? 라는 창이 뜨면 실행(R) 클릭

img04
* Sublime Text가 설치될 경로를 보여주는 창이다. Next 클릭

img05
* Next 클릭

img06
* Install 클릭

img07
* 설치가 완료되었다. Finish 클릭

img08
* 설치된 Sublime Text 3 아이콘을 클릭해 실행한다. 

img09
* https://packagecontrol.io/installation 링크를 클릭하여 홈페이지에 접속한다. 설치를 위한 코드가 공개되어있다. 빨간 네모 칸안에 있는 코드를 복사해서 Sublime Text Console창에 입력하면 간단하게 Package Control설치가 가능하다. 본인 버전에 맞는 탭을 클릭하여 코드를 복사한다.

img10
* 복사해온 코드를 붙여넣기 위한 Console창을 켜야한다. 2가지 방법이 있다. 첫번째 방법은 캡쳐한 이미지에 보이는것과 같이 View - Show Console 을 클릭하는 방법. 두번째 방법은 단축키를 이용하는 방법으로 Ctrl + ' 를 누르면 Console 창이 열린다. 단축키가 편하다. 

img11
* Sublime Text Console창 모습이다.

img12
* 복사한 코드를 붙여넣기한 후 Enter 를 누른다.

img13 
* 정상적으로 입력이 됐다.

img14
* 설치한 Package Control을 사용하기위해 Command Palette를 켜야한다. 이 역시 두가지 방법이 있다. 메뉴도구를 이용한 Tools - Command Palette 클릭. 단축키를 이용한 Ctrl + Shift + p 누르기. 역시 단축키가 편하다. 

img15
* Package Control: Install Package 검색하여 선택한 후 Enter.

img16
* 찰나의 로딩이 끝난 후 검색할수 있는 입력창이 활성화된다.

img17
* git으로 검색하여 Git 선택 후 Enter.

img18
* 설치하고자 하는 Package명을 검색해도 리스트에 표출되지 않는 경우에는 검색한 Package가 이미 설치되어 있는 경우다. 설치된 Package가 궁금한 경우에는 Remove Package 를 검색하여 선택한 후 Enter.

img19
* 설치되어있는 Package List가 표출된다.

img20
* 다시 본론으로 넘어와서, Git Local 저장소를 만들어야한다. 원하는 경로에 빈 폴더를 생성한다.

img21
* 방금 만든 빈 폴더를 Sublime Text 에서 열고자 한다. File - Open Folder 클릭.

img22
* 폴더를 선택한 후 폴더선택 버튼 클릭.

img23
* Sublime Text 창이 하나 더 생겼다. 자세히 보면 상단에 방금 선택한 폴더 명이 보이는 것을 확인할 수 있다.

img24
* 폴더 명이 표출되어있는 새창에서 작업을 진행할 것이다. View - Side Bar - Show Side Bar 클릭  

img25
* 왼쪽에 폴더 명이 표출된다.

img26
* Command Palette(Ctrl + Shift + p)를 열어 Git Init을 검색하여 선택 후 Enter.

img27
* Git directory 입력 칸이 활성화된다. 폴더 경로가 자동으로 잡힌다. 경로가 맞는지 확인 후 맞으면 Enter.

img28
* Console(Ctrl + ')창을 열어보면 Git directory가 정상적으로 잡힌것을 확인할 수 있다.

img29
* 아까 생성한 빈 폴더로 이동해보자. .git폴더가 생긴것을 확인할 수 있다. (안보이는 경우 숨김폴더를 해제해보자)

img30
* Command Palette(Ctrl + Shift + p)를 열어 Git Custom Command를 검색하여 선택한 후 Enter.

img31
* Git Command창이 활성화된다. 이 커맨드 창에 Clone 해오고자 하는 Repository URL을 입력해야한다. 일단.. URL을 복사해오자.

img32
* Git Blog Repository로 이동하여 Clone or download 버튼을 클릭한다. URL을 복사한다.

img33
* clone URL을 입력한다. ::*자 중요한 대목이 나온다 집중!*:: 본인의 URL은 https://github.com/ybebee9/ybebee9.github.io.git 이다. URL사이에 아이디와 비밀번호 그리고 구분을 위한 @를 입력해줘야한다. https://아이디:비밀번호@github.com/ybebee9/ybebee9.github.io.git 이런식으로. 정리하면 clone https://아이디:비밀번호@github.com/ybebee9/ybebee9.github.io.git 입력 후 Enter.


img34
* 띠로리. 에러다. 2틀동안 삽질의 원인이다. 에러를 구글링 해보니 curl openSSL 관련 다양한.. 원인이 될수있는.. 여러 정보들이... 이방법 저방법 시도했는데 잘 안됐다(여기서 시간을 많이 잡아먹었다..). 뭔가 간단하게 해결할 수도 있지 않을까 고민했다. 


img35
* 그러다가 해외 유저의 글을 발견했다. Git Version을 Update 하면 해결된다는 내용이었다.


img36
* 혹시나 해서 아까 생성한 폴더 우클릭 - Git Bash 를 클릭하여 실행했다.

img37
* git --version 입력 후 Enter.

img38
* git version이 1.9.5였다. 해외 유저의 글처럼 2.x로 update하면 해결되지 않을까 생각했다.

img39
* https://confluence.atlassian.com/bitbucketserver/installing-and-upgrading-git-776640906.html 링크를 클릭하여 본인 OS에 맞는 설치파일을 다운로드 하면된다. 본인은 Window 사용자니.. 캡쳐화면에서 보이는 것과 같이 Windows 밑에 있는 Git website 클릭.

img40
* 이러한 화면이 뜨면서 자동으로 실행파일이 다운로드된다.


img41
* 다운로드 된 실행파일을 더블 클릭하여 실행한다. 

img42
* 실행(R) 클릭.

img43
* Next 클릭.

img44
* Next 클릭.

img45
* Next 클릭.

img46
* Next 클릭.

img47
* Next 클릭.

img48
* Next 클릭.

img49
* Next 클릭.

img50
* Next 클릭.

img51
* Next클릭.

img52
* Next 클릭.

img53
* Install 클릭.

img54
* Exit 클릭.

img56
* Finish 클릭.

img57
* 폴더 우클릭 - Git Bash Here 클릭.

img58
* git --version 명령어 입력 후 Enter. 버전 2.22.0 확인.

img59
* Sublime Text 창으로 돌아가 Command Palette(Ctrl + Shift + p)를 열어 Git Custom Command 검색하여 선택 후 Enter.

img60
* clone https://아이디:비밀번호@github.com/ybebee9/ybebee9.github.io.git 입력 후 Enter.

img61
* 오 성공. 왼쪽 폴더창에 Git Repository가 정상적으로 받아졌다. 

img62
* 혹시나해서 포스트를 열어보았다. 

img63
* 아까 생성한 폴더로 이동하여 확인해 보니 Repository가 빠짐없이 모두 다운로드 되었다. 



끝!



다음 포스팅은 아마.. sublime text3로 글을 작성하여 commit하는 과정을 포스팅하지 않을까 싶다..