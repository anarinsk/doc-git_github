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

###  Work Tree and Stage 

`git status`는 working tree와 staging area의 상태를 보여주는 명령어이고, `-s`는 이를 짦게 표현한다. 단축 명령어로는 `gst` 혹은 `gst -s`. `-s` 옵션을 통해 파일 상태를 문자 두개로 짤막하게 보여준다. 첫번째(왼쪽)은 staging area에서의 상태를, 두번째(오른쪽)은 working tree에서의 상태를 나타낸다. Staging 상태는 `A`, `M`, ` `(공백)의 상태, 그리고 working tree의 상태는 `M`, ` `의 두 개의 상태를 지닐 수 있다. 따라서 조합 가능한 상태는 모두 6개가 된다. 




```shell
(README 파일 생성)
> gst -s 
?? README
> git add README 
> gst -s 
A  README
(README 파일 수정)
AM README
> git add README 
A  README
```




### 


