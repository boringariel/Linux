### Basic commands
* echo: 입력내용 또는 시스템 환경변수를 화면에 출력
```.{linux}
$echo HOME  #'HOME'이 출력됨
$echo $HOME #'/root'가 출력됨 ($HOME이 환경 변수로 사용되고 있음)
```


* man: 알고 싶은 명령어의 메뉴얼을 보여준다 (manual)
```.{linux}
$man date #date에 대한 도움말이 표기됨
```


* cat: 텍스트 파일 내용을 출력
```.{linux}
$cat ./(파일 경로 및 이름)
$cat -n ./(파일 경로 및 이름) #line number를 포함해 출력
```


* sort: 텍스트 파일 내용을 알파벳 순서대로 정렬해 화면에 출력

* head: 파일 첫머리 출력
```.{linux}
$head ./a       #a 파일의 앞 10줄 표시
$head ./a -n 20 #a 파일의 앞 20줄 표시
```


* grep: 특정 문자열을 포함하는 line 검색

* more & less: 페이지 단위로 파일 내용을 출력
```.{linux}
$more ./(파일 경로 및 이름)
$less ./(파일 경로 및 이름)
```


* cut: 파일에서 원하는 필드를 뽑아냄
```.{linux}
$cut -f 2 ./a        #a 파일의 2번째 column을 뽑아냄
$cut -d ',' -f 2 ./a #a 파일의 2번째 column을 뽑아냄. 필드 구분은 ','로 되어 있음을 명시
```


* df: System 디스크 사용량과 남은 양 표시
```.{linux}
$df
$df -h #용량 단위를 적용해 표시
```


* who, w: 접속 중인 계정을 표시하는 두 명령어

* clear: 스크린 지우기

---

### 파일 탐색/관리

* I/O Redirection

| Redirector | Function |
| --- | --- |
| cmd1&#124;cmd2  | 명령어 조합시 사용. cmd1과 cmd2 명령어가 조합되어 실행됨 |
| >file      | output to file. 화면에 출력되지는 않음 |
| <file      | input from file |
| >>file     | append to file |

* pwd: 현재 디렉터리 경로를 보여줌 (Print Workind Directory)

* mkdir: 폴더 생성 (MaKe DIRectory)

* cd: 디렉터리 이동 (Change Directory)
```.{linux}
$cd .. #상위 디렉터리로 이동
$cd . #현재 디렉터리로 이동
$cd ~ #홈 디렉터리로 이동
```


* rm: 삭제 (ReMove)
```.{linux}
$rm -f #강제 삭제
$rm -r #디렉터리와 하위 파일 전체 삭제
```


* ls: 디렉터리와 파일 목록 보기 (ListS)

* cp: 파일 또는 디렉터리를 지정한 경로에 복사 (CoPy)
```.{linux}
$cp a b          #a 파일을 같은 경로에 b 파일로 저장
$cp -R dir1 dir2 #dir1 디렉터리와 하위 파일 전체를 dir2로 저장
```


* mv: 파일 또는 디렉터리를 이동하거나 이름 변경 (MoVe)
```.{linux}
$mv a b      #a 파일을 b 경로로 이동. b 경로가 없는 경우 a 파일을 b 이름으로 변경
$mv a dir1/b #a 파일을 dir1 경로 아래에 b 이름으로 바꿔서 이동
```