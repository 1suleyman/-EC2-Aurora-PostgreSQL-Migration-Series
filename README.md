# 🚀 EC2 → Aurora PostgreSQL Migration Series

This repository contains a **progressive, real-world migration series** that walks through moving a **PostgreSQL database running on EC2 (Docker)** to **Amazon Aurora PostgreSQL (Serverless v2)**.

Each part builds intentionally toward an **enterprise-grade migration**, covering backups, Terraform, security, observability, cost control, and final decommissioning.

> 🎯 **Outcome:** You will be able to confidently deliver a production-style migration with validation, rollback strategy, and optimised cloud cost posture.

---

## 🧭 Assumptions

* AWS account access
* AWS CLI configured
* Region selected
* Comfortable SSH’ing into EC2
* Terraform installed
* PostgreSQL fundamentals

**Source DB:** PostgreSQL on EC2 (Docker)
**Target DB:** Aurora PostgreSQL (Serverless v2)

---

## 🗂 Repository Structure (Bullet Points)

* **lab-00-guardrails** — Cost controls, TTL tagging strategy, safety guardrails
* **lab-01-ec2-docker-postgres** — EC2 setup, Docker installation, PostgreSQL container, sample data + users
* **lab-02-backup-ec2-postgres** — Logical backups, disk checks, backup validation
* **lab-03-aurora-terraform** — Terraform-managed Aurora cluster, networking, KMS, outputs
* **lab-04-restore-into-aurora** — Restore data + roles, connectivity tests, validation
* **lab-05-app-cutover** — App configuration updates, environment variables, cutover
* **lab-06-enterprise-addons** — Secrets Manager, least-privilege, insights, alarms, snapshot drills
* **lab-07-cost-optimization** — Serverless scaling limits, runtime discipline, log retention tuning
* **lab-08-validation-decommission** — Final parity checks, app verification, EC2 DB shutdown

---

# 📚 Migration Series Overview

---

## ⭐ **Part 1 — Guardrails (Cost + Safety First)**

📁 **Path:** [`lab-00-guardrails`](https://github.com/1suleyman/-Lab-0-Guardrails-Cost-Safety-/tree/main)

* Resource tagging (Project, Owner, TTL)
* AWS Budgets alerts
* Prevent runaway Aurora costs

👉 **[Go to Part 1](https://github.com/1suleyman/-Lab-0-Guardrails-Cost-Safety-/tree/main)**

---

## ⭐ **Part 2 — EC2 + Docker PostgreSQL (Source DB)**

📁 **Path:** [`lab-01-ec2-docker-postgres`](https://github.com/1suleyman/-Lab-1-EC2-Docker-PostgreSQL-Source-DB-/tree/main)

* Launch EC2
* Install Docker + Compose
* Run PostgreSQL container
* Seed data + roles

👉 **[Go to Part 2 (Manual)](https://github.com/1suleyman/-Lab-1-EC2-Docker-PostgreSQL-Source-DB-/tree/main)**
👉 **[Go to Part 2 (Terraform)](https://github.com/1suleyman/-Lab-1-IaC-EC2-Docker-PostgreSQL-Source-DB-Terraform-/tree/main)**

---

## ⭐ **Part 3 — Backup EC2 PostgreSQL**

📁 **Path:** [`lab-02-backup-ec2-postgres`](https://github.com/1suleyman/-Lab-2-Backup-EC2-PostgreSQL-Docker-Based-/tree/main)

* Logical backups with `pg_dump`
* Disk validation
* Troubleshooting scenarios

👉 **[Go to Part 3](https://github.com/1suleyman/-Lab-2-Backup-EC2-PostgreSQL-Docker-Based-/tree/main)**
👉 **[Go to Part 3 (Terraform)](https://github.com/1suleyman/-Lab-2-Terraform-Backup-EC2-PostgreSQL-Database-Idempotent-/tree/main)**

---

## ⭐ **Part 4 — Deploy Aurora with Terraform**

📁 **Path:** [`lab-03-aurora-terraform`](./lab-03-aurora-terraform)

* Aurora Serverless v2
* Private subnets
* KMS encryption
* Security groups
* Terraform outputs

👉 **[Go to Part 4](./lab-03-aurora-terraform)**

---

## ⭐ **Part 5 — Restore Into Aurora (Users Included)**

📁 **Path:** [`lab-04-restore-into-aurora`](./lab-04-restore-into-aurora)

* Connectivity checks
* `pg_restore` for schema + data
* Restoring roles/global objects
* Aurora validation

👉 **[Go to Part 5](./lab-04-restore-into-aurora)**

---

## ⭐ **Part 6 — Application Cutover**

📁 **Path:** [`lab-05-app-cutover`](./lab-05-app-cutover)

* `.env`-based config
* Docker Compose service updates
* Swapping DB host to Aurora
* Verifying app functionality

👉 **[Go to Part 6](./lab-05-app-cutover)**

---

## ⭐ **Part 7 — Enterprise-Level Enhancements**

📁 **Path:** [`lab-06-enterprise-addons`](./lab-06-enterprise-addons)

* Secrets Manager for DB creds
* Least-privilege DB user model
* Performance Insights
* CloudWatch alarms
* Snapshot restore drill

👉 **[Go to Part 7](./lab-06-enterprise-addons)**

---

## ⭐ **Part 8 — Cost Optimization**

📁 **Path:** [`lab-07-cost-optimization`](./lab-07-cost-optimization)

* Serverless v2 scaling strategy
* Runtime discipline
* Log retention tuning

👉 **[Go to Part 8](./lab-07-cost-optimization)**

---

## ⭐ **Part 9 — Final Validation & Decommissioning**

📁 **Path:** [`lab-08-validation-decommission`](./lab-08-validation-decommission)

* Row count checks
* Role validation
* App health checks
* Shutdown EC2 Postgres

👉 **[Go to Part 9](./lab-08-validation-decommission)**

---

# 🧹 Cleanup Checklist

* `terraform destroy`
* Delete Secrets Manager entries
* Schedule unused KMS key deletion
* Terminate EC2
* Remove orphaned EBS volumes + snapshots

---

# 🧠 What You Gain From This Series

* End-to-end PostgreSQL migration experience
* Terraform infrastructure automation
* Secure, encrypted Aurora deployments
* Real-world troubleshooting
* Production-ready DB migration patterns
* Strong portfolio/DevOps case study
