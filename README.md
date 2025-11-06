## 🔥 EC2 CI/CD 자동화 배포 🔥

### 📌 Overview

- GitHub Actions 자동 배포 파이프라인 구축
- 서버별 환경 변수 관리

---
<br>

## 🔧 GitHub Actions 설정

### ✅ 1. Secrets 설정 

| Key | Description |
|-----|---------------|
| EC2_USER | EC2 접속 유저 |
| EC2_KEY | PEM Key 내용 전체 |
| EC2_HOST | EC2 IP |
| EC2_DATABASE_HOST | 데이터 베이스 ip | 
|AWS_ACCESS_KEY_ID|  IAM 액세스 키 |
|AWS_REGION|  aws 지역명 |
|AWS_S3_BUCKET|  aws s3 버킷 이름 |
|AWS_SECRET_ACCESS_KEY| IAM 시크릿 키 |
|MAIL_PASSWORD| Gmail 비밀번호 |
|JWT_SECRET| openssl rand -base64 32의 결과 값 |
|KAKAO_CLIENT_ID| 카카오 rest api 키 |
|KAKAO_CLIENT_SECRET| 카카오 secret 키 |
|NAVER_CLIENT_ID| 네이버 Client ID |
|NAVER_CLIENT_SECRET| 네이버 Client Secret |
|SMS_ACCESS_KEY| coolsms access 키 |
|SMS_SECRET_KEY| coolsms secret 키 |


<br>

### 📂 2. Workflow 파일 및 Dockerfile 생성 

| 파일 | 설명 | 링크 |
|------|--------|--------|
|`ec2_aws_deploy.yml`| GitHub Actions 배포 설정|
|`Dockerfile`| Docker 빌드 설정|


<br>

## Docker 설치하기 

### 1. 설치
```bash
# 도커 설치하기
sudo apt install docker.io -y

# 등록
sudo systemctl enable docker
# 시작
sudo systemctl start docker
# 체크
sudo systemctl status docker
# 계정 등록
sudo usermod -aG docker ubuntu
# 도커 버전 체크
docker --version

# 실행중인 프로세스 목록 
docker ps  

# 도커이미지 출력
docker images

```
### 2. 결과 이미지
> docker ps 결과


> docker images 결과



### 3. 도커 명령어 모음
| 명령어 | 설명 |
|--------|--------|
| `docker stop [컨테이너명]` | 실행 중인 `[컨테이너명]` 컨테이너 중지 |
| `docker rm [컨테이너명]` | 중지된 `[컨테이너명]` 컨테이너 삭제 |
| `docker images -aq` | 컬럼명 없이 모든 IMAGE ID 출력 |
| `docker rmi $(docker images -aq)` | 모든 Docker 이미지 삭제 |
| `docker images -a` | 로컬에 저장된 Docker 이미지 목록 확인 |
| `docker ps -a` | 실행/중지 포함 모든 컨테이너 목록 확인 |
| `docker logs [컨테이너명]` | `[컨테이너명]` 로그 출력 (`--tail`, `-f` 옵션 사용 가능) |
| `docker system prune -a` | 사용하지 않는 컨테이너/이미지/네트워크 일괄 삭제 (**주의**) |
| `ls` | 현재 디렉토리 파일 목록 확인 |
| `sudo rm -rf [폴더명]` | 로컬 디렉토리 `[폴더명]` 강제 삭제 |

<br>  

## 🧩 troubleshooting

<img width="943" height="554" alt="스크린샷 2025-11-06 오후 5 18 43" src="https://github.com/user-attachments/assets/85e5b5b0-027e-4b65-aff3-a6d9d57e6ca6" />



⚒️ 해결방안












