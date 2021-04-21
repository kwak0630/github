# gitHub

소스코드를 효과적으로 관리하기 위한 서비스로 '분산형 버전 관리 시스템' 입니다.

소스코드를 열람하고 변경된 이력을 쉽게 관리 할 수 있고, 특정 시점에 저장된 버전과 비교하거나 되돌아 갈 수 있어 편리한 버전 관리를 지원합니다.

#### gitHub 기본지식

- 저장소 (repository)

  저장소는 파일이나 디렉토리를 저장하는 장소입니다. 저장소는 내 컴퓨터에 있는 '로컬 저장소'와 전용 서버에서 관리되는 '원격 저장소'의 2개가 존재합니다. 기본적으로 로컬 저장소에서 작업을 진행하고 그 결과를 원격 저장소에 저장할 수 있습니다.

- 브랜치 (branch)

  버전의 지속적인 유지 보수를 통해 기능을 추가하거나 버그를 수정하게 됩니다. 여러 버전을 관리하기 위해 브랜치라는 기능을 사용합니다.

- 커밋 (commit)

  파일을 추가하거나 변경 내용을 저장소에 저장하는 작업. 변경한 사람, 시간, 내용 등을 기록해 과거 변경 이력과 내용을 손쉽게 파악할 수 있습니다.

- 푸시 (push)

  파일을 추가하거나 변경 내용을 원격 저장소에 업로드 하는 작업



#### gitHub 사용법

1. gitHub에 저장소 작성 또는 복제
2. 파일 작성, 편집
3. 파일 생성, 변경, 삭제
4. 변경 결과를 로컬 저장소에 커밋
5. 로컬 저장소에서 푸쉬해 원격 저장소에 반영



##### gitHub에 저장소 작성

Create New Repository 버튼 클릭 -> Repository name 입력 -> Description 작성 -> 저장소 유형 "Public" 선택 (Private 는 유료회원만)



##### 파일의 작성, 편집

로컬 저장소를 만들어 파일 하나를 만든다.

```
mkdir gitTest //새로운 디렉토리 만드는 명령
cd gitTest //디렉토리 이동하는 명령
git init //git 저장소를 새로 만드는 명령. 이 명령을 실행하면 현재 디렉토리를 git 저장소로 변환
```



##### 파일의 생성, 변경, 삭제 를 인덱스에 추가 

hello.html 라는 파일 생성

```
git add hello.html //인덱스에 추가하는 명령
```



##### 변경 결과를 로컬 저장소에 커밋

 커밋은 파일이나 디렉토리의 추가 또는 변경을 저장소에 기록하는 작업입니다.

```
git commit -m "new file" //파일 추가
git status //파일 추가가 되었는지 확인
git remote add origin https://github.com/kwak0630/gitTest.git //원격 저장소의 정보를 추가
```



##### 로컬 저장소에서 원격 저장소로 푸시

```
git push origin master //원격저장소에 반영하는 명령
```

끝으로  https://github.com/kwak0630/gitTest 가서 푸시가 잘 되었는지 확인합니다.



#### branch 사용법

1. 브랜치의 생성, 이동
2. 브랜치에서의 개발 작업
3. 브랜치에서 푸시
4. 브랜치에서 풀
5. 브랜치 병합
6. 브랜치 삭제



##### 브랜치의 생성, 이동

```
git branch //브랜치 목록 살피는 명령어

* master //실행결과
```

현재 브랜치에서 * 표시가 붙습니다. 이것은 브랜치가 master 인 것이고 현재 브랜치도 master 임을 나타내는 것입니다. 새로운 브랜치를 생성해 봅니다.

```
git branch dev //브랜치 생성
git checkout dev //브랜치 이동 명령
git checkout -b dev //브랜치 만들기 및 이동 명령
git branch //다시 브랜치 목록 살피기

* dev //실행결과
master
```



##### 브랜치에서의 개발작업

hello2.html 파일을 만듭니다.



##### 브랜치에서 푸시

```
git add hello2.html
git add -m "new file2"
git push origin dev
```

gitHub에서 확인 해 보면, master 과 dev 브랜치가 존재하고 dev 브랜치에서 푸시된 것을 알 수 있습니다.



##### 브랜치에서 풀

다른 개발자가 dev 저장소로 개발하려면 하기 위해서는 아래 명령어를 실행합니다.

```
git checkout dev
git pull //dev 코드 가져오기
ls //로컬 파일 목록 보기
```



##### 브랜치 병합

실제 개발형장에서는 새로운 기능의 브랜치를 만들고 개발하고, 테스트가 완료되면 메인 master브랜치에 통합이라는 흐름으로 작업을 수행합니다. 이 브랜치의 통합 작업을 병합이라고 합니다.

```
git checkout master //master로 전환
git merge dev //브랜치 결과 병합
hellow.html //실행결과 hellow2가 추가된거 확인
git push origin master //푸쉬
```

https://github.com/kwak0630/gitTest.git 가서 브랜치를 master 로 가서 확인합니다.



##### 브랜치 삭제

사용하지 않는 브랜치를 제거 할 수 있습니다. 하지만 실제 개발 작업에서는 잘 못 작성되었을 경우를 제외하고 작업이 완료된 분기까지 남겨두는 것이 일반적입니다.

```
git branch -d dev //삭제 명령
git branch
```



#### 자주 사용하는 Git 명령어

- mkdir [name] : [name]디렉토리 만드는 명령어

- cd [name] : [name]디렉토리로 들어가는 명령어

- pwd : 현재 디렉토리를 확인하는 명령어

  

- git init : git 저장소 만드는 명령어

- git status : 저장소의 상태 확인 하는 명령어 (이름, 추가/변경 된 파일 및 디렉토리 목록)
- git add : 파일이나 디렉토리를 인덱스에 추가하는 데 사용하는 명령어
- git commit : 추가 된 파일이나 폴더의 내용을 저장소에 쓸 때 사용하는 명령어
- git branch 
  - git branch [name] : [name]브랜치 만들기
  - git branch : 브랜치 목록 보기
  - git branch -d [name] : [name]브랜치 삭제
- git checkout : 로컬 저장소의 브랜치를 전환할 때 사용하는 명령어
- git log : 로컬 저장소의 커밋 히스토리를 탐색하는 데 사용하는 명령어
- git grep : 저장소의 파일 내용에서 검색하고 할 때 사용하는 명령어
- git clone : 기존 원격 저장소를 로컬에 다운로드 하기 위하여 사용하는 명령어
  
  - git clone [url]
- git remote 
  - git remote : 원격 저장소의 이름 목록의 표시
  - git remote -v  : 자세한 목록 보기
  - git remote add [url] : 원격 저장소 추가
  - git remote rm [url] : 원격 저장소 제거
- git reset : 로컬 저장소의 커밋을 취소하기 위하여 사용하는 명령어
- git merge : 현재 브랜치에 다른 지점에서 변경 사항을 병합하는데 사용하는 명령어 
- git pull : 원격 브랜치의 변경 사용을 캡쳐하기 위해 사용하는 명령어