# matdori 랜딩 배포 (GitHub → Vercel, matdori.franchises.co.kr)

이 폴더는 이미지가 CDN 링크라 **그대로 올리면 사진까지 바로 표시**됩니다.
기존 franchises.co.kr / HeaduriChicken 은 건드리지 않습니다(서브도메인 독립 배포).

## 1) GitHub에 올리기 (개발 없이 웹 업로드)
1. github.com → New repository (예: matdori-landing, Private 가능)
2. "uploading an existing file" → 이 폴더의 **index.html, complete.html, privacy.html, robots.txt** 를 드래그&드롭 → Commit

## 2) Vercel 연결 (자동배포)
1. vercel.com → Add New → Project → Import Git Repository → 방금 저장소 선택
2. Framework: Other(정적) 자동 → Deploy
3. 이후 GitHub에 커밋할 때마다 자동 재배포

## 3) 도메인 연결
1. Vercel → 프로젝트 → Settings → Domains → matdori.franchises.co.kr 추가
2. 가비아 → franchises.co.kr → DNS 관리 → 레코드 추가
   - 타입 CNAME / 호스트 matdori / 값 cname.vercel-dns.com (Vercel 안내값)
   - 기존 @, MX, TXT 삭제 금지
3. 메타 도메인 인증: 루트 franchises.co.kr 에 TXT 1회

## 4) 값 넣기 (넣고 커밋하면 자동 재배포)
- index.html, complete.html 상단: MATDORI_PIXEL_ID, GA4_ID
- index.html 스크립트: APPS_SCRIPT_URL (구글 앱스스크립트 웹앱 URL / Make 웹훅)
- privacy.html 의 빨간 [ ] 부분 실제정보로 채우기

## 광고 최종 URL
https://matdori.franchises.co.kr/?utm_source=meta&utm_medium=paid_social&utm_campaign=matdori_test
