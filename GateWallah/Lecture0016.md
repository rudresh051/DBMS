# Tranaction Concept
In **DBMS (Database Management System)**, a **transaction** is a **logical unit of work** that consists of one or more database operations — such as **insert, update, delete, or retrieve** — which are executed as a single unit.

👉 In simple terms:
A **transaction** is a **set of operations that must all succeed or all fail together**, ensuring the **consistency** of the database.

---

### 💡 Example

Suppose you transfer ₹1000 from **Account A** to **Account B**.
This operation involves two steps:

1. **Debit ₹1000** from Account A
2. **Credit ₹1000** to Account B

Both actions **must occur together**.
If the first succeeds and the second fails (due to system crash, etc.), the database would be inconsistent.

Thus, both steps form **a single transaction**.

---

### 🔹 Properties of a Transaction — The ACID Properties

To maintain database reliability and consistency, every transaction should follow the **ACID** properties:

| Property            | Description                                                                                      |
| ------------------- | ------------------------------------------------------------------------------------------------ |
| **A – Atomicity**   | A transaction is **all or nothing**. Either all its operations execute successfully, or none do. |
| **C – Consistency** | The database must remain in a **valid state before and after** the transaction.                  |
| **I – Isolation**   | Multiple transactions executing simultaneously should **not affect each other’s results**.       |
| **D – Durability**  | Once a transaction is committed, its results are **permanent**, even if the system crashes.      |

---

### 🔹 Transaction States

A transaction passes through the following states:

| State                   | Meaning                                                    |
| ----------------------- | ---------------------------------------------------------- |
| **Active**              | Transaction is executing.                                  |
| **Partially Committed** | All operations executed, but not yet saved permanently.    |
| **Committed**           | All changes are permanently saved.                         |
| **Failed**              | Transaction execution failed due to error or system crash. |
| **Aborted**             | All changes rolled back to restore database consistency.   |

---

### 🔹 Commit and Rollback Commands

* **`COMMIT`** → Saves the changes made by the transaction permanently.
* **`ROLLBACK`** → Undoes all the changes if any error occurs.

---

### 💬 Example in SQL

```sql
START TRANSACTION;

UPDATE Accounts SET balance = balance - 1000 WHERE account_id = 'A';
UPDATE Accounts SET balance = balance + 1000 WHERE account_id = 'B';

COMMIT;
```

If an error occurs during the second update:

```sql
ROLLBACK;
```

The database will undo the first update as well — maintaining consistency.

---

### ✅ Summary

| Concept         | Description                                           |
| --------------- | ----------------------------------------------------- |
| **Transaction** | Logical unit of work (a group of operations).         |
| **Goal**        | Ensure database consistency even in case of failures. |
| **Key Idea**    | “All or Nothing” execution.                           |
| **ACID**        | Atomicity, Consistency, Isolation, Durability.        |

