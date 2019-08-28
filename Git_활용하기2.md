



# Git 특강2

### 텔레그램

- MSA : MicroService Architecture
- Monolitic

- 덩어리 처럼 코드를 만들어 하나의 폴더로 보관하는 것은 옛날
- 오늘날은 서로 각각 다른 앱으로 존재하여, 서로 소통하여 구성된다.
  - 로그인 앱, 뉴스피드 기능 앱, 광고 모듈
  - 각각 앱에 사용되는 기술 set이 다양하다.
  - 커리어 관리에 좋다



<br>

<br>

<br>

## Chatbot 만들기 

- Telegram Base의 ChatBot 만들기 

- 파이썬 3.7.4 버전 설치

  ![1566956398522](https://user-images.githubusercontent.com/39547788/63851615-703e7500-c9d1-11e9-8bcf-12fe769d3e34.png)

  <br>

  ​			![1566956544041](https://user-images.githubusercontent.com/39547788/63851616-70d70b80-c9d1-11e9-8363-b49b6a6d0583.png)

  <br>



- chatbot 폴더를 생성하고 코드 에디터를 연다.

  ![1566954764632](https://user-images.githubusercontent.com/39547788/63851613-703e7500-c9d1-11e9-907f-485aa8bae800.png)

  <br>

- app.py 이라는 파이썬 파일을 생성한다.

  ![1566955604821](https://user-images.githubusercontent.com/39547788/63851614-703e7500-c9d1-11e9-87b7-69bead8c4b3a.png)

<br>

- pip list : 파이썬에 설치되어 있는 패키지 리스트를 출력한다.

  ![1566956590918](https://user-images.githubusercontent.com/39547788/63851619-70d70b80-c9d1-11e9-82e9-3efed84a1b7c.png)

  <br>

  - python -m pip install --upgrade pip

    ![1566956615712](https://user-images.githubusercontent.com/39547788/63851620-70d70b80-c9d1-11e9-8a1c-1323336e734d.png)

<br><br>

- pip install flask

  - flask 
    - python 웹 어플리케이션을 만드는 프레임 워크

  <br>

  - flask 설치

    ![1566956671596](https://user-images.githubusercontent.com/39547788/63851621-716fa200-c9d1-11e9-8881-f109a1437fb2.png)

    

    <br>

  - 설치 완료 

    ![1566956763244](https://user-images.githubusercontent.com/39547788/63851622-716fa200-c9d1-11e9-9883-692f2eaacfd1.png)

<br><br><br>

### python flask를 사용해서 경량형 web server 만들기app.py 작성하기 

- app.py 작성하기

  ```python
  from flask import Flask
  
  # 새로운 flask instance를 만들어 app에 저장
  app = Flask(__name__)
  
  # root URL 만들기
  @app.route('/')
  def home():
      return 'hello'
  ```

  <br>

- flask run 

  - 달려라 flask 야~

    ![1566957166518](https://user-images.githubusercontent.com/39547788/63851623-716fa200-c9d1-11e9-9bd2-a7c7569298df.png)

    <br>

  - running  확인 

    ![1566957306031](https://user-images.githubusercontent.com/39547788/63851625-716fa200-c9d1-11e9-885a-4ed90acf4456.png)

    - 코드를 수정할 때 마다 Server를 다시 시작해야한다.

  <br>

- app.py 수정하기

  - 로직
    1. 주문서를 만들기
       - 모든 주문은 url을 통해 받는다.
    2. 해당 주문이 들어왔을 때 무엇을 할지를 정의한다.

  - 기본으로 이름을 요청하는 주문

    ```python
    from flask import Flask
    
    app = Flask(__name__)
    
    # 가장 근본이 되는 주문서 
    @app.route('/')
    def home():
        return 'hello'
    
    # 이름을 요청하는 주문
    @app.route('/name')
    def name():
        return '선아 입니다~'
    ```

    <br>![1566958184209](https://user-images.githubusercontent.com/39547788/63851626-72083880-c9d1-11e9-83e5-b1eabfe6589d.png)

  <br>

  - URL을 통해 사용자의 이름을 요청받는 주문

    ```python 
    from flask import Flask
    
    app = Flask(__name__)
    
    # 가장 근본이 되는 주문서 
    @app.route('/')
    def home():
        return 'hello'
    
    # 이름 요청하는 주문
    @app.route('/name')
    def name():
        return '선아 입니다~'
    
    # URL을 통해 사용자의 이름을 요청받는 주문
    @app.route('/hello/SunAh')
    def hello():
        return 'hello SunAh'
    ```

    <br>![1566958327534](https://user-images.githubusercontent.com/39547788/63851628-72083880-c9d1-11e9-803f-030b5f2964c7.png)

  <br>

  - variable routing

    - URL을 통해 사용자가 직접 입력한 이름을 요청하는 주문

      - < name > : 사용자가 입력하는 값을 해당 변수에 담는다.

        ```python
        from flask import Flask
        
        app = Flask(__name__)
        
        # 가장 근본이 되는 주문서 
        @app.route('/')
        def home():
            return 'hello'
        
        # 이름을 요청하는 주문
        @app.route('/name')
        def name():
            return '선아 입니다~'
        
        # 이름을 요청하는 주문
        # <name> : 사용자가 입력하는 값을 해당 변수에 담는다.
        @app.route('/hello/<name>')
        def hello(name):
            return  name
        ```

        <br>![1566958497066](https://user-images.githubusercontent.com/39547788/63851629-72083880-c9d1-11e9-881c-b260c9ba63d2.png)

  <br>

  - 'hello SunAh'

    - 방법 1 

      - 코드

        ```python
        from flask import Flask
        
        app = Flask(__name__)
        
        # 가장 근본이 되는 주문서 
        @app.route('/')
        def home():
            return 'hello'
        
        # 이름을 요청하는 주문
        @app.route('/name')
        def name():
            return '선아 입니다~'
        
        # <name> : 사용자가 입력하는 값을 해당 변수에 담는다.
        @app.route('/hello/<name>')
        def hello(name):
        #    return  'hello '+name
        #    return  'hello {}'.format(name)
            return  f'hello {name}'
        ```

      <br>

    - 실행 화면 

      ![1566958660564](https://user-images.githubusercontent.com/39547788/63851630-72083880-c9d1-11e9-8b58-028688aae3a4.png)

  <br><br>

  - 입력된 숫자를 제곱하는 주문 

    - < num >은 str 이기 때문에 num을 int로 형변환 필요 

    - flask함수에서 return은 str 이기 때문에 return 값을 str로 형변환 필요 

    - 코드

      ```python
      @app.route('/square/<num>')
      def my_square(num):
          a = (int(num)) * (int(num))
          return f'제곱 :  {a}'
      
      @app.route('/square2/<int:num>')
      def my_square2(num):
          return str(num **2)
      ```

      <br>

    - 실행 화면

      ![1566965171871](https://user-images.githubusercontent.com/39547788/63851633-72a0cf00-c9d1-11e9-8162-70ba3fc758c7.png)

      

      ![1566965142046](https://user-images.githubusercontent.com/39547788/63851631-72a0cf00-c9d1-11e9-83eb-c44e434a1463.png)

<br><br><br>

### 랜덤으로 Menu 선택

- 랜덤 패키지 import

  ```python 
  asdas
  ```

  <br>

- 코드

  ```python 
  @app.route('/menu')
  def menu():
      foods=['바스버거','대우식당','고갯마루','진가와']
      food = random.choice(foods)
      return food
  ```

  <br>

- 실행 화면

  - #1

    ![1566965379431](https://user-images.githubusercontent.com/39547788/63851635-72a0cf00-c9d1-11e9-89fc-c84ebc499e35.png)

    <br>

  - #2

    ![1566965405583](https://user-images.githubusercontent.com/39547788/63851636-73396580-c9d1-11e9-9539-18d614c0b858.png)

<br><br><br>

### 랜덤으로 로또 번호 추천

- 코드 1

  ```python
  @app.route('/lotto')
  def lotto():
      lotto = [random.randint(1,45) for i in range(6)]
      return str(lotto)
  ```

  <br>

  - 실행 화면

    - #1

      ![1566965821669](https://user-images.githubusercontent.com/39547788/63851637-73396580-c9d1-11e9-8dc1-f15a41e2e66b.png)

      <br>

    - #2![1566965944752](https://user-images.githubusercontent.com/39547788/63851638-73396580-c9d1-11e9-9964-82fa34ff3578.png)

<br>

- 코드 2

  ```
  @app.route('/lotto2')
  def lotto2():
      lotto = random.sample(range(1,46),6)
  
      # 원본 배열을 바꾼다.
      #lotto.sort()
  
      # 원본이 바뀌지 않는다.
      # sorted(lotto)
  
      return str(sorted(lotto))
  ```

  <br>

  - 실행 화면

    - #1

      ![1566966251550](https://user-images.githubusercontent.com/39547788/63851639-73d1fc00-c9d1-11e9-9171-a124240504b8.png)

      <br>

    - #2

      ![1566966269583](https://user-images.githubusercontent.com/39547788/63851640-73d1fc00-c9d1-11e9-85a2-33ba7679be6a.png)

<br><br><br>

#### 랜덤으로 추천 받은 로또 번호를 실제 로또 번호와 비교

- 실제 로또 번호와 비교하여 추천받은 번호의 등수를 출력한다.

- 코드

  ```python
  @app.route('/lotto3')
  def lotto3():
      winner = [3,5,12,13,33,39]
      lotto = random.sample(range(1,46),6)
  
      rank = 0
      # 만약 6개 모두 일치하면 1등
      # 만약 5개가 일치하면 3등
      # 만약 4개가 일치하면 4등
      # 만약 3개가 일치하면 5등
  
      count = 0
  
      for val in winner:
          if val in lotto:
              count = count+1
  
      if count == 6:
          rank = 1
      elif count == 5:
          rank = 3
      elif count == 4:
          rank = 4
      elif count == 3:
          rank = 5
      else :
          rank = 6
  
      return f'결과 : {str(sorted(lotto)) + str(rank)}'
  
  ```

  <br>

- 실행 화면

  - #1

    ![1566967415607](https://user-images.githubusercontent.com/39547788/63851641-73d1fc00-c9d1-11e9-95a1-0a3752ffc60b.png)

  <br><br>

- 무조건 1등

  - 코드

    ```python
    @app.route('/lotto4')
    def lotto4():
        winner = [3,5,12,13,33,39]
        #lotto = random.sample(range(1,46),6)
    
        lotto = [3,5,12,13,33,39]
    
        rank = '꽝'
        count = 0
    
        for val in lotto:
            if val in winner:
                count = count+1
    
        if count == 6:
            rank = '1등'
        elif count == 5:
            rank = '3등'
        elif count == 4:
            rank = '4등'
        elif count == 3:
            rank = '5등'
        else :
            rank = '꽝'
    
        return f'결과 : {str(sorted(lotto)) + rank}'
    ```

    <br>

  - 실행 화면

    ![1566967599960](https://user-images.githubusercontent.com/39547788/63851642-73d1fc00-c9d1-11e9-976c-94ee6964c2dc.png)

<br><br>

- 무조건 4등

  - 교집합 구하기
    - set() & set()

  <br>

  - 코드

    ```python
    @app.route('/lotto4')
    def lotto4():
        winner = [3,5,12,13,33,39]
        #lotto = random.sample(range(1,46),6)
    
        lotto = [3,5,12,13,26,88]
    
        count = len(set(winner)&set(lotto))
        # => {3,5,12}
    
        rank = '꽝'
        if count == 6:
            rank = '1등'
        elif count == 5:
            rank = '3등'
        elif count == 4:
            rank = '4등'
        elif count == 3:
            rank = '5등'
        else :
            rank = '꽝'
    
        return f'결과 : {str(sorted(lotto)) + rank}'
    ```

    <br>

- git hub에 올리기

  - ' __ pycache__'라는 Python 캐시 파일이 생성된다.

    ![1566967904529](https://user-images.githubusercontent.com/39547788/63851643-746a9280-c9d1-11e9-8551-321e74e80911.png)

    <br>

  - app.py 파일만 github에 올려도 git status 가 깨끗하지 않다.![1566968008789](https://user-images.githubusercontent.com/39547788/63851644-746a9280-c9d1-11e9-984c-d6c308096401.png)

    <br>

  - .gitignore 파일을 생성하여 __ pycache__를 작성한다.

    ![1566968079759](https://user-images.githubusercontent.com/39547788/63851645-746a9280-c9d1-11e9-9e32-8b4a34824cba.png)

    <br>

  - git status를 하면 __ pycache__가 사라진 것을 볼 수 있다.

    ![1566968142680](https://user-images.githubusercontent.com/39547788/63851646-75032900-c9d1-11e9-89f8-76268794fa99.png)

    <br>

  - .gitignore 파일에 대해 add, commit을 수행한다.

    ![1566968165308](https://user-images.githubusercontent.com/39547788/63851647-75032900-c9d1-11e9-8520-feae50a53b78.png)

    <br>

    ![1566968191335](https://user-images.githubusercontent.com/39547788/63851648-75032900-c9d1-11e9-9b1d-97a9671274f0.png)

<br><br>

#### .gitignore 파일 

- http://gitignore.io/

- Project에 원하지 않는 Backup File이나 Log File , 혹은 컴파일 된 파일들을 Git에서 제외시킬수 있는 설정 파일

  ![1566969074596](https://user-images.githubusercontent.com/39547788/63851649-75032900-c9d1-11e9-9df1-d37224b1086f.png)

  <br>

  ```
  # Created by https://www.gitignore.io/api/python
  # Edit at https://www.gitignore.io/?templates=python
  
  ### Python ###
  # Byte-compiled / optimized / DLL files
  __pycache__/
  *.py[cod]
  *$py.class
  
  # C extensions
  *.so
  
  # Distribution / packaging
  .Python
  build/
  develop-eggs/
  dist/
  downloads/
  eggs/
  .eggs/
  lib/
  lib64/
  parts/
  sdist/
  var/
  wheels/
  pip-wheel-metadata/
  share/python-wheels/
  *.egg-info/
  .installed.cfg
  *.egg
  MANIFEST
  
  # PyInstaller
  #  Usually these files are written by a python script from a template
  #  before PyInstaller builds the exe, so as to inject date/other infos into it.
  *.manifest
  *.spec
  
  # Installer logs
  pip-log.txt
  pip-delete-this-directory.txt
  
  # Unit test / coverage reports
  htmlcov/
  .tox/
  .nox/
  .coverage
  .coverage.*
  .cache
  nosetests.xml
  coverage.xml
  *.cover
  .hypothesis/
  .pytest_cache/
  
  # Translations
  *.mo
  *.pot
  
  # Django stuff:
  *.log
  local_settings.py
  db.sqlite3
  db.sqlite3-journal
  
  # Flask stuff:
  instance/
  .webassets-cache
  
  # Scrapy stuff:
  .scrapy
  
  # Sphinx documentation
  docs/_build/
  
  # PyBuilder
  target/
  
  # Jupyter Notebook
  .ipynb_checkpoints
  
  # IPython
  profile_default/
  ipython_config.py
  
  # pyenv
  .python-version
  
  # pipenv
  #   According to pypa/pipenv#598, it is recommended to include Pipfile.lock in version control.
  #   However, in case of collaboration, if having platform-specific dependencies or dependencies
  #   having no cross-platform support, pipenv may install dependencies that don't work, or not
  #   install all needed dependencies.
  #Pipfile.lock
  
  # celery beat schedule file
  celerybeat-schedule
  
  # SageMath parsed files
  *.sage.py
  
  # Environments
  .env
  .venv
  env/
  venv/
  ENV/
  env.bak/
  venv.bak/
  
  # Spyder project settings
  .spyderproject
  .spyproject
  
  # Rope project settings
  .ropeproject
  
  # mkdocs documentation
  /site
  
  # mypy
  .mypy_cache/
  .dmypy.json
  dmypy.json
  
  # Pyre type checker
  .pyre/
  
  # End of https://www.gitignore.io/api/python
  ```

  <br>

  - add, commit 후 git log로 확인

    ![1566969215675](https://user-images.githubusercontent.com/39547788/63851650-759bbf80-c9d1-11e9-93ea-4f240c8afe7a.png)

<br><br>

#### 태그를 붙이기

- git status 가 깨끗한 상태여야 한다.

  ![1566969563709](https://user-images.githubusercontent.com/39547788/63851581-6b79c100-c9d1-11e9-8aef-e27f556c532f.png)

<br>

- 'v0.0.1'라는 이름의 태그 만들기 

  - git tag -a v0.0.1 -m "Version 0.0.1" ddc0a

    ​			[태그이름]							[log hash 앞 5자리]

    - git tag : 등록된 태그를 출력한다.

      ![1566969609806](https://user-images.githubusercontent.com/39547788/63851582-6c125780-c9d1-11e9-8107-add39e1b7b55.png)

  

  <br>

- 'v0.0.1' 라는 태그로 이동한다.

  - git checkout v0.0.1

  - got log : v0.0.1로 이동한 것을 확인한다.

    ![1566969634773](https://user-images.githubusercontent.com/39547788/63851584-6c125780-c9d1-11e9-9198-279433582eff.png)



<br>

- branch를 master로 변경하여 본래의 상태로 돌린다.

  - git checkout master

  - git log를 통해 변경된 것을 확인한다.

    ![1566969741526](https://user-images.githubusercontent.com/39547788/63851585-6c125780-c9d1-11e9-9284-ca4c35f3a709.png)

<br>

- 'v0.0.2'라는 이름의 태그 만들기 

  - git tag -a v0.0.2 -m "Version 0.0.2" bd79f

  - git log

    ![1566969815953](https://user-images.githubusercontent.com/39547788/63851586-6c125780-c9d1-11e9-9e9d-679a101ce46c.png)

- 태그 생성 

  ![1566990790420](https://user-images.githubusercontent.com/39547788/63851609-6fa5de80-c9d1-11e9-988f-dacc4c040037.png)

<br><br>

#### Json Viewer 설치

- https://chrome.google.com/webstore/detail/json-viewer/gbmdgpbipfallnflgajpaliibnhdgobh?hl=ko&hc_location=ufi

  ![1566970056702](https://user-images.githubusercontent.com/39547788/63851587-6caaee00-c9d1-11e9-9e13-f2b87cceb885.png)

<br><br>

#### requests 설치

- Python에서 HTTP 요청을 보내는 모듈

  ```python 
  pip install requests
  ```

  <br>

  - lotto.py

    - request를 통해 요청 보내고 응답으로 받은 결과물을 response 변수에 담는다.

      - 코드

        ```python 
        '''
            requests를 통해 동행복권 API 요청을 보내,
            1등 번호를 가져와 python list로 만듬
        '''
        
        import requests 
        
        # 1. request를 통해 요청 보내기
        # requests.get('주소')
        url = 'https://www.dhlottery.co.kr/common.do?method=getLottoNumber&drwNo=873'
        
        # 응답으로 받은 결과물을 response 변수에 담는다. 
        response = requests.get(url)
        print(response)
        ```

        <br>

      - 실행 결과 

        ![1566970390571](https://user-images.githubusercontent.com/39547788/63851589-6caaee00-c9d1-11e9-8aa9-68e6ab28469d.png)

      <br>

    - response 안의 내용물을 출력한다.

      - 코드

        ```python 
        # response 안의 내용물 출력
        print(response.text)
        ```

        <br>

      - 실행 결과 

        ![1566970493968](https://user-images.githubusercontent.com/39547788/63851592-6d438480-c9d1-11e9-83d6-176ed352a134.png)

      <br>

    - Json 이라는 글자를 python이 읽을 수 있는 딕셔너리로 만든다.

      - 코드

        ```python 
        res_dict = response.json()
        print(res_dict)
        ```

        <br>

      - 실행 결과 

        ![1566970700880](https://user-images.githubusercontent.com/39547788/63851593-6d438480-c9d1-11e9-9bb5-66d8ad195149.png)

      <br>

    - 딕셔너리 처럼 사용 가능하다.

      - 코드

        ```python
        print(res_dict['drwtNo1'])
        ```

        <br>

      - 실행 결과

        ![1566970823497](https://user-images.githubusercontent.com/39547788/63851595-6ddc1b00-c9d1-11e9-9fbf-ca1b7c7273d4.png)

  

<br><br><br>

### 동행 로또에서 Json으로 되어 있는 로또 번호를 자동으로 가져와 랜덤으로 추천된 로또 번호와 비교하여 등수를 출력한다.

- 코드

  ```python
  @app.route('/lotto4')
  def lotto4():
  
      url = 'https://www.dhlottery.co.kr/common.do?method=getLottoNumber&drwNo=873'
  
      response = requests.get(url)
      res_dict = response.json()
      winner = [res_dict['drwtNo'+ str(val)] for val in range(1,7)]
  #    lotto = random.sample(range(1,46),6)
      lotto = [3,5,12,13,33,39]
  
      count = len(set(winner)&set(lotto))
  
      rank = '꽝'
      if count == 6:
          rank = '1등'
      elif count == 5:
          rank = '3등'
      elif count == 4:
          rank = '4등'
      elif count == 3:
          rank = '5등'
      else :
          rank = '꽝'
  
      return f'결과 : {str(sorted(lotto)) + rank}'
  ```

  <br>

- 실행 화면 

  ![1566971520338](https://user-images.githubusercontent.com/39547788/63851596-6ddc1b00-c9d1-11e9-8adb-7a25a3d856b0.png)



<br><br>

### crypto.py

- 실시간 BTC (Bitcoin) 현재가를 출력한다.

  - 빗썸 : https://apidocs.bithumb.com/docs/ticker

  - Json : https://api.bithumb.com/public/ticker/

    ![1566973425033](https://user-images.githubusercontent.com/39547788/63851597-6ddc1b00-c9d1-11e9-9d2b-3e7e32c88a67.png)

    <br>

  - 코드 

    ```python
    # 실시간 BTC (Bitcoin) 현재가를 출력하는 crypto.py
    import requests 
    
    # 1. request를 통해 요청 보내기
    # requests.get('주소')
    url = 'https://api.bithumb.com/public/ticker/'
    
    # 응답으로 받은 결과물을 response 변수에 담는다. 
    response = requests.get(url)
    # print(response)
    # response 안의 내용물 
    # print(response.text)
    
    res_dict = response.json()
    # print(res_dict)
    print(res_dict['data']['opening_price'])
    
    # # 1등 번호 6개가 담긴 result라는 list를 출력
    # result = [res_dict['drwtNo'+ str(val)] for val in range(1,7)]
    # print(result)
    ```

    <br>

  - 실행 화면

    ![1566973476132](https://user-images.githubusercontent.com/39547788/63851598-6e74b180-c9d1-11e9-84e9-1a2960e63172.png)

<br><br>

#### commit을 분리하기

- 기존의 add.py -> 수정된 add.py

  - lotto.py 부터 add, commit

    ![1566973666719](https://user-images.githubusercontent.com/39547788/63851599-6e74b180-c9d1-11e9-8c43-aaf9285616b2.png)

    <br>

    ![1566973686064](https://user-images.githubusercontent.com/39547788/63851600-6e74b180-c9d1-11e9-9ae0-3ec1d749efb4.png)

    <br>

  - 동행 로또 api를 적용시킨 app.py 를 add, commit

    ![1566973728218](https://user-images.githubusercontent.com/39547788/63851601-6e74b180-c9d1-11e9-83d3-ea46739dc26a.png)

    <br>

  - crypto.py를 add, commit

    - 모든 파일을 add, commit을 수행했기 떄문에 git status 가 깨끗하다.

      ![1566973794665](https://user-images.githubusercontent.com/39547788/63851602-6f0d4800-c9d1-11e9-9637-9609d005cd74.png)

  <br>

  - git log --oneline으로 log를 한줄로 예쁘게 출력하기

    ![1566973823080](https://user-images.githubusercontent.com/39547788/63851605-6f0d4800-c9d1-11e9-83a5-66f7100c845f.png)



<br><br><br>

### Python으로 선아봇에게 메시지 보내기

- telegram의 botfather를 찾아 선아봇(name : sunah_bot)을 생성한다.

- https://core.telegram.org/bots/api

- telegram api : https://api.telegram.org/bot< token>/METHOD_NAME

- METHOD_NAME
  - /getMe

    - 웹 브라우저에 https://api.telegram.org/bot< token >/getMe 

      ![1566991025320](https://user-images.githubusercontent.com/39547788/63851611-6fa5de80-c9d1-11e9-94dd-7a6f49e5fa43.png)

    <br>

  - /sendMessage : 메시지를 전달한다.

    - 파라미터로 chat_id와 text 가 필수 

    - 웹 브라우저에 https://api.telegram.org/bot< token >/sendMessage?chat_id=975161663&text=꺄

      ![1566991089315](https://user-images.githubusercontent.com/39547788/63851612-703e7500-c9d1-11e9-8d03-e4976ad1a308.png)

      

    <br>

  - /getUpdate : 봇의 대화방 상태

    - 웹 브라우저에 https://api.telegram.org/bot< token >/getUpdates!

      ![1566991006344](https://user-images.githubusercontent.com/39547788/63851610-6fa5de80-c9d1-11e9-9105-03f05c25adb3.png)

      <br>

  - 코드 1

    ```python
    '''
    python으로 telegram message 보내기
    '''
    
    import requests
    
    response = requests.get('https://api.telegram.org/bot< token >/getUpdates')
    res_dict = response.json()
    print(res_dict['result'][0]['message']['chat']['id'])
    
    # 1. getUpdates 를 통해 chat_id를 가져옴
    chat_id = str(res_dict['result'][0]['message']['chat']['id'])
    
    # 2. 
    token = 'bot< token >'
    base_url = 'https://api.telegram.org/'
    method = '/sendMessage'
    msg = "telegram.py에서 보내는 메시지"
    param = '?chat_id='+chat_id+'&text='+msg
    
    url = base_url + token + method + param
    print(url)
    requests.get(url)
    ```

    <br>

  - 실행 화면 1

    ![1566978253864](https://user-images.githubusercontent.com/39547788/63851607-6f0d4800-c9d1-11e9-89a7-456b72b9942a.png)

    <br>

  - 코드 2

    ```python 
    '''
    python으로 telegram message 보내기
    '''
    
    import requests
    
    token = '< token >'
    base_url = 'https://api.telegram.org'
    
    
    # 1. getUpdates 를 통해 chat_id를 가져옴
    
    url = f'{base_url}/bot{token}/getUpdates'
    res = requests.get(url)
    res_dict = res.json()
    print(url)
    
    chat_id = str(res_dict['result'][0]['message']['chat']['id'])
    print(chat_id)
    
    # 2. 
    
    msg = "와 자동화 했다~"
    param = '?chat_id='+chat_id+'&text='+msg
    
    url = f'{base_url}/bot{token}/sendMessage?chat_id={chat_id}&text={msg}'
    print(url)
    requests.get(url)
    ```

    <br>

  - 실행 화면 2

    ![1566980630350](https://user-images.githubusercontent.com/39547788/63851608-6fa5de80-c9d1-11e9-98ac-602bb430fc11.png)

<br>