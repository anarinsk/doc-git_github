# doc-git_github
Quick personal guide for git and github 

## Git 

### Frequently but not memorizeable 

+ 로컬의 내용 날리기 
  + 로컬에서 뭔가 작업하던 내용이 있으나 그냥 Github의 내용을 가져오는 게 나을 때 쓰자 
  + 바로 전 커밋으로 돌린다. 

```shell
git reest --hard 
```

### Reuse previous comment 

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
$ git init my-project
$ cd my-project
$ gh repo create

# create a repository with a specific name
$ gh repo create my-project

# create a repository in an organization
$ gh repo create cli/my-project

# disable issues and wiki
$ gh repo create --enable-issues=false --enable-wiki=false
```



