# Technical Due Diligence Checklist

Need a Technical Due Diligence report? [Book a free no-commitment chat today.](https://bogatell.io/technical-due-diligence?utm_source=github)

***

### 1. Intellectual Property & Legal Ownership
**Focus:** Ensuring the seller has clean, transferable title to the code and assets without legal encumbrances.

**Inspection Examples**
* **Open Source Compliance:** Scanning for copyleft licenses (GPL, AGPL) that legally mandate open-sourcing proprietary code.
* **Contributor Rights:** Verifying IP assignment agreements are signed by all past contractors and agencies.
* **Asset Registration:** Checking that domains, cloud accounts (AWS/GCP), and app store accounts are registered to the company entity, not personal emails.
* **Critical Dependencies:** Identifying third-party APIs or data sources that could halt operations if they changed terms.

**Common Tools**
* **Snyk / FOSSA:** Automated scanning of package managers (NPM, Pip, Maven) to identify license risks.
* **GitHub Dependency Graph:** Native view in GitHub to quickly spot GPL-licensed libraries.
* **Whois / ICANN Lookup:** Verifying domain registrant details.

### 2. Team & Key Person Dependency
**Focus:** Assessing if the technology can operate and evolve without the current founders or lead engineers.

**Inspection Examples**
* **Knowledge Silos:** Identifying critical system components understood by only one individual.
* **Admin Access Control:** Checking for shared root passwords or lack of individual identity management for critical infrastructure.
* **Deployment Independence:** Verifying the team can deploy code and manage releases without the founder's physical hardware or input.
* **Retention Criticality:** Identifying specific engineers who hold institutional knowledge not documented elsewhere.

**Common Tools**
* **Git Shortlog / GitExtras:** CLI tools to visualize code contribution percentages by author (identifies "Bus Factor").
* **AWS IAM / GCP IAM:** Auditing user lists to identify shared accounts (e.g., "admin@company.com" used by five people).
* **Pluralsight Flow (formerly GitPrime):** Advanced visualization of engineering impact (optional for larger teams).

### 3. Architecture & Scalability
**Focus:** Determining if the current technology stack supports the investment thesis and growth targets.

**Inspection Examples**
* **Stack Standardisation:** Evaluating if core programming languages and frameworks are widely used to ensure easy hiring.
* **Technical Debt Hotspots:** Locating modules with high cyclomatic complexity or legacy code that typically require rewriting.
* **Database Performance:** Checking for unoptimized queries, lack of indexing, or architectural bottlenecks that limit concurrent users.
* **API Architecture:** Assessing if the system uses modern patterns (REST/GraphQL) versus legacy methods that hinder performance.

**Common Tools**
* **SonarQube / SonarCloud:** Automated code quality scanning to identify complexity hotspots and technical debt.
* **Cloudcraft:** Auto-generating architecture diagrams from live AWS environments to visualize complexity.
* **Locust.io / JMeter:** Load testing tools to simulate traffic spikes and measure system response.

### 4. Infrastructure, Security & Costs
**Focus:** Validating the operational balance sheet, security posture, and true cost of delivery.

**Inspection Examples**
* **Cloud Waste:** Auditing for idle servers, unattached storage, or inefficient resource provisioning.
* **Unit Economics:** Calculating the actual hosting and compute cost per user or transaction.
* **Sensitive Data Handling:** Verifying encryption methods for PII (Personally Identifiable Information) both at rest and in transit.
* **Disaster Recovery:** Checking for automated backups and evidence of recent restoration tests.

**Common Tools**
* **Prowler:** Open-source command line tool for AWS security best practice assessments (CIS Benchmarks).
* **AWS Trusted Advisor / Cost Explorer:** Native cloud tools to identify idle resources and cost-saving opportunities.
* **OWASP ZAP:** Scanning web applications for basic security vulnerabilities (SQL Injection, XSS).

### 5. Data Integrity & Analytics
**Focus:** Confirming that the data in the pitch deck matches the technical reality in the database.

**Inspection Examples**
* **Metric Reconciliation:** Comparing reported active user counts against raw database login timestamps.
* **Traffic Quality:** Filtering analytics for internal traffic, scrapers, and bot activity to find true user volume.
* **Conversion Tracking:** Verifying that marketing pixels fire on confirmed events rather than page views or clicks.
* **Revenue Matching:** Cross-referencing payment gateway logs (Stripe/PayPal) with internal database records.

**Common Tools**
* **Google Tag Assistant:** Browser extension to verify firing triggers for Google Analytics and Ads tags.
* **Segment Inspector:** Debugging tool to view the raw JSON payload of data events in real-time.
* **DBeaver / Postico:** SQL clients for querying the production database to verify raw row counts.

### 6. Code Hygiene & Development Lifecycle
**Focus:** Evaluating the maturity of the engineering process and the maintainability of the codebase.

**Inspection Examples**
* **Secrets Management:** Scanning the repository for hardcoded API keys, passwords, or credentials.
* **Automated Testing:** Checking for the presence and coverage of unit and integration tests.
* **Documentation Quality:** Reviewing the existence of API documentation, setup guides, and architecture diagrams.
* **Repository Health:** Assessing commit frequency, branch management, and code review processes.

**Common Tools**
* **Trivy / GitGuardian:** Scanning repositories specifically for hardcoded secrets and keys.
* **ESLint / Pylint:** Linters that check for adherence to coding standards.
* **Swagger / Postman Collections:** Checking for auto-generated API documentation.

### 7. Integration Readiness
**Focus:** Measuring the technical friction involved in merging the asset with another company or system.

**Inspection Examples**
* **Data Portability:** Assessing the difficulty of exporting all customer and transaction data programmatically.
* **API Write Capabilities:** Checking if external systems can create or update records via API.
* **Authentication Support:** Verifying if the platform supports Single Sign-On standards (SAML, OIDC) for enterprise integration.
* **Webhooks:** Checking for automated event notification systems to sync data with third-party tools.

**Common Tools**
* **Postman:** Testing API endpoints for latency, structure, and write capabilities.
* **SchemaSpy:** Generating visual Entity Relationship Diagrams (ERD) of the database to plan data migrations.

---

### 8. Remediation Guide (Optional)
**Focus:** Standard corrective actions for the most common issues found during LMM diligence.

**Intellectual Property**
* **Issue:** High-risk GPL library detected.
* **Remedy:** Replace with a permissive alternative (MIT/Apache) or purchase a commercial license wrapper pre-close.
* **Issue:** Missing IP assignment for past contractor.
* **Remedy:** Execute a retroactive "Confirmatory Assignment Deed" before signing.

**Security & Infrastructure**
* **Issue:** Shared root credentials / No MFA.
* **Remedy:** Enforce MFA on all root accounts and implement individual Identity & Access Management (IAM) users immediately.
* **Issue:** PII stored in plain text.
* **Remedy:** Implement database-level encryption or application-level hashing for sensitive fields.

**Team & Knowledge**
* **Issue:** Undocumented "Black Box" algorithm.
* **Remedy:** Condition of Closing: CTO must record a comprehensive code walkthrough video explaining the logic.
* **Issue:** Manual deployment from a laptop.
* **Remedy:** Containerize the application (Docker) and set up a basic CI/CD pipeline (GitHub Actions) to automate releases.

***

Need a Technical Due Diligence report? [Book a free no-commitment chat today.](https://bogatell.io/technical-due-diligence?utm_source=github)
