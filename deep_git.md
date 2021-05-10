# Deep Git 
Personal advanture into Git 

## `checkout` vs `reset`

- checkout은 현재 위치 즉, `HEAD`를 옮기는 행위다. 
- reset은 현재 위치한 브랜치를 어떤 다른 브랜치로 업데이트하는 것이다. 그쪽으로 이동하는 게 아니다. 

## `log`

- `git log`를 보면 많은 것을 알 수 있다. 옵션들을 잘 파악해두자. 
- `--oneline` 한줄로 압축 표시 
- `--branches` 브랜치들까지 전부 표기한다. 
- `--networks` 연결관계들을 나타낸다. 

```shell
git config --global alias.logs "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```

- 실행한 뒤 `git logs`를 실헹하면 예쁜 형태의 그래프를 볼 수 있다. 
- 로그는 많은 정보를 담고 있다. 잘 째려보기 바란다. 

