# UniGen Backend

> UniGen SNS 플랫폼의 인증, 피드, 이미지 업로드, AI 콘텐츠 생성을 처리하는 Node.js 백엔드

<p align="center">
  <a href="https://www.notion.so/325441f66d78810f809ec11f775eb92c?pvs=1">
    <img src="https://img.shields.io/badge/Notion%20Project%20Page-View%20Details-7C3AED?style=for-the-badge&logo=notion&logoColor=white" alt="Notion Project Page" />
  </a>
</p>

<p align="center">
  <img src="./assets/unigen-dual-mode.png" width="88%" alt="UniGen 서비스 화면" />
</p>

## ✨ Highlights

| 구분 | 내용 |
|---|---|
| 문제 | SNS 기능을 위해 인증, 피드, 이미지 업로드, AI 콘텐츠 생성 API가 필요함 |
| 해결 | Node.js + Express 기반 REST API와 MySQL, AWS S3, OpenAI API 연동 |
| 담당 | 인증, 피드, 이미지 업로드, AI 콘텐츠 생성, Swagger 문서화 흐름 구현 |
| 결과 | 프론트엔드와 연결 가능한 SNS 백엔드 API 서버 구현 |

---

## 1. 프로젝트 개요

UniGen Backend는 일반 사용자와 시니어 사용자를 함께 고려한 Dual Mode SNS 플랫폼의 서버입니다.

사용자 인증, 게시물/댓글/스토리, 이미지 업로드, AI 콘텐츠 생성 기능을 REST API로 제공하고, 프론트엔드와의 협업을 위해 Swagger 기반 API 문서화를 적용했습니다.

---

## 2. 서비스 화면

<p align="center">
  <img src="./assets/unigen-sns-helper.png" width="88%" alt="UniGen SNS Helper 화면" />
</p>

프론트와 백엔드는 같은 서비스 경험을 기준으로 구성했습니다. 프론트엔드는 사용자 화면을 담당하고, 백엔드는 인증·게시물·이미지·AI 생성 기능을 API로 제공합니다.

---

## 3. 주요 기능

- Kakao OAuth 기반 소셜 로그인
- JWT 기반 인증 및 사용자 권한 처리
- 피드, 댓글, 좋아요, 스토리 관련 API
- 시니어 모드 사용자 흐름을 위한 API 구성
- AWS S3 기반 이미지 업로드 및 저장
- OpenAI API 기반 콘텐츠 생성 기능
- Swagger 기반 API 문서화

---

## 4. My Role

- Node.js + Express 기반 API 서버 구성
- 인증, 피드, 댓글, 이미지 업로드 API 구현
- AWS S3 이미지 저장 흐름 연결
- OpenAI API 기반 콘텐츠 생성 기능 연동
- Swagger 문서화로 프론트엔드와 협업 가능한 API 명세 정리

---

## 5. UX / System Flow

<p align="center">
  <img src="./assets/unigen-architecture.png" width="88%" alt="UniGen UX 및 시스템 플로우" />
</p>

위 이미지는 백엔드 내부 아키텍처가 아니라, 사용자의 서비스 이동 흐름과 각 화면이 어떤 API 그룹과 연결되는지 보여주는 전체 시스템 플로우입니다.

```text
Welcome Page
  → 로그인 / 회원가입
  → 일반 모드 또는 시니어 모드 선택
  → 홈 / 탐색 / 업로드 / 프로필 / 글쓰기
  → users / auth / stories / posts / senior API 연동
```

---

## 6. Tech Stack

| 영역 | 기술 |
|---|---|
| Runtime | Node.js |
| Framework | Express.js |
| Database | MySQL |
| Auth | JWT, Kakao OAuth |
| Storage | AWS S3 |
| AI | OpenAI API |
| API Docs | Swagger |
| Language | JavaScript |

---

## 7. How to Run

```bash
npm install
npm start
```

### Environment Variables

```env
DB_HOST=localhost
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_NAME=unigen
JWT_SECRET=your_jwt_secret
AWS_ACCESS_KEY_ID=your_aws_access_key
AWS_SECRET_ACCESS_KEY=your_aws_secret_key
AWS_REGION=your_aws_region
S3_BUCKET_NAME=your_bucket_name
KAKAO_CLIENT_ID=your_kakao_client_id
KAKAO_REDIRECT_URI=your_kakao_redirect_uri
OPENAI_API_KEY=your_openai_api_key
PORT=3000
```

---

## 8. Related Repository

- [KDY0829/unigen-front](https://github.com/KDY0829/unigen-front)
