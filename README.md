# Awesome-Scala-Extensibility-Runtime

# Top Scala Extensibility & Runtime Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Scala UDF Runtimes, Distributed Compute & Self-Hosted Actor Systems*  
**Last updated: October 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Scala Extensibility & Runtime**. These tools enable organizations to write and execute Scala code in managed data platforms, run distributed Scala workloads on Spark and Flink, and build resilient serverless applications with the Akka actor model—leveraging Scala's type safety and JVM performance without managing the underlying infrastructure.

**Examples** include Snowflake Scala UDFs, Apache Spark Scala API, Databricks Scala Runtime, AWS EMR Scala, Google Cloud Dataproc Scala, Lightbend/Akka, Apache Flink Cloud, Cloudera Scala Runtime, and Azure HDInsight Scala (the category leaders).

**Open-source emphasis**: Scala Extensibility & Runtime is a domain where open-source tooling is **foundational but undergoing significant transitions**. **Apache Spark** remains the dominant distributed compute engine with first-class Scala APIs—but it is now maintained by Apache and has no single commercial vendor driving its Scala surface . **Apache Flink** has **deprecated all Scala APIs** and will remove them in a future major version—Scala users are directed to the Java DataStream and Table APIs . **Akka** (formerly Lightbend) has pivoted from open-source libraries to a commercial platform; the Akka 3 runtime is now a **managed service** (Serverless, BYOC) with app resilience guarantees, while the core actor libraries continue under Apache 2.0 . **Kalix** (the serverless platform) has been retired in favor of Akka . **Scala Native** provides an ahead-of-time compiler and lightweight runtime for Scala, Apache 2.0 licensed, with active development (v0.5.10 released January 2026) . The critical caveat: **the open-source Scala runtime ecosystem is consolidating**—Flink's Scala API is deprecated, Akka's innovation is now commercial, and Spark's Scala API is stable but not the focus of new investment.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Snowflake Scala UDFs](https://docs.snowflake.com/en/developer-guide/udf/scala/udf-scala-introduction)**  
  Write UDF handlers in Scala 2.12 or 2.13 and call them from SQL . Handlers can be in-line or packaged as JARs on a stage; support reading staged files via `SnowflakeFile` and importing directories with `IMPORTS` . **Best for Snowflake users wanting Scala logic in SQL queries**—but limited to the Snowflake runtime and UDF execution model.

- **[Databricks Scala Runtime](https://docs.databricks.com/gcp/en/dev-tools/databricks-connect/scala/jar-compile)**  
  Run Scala code on Databricks serverless compute via JAR tasks (Public Preview); use Databricks Connect for Scala to build compatible JARs with Scala 2.13 and JDK 17, and deploy through the UI or Declarative Automation Bundles . **Best for Databricks users wanting serverless Scala execution**—but it is in preview and requires JAR packaging discipline.

- **[AWS EMR Scala](https://aws.amazon.com/emr/)**  
  Managed Hadoop/Spark clusters supporting Scala workloads; run Spark jobs written in Scala on EMR without managing cluster infrastructure.

- **[Google Cloud Dataproc Scala](https://cloud.google.com/dataproc)**  
  Managed Spark/Hadoop service supporting Scala; run Scala Spark jobs on Dataproc clusters with per-second billing.

- **[Akka (Lightbend)](https://akka.io/)**  
  The commercial successor to Lightbend's platform; **Akka 3** provides a managed runtime (Serverless, BYOC, Dedicated) for building responsive distributed applications with the actor model . Features multi-region replication, multi-master CRDTs, zero-downtime migrations, and an **app resilience guarantee** (Akka indemnifies against app downtime losses) . **Kalix has been retired**; all existing Kalix services continue under Akka . **Best for organizations wanting managed Akka without operating the runtime**—but it is a commercial platform, not an open-source library.

- **[Apache Flink Cloud (Managed Services)](https://flink.apache.org/)**  
  Managed Flink offerings (AWS Managed Service for Apache Flink, Confluent Cloud for Flink) now support Flink 2.2, but **Scala APIs are deprecated** and will be removed . Scala users should migrate to Java DataStream/Table APIs . **Not recommended for new Scala projects**—the Scala surface is shrinking.

- **[Cloudera Scala Runtime](https://www.cloudera.com/)**  
  Enterprise Hadoop/Spark distribution supporting Scala; provides managed clusters with Scala Spark execution.

- **[Azure HDInsight Scala](https://azure.microsoft.com/en-us/products/hdinsight)**  
  Managed Hadoop/Spark service on Azure supporting Scala; run Scala Spark jobs on HDInsight clusters.

## Open-Source GitHub Projects

### Distributed Compute Engines (Scala-Native)

- **[Apache Spark](https://github.com/apache/spark)**  
  The **dominant open-source distributed compute engine** (Apache 2.0) with first-class Scala APIs for SQL, streaming, MLlib, and GraphX . Scala is Spark's primary language—the API is Scala-native, and the Spark shell is Scala. **Best for large-scale data processing with Scala**—but Spark's Scala API is stable rather than rapidly evolving, and the project is now Apache-governed.

- **[Apache Pekko](https://github.com/apache/pekko)**  
  The **Apache-governed fork of Akka 2.6.x** (Apache 2.0) . Provides the actor model, clustering, sharding, persistence, and streams—the same libraries Akka built its reputation on, now under neutral governance. Migration from Akka 2.6 is largely mechanical (package names change from `akka` to `pekko`) . **Best for teams wanting Akka's actor model without the commercial platform dependency**—but Pekko is based on Akka 2.6, not the newer Akka 3 features.

### Scala Runtime & Native

- **[Scala Native](https://github.com/scala-native/scala-native)**  
  Optimizing **ahead-of-time compiler and lightweight managed runtime** for Scala (Apache 2.0) . Compiles Scala to native binaries without a JVM—lower memory footprint, faster startup, and no JVM warmup. Actively developed (v0.5.10, January 2026); sponsored by EPFL, LAMP, and VirtusLab . **Best for CLI tools, edge deployments, and low-latency services** where JVM overhead is unacceptable—but the ecosystem of Scala libraries available for Native is smaller than JVM Scala.

### Workflow & Orchestration (Scala)

- **[OpenMOLE](https://github.com/openmole/openmole)**  
  Open-source **workflow engine for exploration of simulation models** using high-throughput computing (AGPL-3.0, Scala) . Designed for scientific computing—parameter sweeps, model exploration, and distributed execution across grids and clusters. **Niche but active** (updated within days as of listing)—best for research and simulation workloads rather than general-purpose orchestration.

### Additional Strong Open-Source Options

- **Akka (open-source libraries)** — The core Akka actor libraries remain Apache 2.0 and continue to receive feature investment, but the **commercial Akka 3 platform** is where new runtime capabilities (multi-region replication, managed operations) are being built . Open-source Akka is stable but not where innovation is happening.
- **ZIO** — Type-safe, composable library for asynchronous and concurrent programming in Scala; provides a purely functional effect system with structured concurrency, resource management, and a rich ecosystem (ZIO HTTP, ZIO Kafka, ZIO Quill) . **Not a runtime platform** but a foundational library for building Scala services—widely adopted in the functional Scala community.
- **Cats / http4s / Circe** — Foundational Scala libraries for functional programming (Cats), HTTP (http4s), and JSON (Circe); widely adopted across the ecosystem . **Libraries, not runtimes**—but essential for building Scala services.

**Frameworks for building custom systems**: For **distributed data processing with Scala**, Apache Spark remains the standard . For **actor-based distributed systems without commercial dependency**, Apache Pekko (Akka 2.6 fork) . For **managed Akka runtime with resilience guarantees**, Akka 3 commercial platform . For **native binaries without JVM**, Scala Native . For **scientific workflow orchestration**, OpenMOLE . **Avoid**: Apache Flink for new Scala projects—Scala APIs are deprecated and will be removed . No open-source project replicates Akka 3's managed multi-region runtime—that is now commercial territory.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Scala runtime platforms handling production code and data must comply with organizational security policies; **self-hosted runtimes place full responsibility for JVM tuning, dependency management, and patching on the operator**.
- **The Scala runtime ecosystem is consolidating**—**Apache Flink has deprecated all Scala APIs** and will remove them ; **Akka's innovation is now in the commercial Akka 3 platform** ; **Kalix has been retired** . **Apache Pekko** provides the open-source Akka 2.6 lineage under Apache governance . **Apache Spark** remains stable and Scala-native but is not rapidly evolving its Scala surface. Choose based on whether you need managed runtime (Akka), open-source actor model (Pekko), or data processing (Spark)—and avoid Flink for new Scala projects.
- Verify license terms for commercial use; Apache Spark and Apache Pekko use Apache 2.0 , Scala Native uses Apache 2.0 , and OpenMOLE uses AGPL-3.0 .

---

**Made for Scala developers, platform engineers, and organizations choosing their Scala runtime stack.**  
Let's make Scala runtime more open, but with clear eyes about the Flink deprecation and Akka's commercial pivot that define the current landscape.
