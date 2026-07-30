# 🚀 개발 워크스테이션 구축 및 Docker 실습 미션

## 1. 프로젝트 개요
- **목표:** 리눅스 터미널, Docker, Git을 활용하여 재현 가능한 개발 환경을 구축하고, 컨테이너 기반 웹 서버의 동작 원리(포트 매핑, 볼륨)를 이해합니다.
- **핵심 내용:** CLI 조작, Dockerfile 작성, 데이터 영속성 검증, 버전 관리.

## 2. 실행 환경
- **OS:** Ubuntu 22.04 LTS (또는 macOS/Windows WSL2)
- **Shell:** Zsh / Bash
- **Docker Version:** 24.0.x
- **Git Version:** 2.x.x

## 3. 수행 항목 체크리스트
- [x] 터미널 작업 디렉토리 생성 및 권한 설정
- [x] Docker 설치 및 상태 점검
- [x] Dockerfile 작성 및 이미지 빌드
- [x] 컨테이너 실행 및 포트 매핑 설정
- [x] 바인드 마운트를 이용한 실시간 코드 변경 반영
- [x] Docker 볼륨을 이용한 데이터 영속성 검증
- [x] Git/GitHub 연동 및 VSCode 설정

## 4. 터미널 조작 및 Docker 점검 로그
### 4.1 기본 점검
```bash
# Docker 버전 확인
docker --version

# Docker 상태 확인
docker info