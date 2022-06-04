# github_chosun 🌴 

### 오픈소스SW개론 과제

---

1. 리눅스 명령어 : top, ps, jobs, kill 명령어 조사하기
2. vim 에디터에서 매크로 사용방법에 대하여 조사하기

---

**리눅스 명령어 : top, ps, jobs, kill 명령어 조사**
 <br>
 <br>
##### 리눅스 명령어에 대한 간략한 설명 테이블 (top, ps, jobs, kill)

|명령어|내용|설명|
|:---:|:---|:---|
|top|실시간으로 CPU 사용률을 체크해주는 도구|리눅스를 사용하는 서버의 성능이나 현재 돌아가고 있는 상황을 볼 때 사용할 수 있다|
|ps|현재 실행중인 프로세스의 목록을 보여주는 명령어|프로그램 프로세스가 정상적인지 혹은 비정상적인지 확인할 때 사용할 수 있다|
|jobs|작업의 상태를 표시하는 명령어|백그라운드로 실행중인 프로세스나 현재 중지된 프로세스를 확인할 때 사용할 수 있다|
|kill|프로세스에 시그널에 보내는 명령어|프로세스를 종료시킬 때 사용할 수 있다|

---

#### _top_

* top
* top -d 2
   - 2초 간격으로 정보 갱신
* top -s
   - 5초 간격으로 (기본값) 갱신된 정보를 확인 가능
   - 기본값으로 CPU 사용률 순으로 정렬
   - 이 상태에서 다음의 옵션에 따라 정보의 내용이 재정렬 또는 변경
      + q : 정렬
      + N : pid 순 정렬(descending)
      + A : pid 순 정렬(ascending)
      + P : CPU 사용률 순 정렬
      + M : 메모리 사용률 순 정렬
      + T : 누적시간(CTIME) 순 정렬
      + l : load average, uptime 사용정보 on/off
      + m : 메모리 사용량 정보 on/off
      + t : CPU 사용률 정보 on/off
      + c : 사용명령어/사용명령어full on/off -> 명령어 추적시 용이
 <br>
 <br>
[top 명령어 실행 화면]<img width="1280" alt="top을 통한 실시간 CPU 사용률 체크" src="https://user-images.githubusercontent.com/97013643/172012188-278f6d21-56e5-4a36-8c02-463bd71c4209.png">

***위쪽 화면을 통해서 현재 시스템의 상태를 알 수 있고, 아래쪽 화면을 통해서 현재 실행중인 프로세스 현황을 볼 수 있다***
 <br>
 <br>
> Top 정보 시스템 내용
>> 23:10:01 : 현재 서버의 시간
>> 
>> 37 days, 7:50 : uptime(켜져있는시간)
>> 
>> 4 users : 유저
>> 
>> load average : 현재 시스템이 얼마나 일을 하고 있는지 1분, 5분, 15분 단위로 실행/대기 중인 프로세스 수를 나타내고 있음.
>> 
>> Tasks : 프로세스 개수


> CPU
>> %us : 유저레벨에서 사용하고 있는 CPU 비중
>> 
>> %sy : 시스템 레벨에서 사용하고 있는 CPU 비중
>> 
>> %id : 유휴 상태의 CPU 비중
>> 
>> %wa : 시스템이 I/O 요청을 처리하지 못한 상태에서의 CPU idle 상태인 비중
>> 
>> MiB Mem, Swap : 각 메모리의 상태 정보 


> 프로세스 상태 정보
>> PID : 프로세스 ID (PID)
>> 
>> USER : 프로세스를 실행시킨 사용자 ID
>> 
>> PR : 프로세스의 우선순위 (priority)
>> 
>> NI : NICE 값. 일의 nice value값이다. 마이너스를 가지는 nice value는 우선순위가 높음.
>> 
>> VIRT : 가상 메모리의 사용량(SWAP+RES)
>> 
>> RES : 현재 페이지가 상주하고 있는 크기(Resident Size)
>> 
>> SHR : 분할된 페이지, 프로세스에 의해 사용된 메모리를 나눈 메모리의 총합.
>> 
>> S : 프로세스의 상태 [ S(sleeping), R(running), W(swapped out process), Z(zombies) ]
>> 
>> %CPU : 프로세스가 사용하는 CPU의 사용율
>> 
>> %MEM : 프로세스가 사용하는 메모리의 사용율
>> 
>> COMMAND : 실행된 명령어


> Top 명령어 옵션(top 실행중 사용가능)
>> shift + p : CPU 사용률이 높은 프로세스 순서대로 표시
>> 
>> shift + m : 메모리 사용률이 높은 프로세스 순서대로 표시
>> 
>> shift + t : 프로세스가 돌아가고 있는 시간 순서대로 표시
>> 
>> k : 프로세스  kill  - k 입력 후 종료할 PID 입력 signal을 입력하라고 하면 kill signal인 9를 입력
>> 
>> a : 메모리 사용량에 따라 정렬
>> 
>> b : Batch 모드 작동
>> 
>> c : 명령행/프로그램 이름 토글
>> 
>> d : 지연 시간 간격은 다음과 같다. -d ss. tt (seconds.tenths)
>> 
>> h : 도움말 
>> 
>> H : 스레드 토글
>> 
>> i : 유휴 프로세스 토글
>> 
>> m : VIRT/USED 토글
>> 
>> M : 메모리 유닛 탐지
>> 
>> n : 반복 횟수 제한 : -n number
>> 
>> p : PID를 다음과 같이 모니터 : -pN1 -pN2 ... or -pN1, N2 [, ...] 
>> 
>> s : 보안 모드 작동
>> 
>> S : 누적 시간 모드 토글
>> 
>> u : 사용자별 모니터링 : u somebody
>> 
>> U : 사용자별 모니터링 : U somebody
>> 
>> u : 입력한 유저의 프로세스만 표시  which u
>> 
>> 숫자 1 : CPU Core별로 사용량을 보여줍니다.

--- 

#### _ps_

* ps
   - 사용자와 관련된 프로세스를 출력
      + -A : 모든 프로세스를 출력
      + a (BSD 계열) : 터미널과 연관된 프로세스를 출력하는 옵션
      + -a : 세션 리더를 제외하고 데몬 프로세스처럼 터미널에 종속되지 않은 모든 프로세스를 출력
      + -e : 커널 프로세스를 제외한 모든 프로세스를 출력
      + -f : 풀 포맷으로 보여주며 유닉스 스타일로 출력해주는 옵션
      + -l (sys V) : 긴 포맷으로 보여준다
      + l (BSD 계열) : 프로세스의 정보를 길게 보여주는 옵션
      + -o : 출력 포맷을 저장하는 옵션 
      + -M : 64비트 프로세스들을 보여준다
      + -m : 프로세스들 뿐만 아니라 커넬 스레드들도 보여준다
      + -p : 특정 PID를 지정할 때 사용
      + -r : 현재 실행중인 프로세서를 보여준다
      + u (BSD 계열) : 프로세스의 소유자를 기준으로 출력
      + -u : 특정 사용자의 프로세스 정보를 확인할 때 사용 (사용자를 지정하지 않으면 현재 사용자를 기준으로 한다)
      + x (BSD 계열) : 데몬 프로세스처럼 터미널에 종속되지 않는 프로세스를 출력
      + -x : 로그인 상태에 있는 동안 아직 완료되지 않은 프로세서들을 보여준다
 <br>
 <br>
[ps 명령어 실행 화면]<img width="1280" alt="ps 명령어에 -u와 -ef 옵션을 준 화면" src="https://user-images.githubusercontent.com/97013643/172012171-65297a93-b3da-41c1-a4d0-77d1c48b681c.png">

***-u 옵션을 통해 현재 사용자의 프로세스 정보와 -ef 옵션을 통해 모든 프로세스를 풀 포맷으로 확인할 수 있다***
 <br>
 <br>
> ps 정보
>> USER : BSD 계열에서 나타나는 항목으로 프로세스 소유자의 이름
>> 
>> UID : STSTEM V 계열에서 나타나는 항목으로 프로세스 소유자의 이름
>>
>> PID : 프로세스의 식별번호
>> 
>> PPID : 부모 프로세스 ID
>> 
>> %CPU : CPU 사용 비율의 추정치 (BSD)
>> 
>> %MEM : 메모리의 사용 비율의 추정치 (BSD)
>> 
>> VSZ : K 단위 또는 메모리 페이지 단위의 가상메모리 사용량
>> 
>> RSS : 실제 메모리 사용량
>> 
>> TTY : 프로세스와 연결된 터미널
>> 
>> S, STAT : 현재 프로세스의 상태 코드
>> 
>> TIME : 총 CPU 사용 시간
>> 
>> COMMAND : 프로세스의 실행 명령행
>> 
>> STIME : 프로세스가 시작된 시간 혹은 날짜
>> 
>> C, CP : 짧은 기간 동안의 CPU 사용률
>> 
>> F : 프로세스의 플래그
>> 
>> PRI : 실제 실행 우선순위
>> 
>> NI : nice 우선순위 번호

--- 

#### _jobs_

* jobs [옵션][작업번호]
   - 현재 쉘 환경에서 시작된 작업의 상태를 표시
      + -l : 정렬
      + -n : pid 순 정렬(descending)
      + -p : pid 순 정렬(ascending)
      + command : CPU 사용률 순 정렬

> jobs로 알 수 있는 세션의 상태 값
>> Running : BSD 계열에서 나타나는 항목으로 프로세스 소유자의 이름
>> 
>> Done : STSTEM V 계열에서 나타나는 항목으로 프로세스 소유자의 이름
>>
>> Done(code) : 프로세스의 식별번호
>> 
>> Stopped : 부모 프로세스 ID
>> 
>> Stopped(SIGTSTP) : SIGTSTP 신호가 작업을 일시 중단
>> 
>> Stopped(SIGSTOP) : SIGSTOP 신호가 작업을 일시 중단
>> 
>> Stopped(SIGTTIN) : SIGTTIN 신호가 작업을 일시 중단
>> 
>> Stopped(SIGTTOU) : SIGTTOU 신호가 작업을 일시 중단

--- 

#### _kill_

* 프로세스에 시그널을 보내 원하는 작업을 하게 하는 명령어
* 일반적으로 프로세스 종료 명령어로 많이 알려져 있는데 -s 옵션으로 시그널을 지정하지 않으면 기본 시그널 값이 정상종료(SIGTERM,15)이기 때문이다
* 프로세스를 안전하게 종료하기 위해서는 "kill -9 pid", "kill -SIGKILL pid" 형태로 프로세스 강제 종료를 권장하지 않는다 (데이터 유실 위험)
* 일반적으로 해당 Process에 문제가 있어서 다시 시작하고자 할 때에는 SIGHUP, SIGTERM, SIGKILL의 순서로 시도하는 것이 권장된다
* kill 명령어는 내부적으로  kill()이란 시스템 콜을 사용하여 구현하고, 프로세스 식별자(PID)로 지시한 프로세스와 프로세스 그룹 식별자(PGID)로 지시한 프로세스 그룹에 시그널을 보낸다
 <br>
 <br>
[kill 명령어 실행 화면]<img width="1280" alt="kill 명령어에 -l 옵션을 준 화면" src="https://user-images.githubusercontent.com/97013643/172019845-4a4b3370-26b1-4952-8efa-fcc850f6e5db.png">

***-l 옵션을 통해서 사용할 수 있는 시그널을 확인할 수 있다***
 <br>
 <br>
 
##### 시그널 종류에 대한 테이블

|No|Name|Default Action|Description|
|:---:|:---:|:---:|:---:|
|1|SIGHUP|terminate process|terminal line hangup|
|2|SIGINT|terminate process|interrupt program|
|3|SIGQUIT|create core image|quit program|
|4|SIGILL|create core image|illegal instruction|
|5|SIGTRAP|create core image|trace trap|
|6|SIGABRT|create core image|abort program (formerly|SIGIOT)|
|7|SIGEMT|create core image|emulate instruction executed|
|8|SIGFPE|create core image|floating-point exception|
|9|SIGKILL|terminate process|kill program|
|10|SIGBUS|create core image|bus error|
|11|SIGSEGV|create core image|segmentation violation|
|12|SIGSYS|create core image|non-existent system call invoked|
|13|SIGPIPE|terminate process|write on apipe with no reader|
|14|SIGALRM|terminate process|real-time timer expired|
|15|SIGTERM|terminate process|software termination signal|
|16|SIGURG|discard signal|urgent|condition present on socket|
|17|SIGSTOP|stop process|stop|(cannot be caught or ignored)|
|18|SIGTSTP|stop process|stop|signal generated from keyboard|
|19|SIGCONT|discard signal|continue after stop|
|20|SIGCHLD|discard signal|child status has changed|
|21|SIGTTIN|stop process|background read attempted from control terminal|
|22|SIGTTOU|stop process|background write attempted to control terminal|

* OS 마다 지원 시그널이 다를 수도 있다
* 시그널은 여러 종류가 있고 각각 번호가 붙어있다
* SIGUSR1과 SIGUSR2 시그널의 용도는 사용자 정의용이다
* 시그널을 생략할 경우 기본 시그널 값인 SIGTERM(15)로 적용된다
* SIGKILL(9)은 개발자가 프로그램을 개발할 때 핸들링을 할 수 없다
* SIGKILL(9)을 이용해 종료할 경우 개발자가 구현한 종료 함수가 호출되지 않고 즉시 프로세스가 종료되어 데이터가 유실되거나 리소스가 제대로 닫히지 않는 문제가 발생할 수도 있다
* SIGTERM(15)나 SIGINT(2)와 같이 종료를 의미하는 signal을 권장하며 제대로 된 프로그램은 보통 cleanup 코드를 수행하고 종료하게 된다
 <br>
 <br>
##### 주요 시그널에 대한 테이블

|시그널 번호|시그널|설명|
|:---:|:---:|:---|
|1|SIGHUP(HUP)|종료(연결 끊기, 실행 종료)|
|2|SIGINT(INT)|종료 (CTRL + C, 인터럽트)|
|3|SIGQUIT(QUIT)|종료 + 코어 덤프 (CTRL + \)
|9|SIGKILL(KILL)|종료 (강제 종료, 프로그램에서 핸들러를 만들 수 없는 시그널)|
|15|SIGTERM(TERM)|종료 (정상 종료)|
|18|SIGTSTP(CONT)|정지된 프로세스 재실행 (STOP이나 TSTP에 의해 정지된 프로세스를 다시 실행)|
|19|SIGCONT(STOP)|정지 (프로그램에서 핸들러를 만들 수 없는 시그널)
|20|SIGCHLD(TSTP)|정지 (CTRL + Z)|

---
 <br>
 <br>
**vim 에디터에서 매크로 사용방법에 대하여 조사**

* 매크로(macro) 사용법
   - 매크로 저장하기
      + q<저장할 매크로 문자>
      + 동작수행 
      +     → q
      + qa → 매크로 작성 
      +     → q 
   - 매크로 사용하기
      + 특정 문자에 저장한 매크로 실행 
      +     → @<저장한 매크로 문자>
      + 매크로 반복 실행 반복횟수 
      +     → @<저장한 매크로 문자>
      + 마지막에 수행한 매크로 실행 
      +     → @@
   - 파일에 저장하기 (재사용)
      + 현재 편집중 내용을 저장 후 ~/vimrc를 열기 (:e 또는 :r) 
      +     → :W → :e~/.vimrc 
      + insert 모드 전환 후 저장할 매크로 이름을 변수로 하여 사용한 매크로 저장하기 
      +     → i/a → let @<변수명>='ctrl+r ctrl+r <마지막 사용 매크로 문자>' → wq! 또는 x  
 <br>
 <br>
[매크로를 활용하는 VimGolf 문제]<img width="1280" alt="VimGolf 5f1063aa8361810006e73210" src="https://user-images.githubusercontent.com/97013643/172022847-b6d28f8b-1aeb-476e-81ab-854b7d073195.png">

***Keystrokes를 기준으로 VimGolf 문제에 대한 설명이며 굵게 표시된 부분들이 매크로를 활용하는 명령행이다***

* 1 ~ 2. 4G 입력 -> 4번째 라인으로 이동
* **3 ~ 4. qa 입력 -> 매크로를 기록하고 a로 alias를 지정**
* 5 ~ 6. yw 입력 -> 커서 위치에서 오른쪽 한 단어 복사
* 7. O 입력 -> 현재 라인을 다음 줄로 밀고 입력 모드 시작
* 8 ~ 15. // TODO<Esc> 입력 -> ‘// TODO’ 입력 후 입력 모드 종료
* 16. B 입력 -> 단어의 시작 위치로 커서 이동 (backward 방향)
* 17. P 입력 -> 커서 이전에 붙혀넣기
* **18. q 입력 -> 매크로 기록 종료**
* 19 ~ 20. 6G 입력 -> 6번째 라인으로 이동
* **21 ~ 22. @a 입력 -> 기록한 매크로 a 실행**
* 23 ~ 24. ZZ 입력 -> 현재 파일을 저장 후 종료
 <br>
 <br>
<details>
<summary>😎NohGyuSeon github page😎</summary>
<div markdown="1">       

[나의 깃헙 페이지](https://www.youtube.com/watch?v=xs92kqU2YWg&list=PLRx0vPvlEmdDySO3wDqMYGKMVH4Qa4QhR "NGS (new_generation_software__") 

</div>
</details>   
 
