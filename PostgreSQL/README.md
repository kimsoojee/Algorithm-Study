# MAC 에서 PostgreSQL 시작하기

## PostgreSQL 설치
1. Homebrew 를 이용하여 설치한다
```
brew update
brew install postgresql
```
2. 명령어를 입력하여 PostgreSQL 서비스를 시작한다.
```
pg_ctl -D /usr/local/var/postgres start && brew services start postgresql
```
3. 버전 체크하기.
```
psql -V
```

## 명령어 정리
🔖 PostgreSQL 연결 & 해제
- 연결: `psql postgres`
- 해제: `\q`

🔖 
