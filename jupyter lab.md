## Linux server를 이용해 jupyter lab 사용
* jupyter lab 개발환경 구성을 해 보자
---

### jupyter lab 설치 및 서버 환경설정

```{.linux}
#sudo pip install jupyterlab    #conda 명령어도 가능
#jupyter lab --generate-config  #환경설정 파일 만들기
```

* `$HOME/.jupyter/` 경로에 `jupyter_notebook_config.py` 파일이 생성된다
* `jupyter_notebook_config.py` 파일에서 아래 항목의 주석 표기(`#`)를 삭제하고 수정한다

```{.linux}
c.NotebookApp.ip = '*'    #접속을 허용할 ip. '*' 입력시 모든 ip를 허용함
c.NotebookApp.port = 8888 #접속에 사용할 포트. 기본값은 8888
```

### jupyter lab 접속
* jupyter lab 접속시에는 아래 명령어를 입력한다. 이 때는 터미널창을 띄워놓는 동안에만 접속할 수 있다

```{.linux}
#sudo su                                #패키지 설치를 위해서는 관리자 권한을 획득한 상태에서 실행하는 것이 좋다
#jupyter lab --ip=(ip주소) --allow-root #루트 접속 권한을 주는 것이 좋다
```

* 해당 프로세스가 가동되는 동안, 아래 주소로 접속할 수 있다<br>
`http://(ip주소):(포트)/?token=(SHA-1 코드로 적힌 비밀번호, 적지 않아도 됨)`


### jupyter lab background 접속
* 아래 명령어를 이용해서 터미널창을 꼭 띄워놓을 필요 없게 만들 수도 있다

```{.linux}
#sudo su                                      #패키지 설치를 위해서는 관리자 권한을 획득한 상태에서 실행하는 것이 좋다
#nohup jupyter lab --ip=(ip주소) --allow-root #백그라운드 구동, 루트 접속 권한을 주는 것이 좋다
```

* 해당 프로세스가 가동되는 동안, 접속은 포그라운드로 접속할 때와 동일한 방법으로 가능하다
* 프로세스 종료는 아래 명령어로 가능하다

```{.linux}
#ps -ef | grep jupyter   #jupyter 명령어를 사용한 프로세스 번호 확인
#kill -9 (프로세스 번호)  #프로세스 강제 종료
```

### jupyter lab 비밀번호 설정
* 기본 설정으로는 접속할 때, jupyter lab 실행시 제공되는 token을 입력해야 한다
* 불편함을 없애기 위해 개인 비밀번호를 사용할 수 있다<br>
`#jupyter notebook password` 입력 후, 비밀번호를 입력하면 된다
