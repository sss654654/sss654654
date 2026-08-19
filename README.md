# 홍수빈 · Subin Hong

인프라 · DevOps · SRE 방향으로 공부하고 있습니다.

클라우드 매니지드가 대신 해주던 CNI · 로드밸런서 · 스토리지 · 시크릿을 직접 구성하면서,
쿠버네티스 클러스터를 세우고 그 위에 서비스를 올려 운영합니다.

[![Blog](https://img.shields.io/badge/Blog-zed6740.tistory.com-EE7300?style=flat-square&logo=tistory&logoColor=white)](https://zed6740.tistory.com/category/HomeLab)
[![Email](https://img.shields.io/badge/Email-subinhong0109@dankook.ac.kr-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:subinhong0109@dankook.ac.kr)

---

## 홈랩 프로젝트 — 온프레미스 k3s 클러스터

쓰던 노트북에 Proxmox를 올려 VM 3노드로 k3s를 세우고, 대기열·예매 MSA를 GitOps로 배포·관측합니다.
설치 스크립트부터 대시보드까지 전부 Git에 있고, 클러스터는 그것을 따라갑니다.

```
노트북 ── 외장 USB SSD ── Proxmox VE 9
                            ├─ k3s-1   4 vCPU · 8GB · role=db
                            ├─ k3s-2   4 vCPU · 8GB · role=obs
                            └─ k3s-3   4 vCPU · 8GB · role=obj

──────────────────────────────────────────────────────────────
클러스터   k3s v1.36 · 3 server · embedded etcd 3-member
네트워크   Calico · MetalLB(L2) · Traefik · NetworkPolicy 출처 지정
배포       GitLab CI 5단 게이트 → 불변 태그 → Argo CD 롤아웃 → 태그 write-back
관측       Alloy → Mimir · Loki · Tempo → Grafana (대시보드 4장, as-code)
시크릿     Sealed Secrets 15종 — 암호문만 Git 에
부하       k6 판 21회 — 사용자 10,000명 통과 · 정원 500 · 파드 스펙을 실측으로 확정
```

| 저장소 | 내용 |
|:--|:--|
| **[cgv-infra](https://github.com/sss654654/cgv-infra)** | 인프라. 노드 프로비저닝 · 플랫폼 부트스트랩 · Argo CD GitOps · LGTM 관측 스택 |
| **[cgv-onprem](https://github.com/sss654654/cgv-onprem)** | 애플리케이션. queue(Go) · booking(Java/Spring)을 Kafka로 격리한 대기열 MSA |

구축 과정은 [블로그](https://zed6740.tistory.com/category/HomeLab)에 편별로 적고 있습니다 — 현재 17편.

---

## 다뤄 본 것

| 갈래 | 도구 | 한 것 |
|:--|:--|:--|
| **플랫폼** | `Kubernetes(k3s)` `Helm` `Argo CD` | 3 server 노드 etcd HA · Application 23개 GitOps 수렴 |
| **네트워크** | `Calico` `MetalLB` `Traefik` | 번들 CNI 교체 · L2 VIP · data 계층 ingress 출처 지정 |
| **CI/CD** | `GitLab CI` `Docker` `Container Registry` | 5단 게이트 · 불변 태그 · 태그 write-back |
| **관측** | `Mimir` `Loki` `Tempo` `Grafana` `Alloy` | 수집·저장·질의 배선 · 시리즈 상한 조정 · 대시보드 4장 |
| **OS · 가상화** | `Linux` `Proxmox VE` | VM 3노드 · 데이터 디스크 10장 정적 PV · 커널 파라미터 |
| **클라우드 · IaC** | `AWS` `Terraform` | VPC · 서브넷 · 라우팅 · SG · VPC Endpoint · ECR |
| **언어 · 데이터** | `Go` `Java/Spring` `Kafka` `MySQL` `Redis` | 대기열·예매 MSA 운영 · 계측 · 자원 실측 |

---

## 경력

**semiai** · 인프라팀 · 2026.03 – 2026.06

k3s + LGTM 스택 위에서 애플리케이션과 클러스터의 관측을 담당했습니다.

- Go 백엔드에 OpenTelemetry 4축(metric · log · trace · profile)을 계측하고, 그 신호를 받는 수집 파이프라인을 구성
- 클러스터 대시보드 설계 — control-plane에서 Pod, 컨테이너 자원 순으로 좁혀가는 진단 동선
- 노드 상태 메트릭이 etcd 쿼럼 손실 시 갱신을 멈추는 것을 확인하고, kubelet 직접 scrape로 수집 경로를 전환

---

<details>
<summary><b>학력 · 자격 · 이력</b></summary>

<br/>

**단국대학교 소프트웨어학과** · 2021.03 편입 – 2026.02 졸업

| 자격증 | 취득 |
|:--|:--|
| AWS Certified Developer – Associate | 2025.09 |
| AWS Certified Solutions Architect – Associate | 2024.11 |
| 정보처리기사 | 2024.06 |
| 리눅스마스터 2급 | 2023.12 |
| SQLD | 2022.12 |

```
2022.03 - 2022.06   동아리 QR 출석 관리 애플리케이션 개발
2022.07 - 2022.12   LevelDB 캐시 구조 분석
2023.08 - 2025.05   공군 병장 만기전역
2025.06 - 2025.09   CJ 올리브네트웍스 클라우드웨이브 6기 수료
2026.03 - 2026.06   semiai 인프라팀
2026.07 -           온프레미스 k3s 구축 프로젝트
```

</details>
