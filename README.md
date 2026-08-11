<h1 align="center">Nahim Uddin</h1>
<p align="center">
  <b>Backend Engineer</b> · Python · APIs · Microservices · Bangladesh
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

### About

I build **backend systems in Python** — REST APIs, service boundaries, Postgres data models, and Dockerized deployments.

I usually own the path from **API → database → cache/async work**, with clear auth and reliable request flows.

- 🔭 **Building:** FastAPI, BlackSheep, and Django/DRF backends
- 🧩 **Focus:** API design, SQL/Postgres, auth, caching, background jobs
- 🌱 **Exploring:** event-driven services, OIDC / gateway auth, search with Meilisearch
- 💬 **Ask me about:** Python backends, PostgreSQL, FastAPI/BlackSheep, Docker
- 👨‍💻 **Portfolio:** [nahimportfolio.netlify.app](https://nahimportfolio.netlify.app/)
- 📫 **Email:** nahim.211902019@gmail.com
- ⚡ **Fun fact:** when I sit down to practice, music wins more rounds than the skills 😂

---

### System design

How I structure backend work: **APIs → SQL (ORM + raw queries) → Postgres**.

```mermaid
flowchart LR
  subgraph Clients
    WEB[React / Web]
    APP[API clients]
  end

  subgraph APIs["API Layer"]
    FA[FastAPI]
    BS[BlackSheep]
    DJ[Django / DRF]
  end

  subgraph Query["Data Access"]
    ORM[ORM / Query Builder<br/>Piccolo · Django ORM]
    RAW[Raw SQL<br/>parameterized queries]
  end

  subgraph Store["Storage"]
    PG[(PostgreSQL)]
    REDIS[(Redis / Valkey cache)]
  end

  WEB --> FA & BS & DJ
  APP --> FA & BS & DJ
  FA & BS & DJ --> ORM
  FA & BS & DJ --> RAW
  ORM --> PG
  RAW --> PG
  FA & BS --> REDIS
```

```sql
-- Example: API handler path uses SQL + raw query when needed
-- GET /orders?user_id=42

-- ORM / query builder (simple reads)
SELECT id, status, total
FROM orders
WHERE user_id = 42
ORDER BY created_at DESC;

-- Raw SQL (joins / reporting / performance-sensitive paths)
SELECT o.id, o.status, SUM(oi.qty * oi.price) AS line_total
FROM orders o
JOIN order_items oi ON oi.order_id = o.id
WHERE o.user_id = $1
  AND o.status = 'paid'
GROUP BY o.id, o.status;
```

---

### Featured work

| Project | Stack | What it shows |
|--------|--------|----------------|
| [Clinic Management API](https://github.com/UddinNahim/Clinic-Management-using-fastapi) | FastAPI · Python | Domain APIs, request validation, service structure |
| [E-Commerce Platform](https://github.com/UddinNahim/E-Commerce-Website-) | Django · Python | Full backend flows for catalog, auth, and orders |
| [BlackSheep Learning](https://github.com/UddinNahim/blacksheep-learning) | BlackSheep · Python | Async API patterns with a modern Python framework |
| [Apache Kafka Practice](https://github.com/UddinNahim/Apache-Kafka) | Python · Kafka | Producers/consumers and event-driven basics |
| [Backend Recap](https://github.com/UddinNahim/backend-_development_recape) | Python | Core backend patterns and API practice |
| [DSA Journey](https://github.com/UddinNahim/DSAJourney) | Python | Algorithms and problem-solving practice |

---

### Tech I use

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

<p align="center">
  <img height="180" src="https://github-readme-stats-fast.vercel.app/api?username=UddinNahim&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" alt="UddinNahim GitHub stats" />
  &nbsp;&nbsp;
  <img height="180" src="https://github-readme-stats-fast.vercel.app/api/top-langs/?username=UddinNahim&layout=compact&theme=tokyonight&hide_border=true&langs_count=8" alt="Top languages" />
</p>

<p align="center">
  <img src="./profile/streak.svg" alt="GitHub streak" />
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
