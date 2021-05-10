# Github 
On github 

## Big Assumption

+ Ubuntu (with WSL 2)
+ Github CLI 설치 https://github.com/cli/cli#installation

## git initialized 

+ github 웹에 들어가지 않고 터미널에서 해결하자. 
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
