# 🚀 개발 워크스테이션 구축 및 Docker 실습 미션

## 1. 프로젝트 개요
- **목표:** 리눅스 터미널, Docker, Git을 활용하여 재현 가능한 개발 환경을 구축하고, 컨테이너 기반 웹 서버의 동작 원리(포트 매핑, 볼륨)를 이해합니다.
- **핵심 내용:** CLI 조작, Dockerfile 작성, 데이터 영속성 검증, 버전 관리.

## 2. 실행 환경
- **OS:** Windows WSL2
- **Shell:** Bash
- **Docker Version:** 29.6.2
- **Git Version:** 2.52.0.windows.1

## 3. 수행 항목 체크리스트
- [x] 터미널 작업 디렉토리 생성 및 권한 설정
- [x] Docker 설치 및 상태 점검
- [x] Dockerfile 작성 및 이미지 빌드
- [x] 컨테이너 실행 및 포트 매핑 설정
- [x] 바인드 마운트를 이용한 실시간 코드 변경 반영
- [x] Docker 볼륨을 이용한 데이터 영속성 검증
- [x] Git/GitHub 연동 및 VSCode 설정

## 4. 터미널 조작 로그 기록
### 4.1 기본 점검
```bash
1. 현재 위치 확인
PS C:\Users\PC\Desktop\my-learning-project> pwd

Path
----
C:\Users\PC\Desktop\my-learning-project

2. 목록 확인 (숨김 파일 포함 상세 정보)
PS C:\Users\PC\Desktop\my-learning-project> Get-ChildItem -Force

    디렉터리: C:\Users\PC\Desktop\my-learning-project


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d--h--    26-07-30(목)   오후 9:09                .git
-a----    26-07-30(목)   오후 9:04           4827 README.md

3. 디렉토리 생성 및 이동 (New-Item, Set-Location)

##폴더 생성
PS C:\Users\PC\Desktop\my-learning-project> New-Item -Path "ps_test" -ItemType Directory


    디렉터리: C:\Users\PC\Desktop\my-learning-project


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----    26-07-30(목)   오후 9:24                ps_test

##폴더 이동
PS C:\Users\PC\Desktop\my-learning-project> Set-Location ps_test
PS C:\Users\PC\Desktop\my-learning-project\ps_test>

4. 빈 파일 생성 및 내용 확인 (New-Item, Get-Content)

## 빈 파일 생성
PS C:\Users\PC\Desktop\my-learning-project\ps_test> New-Item -Path "hello.txt" -ItemType File


    디렉터리: C:\Users\PC\Desktop\my-learning-project\ps_test


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----    26-07-30(목)   오후 9:31              0 hello.txt

##파일 내용 확인 (내용이 없으므로 아무것도 출력되지 않음)
PS C:\Users\PC\Desktop\my-learning-project\ps_test> Get-Content hello.txt

5. 파일 복사 (Copy-Item)
# 이름 변경 (hello_copy.txt -> renamed.txt)
PS C:\Users\Student\ps_test> Move-Item hello_copy.txt renamed.txt

# 결과 확인
PS C:\Users\Student\ps_test> ls
Name
----
hello.txt
renamed.txt
