---
title: "What is SQL Server Machine Learning Services? | Microsoft Docs"
ms.date: "03/07/2018"
ms.prod: "machine-learning-services"
ms.prod_service: "machine-learning-services"
ms.service: ""
ms.component: ""
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 
caps.latest.revision: 
author: "HeidiSteen"
ms.author: "heidist"
manager: "cgronlun"
ms.workload: 
---
# What is SQL Server Machine Learning Services?
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

SQL Server Machine Learning Services is an embedded, predictive analytics and data science engine that can execute R and Python code within a SQL Server database as stored procedures, as T-SQL script containing R or Python statements, or as R or Python code containing T-SQL. 

The key value proposition of Machine Learning Services is the power of its proprietary packages to deliver advanced analytics at scale, and the ability to bring calculations and processing to where the data resides, eliminating the need to pull data across the network.

There are two options for using machine learning capabilities in SQL Server: 

+ **SQL Server Machine Learning Services (In-Database)** operates within the database engine instance, where the calculation engine is fully integrated with the database engine. Most installations are this option.
+ **SQL Server Machine Learning Server (Standalone)** is a non-SQL installation. Although you use SQL Server Setup to install the server, it is completely decoupled from SQL Server.

## R and Python packages

Support for each language is through proprietary Microsoft packages used for creating and training models of various types, scoring data, and processing in parallel using the underlying system resources.

Because the proprietary packages are built on open-source R and Python distributions, script or code that you run in SQL Server can also call base functions and use third-party packages compatible with the language version provided in SQL Server (Python 3.5 and recent versions of R, currently 3.3.3).

| R  | Python | Description |
|-----------|----------------|-------------|
| [RevoScaleR](r/revoscaler-overview.md) | [revoscalepy](python/what-is-revoscalepy.md)   | Functions in these libraries are among the most widely used. Data transformations and manipulation, statistical summarization, visualization, and many forms of modeling and analyses are found in these libraries. Additionally, functions in these libraries automatically distribute workloads across available cores for parallel processing, with the ability to work on chunks of data that are coordinated and managed by the calculation engine. |
| [MicrosoftML](using-the-microsoftml-package.md) | [microsoftml](https://docs.microsoft.com/machine-learning-server/python-reference/microsoftml/microsoftml-package) | Industry-leading machine learning algorithms for image featurization, classification problems  |
| [olapR](r/how-to-create-mdx-queries-using-olapr.md) | none | Build or execute an MDX query in R script.
| [sqlRUtils](r/generating-an-r-stored-procedure-for-r-code-using-the-sqlrutils-package.md) | none | Functions for putting R scripts into a T-SQL stored procedure, registering a stored procedure with a database, and running the stored procedure from an R development environment.
| [mrsdeploy](operationalization-with-mrsdeploy.md) | none | Primarily used on a non-SQL installation of Machine Learning Server, such as the [(Standalone) version](r/r-server-standalone.md). Use this package to deploy and host web services, build scale-out topologies with dedicated web and compute nodes, toggle between local and remote sessions, run diagnostics, and more. For an (In-Database) installation, use this package in a client capacity: for example, to access a web service on a remote server dedicated to running just Machine Learning Services workloads. |

Portability of your custom R and Python code is addressed through package distribution and interpreters that are built into multiple products. The same packages that ship in SQL Server are also available in several other Microsoft products and services, including a non-SQL version called [Microsoft Machine Learning Server](https://docs.microsoft.com/machine-learning-server/). Free clients that include our R and Pyton interpreters include [Microsoft R Client](https://docs.microsoft.com/machine-learning-server/r-client/what-is-microsoft-r-client) and the [Python libraries](https://docs.microsoft.com/machine-learning-server/install/python-libraries-interpreter).

Packages and interpreters are also available on several [Azure virtual machines](https://docs.microsoft.com/machine-learning-server/install/machine-learning-server-azure-vm-on-linux), Azure Machine Learning, and Azure services like [HDInsight](https://docs.microsoft.com/machine-learning-server/install/machine-learning-server-on-azure-hdinsight). 


## Use cases

Develop on a client workstation using the same libraries and interpreters, and then deploy production code on SQL Server Machine Learning Services (In-Database). 

Use the SQL Server computer as the *remote compute context* for jobs launched from a remote development environment.

## Version history

SQL Server 2017 Machine Learning Services is the next generation of SQL Server 2016 R Services, enhanced to include Python. The following table is a complete list of all versions, from inception to the current release. 

| Product name | Engine version | Release date |
|--------------|---------|--------------|
| SQL Server 2017 Machine Learning Services (In-Database) | R Server 9.2.1 <br/> Python Server 9.2 | October 2017 |
| SQL Server 2017 Machine Learning Server (Standalone) | R Server 9.2.1 <br/> Python Server 9.2 | October 2017 |
| SQL Server 2016 R Services (In-Database) | R Server 9.1  | July 2017  |
| SQL Server 2016 R Server (Standalone)  |  R Server 9.1 | July 2017 |



## Documentation for each version

Recent releases of SQL Server documentation are version-agnostic. For SQL Server Machine Learning Services, Python is only available in 2017 and later, while R support is in all versions. Unless noted otherwise, you can assume R documentation applies to both 2016 and 2017 versions.

## How to get started

**Step 1:** Install and configure the software. 

+ [Install SQL Server 2017 Machine Learning Services (In-Database)](python/setup-python-machine-learning-services.md#bkmk_installPythonInDatabase)

**Step 2:** Get started with code using either one of these tutorials:

+ [Tutorial: Run Python in T-SQL](/tutorials/run-python-using-t-sql.md)
+ [Tutorial: Run R in T-SQL](/tutorials/rtsql-using-r-code-in-transact-sql-quickstart.md)

**Step 3:** Add your favorite R and Python packages and use them together with packages provided by Microsoft

+ [R Package management for SQL Server](r/r-package-management-for-sql-server-r-services.md)
