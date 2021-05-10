# Quick and Git 
Quick and easy to forget items 

## Deleting local 

+ 로컬의 내용 날리기 
  + 로컬에서 뭔가 작업하던 내용이 있으나 그냥 Github의 내용을 가져오는 게 나을 때 쓰자 
  + 바로 전 커밋으로 돌린다. 

```shell
git reset --hard 
```

## Reuse comment 

+ 이전 코멘트 그대로 재사용 하기 

```shell
git commit --reuse-message=HEAD
```

## Clone, easy way 

+ 보통 `git clone`이 표준적인 사용이다. 
+ `gh` CLI를 깔았다면 조금 더 편리한 방법으로 사용할 수 있다. 

```shell
gh repo clone {account}/{repo}
```