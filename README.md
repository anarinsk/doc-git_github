# doc-git_github
Quick personal guide for git and github 

## Git 

## Ultimate Reference 

https://git-scm.com/book/ko/v2/

## Frequently but not memorizeable 

+ 로컬의 내용 날리기 
  + 로컬에서 뭔가 작업하던 내용이 있으나 그냥 Github의 내용을 가져오는 게 나을 때 쓰자 
  + 바로 전 커밋으로 돌린다. 

```shell
git reset --hard 
```
+ 이전 코멘트 그대로 재사용 하기 

```shell
git commit --reuse-message=HEAD
```

## Github 

### 가정 

+ Ubuntu 
+ Github CLI 설치 https://github.com/cli/cli#installation

### git initialized 

+ Git을 초기 설정하는 초반 과정이 그대로 필요하다. 
+ https://cli.github.com/manual/gh_repo_create

```shell
# create a repository under your account using the current directory name
$ git init my-project # Do not make directory with mkdir!
$ cd my-project
$ gh repo create

# create a repository with a specific name
$ gh repo create my-project

# create a repository in an organization
$ gh repo create cli/my-project

# disable issues and wiki
$ gh repo create --enable-issues=false --enable-wiki=false
```

### `master`로 생성되는 게 싫다면?

+ 일단 뭔가 파일이 있어야 한다. 

```shell
$ touch README.md
$ git add . 
$ git commit -m "initial commit"
$ git branch -m master main 
$ git push -u origin main 
```

## Key Usages 

### `checkout` vs `reset`

- checkout은 현재 위치 즉, `HEAD`를 옮기는 행위다. 
- reset은 현재 위치한 브랜치를 어떤 다른 브랜치로 업데이트하는 것이다. 그쪽으로 이동하는 게 아니다. 

### `log`

- `git log`를 보면 많은 것을 알 수 있다. 옵션들을 잘 파악해두자. 
- `--oneline` 한줄로 압축 표시 
- `--branches` 브랜치들까지 전부 표기한다. 
- `--networks` 연결관계들을 나타낸다. 

```shell
git config --global alias.logs "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```

- 실행한 뒤 `git logs`를 실헹하면 예쁜 형태의 그래프를 볼 수 있다. 
- 로그는 많은 정보를 담고 있다. 잘 째려보기 바란다. 




