# The Basics of the Basic 
가장 기본이 되는 것을 알아두자. 


## How to Start Repo 

### Create 

먼저 로컬에 생성하는 법이다. 

```shell
> git init {your-dir}
```

git이 해당 디렉토리를 만들고 이 디렉토리 내부의 깃을 초기화 한다. 

Github CLI가 설치되어 있다면 깃허브에 리포를 함께 만들 수 있다. 

```shell
> gh repo create {your-dir}
```

명령을 실행하면, 

+ 퍼브릭, 프라이빗으로 만들 것인지 
+ 원격 저장소를 만들 것인지 
+ 로컬 저장소를 만들 것인지 

여부를 물어본다. 

### Clone 

```shell
> git clone {your-https}
```

```shell
> gh repo clone {your-repo-in-github}
```

둘 중 어느 것을 써도 좋다. 후자를 쓴다면 거추장스럽지 않게 리포만 따올 수 있다. 

## File Status 

![](https://git-scm.com/book/en/v2/images/areas.png)

|:File Status:|Staged?|Committed?|
|------|---|---|
|Modified| X | X |
|Staged (index)| O | X |
|Committed| O | O |

- Modified는 Working Directory의 상태를 나타낸다. 
- Staged는 Staging Area에서의 상태를 나타낸다. 
- Committed는 스냅샷이 만들어졌다는 뜻이다. 


## Life Cycle of a File

![](https://git-scm.com/book/en/v2/images/lifecycle.png)

###  Work Tree and Staging Area

`git status`는 working tree와 staging area의 상태를 보여주는 명령어이고, `-s`는 이를 짦게 표현한다. 단축 명령어로는 `gst` 혹은 `gst -s`. `-s` 옵션을 통해 파일 상태를 문자 두개로 짤막하게 보여준다. 첫번째(왼쪽)은 staging area에서의 상태를, 두번째(오른쪽)은 working tree에서의 상태를 나타낸다. Staging 상태는 `A`, `M`, ` `(공백)의 상태, 그리고 working tree의 상태는 `M`, ` `의 두 개의 상태를 지닐 수 있다. 따라서 조합 가능한 상태는 모두 6개가 된다. 


```shell
(README 파일 생성)
> echo "generate README" > README
> gst -s 
?? README
(README 파일 스테이징)
> git add README 
> gst -s 
A  README
(README 파일 수정)
> echo "modify README 1st" > README
AM README
> git add README 
A  README
> git commit -a -m "first commit"
> gst -s 

(README 파일 수정)
> echo "modify README 2nd with 1st commit" >> README
> gst -s 
 M README
(README 파일 스테이징) 
> git add README 
> gst -s 
M README 
(README 파일 수정) 
> echo "modify README 3rd with 1st commit" >> README
> gst -s
MM README 
(README 파일 스테이징)
> git add README 
> gst -s 
M README 
```

git의 주기를 대략 파악할 수 있을 것이다. 

+ staging area에서 
  + `A` commit이 되기 전에만 설정되는 상태이다. 파일이 편입되었음을 뜻한다. 
  + `M` 이전에 커밋된 적이 있는 파일이 수정되었음을 뜻한다. 
  + ` ` 해당 파일에 대한 정보가 현재 스테이징 영역에 없다. 
 
+ working tree에서 
  + ` ` 해당 파일이 워킹 트리에서 아무런 조직도 일어나지 않았다. 
  + `M` 해당 파일이 워킹 트리에서 변경되었다. 


commit의 개념은 현재 staging area의 스냅샷을 뜨는 것이다. 이런게 사직이 찍히면 스테이징 영역을 비워진다. 둘 다 공백인 상태, 즉 파일이 처음 생성되고 아무런 작업이 이루어지지 않은 상태는 `??`이 표시된다. 한번이라도 파일을 스테이징 영역에 올려놓지 않으면 해당 파일에 어떤 조작을 하더라도 상태는 계속 `??`에 머물러 있다. 


## Branch 

```shell
> git add README test.rb LICENSE
> git commit -m 'The initial commit of my project'
```

하나의 커밋에 대해서 깃 디렉토리에 아래와 같이 세 종류의 파일이 생성된다. 이 셋은 항상 함께 따라 다닌다. 

![](https://git-scm.com/book/en/v2/images/commit-and-tree.png)

- 커밋 정보 (커밋 사이즈, 참조 트리, 저자, 페어런트)
- 트리에 관한 정보 (파일에 관한 정보) 
- blob (파일의 내용) 

![](https://git-scm.com/book/en/v2/images/commits-and-parents.png)

커밋은 위의 그림처럼 진행된다. 화살표의 의미를 새기자. 화살표는 페어런트을 나타낸다. 즉, `HEAD` -> `cd14e`, 라면 이는 HEAD가 `Cd14e` 커밋을 참조한다는 이야기다. 화살표 때문에 조상 후손 관계가 약간 혼동될 수 있지만, `git log`를 자주 보면 그럴 일이 없다. 

한마디로! Git의 브랜치는 커밋 사이를 가볍게 이동할 수 있는 어떤 포인터 같은 것이다. 

### Branches in action 

```shell
git branch testing 
```

![](https://git-scm.com/book/en/v2/images/two-branches.png)

testing이라는 브랜치를 만들어도 위 그림처럼 master와 함께 따라다닌다. 깃에는 특별한 포인터가 있다. `HEAD`는 현재 내가 있는 위치를 나타낸다. 

![](https://git-scm.com/book/en/v2/images/head-to-master.png)

```shell
git checkout testing 
```

![](https://git-scm.com/book/en/v2/images/head-to-testing.png)

