## 🧠 **What is a Key?**

A **key** is an attribute (or a set of attributes) that is used to **uniquely identify a record (row)** in a table.

Without keys, a database table would have **duplicate or ambiguous data**.

---

## 🔑 **Types of Keys in DBMS**

| Type                 | Description                                                                                                             | Example                                                                                                                  |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **1. Super Key**     | A set of one or more attributes that **uniquely identifies** each record in a table.                                    | `{Emp_ID}`, `{Emp_ID, Emp_Name}`, `{Emp_ID, Dept}` all can be super keys.                                                |
| **2. Candidate Key** | The **minimal super key** — i.e., a super key with **no unnecessary attributes**.                                       | `{Emp_ID}` is a candidate key. `{Emp_ID, Dept}` is not (because Dept is extra).                                          |
| **3. Primary Key**   | One **candidate key** chosen by the database designer to **uniquely identify records**. It **cannot have NULL** values. | `Emp_ID`                                                                                                                 |
| **4. Alternate Key** | The **candidate keys** that are **not chosen** as the primary key.                                                      | If `{Emp_ID}` and `{Email}` are candidate keys, and `Emp_ID` is chosen as primary, then `Email` is an **alternate key**. |
| **5. Composite Key** | A key formed by **combining two or more attributes** to uniquely identify a record.                                     | `{Student_ID, Course_ID}` uniquely identifies enrollment records.                                                        |
| **6. Foreign Key**   | An attribute that **creates a link** between two tables — it **references the primary key** of another table.           | `Dept_ID` in `Employee` table referencing `Dept_ID` in `Department` table.                                               |
| **7. Unique Key**    | Ensures that all values in a column are **unique**, but unlike primary key, it **can have one NULL value**.             | `Email` column can be declared as UNIQUE.                                                                                |

---

## 🧩 **Example to Illustrate**

Let’s take a sample **Employee** table:

| Emp_ID | Email                         | Dept_ID | Name    |
| ------ | ----------------------------- | ------- | ------- |
| E01    | [a@xyz.com](mailto:a@xyz.com) | D01     | Alice   |
| E02    | [b@xyz.com](mailto:b@xyz.com) | D02     | Bob     |
| E03    | [c@xyz.com](mailto:c@xyz.com) | D01     | Charlie |

Now:

| Type               | Example                                           |
| ------------------ | ------------------------------------------------- |
| **Super Keys**     | {Emp_ID}, {Emp_ID, Email}, {Email, Dept_ID}       |
| **Candidate Keys** | {Emp_ID}, {Email}                                 |
| **Primary Key**    | {Emp_ID}                                          |
| **Alternate Key**  | {Email}                                           |
| **Foreign Key**    | Dept_ID (refers to Department table)              |
| **Composite Key**  | If Emp_ID + Project_ID together identify a record |
| **Unique Key**     | Email (if defined unique and can have one NULL)   |

---

## 🧭 **Quick way to remember them**

| Purpose                                 | Key Type                  |
| --------------------------------------- | ------------------------- |
| Identify uniquely                       | Super Key / Candidate Key |
| Chosen for identification               | Primary Key               |
| Remaining identifiers                   | Alternate Key             |
| Combination used for uniqueness         | Composite Key             |
| Link between tables                     | Foreign Key               |
| Enforce unique values (but allows NULL) | Unique Key                |

---

## 🎯 **Interview-Ready One-Liner Definitions**

* **Super Key:** A set of attributes that uniquely identifies a record.
* **Candidate Key:** A minimal super key (no redundant attributes).
* **Primary Key:** The main candidate key chosen for identification.
* **Alternate Key:** Other candidate keys not chosen as primary.
* **Composite Key:** Combination of multiple attributes acting as a key.
* **Foreign Key:** Attribute linking one table’s primary key to another.
* **Unique Key:** Ensures uniqueness but allows a NULL value.



### 🧸 Imagine you have a big box of toys.

Each toy has **different details**:

| Toy_ID | Color  | Name  | Type    |
| ------ | ------ | ----- | ------- |
| 1      | Red    | Teddy | Soft    |
| 2      | Blue   | Car   | Plastic |
| 3      | Yellow | Doll  | Soft    |

Now, we’ll see what each kind of **key** means using these toys 👇

---

### 🔑 1. **Super Key**

➡️ Anything that can **find your toy** in the box — even if it has extra info.

If you say:

* “Toy_ID” — you can find the toy ✅
* “Toy_ID + Color” — you can *also* find the toy ✅

So both are **super keys**.
(But the second one has extra info — not needed!)

🧠 *Think of Super Key like: many clues that work, but some are too big.*

---

### 🪄 2. **Candidate Key**

➡️ The **best, smallest clue** that still finds your toy.

Here, “Toy_ID” alone is enough — no need for “Color.”
So it’s a **candidate key**.

🧠 *Think: many clues work (super keys), but this one is the smartest clue.*

---

### 🌟 3. **Primary Key**

➡️ The **special main clue** you choose to always find toys.

You decide: “I’ll always use Toy_ID to find toys!”
So “Toy_ID” becomes your **primary key**.

🧠 *Think: the most important clue you write on every toy box.*

---

### 🎲 4. **Alternate Key**

➡️ Another clue that could find toys — but you didn’t choose it.

Maybe every toy’s **Name** is also different —
You *could* use it, but you already chose “Toy_ID.”

So “Name” is an **alternate key**.

🧠 *Think: a backup clue that also works.*

---

### 🧩 5. **Composite Key**

➡️ When you need **two clues together** to find something.

Imagine two toys both named “Car” — but one is plastic, one is soft.
You can’t find it by “Name” alone or “Type” alone.
But together: “Name + Type” works!

That’s a **composite key**.

🧠 *Think: two puzzle pieces joined together to find the right toy.*

---

### 🧭 6. **Foreign Key**

➡️ A **link** between two boxes of toys.

You have another box called **Toy Types**:

| Type_ID | Type_Name |
| ------- | --------- |
| 1       | Soft      |
| 2       | Plastic   |

In your toy box, “Type” connects to “Type_ID” in the second box —
that’s a **foreign key** — it tells where to look for extra info!

🧠 *Think: like saying “Ask that box for more details!”*

---

### 💫 7. **Unique Key**

➡️ A rule that says “this thing must be different for every toy.”

Maybe each toy’s **Name** must be unique (no two toys with same name).
So you mark “Name” as a **unique key**.

🧠 *Think: your toy names — no two can be the same!*

---

### 🎯 Summary (like a story):

| Key Type          | What it does              | Easy way to remember |
| ----------------- | ------------------------- | -------------------- |
| **Super Key**     | Any clue that finds a toy | Many clues work      |
| **Candidate Key** | Smallest clue that works  | Smartest clue        |
| **Primary Key**   | Main clue you always use  | Your favorite clue   |
| **Alternate Key** | Other good clues          | Backup clue          |
| **Composite Key** | Two clues together        | Teamwork clue        |
| **Foreign Key**   | Connects to another box   | "Ask my friend" clue |
| **Unique Key**    | Must be different for all | No name repeats      |


