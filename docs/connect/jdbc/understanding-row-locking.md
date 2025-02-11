---
description: Learn how row locking is used to control how concurrent users access data at the same time from different connections.
title: Understanding row locking
ms.custom: ""
ms.date: "12/08/2020"
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ""
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 63c76a2f-f2b9-461f-8904-acbda0169ac3
author: David-Engel
ms.author: v-davidengel
---

# Understanding row locking

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

The [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] row locks. These implement concurrency controls among multiple users who are performing modifications in a database at the same time. By default, transactions and locks are managed on a per-connection basis. For example, if an application opens two JDBC connections, locks that are acquired by one connection cannot be shared with the other connection. Neither connection can acquire locks that would conflict with locks held by the other connection.

> [!NOTE]  
> If row locking is used, all rows in the fetch buffer are locked, so a very large setting for the fetch size can affect concurrency.

Locking is used to assure transactional integrity and database consistency. Locking prevents users from reading data that is being changed by other users, and prevents multiple users from changing the same data at the same time. If locking is not used, data within the database might become logically incorrect, and queries run against that data might produce unexpected results.

> [!NOTE]  
> For more information about row locking in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Locking in the [!INCLUDE[ssDE](../../includes/ssde_md.md)]](../../relational-databases/sql-server-transaction-locking-and-row-versioning-guide.md#Lock_Engine).

## See also

[Managing result sets with the JDBC driver](managing-result-sets-with-the-jdbc-driver.md)
