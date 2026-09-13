---
layout: page
title: "참고 자료"
kicker: "부록"
summary: "연작에 나오는 장애 대응 관행과 용어의 출처"
permalink: /appendix/
wide: true
---

이 연작의 회사와 사람과 장애는 지어낸 것이지만, 인물들이 따르는 관행과 어휘는 지어낸 것이 아닙니다. 각 화의 소재가 된 문서와, 표현을 고를 때 참고한 국내 사례를 모았습니다.

## 페이브릭의 대응 규정

연작의 회사 페이브릭이 따르는 역할 구분입니다. 1화에서 유현이 쓴 규정이고, 15화에서 하늘에게 넘어갑니다.

| 역할 | 누가 | 순번 | 대기 방식 | 하는 일 | 하지 않는 일 |
|---|---|---|---|---|---|
| 온콜 | SRE 팀원(팀장 포함), 주 단위 교대 | SRE 온콜 교대표 | 페이지를 직접 받고 몇 분 안에 ack. 노트북 상시 휴대. 술은 사이다 | 초동 대응, 손(시스템 변경) | SEV1에서 혼자 판단하고 혼자 손 쓰기 |
| 지휘 순번(인시던트 커맨더) | SRE 팀원(팀장 포함), 주 단위 | SRE 지휘 순번 | 페이지가 오지 않음. SEV1이 선언되면 불려 나오고, 닿지 않으면 다음 순번. 술은 사이다 | 상황 파악, 역할 배정, 판단과 지시, 타임라인 | 키보드 잡기 |
| 손 | 기본은 온콜. 커맨더가 담당 개발자에게 맡길 수 있음 | 없음(커맨더가 지정) | 지정된 동안만 | 지시받은 변경 실행, 보이는 것 보고 | 지시 없는 변경 |
| 서비스 팀 담당 개발자(결제팀 등) | 결제팀 | 온콜도 지휘 순번도 없음 | 부르면 들어감 | 자기 코드 설명, 필요하면 손 | |
| 배포 게이트 승인자 | 결제팀 명단, 5화 이후 주 단위 교대표 두 명 | 별개 | 승인 요청이 오면 응답 | 플래그·배포 승인 | 혼자 승인 |
| 동결 예외 승인 | 플랫폼 본부장과 결제팀 리드의 서면 | 별개 규정 | | 동결 중 배포 허가 | |

역할표 밖의 조항은 셋입니다. 음주 상태로는 프로덕션 접근도 지휘도 하지 않는다(1화). 상중인 사람은 온콜과 시스템 접근에서 뺀다(10화). 이동이나 행사가 있으면 전날까지 교대를 올리고, 받아 주는 대체 순번을 따로 둔다(12화).

### 구조가 비슷한 회사와 문서

- [Managing Incidents · Google SRE Book](https://sre.google/sre-book/managing-incidents/): 지휘(Incident Command)와 운영(Operational Work)을 나누고, "시스템을 바꾸는 건 운영 팀뿐"이라고 명시합니다. 지휘 순번이 키보드를 잡지 않는다는 페이브릭의 규정은 이 조항을 그대로 가져온 것입니다.
- [Being On-Call · Google SRE Book](https://sre.google/sre-book/being-on-call/): 사용자 대면 서비스의 응답 기대치는 5분, 덜 급한 시스템은 30분. 많은 팀이 primary와 secondary 두 순번을 두고 secondary는 primary가 놓친 페이지를 받는 예비로 씁니다. 페이브릭의 온콜과 지휘 순번의 대기 방식이 다른 것과 같은 구조입니다.
- [Incident Management · GitLab Handbook](https://handbook.gitlab.com/handbook/engineering/infrastructure-platforms/incident-management/): 페이지를 24x7 받는 SRE의 EOC(Engineer On Call), 영향 파악과 인원 소집을 맡는 IMOC(Incident Manager On Call), 고객 대응의 CMOC를 각각 별도 순번으로 돌립니다. 온콜과 지휘 순번을 따로 두는 회사의 공개된 예입니다. [Incident Responder](https://handbook.gitlab.com/handbook/engineering/infrastructure-platforms/incident-management/roles/incident-responder/)와 [Incident Lead](https://handbook.gitlab.com/handbook/engineering/infrastructure-platforms/incident-management/roles/incident-lead/) 역할 문서가 따로 있습니다.
- [Different Roles for Incidents · PagerDuty](https://response.pagerduty.com/before/different_roles/): "인시던트 커맨더는 해결자가 아니다. 모든 복구 작업은 위임한다." SME(Subject Matter Expert)는 보통 해당 서비스의 primary 온콜이 맡습니다. 결제팀 개발자가 손으로 불려 들어오는 구조는 이 SME 역할을 따른 것입니다.
- [Incident Commander Training · PagerDuty](https://response.pagerduty.com/training/incident_commander/): 커맨더는 그래프도 로그도 직접 보지 않고 위임합니다. 훈련을 마친 사람이 스스로 커맨더 순번표에 이름을 올리는 것으로 정식 커맨더가 됩니다. 피로해서 계속할 수 없으면 인계하라는 조항이 있는데, 음주를 명시한 조항은 이 문서에도 없습니다. 페이브릭의 음주 조항은 참고한 문서 없이 회사가 스스로 정한 것입니다.
- [Being On-Call · PagerDuty](https://response.pagerduty.com/oncall/being_oncall/): 에스컬레이션 5분, 여행이나 일정이 있으면 미리 교대를 잡을 것. 12화의 다섯 번째 재발 방지 항목은 이 조항을 옮겨 적은 것입니다.
- [Escalation Policies · PagerDuty](https://support.pagerduty.com/main/docs/escalation-policies): 정해진 시간 안에 ack가 없으면 다음 단계로 넘어가는 규칙. 1화와 9화에서 지휘 순번이 닿지 않아 다음 순번인 유현이 잡는 장면의 배경입니다.
- [데브시스터즈의 장애 대응 원칙과 방법](https://tech.devsisters.com/posts/incident-management-principles/): 지휘자와 기록가를 두고 "시스템 변경은 1인이 진행"합니다. 다만 지휘자는 순번이 아니라 최초 인지자가 맡고 필요하면 인계합니다. 페이브릭과 다른 선택입니다.
- [장애 모의 훈련 그리고 배운 점 · Hyperconnect Tech Blog](https://hyperconnect.github.io/2024/11/12/sre-incident-training.html): SRE 팀은 장애를 감독하며 전체 상황을 보고, 개발팀은 자기 컴포넌트 상태를 보고하고 빠르게 에스컬레이션합니다. SRE가 지휘하고 서비스 팀이 불려 들어오는 역할 배치가 페이브릭과 같습니다.

## 인시던트 지휘

1화에서 유현이 쓴 규정, "손을 쓰는 사람과 지휘하는 사람을 나눈다"는 원칙의 출처입니다.

- [Managing Incidents · Google SRE Book](https://sre.google/sre-book/managing-incidents/): 인시던트 커맨더, 운영 리드, 커뮤니케이션 리드로 역할을 나누는 구조. 유현이 브리지 콜에서 맡는 역할은 이 구조의 인시던트 커맨더입니다.
- [Emergency Response · Google SRE Book](https://sre.google/sre-book/emergency-response/): 대응 중에 '누가 무엇을 했는지'를 남기는 습관에 관한 장.
- [Incident Response · Google SRE Workbook](https://sre.google/workbook/incident-response/): 실제 사례로 풀어 쓴 지휘 체계.
- [PagerDuty Incident Response](https://response.pagerduty.com/): 공개된 대응 매뉴얼. [역할 정의](https://response.pagerduty.com/before/different_roles/)와 [인시던트 커맨더 훈련](https://response.pagerduty.com/training/incident_commander/)이 따로 있습니다.
- [What is an Incident Commander? · PagerDuty](https://www.pagerduty.com/resources/learn/what-is-incident-commander/)
- [인시던트에 대응하는 방법 · Atlassian 핸드북](https://www.atlassian.com/ko/incident-management/handbook/incident-response): 한국어로 읽을 수 있는 대응 절차.

## 블레임리스 포스트모템

1화의 제목이자 민석이 회의실에서 먼저 꺼내는 말입니다.

- [Postmortem Culture: Learning from Failure · Google SRE Book](https://sre.google/sre-book/postmortem-culture/): 비난 없는 포스트모템을 왜, 어떻게 쓰는지를 정리한 장.
- [Postmortem Culture · Google SRE Workbook](https://sre.google/workbook/postmortem-culture/): 잘 쓴 포스트모템과 잘못 쓴 포스트모템의 예.
- [Blameless PostMortems and a Just Culture · Etsy Code as Craft](https://www.etsy.com/codeascraft/blameless-postmortems): 2012년 글. '블레임리스'라는 말을 널리 퍼뜨린 문서입니다.
- [비난 없는 포스트모템 · Atlassian](https://www.atlassian.com/ko/incident-management/postmortem/blameless)

## 온콜

유현과 도경이 새벽 두 시 술집에서 다투는 규정의 배경입니다.

- [Being On-Call · Google SRE Book](https://sre.google/sre-book/being-on-call/): 온콜의 부담과 교대, 대응 시간에 관한 장.
- [운영 비용을 95% 절감한 서버리스 온콜 시스템 구축기 · 올리브영 테크블로그](https://oliveyoung.tech/2025-12-24/amazon-connect/): 국내 회사의 온콜 호출 체계 사례.

## 피처 플래그와 비밀 관리

1화의 스위치보드 감사 로그, 2화의 승인 봇과 자동 원복, 3화의 퇴사자 토큰을 쓸 때 참고했습니다.

- [Feature Toggles · martinfowler.com](https://martinfowler.com/articles/feature-toggles.html): 플래그의 종류와 수명, 운영 플래그를 언제 치워야 하는지.
- [Secrets Management Cheat Sheet · OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html): 토큰의 소유자, 만료, 접근 기록에 관한 점검 항목.

## 429와 재시도

4화의 제목이자 유리가 벤더 쪽에서 보는 숫자입니다.

- [RFC 6585 · Additional HTTP Status Codes](https://www.rfc-editor.org/rfc/rfc6585): 429 Too Many Requests를 정의한 문서.
- [RFC 9110 · HTTP Semantics](https://www.rfc-editor.org/rfc/rfc9110): Retry-After 헤더의 의미.
- [Timeouts, retries, and backoff with jitter · Amazon Builders' Library](https://aws.amazon.com/builders-library/timeouts-retries-and-backoff-with-jitter/): 재시도가 장애를 키우는 방식과 지터의 필요성.

## 헬스체크

6화에서 하늘이 찾는 '사람이 안 나오는 장애'의 배경입니다.

- [Implementing health checks · Amazon Builders' Library](https://aws.amazon.com/builders-library/implementing-health-checks/): 얕은 헬스체크와 깊은 헬스체크, 잘못된 헬스체크가 만드는 장애.
- [Configure Liveness, Readiness and Startup Probes · Kubernetes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/)

## 잠금과 롱 트랜잭션

7화에서 임재헌이 건 배타 락과, 대기가 끝나도 풀리지 않던 거래의 배경입니다.

- [Explicit Locking · PostgreSQL Documentation](https://www.postgresql.org/docs/current/explicit-locking.html): `ACCESS EXCLUSIVE` 락이 읽기까지 막는 이유. 대기 중인 배타 락이 뒤따르는 요청을 줄 세우는 동작.
- [pg_locks · PostgreSQL Documentation](https://www.postgresql.org/docs/current/view-pg-locks.html): 은서가 잠금을 물고 있는 연결을 찾을 때 보는 뷰.
- [Transactions · PostgreSQL Tutorial](https://www.postgresql.org/docs/current/tutorial-transactions.html): `BEGIN`으로 연 거래는 `COMMIT`이나 `ROLLBACK` 전까지 락을 놓지 않는다는 것. 임재헌이 놓친 부분입니다.
- [Managing Long-Running Queries and Idle-in-Transaction · PostgreSQL Wiki](https://wiki.postgresql.org/wiki/Lock_Monitoring): 잠긴 세션을 찾아 종료하는 방법.

## 감사 로그와 내부자 위협

7화에서 임재헌이 직접 결재한 비용으로 만든 감사 로그에 그 자신이 잡히는 배경입니다.

- [Logging Cheat Sheet · OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html): 무엇을, 어디에, 얼마나 오래 남길지. 운영 데이터와 분리해 변조를 막는 감사 로그.
- [CIS Control 8 · Audit Log Management](https://www.cisecurity.org/controls/audit-log-management): 접근과 변경을 사람 단위로 추적하는 통제 항목.
- [Insider Threat Mitigation · CISA](https://www.cisa.gov/topics/physical-security/insider-threat-mitigation): 권한이 있는 내부자가 만드는 사고의 성격.
- [공용 계정을 없애야 하는 이유 · NIST SP 800-53 AC-2](https://csrc.nist.gov/projects/risk-management/sp800-53-controls/release-search#!/control?version=5.1&number=AC-2): 계정을 사람에게 귀속시켜 로그의 actor가 사람을 가리키게 하는 통제. `ops-admin` 같은 공용 계정이 왜 문제인지.

## DNS와 TTL

8화의 제목이자, 하늘이 전화번호부에 비유하는 것입니다. 엔드포인트를 옮길 때 왜 TTL을 미리 낮춰야 하는지의 배경입니다.

- [RFC 1035 · Domain Names: Implementation and Specification](https://www.rfc-editor.org/rfc/rfc1035): DNS 레코드의 TTL을 정의한 문서.
- [RFC 2308 · Negative Caching of DNS Queries](https://www.rfc-editor.org/rfc/rfc2308): 없는 응답도 캐시된다는 것. 커토버가 늦게 수렴하는 또 다른 이유.
- [Managing RFC 1918 and DNS TTL for migrations · Cloudflare Learning](https://www.cloudflare.com/learning/dns/dns-records/dns-ttl/): 이전 전에 TTL을 낮추는 관행.
- [Reliability, constant work, and a good cup of coffee · Amazon Builders' Library](https://aws.amazon.com/builders-library/reliability-and-constant-work/): 부분 장애가 전면 장애보다 진단이 어려운 이유의 배경.

## 외부 사업자의 포스트모템

8화에서 넉 달 만에 도착하는 클라우드 사업자의 포스트모템, 그리고 6화에서 하늘이 던진 '사람이 안 나오는 장애' 질문의 답입니다.

- [Summary of the Amazon S3 Service Disruption · AWS](https://aws.amazon.com/message/41926/): 사업자가 공개하는 사후 보고서의 실제 예. 원인은 기술과 절차로 적히고, 사람 이름은 나오지 않습니다.
- [Google Cloud Incident Reports](https://status.cloud.google.com/summary): 공개 포스트모템 모음.
- [Cloudflare outage postmortems](https://blog.cloudflare.com/tag/outage/): 블레임리스로 쓰인 외부 공개 보고서들.

## 배포 동결과 시퀀스 소진

9화에서 연말 배포 동결 중에 승인 번호가 천장에 닿은 이유, 그리고 고칠 코드가 있어도 올릴 수 없던 상황의 배경입니다.

- [Release Engineering · Google SRE Book](https://sre.google/sre-book/release-engineering/): 언제 배포를 멈추고, 그 동결에 어떤 예외를 둘지.
- [Numeric Types · PostgreSQL Documentation](https://www.postgresql.org/docs/current/datatype-numeric.html): 정수 시퀀스에도 천장이 있다는 것. 다 쓰기 전에는 조용하다가 다 쓰는 순간 삽입이 실패한다.
- [CREATE SEQUENCE · PostgreSQL Documentation](https://www.postgresql.org/docs/current/sql-createsequence.html): 천장에 닿은 시퀀스는 기본적으로 오류를 내고, `CYCLE`이 붙어 있으면 처음으로 돌아간다. 9화의 중복은 오류 대신 순환을 고른 결과입니다.
- [Feature Toggles · martinfowler.com](https://martinfowler.com/articles/feature-toggles.html): 동결 중의 대응은 배포가 아니라, 이미 배포된 코드를 플래그로 켜는 것.

## 복제 지연과 하드웨어 장애

10화에서 저녁 피크마다 밀리다가 저절로 풀리던 복제, 그리고 그 뒤에 있던 광 트랜시버의 배경입니다.

- [Replication Lag · PostgreSQL Documentation](https://www.postgresql.org/docs/current/warm-standby.html#STANDBY-SERVER-OPERATION): 복제본이 원본을 따라잡지 못하는 상태와 지연 측정.
- [Monitoring Replication Lag](https://www.postgresql.org/docs/current/monitoring-stats.html): 랙을 보는 지표들.
- [The Tail at Scale · Communications of the ACM](https://research.google/pubs/pub40801/): 특정 부하에서만 나타나는 꼬리 지연이 왜 진단이 어려운지.
- [When a NIC goes bad · 하드웨어 결함으로 인한 부분 패킷 손실](https://www.kernel.org/doc/html/latest/networking/statistics.html): 임계 처리량 이상에서 프레임을 흘리는 NIC/트랜시버 결함을 로그와 통계로 추적하는 관점.

## 슬픔과 판단, 그리고 온콜에서 빼기

10화에서 유현이 상을 당한 팀원을 온콜과 시스템 접근에서 빼는 이유입니다. 1화의 음주 규정과 같은 원칙에서 나왔습니다.

- [Being On-Call · Google SRE Book](https://sre.google/sre-book/being-on-call/): 대응자의 상태와 교대. 컨디션이 좋지 않은 사람을 대응에서 빼는 것도 신뢰성의 일부입니다.
- [Human factors and just culture](https://www.skybrary.aero/articles/just-culture): 판단이 흐려진 사람에게 결정을 몰아주지 않는다는, 항공 안전에서 온 개념.

## 윤일과 날짜 연산

11화의 제목이자, 2월 29일에만 깨어난 버그의 배경입니다. 4년에 한 번 오는 날은 테스트도 4년에 한 번만 실행됩니다.

- [`datetime.date.replace` · Python 문서](https://docs.python.org/3/library/datetime.html#datetime.date.replace): 윤일에서 `replace(year=...)`가 예외를 던지는 부분.
- [`relativedelta` · dateutil](https://dateutil.readthedocs.io/en/stable/relativedelta.html): 1년을 더할 때 2월 29일을 2월 28일로 맞추는 안전한 연산.
- [Falsehoods programmers believe about time](https://gist.github.com/timvisee/fcda9bbdff88d45cc9061606b4b923ca): 날짜에 관해 우리가 틀리게 믿는 것들. 윤일도 그중 하나입니다.
- [The Leap Day bug that took down Microsoft Azure (2012)](https://azure.microsoft.com/en-us/blog/summary-of-windows-azure-service-disruption-on-feb-29th-2012/): 인증서 유효기간을 1년 뒤로 계산하다 2월 29일에 서비스가 멈춘 실제 사례.

## git blame과 진짜 작성자

11화에서 민서가 blame이 가리킨 이름을 진범으로 오해하지 않는 배경입니다.

- [git-blame · Git 문서](https://git-scm.com/docs/git-blame): blame은 그 줄을 마지막으로 바꾼 커밋을 가리킬 뿐입니다.
- [Ignoring commits in git blame · `.git-blame-ignore-revs`](https://git-scm.com/docs/git-blame#Documentation/git-blame.txt---ignore-revs-fileltfilegt): 대량 포매팅 커밋을 blame에서 건너뛰어 진짜 작성자를 드러내는 방법.

## 대기열과 재시도 우회

12화의 제목이자, 굿즈 오픈 때 절반만 동작하던 방어의 배경입니다. 대기열은 신규 진입만 막고, 실패한 사람의 재시도는 그 밖에서 새고 있었습니다.

- [Using a virtual waiting room to protect your application · AWS](https://aws.amazon.com/solutions/implementations/virtual-waiting-room-on-aws/): 가상 대기실이 뒤의 시스템을 보호하는 구조.
- [Handling Overload · Google SRE Book](https://sre.google/sre-book/handling-overload/): 과부하를 앞에서 흘려보내는 부하 차단(load shedding). 통과율을 낮춰 뒤를 지키는 방식.
- [Addressing Cascading Failures · Google SRE Book](https://sre.google/sre-book/addressing-cascading-failures/): 재시도가 어떻게 장애를 스스로 지속시키는지.
- [Timeouts, retries, and backoff with jitter · Amazon Builders' Library](https://aws.amazon.com/builders-library/timeouts-retries-and-backoff-with-jitter/): 방어를 우회한 재시도가 부하를 배로 만드는 방식.

## 콜드 스타트와 기동 의존성

13화에서 전기는 돌아왔는데 시스템이 안 켜지던 이유, 서로가 서로를 기다리던 순환의 배경입니다.

- [Addressing Cascading Failures · Google SRE Book](https://sre.google/sre-book/addressing-cascading-failures/): 전체가 식은 뒤 다시 켜질 때 나타나는 부하와 순환.
- [Reducing the Impact of a Cold Cache/Cold Start](https://aws.amazon.com/builders-library/avoiding-fallback-in-distributed-systems/): 늘 켜져 있던 시스템을 처음부터 켤 때에야 드러나는 의존성.
- [GameDay / 카오스 엔지니어링 · Principles of Chaos](https://principlesofchaos.org/): 처음부터 켜 보지 않은 순서는 순서가 아니라는 것. 실제로 껐다 켜 보는 훈련.

## 관측의 사각과 데드맨 스위치

14화에서 대시보드가 전부 초록인데 사용자는 실패하던 이유, 무신호를 무장애로 착각한 사각의 배경입니다.

- [Monitoring Distributed Systems · Google SRE Book](https://sre.google/sre-book/monitoring-distributed-systems/): 지표가 오지 않는 것과 문제가 없는 것을 구별하기.
- [Dead man's switch · 정상 신호의 부재를 경보로](https://en.wikipedia.org/wiki/Dead_man%27s_switch): 보고가 끊기는 것 자체를 경보 조건으로 삼는 발상.
- [My Philosophy on Alerting · Rob Ewaschuk](https://docs.google.com/document/d/199PqyG3UsyXlwieHaqbGiWVa8eMWi8zzAn0YfcApr8Q/edit): 증상 기반 경보와, 관측 파이프라인 자체의 건강.

## 캐시 스탬피드

15화에서 캐시가 텅 빈 채 돌아오자 모두가 같은 문을 동시에 두드리던 현상의 배경입니다.

- [Cache stampede · thundering herd](https://en.wikipedia.org/wiki/Cache_stampede): 캐시가 비면 같은 값을 여러 요청이 동시에 다시 계산하는 문제.
- [Caching at Reddit: request coalescing / single-flight](https://www.rfc-editor.org/rfc/rfc5861): 하나만 계산하고 나머지는 그 결과를 기다리게 하는 단일 실행.
- [Timeouts, retries, and backoff with jitter · Amazon Builders' Library](https://aws.amazon.com/builders-library/timeouts-retries-and-backoff-with-jitter/): 만료 시각에 흔들림을 줘서 한꺼번에 몰리는 것을 흩뜨리기.

## 국내 회사의 장애 대응 사례

인물들의 말투와 절차를 한국 회사의 것으로 맞출 때 참고했습니다.

- [데브시스터즈의 장애 대응 원칙과 방법](https://tech.devsisters.com/posts/incident-management-principles/): 인시던트 커맨더를 '지휘자'로, 기록 담당을 '기록가'로 부릅니다. 최초 인지자가 지휘자를 맡고 필요하면 인계한다는 원칙.
- [장애 모의 훈련 그리고 배운 점 · Hyperconnect Tech Blog](https://hyperconnect.github.io/2024/11/12/sre-incident-training.html): SRE 팀이 장애 대응을 '총괄'하는 조직의 모의 훈련 기록.
- [우아~한 장애대응 · 우아한형제들 기술블로그](https://techblog.woowahan.com/4886/): 장애 전파와 보고 체계.
- [장애 발생 시 대처 방법: 4단계 장애 대응 플레이북 · 비브라늄랩스](https://vibraniumlabs.ai/blog/what-to-do-during-an-outage): 역할을 먼저 정하고 책임은 나중에 묻는다는 순서.

## 용어에 관한 메모

연작에서는 장애 지휘 역할을 "인시던트 커맨더"라고 부르고, 그 역할을 "맡다"라는 동사와 씁니다. "인시던트 커맨더"라는 명사는 [Atlassian 한국어 용어집](https://www.atlassian.com/ko/incident-management/glossary)을 비롯한 번역 자료에서 그대로 쓰이지만, 국내 회사들은 위의 사례처럼 "지휘자"나 "총괄"이라는 자기 말을 더 자주 씁니다. 페이브릭은 PagerDuty와 SEV 등급을 쓰는 곳이라 영어 명사를 그대로 두었습니다.
