# TechReads Data Engineering Pipeline

End-to-end data engineering pipeline scraping tech book data from Amazon, storing in MySQL, automating with Apache NiFi, and migrating to MongoDB — with performance benchmarking across both databases.

---

## Pipeline Architecture

```
Amazon (Web Source)
        |
        v
BeautifulSoup (Web Scraping)
        |
        v
Pandas (Data Cleaning & CSV Export)
        |
        v
MySQL (Relational Storage & SQL Queries)
        |
        v
Apache NiFi (Automated ETL / Data Flow)
        |
        v
MongoDB (NoSQL Storage & Benchmarking)
```

---

## Performance Benchmarking: MongoDB vs MySQL

Query performance measured on the same dataset (cold queries, no caching):

| Query | MongoDB Response Time | MySQL Response Time |
|---|---|---|
| Price < £30 | 17.51 ms | 0.72 ms |
| Year >= 2023 | 1.23 ms | 0.68 ms |
| Star Rating >= 4.5 | 1.98 ms | 1.57 ms |

**Finding:** MySQL outperforms MongoDB on all three queries for this dataset size. MongoDB's flexibility in schema evolution comes at the cost of higher latency on simple indexed queries at small scale.

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Python / BeautifulSoup | Web scraping from Amazon |
| Pandas | Data cleaning and CSV export |
| MySQL | Relational storage and SQL querying |
| Apache NiFi | Automated data flow and ETL orchestration |
| MongoDB | NoSQL storage and performance benchmarking |

---

**Ans Arab** — [LinkedIn](https://www.linkedin.com/in/ans-arab-a60a28223)
