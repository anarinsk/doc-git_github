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


