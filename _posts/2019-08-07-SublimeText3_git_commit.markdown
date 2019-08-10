---
layout: post
title:  "Sublime Text 3 - Git 파일 Commit & Push 하기"
date:   2019-08-07
categories: Editor
---
<br>
<br>
<br>
**sublime text**와 **Git**을 연동한 후 파일 Commit & Push 하는 과정을 정리해봤다.
음 `시작!`<br>
<br>
<br>
<br>
![img01](./images/post/sublimetext-git-commit/01.PNG)
* 파일을 생성하고자 하는 위치의 폴더 우클릭 - New File 클릭   
<br>
<br>
<br>
<br>
![img 02](./images/post/sublimetext-git-commit/02.PNG)
* 파일이 생성되었다. 내용을 작성한다. 테스트용이라 git commit test라고 작성했다.
<br>
<br>
<br>
<br>
![img03](./images/post/sublimetext-git-commit/03.PNG)
* **Ctrl + S** 를 눌러서 파일을 저장한다. 
<br>
<br>
<br>
<br>
![img04](./images/post/sublimetext-git-commit/04.PNG)
* 파일이 저장되었다.
<br>
<br>
<br>
<br>
![img05](./images/post/sublimetext-git-commit/05.PNG)
* **Ctrl + Shift + p** 눌러서 Git Add Current File을 검색한 후 Enter.
<br>
<br>
<br>
<br>
![img06](./images/post/sublimetext-git-commit/06.PNG)
* add가 되면 연두색으로 표시가 된다.
<br>
<br>
<br>
<br>
![img07](./images/post/sublimetext-git-commit/07.PNG)
* **Ctrl + Shift + p** 눌러서 Git Commit을 검색한 후 Enter.
<br>
<br>
<br>
<br>
![img08](./images/post/sublimetext-git-commit/08.PNG)
* Commit 메세지를 입력하는 창이 뜬다.
<br>
<br>
<br>
<br>
![img09](./images/post/sublimetext-git-commit/09.PNG)
* Commit 메세지를 입력한 후 x표시를 누른다. 따로 저장하지 않고 commit 메세지 입력후 해당 창을 끄면 commit이 진행된다.
<br>
<br>
<br>
<br>
![img10](./images/post/sublimetext-git-commit/10.PNG)
* commit이 되면 콘솔창에 메세지가 출력된다.
<br>
<br>
<br>
<br>
![img11](./images/post/sublimetext-git-commit/11.PNG)
*  **Ctrl + Shift + p** 눌러서 Git Push 검색한 후 Enter. Push가 완료되면 콘솔창에 메세지가 출력된다.
<br>
<br>
<br>
<br>
![img12](./images/post/sublimetext-git-commit/12.PNG)
* 깃에 들어가보니 파일이 정상적으로 업로드된걸 확인할 수 있다.
<br>
<br>
<br>
<br>
![img13](./images/post/sublimetext-git-commit/13.PNG)
* 한번 지워보자. 쓰레기통 버튼 클릭.
<br>
<br>
<br>
<br>
![img14](./images/post/sublimetext-git-commit/14.PNG)
* 테스트 파일이라 별도의 commit 메세지는 작성하지 않고 Commit changes 버튼 클릭.
<br>
<br>
<br>
<br>
![img15](./images/post/sublimetext-git-commit/15.PNG)
* 정상적으로 해당 파일이 삭제됐다. 
<br>
<br>
<br>
<br>
![img16](./images/post/sublimetext-git-commit/16.PNG)
* 하지만 SublimeText 창에는 여전히 파일이 남아있다.
<br>
<br>
<br>
<br>
![img17](./images/post/sublimetext-git-commit/17.PNG)
* **Ctrl + Shift + p** 눌러서 Git Pull Current Branch 클릭
<br>
<br>
<br>
<br>
![img18](./images/post/sublimetext-git-commit/18.PNG)
* 콘솔창에 메세지가 출력되며 삭제한 파일이 SublimeText창 내에서도 지워진걸 확인할 수 있다.
<br>
<br>
<br>
<br>
