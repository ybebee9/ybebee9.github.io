---
layout: post
title:  "Sublime Text 3 - Git 연동하기(feat.이틀간의 삽질)"
date:   2019-07-10
categories : Editor
---
<br>
<br>
<br>
개인적으로 **Sublime Text**를 좋아한다.  
웹 서핑중 **sublime text**와 **Git**을 연동해서 사용하시는 분들이 있는걸 발견하고 나도 해보자 싶어 해봤다.  
이틀간의 삽질을 했지만 과정에서 공부가 많이 됐다.  
나중에 다시 볼 기회가 생기면 보기위한 기록용 포스팅..  
**sublime text**가 생소한 분들도 있지않을까 싶어 설치부터 캡쳐했다.. 음 `시작!`<br>
<br>
<br>
<br>
![imgp01](./images/post/sublimetext3-git/01.png)
* Google에 **Sublime Text 3** 를 검색한다. Download - Sublime Text 클릭  
<br>
<br>
<br>
<br>
![img 02](./images/post/sublimetext3-git/02.png)
* **Sublime Text Download** 페이지로 이동된다. 본인 OS에 맞는걸 클릭하면 된다. 본인은 윈도우 사용자이므로 .. Windows 64 bit 클릭
<br>
<br>
<br>
<br>
![img03](./images/post/sublimetext3-git/03.png)
* 설치파일이 다운로드되면 더블클릭하여 실행한다. 실행하시겠습니까? 라는 창이 뜨면 **실행(R)** 클릭
<br>
<br>
<br>
<br>
![img04](./images/post/sublimetext3-git/04.png)
* **Sublime Text**가 설치 될 경로를 보여주는 창이다. **Next** 클릭
<br>
<br>
<br>
<br>
![img05](./images/post/sublimetext3-git/05.png)
* **Next** 클릭
<br>
<br>
<br>
<br>
![img06](./images/post/sublimetext3-git/06.png)
* **Install** 클릭
<br>
<br>
<br>
<br>
![img07](./images/post/sublimetext3-git/07.png)
* 설치가 완료되었다. **Finish** 클릭
<br>
<br>
<br>
<br>
![img08](./images/post/sublimetext3-git/08.png)
* 설치된 **Sublime Text 3** 아이콘을 클릭해 실행한다. 
<br>
<br>
<br>
<br>
![img09](./images/post/sublimetext3-git/09.png)
* [PackgeControl 다운로드](https://packagecontrol.io/installation)를  클릭하여 홈페이지에 접속한다. 설치를 위한 코드가 공개되어있다. 빨간 네모 칸안에 있는 코드를 복사해서 Sublime Text **Console**창에 입력하면 간단하게 **Package Control 설치**가 가능하다. 본인 버전에 맞는 탭을 클릭하여 코드를 복사한다.
<br>
<br>
<br>
<br>
![img10](./images/post/sublimetext3-git/10.png)
* 복사해온 코드를 붙여넣기 위한 **Console**창을 켜야한다. **2가지 방법**이 있다. 첫번째 방법은 **메뉴도구**를 이용하여 **View - Show Console 을 클릭**하는 방법. 두번째 방법은 **단축키**를 이용하는 방법으로 **Ctrl + '** 를 누르면 Console 창이 열린다. 단축키가 편하다. 
<br>
<br>
<br>
<br>
![img11](./images/post/sublimetext3-git/11.png)
* Sublime Text **Console**창 모습이다.
<br>
<br>
<br>
<br>
![img12](./images/post/sublimetext3-git/12.png)
* 복사한 코드를 붙여넣기한 후 **Enter** 를 누른다.
<br>
<br>
<br>
<br>
![img13](./images/post/sublimetext3-git/13.png)
* 정상적으로 입력이 됐다.
<br>
<br>
<br>
<br>
![img14](./images/post/sublimetext3-git/14.png)
* 설치한 **Package Control**을 사용하기위해 **Command Palette**를 켜야한다. 이 역시 두가지 방법이 있다. 메뉴도구를 이용한 **Tools - Command Palette** 클릭. 단축키를 이용한 **Ctrl + Shift + p** 누르기. 역시 단축키가 편하다. 
<br>
<br>
<br>
<br>
![img15](./images/post/sublimetext3-git/15.png)
* **Package Control: Install Package** 검색하여 선택한 후 **Enter**.
<br>
<br>
<br>
<br>
![img16](./images/post/sublimetext3-git/16.png)
* 찰나의 로딩이 끝난 후 검색할수 있는 입력창이 활성화된다.
<br>
<br>
<br>
<br>
![img17](./images/post/sublimetext3-git/17.png)
* git으로 검색하여 **Git** 선택 후 **Enter**.
<br>
<br>
<br>
<br>
![img18](./images/post/sublimetext3-git/18.png)
* 설치하고자 하는 **Package명을 검색해도 리스트에 표출되지 않는 경우에는 검색한 Package가 이미 설치되어 있는 경우**다. 설치된 Package가 궁금한 경우에는 **Remove Package** 를 검색하여 선택한 후 Enter.
<br>
<br>
<br>
<br>
![img19](./images/post/sublimetext3-git/19.png)
* 설치되어있는 **Package List**가 표출된다.
<br>
<br>
<br>
<br>
![img20](./images/post/sublimetext3-git/20.png)
* 다시 본론으로 넘어와서, **Git Local 저장소**를 만들어야한다. 원하는 경로에 **빈 폴더**를 생성한다.
<br>
<br>
<br>
<br>
![img21](./images/post/sublimetext3-git/21.png)
* 방금 만든 빈 폴더를 Sublime Text 에서 열고자 한다. **File - Open Folder** 클릭.
<br>
<br>
<br>
<br>
![img22](./images/post/sublimetext3-git/22.png)
* 폴더를 선택한 후 **폴더선택** 버튼 클릭.
<br>
<br>
<br>
<br>
![img23](./images/post/sublimetext3-git/23.png)
* Sublime Text 창이 하나 더 생겼다. 자세히 보면 상단에 방금 선택한 **폴더명**이 보이는 것을 확인할 수 있다.
<br>
<br>
<br>
<br>
![img24](./images/post/sublimetext3-git/24.png)
* 폴더 명이 표출되어있는 새창에서 작업을 진행할 것이다. **View - Side Bar - Show Side Bar** 클릭  
<br>
<br>
<br>
<br>
![img25](./images/post/sublimetext3-git/25.png)
* 왼쪽에 폴더 명이 표출된다.
<br>
<br>
<br>
<br>
![img26](./images/post/sublimetext3-git/26.png)
* **Command Palette(Ctrl + Shift + p)**를 열어 **Git Init**을 검색하여 선택 후 **Enter**.
<br>
<br>
<br>
<br>
![img27](./images/post/sublimetext3-git/27.png)
* **Git directory 입력 칸**이 활성화된다. 폴더 경로가 자동으로 잡힌다. 경로가 맞는지 확인 후 맞으면 **Enter**.
<br>
<br>
<br>
<br>
![img28](./images/post/sublimetext3-git/28.png)
* **Console(Ctrl + ')**창을 열어보면 **Git directory**가 정상적으로 잡힌것을 확인할 수 있다.
<br>
<br>
<br>
<br>
![img29](./images/post/sublimetext3-git/29.png)
* 아까 생성한 빈 폴더로 이동해보자. **.git**폴더가 생긴것을 확인할 수 있다. (안보이는 경우 숨김폴더를 해제해보자)
<br>
<br>
<br>
<br>
![img30](./images/post/sublimetext3-git/30.png)
* **Command Palette(Ctrl + Shift + p)**를 열어 **Git Custom Command**를 검색하여 선택한 후 **Enter**.
<br>
<br>
<br>
<br>
![img31](./images/post/sublimetext3-git/31.png)
* **Git Command창**이 활성화된다. 이 커맨드 창에 **Clone** 해오고자 하는 **Repository URL**을 입력해야한다. 일단.. URL을 복사해오자.
<br>
<br>
<br>
<br>
![img32](./images/post/sublimetext3-git/32.png)
* Git Blog Repository로 이동하여 **Clone or download 버튼**을 클릭한다. URL을 복사한다.
<br>
<br>
<br>
<br>
![img33](./images/post/sublimetext3-git/33.png)
* clone URL을 입력한다.  
`자 중요한 대목이 나온다 집중!`  
본인의 URL은 `https://github.com/ybebee9/ybebee9.github.io.git` 이다.  
URL사이에 아이디와 비밀번호 그리고 구분을 위한 @를 입력해줘야한다.  
`https://아이디:비밀번호@github.com/ybebee9/ybebee9.github.io.git` 이런식으로.  
정리하면 `clone https://아이디:비밀번호@github.com/ybebee9/ybebee9.github.io.git` 입력 후 Enter.
<br>
<br>
<br>
<br>
![img34](./images/post/sublimetext3-git/34.png)
* 띠로리. 에러다. **2틀동안 삽질의 원인이다.** 에러를 구글링 해보니 curl openSSL 관련 다양한.. 원인이 될수있는.. 여러 정보들이... 이방법 저방법 시도했는데 잘 안됐다(여기서 시간을 많이 잡아먹었다..). 뭔가 간단하게 해결할 수도 있지 않을까 고민했다. 
<br>
<br>
<br>
<br>
![img35](./images/post/sublimetext3-git/35.png)
* 그러다가 해외 유저의 글을 발견했다. **Git Version을 Update 하면 해결된다는 내용**이었다.
<br>
<br>
<br>
<br>
![img36](./images/post/sublimetext3-git/36.png)
* 혹시나 해서 아까 생성한 **폴더 우클릭 - Git Bash** 를 클릭하여 실행했다.
<br>
<br>
<br>
<br>
![img37](./images/post/sublimetext3-git/37.png)
* **git --version** 입력 후 **Enter**.
<br>
<br>
<br>
<br>
![img38](./images/post/sublimetext3-git/38.png)
* `git version이 1.9.5`였다. 해외 유저의 글처럼 **2.x로 update하면 해결되지 않을까** 생각했다.
<br>
<br>
<br>
<br>
![img39](./images/post/sublimetext3-git/39.png)
* [Git Update 	파일 다운로드](https://confluence.atlassian.com/bitbucketserver/installing-and-upgrading-git-776640906.html)를 클릭하여 본인 OS에 맞는 설치파일을 다운로드 하면된다.  
본인은 Window 사용자니.. 캡쳐화면에서 보이는 것과 같이 Windows 밑에 있는 **Git website** 클릭.
<br>
<br>
<br>
<br>
![img40](./images/post/sublimetext3-git/40.png)
* 이러한 화면이 뜨면서 자동으로 실행파일이 다운로드된다.
<br>
<br>
<br>
<br>
![img41](./images/post/sublimetext3-git/41.png)
* 다운로드 된 실행파일을 더블 클릭하여 실행한다. 
<br>
<br>
<br>
<br>
![img42](./images/post/sublimetext3-git/42.png)
* **실행(R)** 클릭.
<br>
<br>
<br>
<br>
![img43](./images/post/sublimetext3-git/43.png)
* **Next** 클릭.
<br>
<br>
<br>
<br>
![img44](./images/post/sublimetext3-git/44.png)
* **Next** 클릭.
<br>
<br>
<br>
<br>
![img45](./images/post/sublimetext3-git/45.png)
* **Next** 클릭.
<br>
<br>
<br>
<br>
![img46](./images/post/sublimetext3-git/46.png)
* **Next** 클릭.
<br>
<br>
<br>
<br>
![img47](./images/post/sublimetext3-git/47.png)
* **Next** 클릭.
<br>
<br>
<br>
<br>
![img48](./images/post/sublimetext3-git/48.png)
* **Next** 클릭.
<br>
<br>
<br>
<br>
![img49](./images/post/sublimetext3-git/49.png)
* **Next** 클릭.
<br>
<br>
<br>
<br>
![img50](./images/post/sublimetext3-git/50.png)
* **Next** 클릭.
<br>
<br>
<br>
<br>
![img51](./images/post/sublimetext3-git/51.png)
* **Next** 클릭.
<br>
<br>
<br>
<br>
![img52](./images/post/sublimetext3-git/52.png)
* **Next** 클릭.
<br>
<br>
<br>
<br>
![img53](./images/post/sublimetext3-git/53.png)
* **Install** 클릭.
<br>
<br>
<br>
<br>
![img54](./images/post/sublimetext3-git/54.png)
* **Exit** 클릭.
<br>
<br>
<br>
<br>
![img56](./images/post/sublimetext3-git/56.png)
* **Finish** 클릭.
<br>
<br>
<br>
<br>
![img57](./images/post/sublimetext3-git/57.png)
* **폴더 우클릭 - Git Bash Here** 클릭.
<br>
<br>
<br>
<br>
![img58](./images/post/sublimetext3-git/58.png)
* **git --version 명령어** 입력 후 **Enter**. `버전 2.22.0 확인`.
<br>
<br>
<br>
<br>
![img59](./images/post/sublimetext3-git/59.png)
* Sublime Text 창으로 돌아가 **Command Palette(Ctrl + Shift + p)**를 열어 **Git Custom Command** 검색하여 선택 후 **Enter**.
<br>
<br>
<br>
<br>
![img60](./images/post/sublimetext3-git/60.png)
* `clone https://아이디:비밀번호@github.com/ybebee9/ybebee9.github.io.git` 입력 후 **Enter**.
<br>
<br>
<br>
<br>
![img61](./images/post/sublimetext3-git/61.png)
* 오 성공. 왼쪽 폴더창에 **Git Repository**가 정상적으로 받아졌다. 
<br>
<br>
<br>
<br>
![img62](./images/post/sublimetext3-git/62.png)
* 혹시나해서 포스트를 열어보았다. 
<br>
<br>
<br>
<br>
![img63](./images/post/sublimetext3-git/63.png)
* 아까 생성한 폴더로 이동하여 확인해 보니 Repository가 빠짐없이 모두 다운로드 되었다. 
<br>
<br>
<br>
<br>
`끝!`
<br>
<br>
<br>
<br>
> 다음 포스팅은 아마.. sublime text3로 글을 작성하여 commit하는 과정을 포스팅하지 않을까 싶다..
<br>
<br>
<br>
<br>