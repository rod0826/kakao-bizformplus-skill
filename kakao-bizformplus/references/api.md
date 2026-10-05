# 응답 조회 API

확인일: 2026-10-05. [Kakao Developers 공식 문서](https://developers.kakao.com/docs/ko/kakaomoment/bizformplus). 구현할 때 최신 인증·오류·쿼터 문서도 확인한다.

|계약|값|
|---|---|
|메서드|GET|
|엔드포인트|https://apis.moment.kakao.com/openapi/v4/adAccounts/bizFormPlus/report|
|인증|비즈니스토큰; Authorization: Bearer|
|계정헤더|adAccountId|
|필수쿼리|formId|
|선택쿼리|cursorId; size(기본100/최대1,000)|
|조건|앱/광고계정 사업자번호일치; 사용권한; 비즈앱; 리다이렉트URI; moment_bizform_result_read 사용자동의; 광고계정/폼다운로드권한|
|페이징|hasNext/nextCursor|
|결과|code/message/data|
|식별·시간|applyId/submittedAt/expiresAt(제출후90일)|
|정보|email/birthDate/gender/name/phoneNumber/address|
|설문|answers(question/answer)|
|기타|optionalAgreements(title/agree); channelAddStatus; inflowSource; kakaoResponseUse(사용시); creativeId|

이 API는 응답 조회용이다. 폼 생성·수정·삭제 API로 확장해 추정하지 않는다. 사용자가 API 연동을 요청했을 때만 구현하거나 호출한다. 폼을 만들기 위해 토큰 발급이나 권한 확대를 시작하지 않는다.

환경변수/비밀 저장소로 토큰을 전달하며 코드·채팅·URL·명령 출력에 토큰이나 실응답을 노출하지 않는다. 로그에는 상태·페이지수·응답수처럼 진단에 필요한 정보만 남긴다. 실제 응답을 외부 CRM에 전송하는 것은 목적지·데이터·사용자 권한이 확인된 경우에만 수행한다.

페이징은 hasNext와 nextCursor로 진행하고 동일 커서 반복 시 중단한다. 증분 저장을 구현한다면 응답 ID를 기준으로 중복 반영을 막고 만료·보유 정책을 별도로 반영한다. 실패 시 최신 공식 오류 문서로 인증/동의/계정/폼권한을 구분한다. API 호출로 동의문 보유 기간이 자동 집행된다고 가정하지 않는다.

공식 문서의 creativeId와 관리 UI의 상품/소재별 집계 제한을 구분한다. creativeId 존재만으로 UI가 소스별 보고서를 제공한다고 설명하지 않는다. 선택형 응답의 실제 직렬화와 날짜 형식을 확인한 뒤 파싱한다.
