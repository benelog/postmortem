---
layout: page
title: "참고 자료"
kicker: "부록"
summary: "연작에 나오는 장애 대응 관행과 용어의 출처"
permalink: /appendix/
---

이 연작의 회사와 사람과 장애는 지어낸 것이지만, 인물들이 따르는 관행과 어휘는 지어낸 것이 아닙니다. 각 화의 소재가 된 문서와, 표현을 고를 때 참고한 국내 사례를 모았습니다.

## 인시던트 지휘

1화에서 지안이 쓴 규정, "손을 쓰는 사람과 지휘하는 사람을 나눈다"는 원칙의 출처입니다.

- [Managing Incidents · Google SRE Book](https://sre.google/sre-book/managing-incidents/) — 인시던트 커맨더, 운영 리드, 커뮤니케이션 리드로 역할을 나누는 구조. 지안이 브리지 콜에서 하는 일이 여기서 나옵니다.
- [Emergency Response · Google SRE Book](https://sre.google/sre-book/emergency-response/) — 대응 중에 '누가 무엇을 했는지'를 남기는 습관에 관한 장.
- [Incident Response · Google SRE Workbook](https://sre.google/workbook/incident-response/) — 실제 사례로 풀어 쓴 지휘 체계.
- [PagerDuty Incident Response](https://response.pagerduty.com/) — 공개된 대응 매뉴얼. [역할 정의](https://response.pagerduty.com/before/different_roles/)와 [인시던트 커맨더 훈련](https://response.pagerduty.com/training/incident_commander/)이 따로 있습니다.
- [What is an Incident Commander? · PagerDuty](https://www.pagerduty.com/resources/learn/what-is-incident-commander/)
- [인시던트에 대응하는 방법 · Atlassian 핸드북](https://www.atlassian.com/ko/incident-management/handbook/incident-response) — 한국어로 읽을 수 있는 대응 절차.

## 블레임리스 포스트모템

1화의 제목이자 민석이 회의실에서 먼저 꺼내는 말입니다.

- [Postmortem Culture: Learning from Failure · Google SRE Book](https://sre.google/sre-book/postmortem-culture/) — 비난 없는 포스트모템의 원형.
- [Postmortem Culture · Google SRE Workbook](https://sre.google/workbook/postmortem-culture/) — 잘 쓴 포스트모템과 잘못 쓴 포스트모템의 예.
- [Blameless PostMortems and a Just Culture · Etsy Code as Craft](https://www.etsy.com/codeascraft/blameless-postmortems) — 2012년 글. '블레임리스'라는 말을 널리 퍼뜨린 문서입니다.
- [비난 없는 포스트모템 · Atlassian](https://www.atlassian.com/ko/incident-management/postmortem/blameless)

## 온콜

지안과 도현이 새벽 두 시 술집에서 다투는 규정의 배경입니다.

- [Being On-Call · Google SRE Book](https://sre.google/sre-book/being-on-call/) — 온콜의 부담과 교대, 대응 시간에 관한 장.
- [운영 비용을 95% 절감한 서버리스 온콜 시스템 구축기 · 올리브영 테크블로그](https://oliveyoung.tech/2025-12-24/amazon-connect/) — 국내 회사의 온콜 호출 체계 사례.

## 피처 플래그와 비밀 관리

1화의 스위치보드 감사 로그, 2화의 승인 봇과 자동 원복, 3화의 퇴사자 토큰이 여기서 나옵니다.

- [Feature Toggles · martinfowler.com](https://martinfowler.com/articles/feature-toggles.html) — 플래그의 종류와 수명, 운영 플래그를 언제 치워야 하는지.
- [Secrets Management Cheat Sheet · OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html) — 토큰의 소유자, 만료, 접근 기록에 관한 점검 항목.

## 429와 재시도

4화의 제목이자 유리가 벤더 쪽에서 보는 숫자입니다.

- [RFC 6585 · Additional HTTP Status Codes](https://www.rfc-editor.org/rfc/rfc6585) — 429 Too Many Requests를 정의한 문서.
- [RFC 9110 · HTTP Semantics](https://www.rfc-editor.org/rfc/rfc9110) — Retry-After 헤더의 의미.
- [Timeouts, retries, and backoff with jitter · Amazon Builders' Library](https://aws.amazon.com/builders-library/timeouts-retries-and-backoff-with-jitter/) — 재시도가 장애를 키우는 방식과 지터의 필요성.

## 헬스체크

6화에서 하늘이 찾는 '사람이 안 나오는 장애'의 배경입니다.

- [Implementing health checks · Amazon Builders' Library](https://aws.amazon.com/builders-library/implementing-health-checks/) — 얕은 헬스체크와 깊은 헬스체크, 잘못된 헬스체크가 만드는 장애.
- [Configure Liveness, Readiness and Startup Probes · Kubernetes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/)

## 잠금과 롱 트랜잭션

7화에서 임재헌이 건 배타 락과, 대기가 끝나도 풀리지 않던 거래의 배경입니다.

- [Explicit Locking · PostgreSQL Documentation](https://www.postgresql.org/docs/current/explicit-locking.html) — `ACCESS EXCLUSIVE` 락이 읽기까지 막는 이유. 대기 중인 배타 락이 뒤따르는 요청을 줄 세우는 동작.
- [pg_locks · PostgreSQL Documentation](https://www.postgresql.org/docs/current/view-pg-locks.html) — 은서가 잠금을 물고 있는 연결을 찾을 때 보는 뷰.
- [Transactions · PostgreSQL Tutorial](https://www.postgresql.org/docs/current/tutorial-transactions.html) — `BEGIN`으로 연 거래는 `COMMIT`이나 `ROLLBACK` 전까지 락을 놓지 않는다는 것. 임재헌이 놓친 부분입니다.
- [Managing Long-Running Queries and Idle-in-Transaction · PostgreSQL Wiki](https://wiki.postgresql.org/wiki/Lock_Monitoring) — 잠긴 세션을 찾아 종료하는 방법.

## 감사 로그와 내부자 위협

7화의, 범인이 결재한 비용으로 만든 감사 로그가 범인을 잡는 배경입니다.

- [Logging Cheat Sheet · OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html) — 무엇을, 어디에, 얼마나 오래 남길지. 운영 데이터와 분리해 변조를 막는 감사 로그.
- [CIS Control 8 · Audit Log Management](https://www.cisecurity.org/controls/audit-log-management) — 접근과 변경을 사람 단위로 추적하는 통제 항목.
- [Insider Threat Mitigation · CISA](https://www.cisa.gov/topics/physical-security/insider-threat-mitigation) — 권한을 가진 내부자가 만드는 사고의 성격.
- [공용 계정을 없애야 하는 이유 · NIST SP 800-53 AC-2](https://csrc.nist.gov/projects/risk-management/sp800-53-controls/release-search#!/control?version=5.1&number=AC-2) — 계정을 사람에게 귀속시켜 로그의 actor가 사람을 가리키게 하는 통제. `ops-admin` 같은 공용 계정이 왜 문제인지.

## 국내 회사의 장애 대응 사례

인물들의 말투와 절차를 한국 회사의 것으로 맞출 때 참고했습니다.

- [데브시스터즈의 장애 대응 원칙과 방법](https://tech.devsisters.com/posts/incident-management-principles/) — 인시던트 커맨더를 '지휘자'로, 기록 담당을 '기록가'로 부릅니다. 최초 인지자가 지휘자를 맡고 필요하면 인계한다는 원칙.
- [장애 모의 훈련 그리고 배운 점 · Hyperconnect Tech Blog](https://hyperconnect.github.io/2024/11/12/sre-incident-training.html) — SRE 팀이 장애 대응을 '총괄'하는 조직의 모의 훈련 기록.
- [우아~한 장애대응 · 우아한형제들 기술블로그](https://techblog.woowahan.com/4886/) — 장애 전파와 보고 체계.
- [장애 발생 시 대처 방법: 4단계 장애 대응 플레이북 · 비브라늄랩스](https://vibraniumlabs.ai/blog/what-to-do-during-an-outage) — 역할을 먼저 정하고 책임은 나중에 묻는다는 순서.

## 용어에 관한 메모

연작에서는 장애 지휘 역할을 "인시던트 커맨더"라고 부르고, 그 역할을 "맡다"라는 동사와 씁니다. "인시던트 커맨더"라는 명사는 [Atlassian 한국어 용어집](https://www.atlassian.com/ko/incident-management/glossary)을 비롯한 번역 자료에서 그대로 쓰이지만, 국내 회사들은 위의 사례처럼 "지휘자"나 "총괄"이라는 자기 말을 더 자주 씁니다. 지안의 회사는 PagerDuty와 SEV 등급을 쓰는 곳이라 영어 명사를 그대로 두었습니다.
