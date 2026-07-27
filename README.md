## 홍수빈 · Subin Hong

인프라 · SRE 엔지니어를 준비하고 있습니다.
쿠버네티스 위에서 장애를 장애로 드러내는 관측 환경을 만드는 데 관심이 있습니다.

[블로그](https://zed6740.tistory.com/) · subinhong0109@dankook.ac.kr

### 준비 중인 것

**온프레미스 k3s 클러스터 구축** — 노트북 한 대에 Proxmox를 올려 VM 3노드로 k3s(embedded etcd HA)를 세우고,
티켓팅 MSA를 GitOps로 배포·관측합니다. 클라우드 매니지드가 대신 해주던 CNI·로드밸런서·스토리지·시크릿을 직접 구성합니다.
과정은 블로그에 [노트북 홈서버 k3s 구축기](https://zed6740.tistory.com/)로 연재하고 있습니다.

- [**cgv-infra**](https://github.com/sss654654/cgv-infra) — 인프라. 노드 프로비저닝 · 플랫폼 부트스트랩 · ArgoCD GitOps · LGTM 관측 스택
- [**cgv-onprem**](https://github.com/sss654654/cgv-onprem) — 애플리케이션. queue(Go) · booking(Java/Spring)을 Kafka로 격리한 대기열 MSA

### 경력

**semiai** · 인프라팀 · 2026.03 – 2026.06
k3s + LGTM 스택 위에서 애플리케이션과 클러스터의 관측을 담당했습니다.

- Go 백엔드에 OpenTelemetry 4축(metric · log · trace · profile)을 계측하고, 그 신호를 받는 수집 파이프라인을 구성
- 클러스터 대시보드 설계 — control-plane에서 Pod, 컨테이너 자원 순으로 좁혀가는 진단 동선
- 노드 상태 메트릭이 etcd 쿼럼 손실 시 갱신을 멈추는 것을 확인하고, kubelet 직접 scrape로 수집 경로를 전환

### 기술

**Infra** Kubernetes(k3s) · Helm · ArgoCD · Proxmox · Terraform · AWS · Linux
**Observability** Prometheus/Mimir · Grafana · Loki · Tempo · OpenTelemetry · Alloy
**Language** Go · Java

<details>
<summary><b>학력 · 자격 · 전체 이력</b></summary>

```
2021.03            단국대학교 소프트웨어학과 3학년 편입
2022.03 - 2022.06  동아리 QR 출석 관리 애플리케이션 개발
2022.07 - 2022.12  LevelDB 캐시 구조 분석 · SQLD 취득
2023.08            입대 · 리눅스마스터 2급 취득(12월)
2024.06            정보처리기사 취득 · AWS Solutions Architect Associate 취득(11월)
2025.05            전역
2025.06 - 2025.09  CJ 올리브네트웍스 클라우드웨이브 6기 수료 · AWS Developer Associate 취득(9월)
2026.02            단국대학교 소프트웨어학과 졸업
2026.03 - 2026.06  semiai 인프라팀
2026.07 -          온프레미스 k3s 구축 프로젝트
```

**자격** AWS Solutions Architect Associate · AWS Developer Associate · 정보처리기사 · 리눅스마스터 2급 · SQLD

</details>
