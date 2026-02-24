
12/12
* AI 코드 리뷰 사례 연구
	* https://docs.google.com/document/d/1qMz1pSWyVBZVzqYy5gv-UHXfiPTEgHYgthYfFb9UPlM/edit?tab=t.0


12/15
* [qodo merge](https://qodo-merge-docs.qodo.ai/) 확인
* Antigravity tool - Very Gooooood!!

1. SVN
	* 환경 변수
		* SMTP_SERVER = "smtp.gmail.com"
		* SMTP_PORT = 465
		* SENDER_EMAIL = "pacsbackend@gmail.com"
		* SENDER_PASSWORD = "caqqgfotruzeyuml"
		* RECIPIENT_EMAIL = "kth@infinitt.com"
		* GEMINI_API_KEY = "AIzaSyApS-Ftm2aqfQxqs316UoFHihbE19LaK_E"
		* SVN_REPO_URL = "http://code.infinitt.com:8080/svn/imt_g3/trunk/G3NetGate"
		* SVN_USER = "kth"
		* SVN_PASS = "Kq]q&S5;v9^]U=Q"
		
	* Flow
		1. Jenkins에서 매일 밤 12시 event
		2. 오늘 commit된 소스 코드 (from SVN)
		3. 2번에서 소스 코드가 없으면 종료
		4. 소스 코드로 코드 리뷰 진행
		5. 예약된 메일 주소로 전송
		6. 끝
	
	* Condition
		* Jenkins에서 실행 된다.
		* 


2. Gitea


* http://devops:3000/ Gitea
* http://g3tbuild:8081/ Jenkins 
* Qodo Merge

* pacsbackend@gmail.com / cipher
* access token : d9120a0eb2f8fa0a9e4d189313a10476be6a7bf9



12/16
* Linux 서버 요청 to 본부장


12/22
* 코드리뷰 포인트
# 📝 Daily Code Review Checklist

### 1. Safety (안전성)
- **Null 처리:** `NullPointerException` 방지 로직이 있는가? (Optional 등 활용)
- **리소스 해제:** DB 연결, File I/O, DICOM 스트림 사용 후 `close()` 처리가 확실한가?
- **대용량 처리:** 대용량 영상/리스트 조회 시 페이징(Paging)이나 스트리밍 처리가 되었는가?
- **입력값 검증:** 프론트/외부에서 들어오는 데이터의 유효성 체크 및 올바른 Type Casting인가?
- **예외 처리:** 에러를 단순히 삼키지 않고, 적절한 로깅 및 전파(Throw)를 하고 있는가?

### 2. 목적 적합성 (Business Logic)
- **요구사항 일치:** Redmine 이슈(티켓)에 명시된 기능이 누락 없이 구현되었는가?
- **사이드 이펙트:** 이 수정으로 인해 기존 로직에 영향을 줄 가능성은 없는가?

### 3. 코드 품질 (Code Quality)
- **가독성:** 함수가 너무 길거나 복잡하지 않고 한눈에 읽히는가?
- **변수명:** 변수/함수 이름이 의도를 명확히 드러내는가? (예: `d` -> `dicomData`)
- **유지보수성:** 하드코딩된 매직 넘버/스트링은 없는가? (상수로 분리)
- **정리:** 오타, 미사용 Import, 불필요한 주석이 제거되었는가? 

### 4. 보안 (Security)
- **정보 노출:** 로그(Log)에 환자 정보, 비밀번호 등 민감 데이터가 출력되지 않는가?
- **비밀 관리:** 코드 안에 비밀번호나 API Key가 하드코딩되어 있지 않은가?


## Oracle PL/SQL 리뷰 기준

### 1. 예외 처리 (Exception Handling)
* [Pass/Fail] `EXCEPTION WHEN OTHERS THEN NULL` 등 무의미한 예외 삼킴 금지
* [Pass/Fail] 예외 발생 시 적절한 로깅 또는 에러 메시지 반환 여부
* [Pass/Fail] `RAISE` 또는 `RAISE_APPLICATION_ERROR` 적절히 사용

### 2. 트랜잭션 관리
* [Pass/Fail] `COMMIT`, `ROLLBACK` 위치가 명확한지 확인
* [Pass/Fail] 프로시저/함수 내부에서 불필요한 `COMMIT` 남발 금지

### 3. 커서 및 리소스 관리
* [Pass/Fail] 명시적 커서 사용 시 반드시 `CLOSE` 호출
* [Pass/Fail] `REF CURSOR` 반환 시 호출자가 닫을 책임 명시

### 4. SQL Injection 방지
* [Pass/Fail] `EXECUTE IMMEDIATE` 사용 시 바인드 변수(`USING`) 적용 필수
* [Pass/Fail] 사용자 입력값을 문자열 연결(`||`)로 SQL에 직접 포함 금지

### 5. 성능 (코드 레벨)
* [Pass/Fail] 루프 내 반복 쿼리(N+1 문제) 지양 → `BULK COLLECT` 또는 조인 권장
* [Pass/Fail] `SELECT *` 대신 필요한 컬럼만 명시

### 6. 보안
* [Pass/Fail] 로그에 개인정보/비밀번호/민감 데이터 출력 금지
* [Pass/Fail] DB 접속 정보(사용자명, 비밀번호) 하드코딩 금지

### 7. 코드 가독성
* [Pass/Fail] 변수/프로시저명 Naming Convention 준수
* [Pass/Fail] 불필요한 주석 또는 사용하지 않는 변수 제거
* [Pass/Fail] **주석에 한글 사용 금지** (영문 주석만 허용)