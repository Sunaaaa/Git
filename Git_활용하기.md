# Git 특강

- 폴더 만들기

  ![1566865815073](https://user-images.githubusercontent.com/39547788/63750999-8a048d00-c8e9-11e9-81bd-cd3accf28954.png)

  <br>

- 폴더 이동

  ![1566865854344](https://user-images.githubusercontent.com/39547788/63751003-8a048d00-c8e9-11e9-9874-f751d8dc8743.png)

  <br>

- 새로운 폴더 만들고 해당 폴더로 이동

  ![1566865899097](https://user-images.githubusercontent.com/39547788/63751004-8a9d2380-c8e9-11e9-9bec-f6726c5d3a4f.png)

  <br>

![1566865924465](https://user-images.githubusercontent.com/39547788/63751005-8a9d2380-c8e9-11e9-8f86-6378dd5392c2.png)

<br>

- code editer 열기 --> 뾰로롱 하고 code editer 가 열린다~~

  ![1566866262361](https://user-images.githubusercontent.com/39547788/63751007-8a9d2380-c8e9-11e9-8742-020f952d5044.png)

  <br>

- 새로운 웹 페이지 만들기

  ![1566868570671](https://user-images.githubusercontent.com/39547788/63751009-8b35ba00-c8e9-11e9-9177-63ae9a5dbca8.png)

  <br>

- 코드 indentation 4->2 로 변경

  ![1566866528743](https://user-images.githubusercontent.com/39547788/63751008-8b35ba00-c8e9-11e9-8ecc-f06bafdfd806.png)

  <br>

  ![1566868662658](https://user-images.githubusercontent.com/39547788/63751010-8b35ba00-c8e9-11e9-84a5-98e4844d290a.png)



<br><br>

- 기본 코드 자동완성

  - ! + TAB

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <meta http-equiv="X-UA-Compatible" content="ie=edge">
      <title>Document</title>
    </head>
    <body>
      
    </body>
    </html>
    ```

    

- git init 

  - git으로 프로젝트 관리 시작하겠다는 명령어

    - 해당 프로젝트를 기분으로 프로젝트 관리를 시작하겠다.

      ![1566868748704](https://user-images.githubusercontent.com/39547788/63751011-8b35ba00-c8e9-11e9-9d42-d81a1d9fc70e.png)

<br>

- git status

  ![1566868816628](https://user-images.githubusercontent.com/39547788/63751012-8bce5080-c8e9-11e9-8b26-9a7fbaf6fc6e.png)

  - No commits yet : Commit 단계 까지 간 것은 없다.

    <br>

- add, commit

  - add

    ![1566869104743](https://user-images.githubusercontent.com/39547788/63751014-8bce5080-c8e9-11e9-834a-85d5fba6301b.png)

    <br>

  - commit

    - 에러 발생

      - 이메일과 이름을 등록해줘야 저장이 가능하다.

        ![1566869177210](https://user-images.githubusercontent.com/39547788/63751015-8bce5080-c8e9-11e9-9570-0b8dc9cf7eec.png)

        - git-hub의 이메일 주소와 본인 영문 이름 

          ![1566869272381](https://user-images.githubusercontent.com/39547788/63751016-8c66e700-c8e9-11e9-8325-101c2f5a4703.png)

    - commit 완료!

      ![1566869310395](https://user-images.githubusercontent.com/39547788/63751018-8c66e700-c8e9-11e9-8fd8-00165aedfb54.png)

<br>

- 수정 후 업데이트 
  - add -> commit (내 컴퓨터에 저장)  -> push (원격 저장소에 저장)

<br><br><br>

### github pages 만들기 (feat. MyResume)

- 새로운 repository 생성

  - name 

    ```
    Sunaaaa.github.io
    ```

    <br>

    ![1566869874935](https://user-images.githubusercontent.com/39547788/63751019-8cff7d80-c8e9-11e9-9e93-a4880c0182ed.png)

<br>

- 저장소의 주소를 하나 추가

  - 첫번째 저장소의 이름은 관례적으로 origin  

  - 원격 저장소가 github로 설정됨

    ![1566870059875](https://user-images.githubusercontent.com/39547788/63751020-8cff7d80-c8e9-11e9-8d19-8b4a87dad0b2.png)

  <br>

- 저장소의 이름과 master라는 branch로 push 수행

  ![1566870115858](https://user-images.githubusercontent.com/39547788/63751021-8cff7d80-c8e9-11e9-9708-72073f59d3a1.png)

  <br>

  - github 아이디와 비밀번호 작성

    ![1566870138322](https://user-images.githubusercontent.com/39547788/63751022-8d981400-c8e9-11e9-85d4-eebc35e7d2c9.png)

    <br>

    ![1566870171320](https://user-images.githubusercontent.com/39547788/63751023-8d981400-c8e9-11e9-85f8-7face368048f.png)

  <br>

- https://sunaaaa.github.io/ 를 브라우저 검색창에 작성하면 우리가 작성한 index.html이 보이게 된다.

  ![1566870362722](https://user-images.githubusercontent.com/39547788/63751024-8d981400-c8e9-11e9-8a3d-4b1e715a3aad.png)





- git hub 에서는 절대로 코드를 변경하지 않는다. 

  ```
  git pull
  git status
  git add [파일명]
  git commit -m "complete merged" 
  git push
  ```

  <br>

- git log

  - Author : commit 한 사람

  - Commit Hash

    - 암호화를 통해 commit과 코드에 대한 정보

    ![1566879074035](https://user-images.githubusercontent.com/39547788/63751026-8e30aa80-c8e9-11e9-99e1-14dc3f9d8eb2.png)

    <br>

    - git checkout dcbb2

      - 해당 commit의 상태로  돌아간다.

        ![1566879540098](https://user-images.githubusercontent.com/39547788/63751027-8e30aa80-c8e9-11e9-8fe8-db01f76d5227.png)

        <br>

      - 다시 원래의 상태로 돌아간다.

        ![1566879573050](https://user-images.githubusercontent.com/39547788/63751029-8e30aa80-c8e9-11e9-80f4-ef28ebd8b00c.png)

  - q : 탈출

  - git log --oneline : log를 한줄로 찍어주세용

    ![1566879009083](https://user-images.githubusercontent.com/39547788/63751025-8e30aa80-c8e9-11e9-917e-ea25fe888787.png)



<br>

#### 기술면접 github

https://github.com/JaeYeopHan/Interview_Question_for_Beginner

- git add .

  : 모든 파일 add

#### git 정리

https://opentutorials.org/course/2708

<br>

#### git branching 연습



<br><br><br>

### 끝말잇기 (feat. 대장님과 부하님)

- 대장님

  ```
  mkdir ggutmal
  ls
  cd ggutmal
  git init (git으로 관리하겠다)
  code . (여기서 작업할 코드 에디터 열기)
  
  # 끝말잇기 하기 
  ```

- 협업

  - git add read.me

  - git commit -m "first commit"

  - github 에 새로운 repository 생성

  - git remote, git push 하기

    

  - Collaboration에 협업하는 사람들 추가

- 부하님

  - 해당 파일을 가져와야 한다.

  - 대장이 보낸 초대장 받기

    ![1566891489149](https://user-images.githubusercontent.com/39547788/63751082-9557b880-c8e9-11e9-9816-55a051a8fd9a.png)

    <br>

  - 올라와 있는 repository를 나에게 복제한다.

    ![1566883814883](https://user-images.githubusercontent.com/39547788/63751031-8ec94100-c8e9-11e9-927f-935f3bf8526c.png)

    <br>

  - 해당 폴더로 들어가 코드 에디터를 연다.

    ![1566883888163](https://user-images.githubusercontent.com/39547788/63751032-8ec94100-c8e9-11e9-90ae-ffe269db9d59.png)

    <br>

  - 작업을 한다.

    ![1566883907921](https://user-images.githubusercontent.com/39547788/63751033-8ec94100-c8e9-11e9-8657-289bc6e39a6a.png)

  <br>

  - add와 commit을 수행한다.

    ![1566884070904](https://user-images.githubusercontent.com/39547788/63751034-8f61d780-c8e9-11e9-9241-1744365324b9.png)

- 대장님

  - 변경된 것을 확인하고 공유 한다.
    - git pull origin master
  - 또 add , commit
  - git push origin master

  <br>

- git pull origin master

- code .

  

- git add README.md

- git commit -m "받아라 대장아"

- git push -u origin master

- git 아이디과 비밀번호 작성

<br><br><br>

### git graph

- 반드시 하나의 branch에 속하게 되어 있다. 

  - master : 시작하면 기본적으로 생성

- http://git-school.github.io/visualizing-git/

- git commit

  ![1566886245269](https://user-images.githubusercontent.com/39547788/63751035-8f61d780-c8e9-11e9-9744-c8c728b1d477.png)

<br>

- git checkout e137e

  ![1566886298438](https://user-images.githubusercontent.com/39547788/63751036-8f61d780-c8e9-11e9-919f-b4941af9aee8.png)

<br>

- git checkout master

  ![1566886333914](https://user-images.githubusercontent.com/39547788/63751038-8f61d780-c8e9-11e9-998d-80c204cb0bf3.png)

<br><br><br>

### branching

- git branch SunAh

  ![1566886506012](https://user-images.githubusercontent.com/39547788/63751039-8ffa6e00-c8e9-11e9-85a4-b499644b4b58.png)

  <br>

- git branch

  - 우리가 가지고 있는 branch와 어디에 속해 있는지를 알 수 있다. 

    ![1566886547252](https://user-images.githubusercontent.com/39547788/63751040-8ffa6e00-c8e9-11e9-851b-821ceaa6a957.png)

    - 지금은 master에 있다.

    - SunAh라는 branch를 보고 있어요

      - git checkout SunAh

        ![1566886631634](https://user-images.githubusercontent.com/39547788/63751042-8ffa6e00-c8e9-11e9-85ae-505c9e8c50d8.png)

        <br>

      - git commit

        ![1566886670708](https://user-images.githubusercontent.com/39547788/63751044-8ffa6e00-c8e9-11e9-8dd9-46ca031e7c9f.png)

        <br>

      - git checkout master

        - git commit

        ![1566886703790](https://user-images.githubusercontent.com/39547788/63751045-90930480-c8e9-11e9-85ed-6c2cc38dbc8d.png)

        <br>

      - git checkout SunAh

        ![1566886771078](https://user-images.githubusercontent.com/39547788/63751047-90930480-c8e9-11e9-9cc2-5d2f43623d1e.png)

<br><br><br>

### branch 연습

- branch 폴더 생성cd branch

  ![1566886872037](https://user-images.githubusercontent.com/39547788/63751050-912b9b00-c8e9-11e9-90b3-32fe911e075a.png)

  <br>

- branch 폴더로 이동해서 코드 에디터 열기

  ![1566886919028](https://user-images.githubusercontent.com/39547788/63751051-912b9b00-c8e9-11e9-9f12-04f9d4b6390b.png)

  <br>

- hello.py

  ```
  print("안녕하세요~")
  ```

  <br>

- git init : 해당 프로젝트를 git으로 관리하겠다리

  ![1566886991023](https://user-images.githubusercontent.com/39547788/63751052-912b9b00-c8e9-11e9-8af7-a621146d52ef.png)

  <br>

- add , commit

  ![1566887033648](https://user-images.githubusercontent.com/39547788/63751054-912b9b00-c8e9-11e9-871d-da9124518447.png)

  <br>

- branch-commit 상태 

  ![1566890066118](https://user-images.githubusercontent.com/39547788/63751074-94268b80-c8e9-11e9-9196-a4231e03ad48.png)

  <br>

  <br>

  <br>

- 새로운 branch 'comment' 만들기 

  ![1566887079556](https://user-images.githubusercontent.com/39547788/63751055-91c43180-c8e9-11e9-8792-c791b3958045.png)

  <br>

- 새로운 branch 'new' 를 만들면서 이동까지 한번에 

  ![1566887123693](https://user-images.githubusercontent.com/39547788/63751056-91c43180-c8e9-11e9-86e1-7390e1518bf1.png)

  <br>

- comment branch로 이동

  ![1566887178656](https://user-images.githubusercontent.com/39547788/63751057-91c43180-c8e9-11e9-867c-d53dca2620be.png)

  <br>

- branch 삭제

  ![1566887214013](https://user-images.githubusercontent.com/39547788/63751058-925cc800-c8e9-11e9-897a-c11aacc79144.png)

<br><br>



- comment branch에서 hello.py에 주석 추가

  ```
  print("안녕하세요~")
  
  
  #  이 코드는 hello를 출력합니다.
  ```

  <br>

- add, commit

  ![1566887872982](https://user-images.githubusercontent.com/39547788/63751059-925cc800-c8e9-11e9-9e09-d0db1c266c85.png)

  <br>

- branch-commit 상태 

  ![1566890235011](https://user-images.githubusercontent.com/39547788/63751075-94268b80-c8e9-11e9-87e9-ea418666a06d.png)

<br>

- master로 오는 순간 추가한 주석이 사라진다.

  ![1566887956277](https://user-images.githubusercontent.com/39547788/63751060-925cc800-c8e9-11e9-9cc1-b3e27375cb62.png)

<br>

- 여기서 hello.py 수정

  ```
  print("안녕하세요~")
  
  def hello():
      return "Hello"
  ```

  <br>

- add,commit

  ![1566888067578](https://user-images.githubusercontent.com/39547788/63751061-925cc800-c8e9-11e9-93e2-0d47b58e3652.png)

  <br>

- branch-commit 상태

  ![1566890273813](https://user-images.githubusercontent.com/39547788/63751078-94bf2200-c8e9-11e9-8b6c-41b4d4c36521.png)

  

<br>

- 다시 comment로 branch를 바꾸는 순간 hello.py가 이전의 주석으로 바뀜

  ![1566888136827](https://user-images.githubusercontent.com/39547788/63751066-92f55e80-c8e9-11e9-87d3-0137d1360617.png)

  ![1566888122766](https://user-images.githubusercontent.com/39547788/63751063-92f55e80-c8e9-11e9-90c4-4f09b8ea14a6.png)

  

<br>

<br><br>

### Merge

- 2갈래로 나눠진 것을 합친다.

  - **<u>반드시 master에서 수행!!!</u>**

    ![1566888272037](https://user-images.githubusercontent.com/39547788/63751067-92f55e80-c8e9-11e9-8468-5a4ace32d4f1.png)

    <br>

  - git merge comment

    : comment와 병합한다.

    ![1566888305660](https://user-images.githubusercontent.com/39547788/63751068-92f55e80-c8e9-11e9-9fb0-4f03ea72f74f.png)

    <br>

    - 에러!!!!!!! 함수/ 주석/ 둘다 중에 선택

      ![1566888342017](https://user-images.githubusercontent.com/39547788/63751069-938df500-c8e9-11e9-9da4-322c1c7c1148.png)

      <br>

    - 코드 편집기에서 함수/ 주석/ 둘다 중에 선택한다.

      ![1566891418712](https://user-images.githubusercontent.com/39547788/63751081-9557b880-c8e9-11e9-9317-e4a94d1c6925.png)

      <br>

    - add, commit

      ![1566888479528](https://user-images.githubusercontent.com/39547788/63751070-938df500-c8e9-11e9-9792-7fec2764d7b5.png)

      <br>

      ![1566888525782](https://user-images.githubusercontent.com/39547788/63751071-938df500-c8e9-11e9-975a-628b23e46a0a.png)

      <br>

    - 병합 후의 hello.py 

      - master branch의 hello.py![1566890530729](https://user-images.githubusercontent.com/39547788/63751079-94bf2200-c8e9-11e9-94dc-a30ca1fc2a6f.png)

        <br>

      - commnet branch의 hello.py

        ![1566890614762](https://user-images.githubusercontent.com/39547788/63751080-9557b880-c8e9-11e9-8acc-5086953d2ebc.png)

      <br><br>

    - git graph로 병합 전 & 후 살펴보기

      - 병합 전

        ![1566888556923](https://user-images.githubusercontent.com/39547788/63751072-94268b80-c8e9-11e9-8bfc-810175816817.png)

        <br>

      - 병합 후 

        ![1566888581051](https://user-images.githubusercontent.com/39547788/63751073-94268b80-c8e9-11e9-8578-37721408737c.png)
