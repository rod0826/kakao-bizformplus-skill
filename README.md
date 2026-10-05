# 비즈니스폼+ 만들기 — Codex Skill

카카오모먼트 비즈니스폼+의 설계, 제작, 저장 확인과 관리 작업을 재사용하는 한국어 스킬입니다. 세미나 후기·추첨 참여 템플릿을 포함합니다. 카카오 공식 제품이나 공식 배포물은 아닙니다.

## 포함 범위

|분야|지원|
|---|---|
|제작|시작 페이지, 7가지 설문 유형, 계층형 엑셀, 개인정보 수집, 동의문, 채널 추가, 완료 안내·상담·액션·공유|
|저장|임시 저장/완료 구분, 권한 확인, 결과 검증, 실패 대응|
|관리|권한, 알림 일정, 랜딩 URL, 보고서·암호 안내, 변경 이력, 삭제 조건|
|연동|공식 응답 조회 API 계약·페이징·권한 안내|
|예시|테스트 후기 설문, 실운영 전환, 상담·참석 신청 응용|

UI 자동화는 Codex native Computer Use와 Chrome을 기본으로 사용합니다. 카카오모먼트 로그인과 해당 광고계정의 권한이 필요합니다. 브라우저 제어 기능을 사용할 수 없는 환경에서도 기획·문구 작성·기능 안내는 가능합니다. 구독 플랜별 브라우저 기능 제공을 이 저장소가 보장하지는 않습니다.

## 설치

[GitHub 저장소](https://github.com/rod0826/kakao-bizformplus-skill)를 내려받아 `kakao-bizformplus` 폴더 전체를 `~/.codex/skills/`에 복사합니다. 사용자 지정 CODEX_HOME을 쓰는 경우 해당 경로의 `skills/`에 복사하세요. 기존 동일 이름 폴더가 있으면 먼저 비교·백업하세요.

Codex에서 `$skill-installer`로 이 GitHub 저장소의 `kakao-bizformplus` 경로 설치를 요청해도 됩니다. 설치 후 새 대화에서 스킬 선택 목록을 확인하세요.

## 사용 예시

> $kakao-bizformplus 참여형광고 세미나 참석자용 후기 폼을 만들어줘. 테스트이며 실제 추첨·경품 지급은 없어. 전화번호만 수집하고 테스트 종료 후 30일 이내 파기할 예정이야. 우선 검토용 초안으로 만들어줘.

> 비즈니스폼+ 만들기 스킬로 상담 신청 폼을 만들어줘. 계정과 행사 정보는 현재 Chrome 화면과 아래 운영 조건을 사용해줘.

> $kakao-bizformplus 기존 폼의 알림톡 수신 일정을 확인하고 평일 10~18시, 30분 간격으로 변경해줘.

> $kakao-bizformplus 응답 결과 API를 연동하려고 해. 필요한 권한과 구현 계약을 정리해줘.

행사별 조건과 원하는 저장 상태를 알려주면 됩니다. 광고 집행, 실제 추첨·경품 지급, 참가자에게 메시지 발송은 별도 작업입니다.

## 검증과 출처

2026-10-05 공식 문서와 Chrome 관리자 화면을 확인했습니다. 상세 검증 범위는 [verification.md](kakao-bizformplus/references/verification.md)에 기록했습니다. 전체 기능의 실서비스 실행을 검증한 것은 아닙니다.

- [카카오 비즈니스폼+ 소개](https://kakaobusiness.gitbook.io/main/ad/moment/engagement/bizformplus)
- [비즈니스폼+ 만들기](https://kakaobusiness.gitbook.io/main/ad/moment/engagement/bizformplus/new)
- [비즈니스폼+ 관리](https://kakaobusiness.gitbook.io/main/ad/moment/engagement/bizformplus/manage)
- [응답 조회 API](https://developers.kakao.com/docs/ko/kakaomoment/bizformplus)

가이드는 필요한 사실을 요약하고 원문으로 연결합니다. 공식 이미지·매뉴얼 전문·계정 화면·응답 데이터·인증정보를 재배포하지 않습니다. 플랫폼이 바뀌면 해당 기능의 공식 문서와 현재 UI를 다시 확인합니다.

## 배포 상태

GitHub에서 파일을 배포하며, 별도 태그·릴리스가 없으면 기본 브랜치의 최신 파일을 사용합니다. 버전 고정이 필요하면 배포 태그를 확인하세요. 공개된 스킬을 개인 계정에 설치해 사용하는 방식이며 카카오에 별도 등록하는 앱은 아닙니다.

## 라이선스

독자 작성한 스킬 파일은 [MIT License](LICENSE)로 배포합니다. 카카오의 상표·공식 문서·서비스에는 이 라이선스가 적용되지 않습니다.
