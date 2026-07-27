<h1 align="center">홍수빈 · Subin Hong</h1>

<p align="center">
  <b>인프라 · SRE 엔지니어를 준비하고 있습니다</b><br/>
  쿠버네티스 위에서 장애를 장애로 드러내는 관측 환경을 만드는 데 관심이 있습니다
</p>

<p align="center">
  <a href="https://zed6740.tistory.com/"><img src="https://img.shields.io/badge/Blog-zed6740.tistory.com-EE7300?style=flat-square&logo=tistory&logoColor=white"/></a>
  <a href="mailto:subinhong0109@dankook.ac.kr"><img src="https://img.shields.io/badge/Email-subinhong0109@dankook.ac.kr-EA4335?style=flat-square&logo=gmail&logoColor=white"/></a>
</p>

---

<h3 align="center">Tech Stack</h3>

<p align="center">
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white"/>
  <img src="https://img.shields.io/badge/Helm-0F1689?style=flat-square&logo=helm&logoColor=white"/>
  <img src="https://img.shields.io/badge/Argo%20CD-EF7B4D?style=flat-square&logo=argo&logoColor=white"/>
  <img src="https://img.shields.io/badge/Proxmox-E57000?style=flat-square&logo=proxmox&logoColor=white"/>
  <img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black"/>
  <img src="https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white"/>
  <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/>
</p>
<p align="center">
  <img src="https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white"/>
  <img src="https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white"/>
  <img src="https://img.shields.io/badge/Loki-F46800?style=flat-square&logo=grafana&logoColor=white"/>
  <img src="https://img.shields.io/badge/Tempo-F46800?style=flat-square&logo=grafana&logoColor=white"/>
  <img src="https://img.shields.io/badge/OpenTelemetry-000000?style=flat-square&logo=opentelemetry&logoColor=white"/>
</p>
<p align="center">
  <img src="https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white"/>
  <img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white"/>
  <img src="https://img.shields.io/badge/Spring-6DB33F?style=flat-square&logo=spring&logoColor=white"/>
  <img src="https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white"/>
  <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/>
</p>

---

### 경력

**semiai** · 인프라팀 · 2026.03 – 2026.06
k3s + LGTM 스택 위에서 애플리케이션과 클러스터의 관측을 담당했습니다.

- Go 백엔드에 OpenTelemetry 4축(metric · log · trace · profile)을 계측하고, 그 신호를 받는 수집 파이프라인을 구성
- 클러스터 대시보드 설계 — control-plane에서 Pod, 컨테이너 자원 순으로 좁혀가는 진단 동선
- 노드 상태 메트릭이 etcd 쿼럼 손실 시 갱신을 멈추는 것을 확인하고, kubelet 직접 scrape로 수집 경로를 전환

---

### 이력

```
  2021.03            ┌─  단국대학교 소프트웨어학과 3학년 편입
                     │
  2022.03 - 2022.06  ├─  동아리 QR 출석 관리 애플리케이션 개발
                     │
  2022.07 - 2022.12  ├─  LevelDB 캐시 구조 분석
                     │
  2023.08 - 2025.05  ├─  공군 병장 만기전역
                     │
  2025.06 - 2025.09  ├─  CJ 올리브네트웍스 클라우드웨이브 6기 수료
                     │
  2026.02            ├─  단국대학교 소프트웨어학과 졸업
                     │
  2026.03 - 2026.06  ├─  semiai 인프라팀
                     │
  2026.07 -          └─  온프레미스 k3s 구축 프로젝트  (진행 중)
```

---

### 자격

| 자격증 | 취득 |
|---|---|
| SQLD | 2022.12 |
| 리눅스마스터 2급 | 2023.12 |
| 정보처리기사 | 2024.06 |
| AWS Certified Solutions Architect – Associate | 2024.11 |
| AWS Certified Developer – Associate | 2025.09 |

---

<details>
<summary><b>진행 중 · 온프레미스 k3s 클러스터 구축</b> — Proxmox VM 3노드 · GitOps · LGTM 관측</summary>

<br/>

노트북 한 대에 Proxmox를 올려 VM 3노드로 k3s를 세우고, 티켓팅 MSA를 GitOps로 배포·관측합니다.
클라우드 매니지드가 대신 해주던 CNI · 로드밸런서 · 스토리지 · 시크릿을 직접 구성합니다.

```
노트북 ── 외장 USB SSD ── Proxmox VE 9
                            ├─ k3s-1   4 vCPU · 8GB · role=db
                            ├─ k3s-2   4 vCPU · 8GB · role=obs
                            └─ k3s-3   4 vCPU · 8GB · role=obj

        k3s v1.36 · 3 server 노드 · embedded etcd 3-member HA
```

| 저장소 | 내용 |
|---|---|
| **[cgv-infra](https://github.com/sss654654/cgv-infra)** | 인프라. 노드 프로비저닝 · 플랫폼 부트스트랩 · ArgoCD GitOps · LGTM 관측 스택 |
| **[cgv-onprem](https://github.com/sss654654/cgv-onprem)** | 애플리케이션. queue(Go) · booking(Java/Spring)을 Kafka로 격리한 대기열 MSA |

**연재 · 노트북 홈서버 k3s 구축기**

- [1. 왜 k3s, 왜 Proxmox](https://zed6740.tistory.com/209)
- [2. USB 굽기 및 홈 네트워크 분석](https://zed6740.tistory.com/210)
- [3. 내 골목 개통, 그리고 Proxmox 설치](https://zed6740.tistory.com/211)
- [4. Proxmox 설치 직후 설정](https://zed6740.tistory.com/212)
- [5. 노드(VM) 구축](https://zed6740.tistory.com/213)
- [6. 데이터 디스크와 k3s 클러스터](https://zed6740.tistory.com/214)

</details>
