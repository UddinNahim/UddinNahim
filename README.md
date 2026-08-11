<h1 align="center">Nahim Uddin</h1>
<p align="center">
  <b>Backend Engineer</b> · Python · Microservices · Bangladesh
</p>

<p align="center">
  <a href="https://nahimportfolio.netlify.app/"><img src="https://img.shields.io/badge/Portfolio-Live-0A66C2?style=for-the-badge&logo=netlify&logoColor=white" alt="Portfolio" /></a>
  <a href="mailto:nahim.211902019@gmail.com"><img src="https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
  <a href="https://www.linkedin.com/in/nahimuddin/"><img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="https://twitter.com/nahim_uddin_"><img src="https://img.shields.io/badge/Twitter-Follow-1DA1F2?style=for-the-badge&logo=x&logoColor=white" alt="Twitter" /></a>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=UddinNahim&label=Profile%20views&color=0e75b6&style=flat" alt="profile views" />
</p>

---

### System design I build around

Event-driven LMS commerce: checkout stays fast, fulfillment stays reliable.

```mermaid
flowchart LR
  subgraph Edge["Edge"]
    C[Client]
    G[API Gateway<br/>Auth Context]
  end

  subgraph Services["Microservices"]
    PKG[Package Service<br/>FastAPI]
    CRS[Course Service<br/>BlackSheep]
    ORD[Order Service<br/>BlackSheep]
    PAY[Payment Service<br/>BlackSheep]
  end

  subgraph Data["Data & Infra"]
    PG[(PostgreSQL<br/>+ Outbox)]
    CACHE[(Valkey / Redis)]
    BUS{{Event Bus<br/>s2-lite}}
    SEARCH[(Meilisearch)]
  end

  subgraph Provider["External"]
    SSL[SSLCommerz]
  end

  C --> G
  G --> PKG & CRS & ORD & PAY
  PKG & CRS & ORD & PAY --> PG
  PKG & CRS --> CACHE
  PKG & CRS --> SEARCH

  ORD -->|create payment| PAY
  PAY -->|redirect / IPN| SSL
  SSL -->|payment.paid| PAY
  PAY -->|outbox| BUS
  BUS -->|COURSE / PACKAGE_PURCHASED| CRS & PKG
```

```mermaid
sequenceDiagram
  autonumber
  actor User
  participant Order as Order Service
  participant Pay as Payment Service
  participant PG as Postgres + Outbox
  participant Bus as Event Bus
  participant Course as Course Service

  User->>Order: Checkout
  Order->>Pay: Create payment
  Pay-->>User: Redirect to gateway
  User->>Pay: IPN / return callback
  Pay->>PG: Mark paid + write outbox
  PG-->>Bus: Publish payment.paid
  Bus->>Order: Fulfill order
  Order->>PG: Write COURSE_PURCHASED
  PG-->>Bus: Publish purchase event
  Bus->>Course: Enroll learner
  Course-->>User: Access granted
```

---

### About

I design and ship **production backend systems** — APIs, payments, and event-driven services for learning platforms.

Right now I’m building **Flyger LMS**: course, package, order, and payment microservices that turn checkout into enrollment with a transactional outbox.

---

### What I work on

- 🔭 **Building:** Flyger LMS microservices with **BlackSheep** & **FastAPI**
- 🧩 **Patterns:** gateway-forwarded auth, permission context, transactional outbox
- 🌱 **Deepening:** event-driven fulfillment, OIDC / IdP flows, payment provider IPNs
- 💬 **Ask me about:** Python backends, SQL, BlackSheep vs FastAPI, microservice design
- 📫 **Email:** nahim.211902019@gmail.com
- ⚡ **Fun fact:** when I sit down to practice, music wins more rounds than the skills 😂

---

### Backend stack

<p align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI" />
  <img src="https://img.shields.io/badge/BlackSheep-111827?style=for-the-badge&logo=python&logoColor=white" alt="BlackSheep" />
  <img src="https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white" alt="Django" />
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/Redis%20/%20Valkey-DC382D?style=for-the-badge&logo=redis&logoColor=white" alt="Redis" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker" />
  <img src="https://img.shields.io/badge/Meilisearch-FF5CAA?style=for-the-badge&logo=meilisearch&logoColor=white" alt="Meilisearch" />
  <img src="https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white" alt="Rust" />
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React" />
</p>

---

### GitHub stats

<!-- Public github-readme-stats.vercel.app is often paused; these mirrors stay online. -->
<p align="center">
  <img height="180" src="https://github-readme-stats-fast.vercel.app/api?username=UddinNahim&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" alt="UddinNahim GitHub stats" />
  &nbsp;&nbsp;
  <img height="180" src="https://github-readme-stats-fast.vercel.app/api/top-langs/?username=UddinNahim&layout=compact&theme=tokyonight&hide_border=true&langs_count=8" alt="Top languages" />
</p>

<p align="center">
  <img src="https://streak-stats.demolab.com?user=UddinNahim&theme=tokyonight&hide_border=true" alt="GitHub streak" />
</p>

<p align="center">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=UddinNahim&theme=github_dark" alt="Profile details" />
</p>

---

### Connect

<p align="left">
  <a href="https://twitter.com/nahim_uddin_" target="blank">
    <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/twitter.svg" alt="twitter" height="30" width="40" />
  </a>
  <a href="https://www.linkedin.com/in/nahimuddin/" target="blank">
    <img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="linkedin" height="30" width="40" />
  </a>
</p>
