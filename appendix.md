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

## DNS와 TTL

8화의 제목이자, 하늘이 전화번호부에 비유하는 것입니다. 엔드포인트를 옮길 때 왜 TTL을 미리 낮춰야 하는지의 배경입니다.

- [RFC 1035 · Domain Names — Implementation and Specification](https://www.rfc-editor.org/rfc/rfc1035) — DNS 레코드의 TTL을 정의한 문서.
- [RFC 2308 · Negative Caching of DNS Queries](https://www.rfc-editor.org/rfc/rfc2308) — 없는 응답도 캐시된다는 것. 커토버가 늦게 수렴하는 또 다른 이유.
- [Managing RFC 1918 and DNS TTL for migrations · Cloudflare Learning](https://www.cloudflare.com/learning/dns/dns-records/dns-ttl/) — 이전 전에 TTL을 낮추는 관행.
- [Reliability, constant work, and a good cup of coffee · Amazon Builders' Library](https://aws.amazon.com/builders-library/reliability-and-constant-work/) — 부분 장애가 전면 장애보다 진단이 어려운 이유의 배경.

## 외부 사업자의 포스트모템

8화에서 넉 달 만에 도착하는 클라우드 사업자의 포스트모템, 그리고 6화에서 하늘이 던진 '사람이 안 나오는 장애' 질문의 답입니다.

- [Summary of the Amazon S3 Service Disruption · AWS](https://aws.amazon.com/message/41926/) — 사업자가 공개하는 사후 보고서의 실제 예. 원인은 기술과 절차로 적히고, 사람 이름은 나오지 않습니다.
- [Google Cloud Incident Reports](https://status.cloud.google.com/summary) — 공개 포스트모템 모음.
- [Cloudflare outage postmortems](https://blog.cloudflare.com/tag/outage/) — 블레임리스로 쓰인 외부 공개 보고서들.

## 복제 지연과 하드웨어 장애

9화에서 저녁 피크마다 밀리다가 저절로 풀리던 복제, 그리고 그 뒤에 있던 광 트랜시버의 배경입니다.

- [Replication Lag · PostgreSQL Documentation](https://www.postgresql.org/docs/current/warm-standby.html#STANDBY-SERVER-OPERATION) — 복제본이 원본을 따라잡지 못하는 상태와 지연 측정.
- [Monitoring Replication Lag](https://www.postgresql.org/docs/current/monitoring-stats.html) — 랙을 보는 지표들.
- [The Tail at Scale · Communications of the ACM](https://research.google/pubs/pub40801/) — 특정 부하에서만 나타나는 꼬리 지연이 왜 진단이 어려운지.
- [When a NIC goes bad · 하드웨어 결함으로 인한 부분 패킷 손실](https://www.kernel.org/doc/html/latest/networking/statistics.html) — 임계 처리량 이상에서 프레임을 흘리는 NIC/트랜시버 결함을 로그와 통계로 추적하는 관점.

## 슬픔과 판단, 그리고 온콜에서 빼기

9화에서 지안이 상을 당한 팀원을 온콜과 시스템 접근에서 빼는 이유, 1화의 음주 규정과 같은 결의 원칙입니다.

- [Being On-Call · Google SRE Book](https://sre.google/sre-book/being-on-call/) — 대응자의 상태와 교대. 컨디션이 좋지 않은 사람을 대응에서 빼는 것도 신뢰성의 일부입니다.
- [Human factors and just culture](https://www.skybrary.aero/articles/just-culture) — 판단이 흐려진 사람에게 결정을 몰아주지 않는다는, 항공 안전에서 온 개념.

## 윤일과 날짜 연산

10화의 제목이자, 2월 29일에만 깨어난 버그의 배경입니다. 4년에 한 번 오는 날은 테스트도 4년에 한 번만 만납니다.

- [`datetime.date.replace` · Python 문서](https://docs.python.org/3/library/datetime.html#datetime.date.replace) — 윤일에서 `replace(year=...)`가 예외를 던지는 지점.
- [`relativedelta` · dateutil](https://dateutil.readthedocs.io/en/stable/relativedelta.html) — 1년을 더할 때 2월 29일을 2월 28일로 맞추는 안전한 연산.
- [Falsehoods programmers believe about time](https://gist.github.com/timvisee/fcda9bbdff88d45cc9061606b4b923ca) — 날짜에 관해 우리가 틀리게 믿는 것들. 윤일도 그중 하나입니다.
- [The Leap Day bug that took down Microsoft Azure (2012)](https://azure.microsoft.com/en-us/blog/summary-of-windows-azure-service-disruption-on-feb-29th-2012/) — 인증서 유효기간을 1년 뒤로 계산하다 2월 29일에 무너진 실제 사례.

## git blame과 진짜 작성자

10화에서 민서가 blame이 가리킨 이름을 진범으로 오해하지 않는 배경입니다.

- [git-blame · Git 문서](https://git-scm.com/docs/git-blame) — blame은 그 줄을 마지막으로 바꾼 커밋을 가리킬 뿐입니다.
- [Ignoring commits in git blame · `.git-blame-ignore-revs`](https://git-scm.com/docs/git-blame#Documentation/git-blame.txt---ignore-revs-fileltfilegt) — 대량 포매팅 커밋을 blame에서 건너뛰어 진짜 작성자를 드러내는 방법.

## 국내 회사의 장애 대응 사례

인물들의 말투와 절차를 한국 회사의 것으로 맞출 때 참고했습니다.

- [데브시스터즈의 장애 대응 원칙과 방법](https://tech.devsisters.com/posts/incident-management-principles/) — 인시던트 커맨더를 '지휘자'로, 기록 담당을 '기록가'로 부릅니다. 최초 인지자가 지휘자를 맡고 필요하면 인계한다는 원칙.
- [장애 모의 훈련 그리고 배운 점 · Hyperconnect Tech Blog](https://hyperconnect.github.io/2024/11/12/sre-incident-training.html) — SRE 팀이 장애 대응을 '총괄'하는 조직의 모의 훈련 기록.
- [우아~한 장애대응 · 우아한형제들 기술블로그](https://techblog.woowahan.com/4886/) — 장애 전파와 보고 체계.
- [장애 발생 시 대처 방법: 4단계 장애 대응 플레이북 · 비브라늄랩스](https://vibraniumlabs.ai/blog/what-to-do-during-an-outage) — 역할을 먼저 정하고 책임은 나중에 묻는다는 순서.

## 용어에 관한 메모

연작에서는 장애 지휘 역할을 "인시던트 커맨더"라고 부르고, 그 역할을 "맡다"라는 동사와 씁니다. "인시던트 커맨더"라는 명사는 [Atlassian 한국어 용어집](https://www.atlassian.com/ko/incident-management/glossary)을 비롯한 번역 자료에서 그대로 쓰이지만, 국내 회사들은 위의 사례처럼 "지휘자"나 "총괄"이라는 자기 말을 더 자주 씁니다. 지안의 회사는 PagerDuty와 SEV 등급을 쓰는 곳이라 영어 명사를 그대로 두었습니다.
