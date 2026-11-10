Create a file named `README.md` in the root folder of your project (`placement-eligibility-decision-engine/`) and paste the following content:

```markdown
# 🎓 Placement Eligibility Decision Engine

<p align="center">
  <img src="https://img.shields.io/badge/Language-Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java" />
  <img src="https://img.shields.io/badge/Architecture-Clean%20OOP-00599C?style=for-the-badge" alt="OOP" />
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge" alt="Status" />
  <img src="https://img.shields.io/badge/Platform-Console%20Application-4EAA25?style=for-the-badge" alt="Platform" />
</p>

---

## 📌 Overview

The **Placement Eligibility Decision Engine** is a robust, modular Core Java console application designed to evaluate candidate job readiness in real-time. Built entirely around core **Object-Oriented Programming (OOP)** design principles, it takes dynamic candidate profiles, multiple job vacancies, and automated validation rules to produce clear, structured eligibility verdicts.

---

## 🚀 Key Features

- 👤 **Dynamic Candidate Input:** Reads personal details, academic percentage, active backlogs, graduation year, and skill sets.
- 💼 **Multi-Job Processing:** Dynamically accepts and stores an arbitrary collection of job openings using arrays.
- 🎯 **Interactive Selection:** Lets users select their target company and role at runtime.
- ⚙️ **Modular Validation Pipeline:** Uses independent rule objects for each criteria:
  - 📊 **Percentage Verification**
  - 🚫 **Backlog Verification**
  - 🎓 **Graduation Year Matching**
  - 🛠️ **Required Skillset Verification**
- 📋 **Readable Formatted Reports:** Prints a clear breakdown showing rule-by-rule status (`PASS`/`FAIL`) along with the final verdict.

---

## 🧩 OOP Concepts Applied

| OOP Concept | Implementation Details |
| :--- | :--- |
| **Encapsulation** | Private instance fields in `Candidate` and `Job` exposed via explicit public getter methods. |
| **Abstraction** | Defined in `EligibilityRule` through abstract methods `check()` and `getRuleName()`. |
| **Inheritance** | Specific rule classes (`PercentageRule`, `BacklogRule`, etc.) extend the base `EligibilityRule`. |
| **Polymorphism** | `EligibilityChecker` iterates over an array of `EligibilityRule[]`, dynamically executing the overridden logic of each subclass at runtime. |
| **HAS-A Relationship** | `EligibilityChecker` has a collection of `EligibilityRule` objects; `Candidate` and `Job` maintain array references for skills. |

---

## 🔄 Project Execution Flow

```text
       [ Start Application ]
                 │
                 ▼
       ┌──────────────────┐
       │ Candidate Input  │ ──► (Name, Marks, Backlogs, Year, Skills)
       └──────────────────┘
                 │
                 ▼
       ┌──────────────────┐
       │ Dynamic Job List │ ──► (Jobs Array & Skill Requirements)
       └──────────────────┘
                 │
                 ▼
       ┌──────────────────┐
       │ Select Target Job│ ──► (User chooses job index)
       └──────────────────┘
                 │
                 ▼
     ┌──────────────────────┐
     │  EligibilityChecker  │
     └──────────┬───────────┘
                │
    ┌───────────┼───────────┬──────────────┐
    ▼           ▼           ▼              ▼
[Percentage] [Backlogs]  [Year]        [Skills]
   Rule        Rule       Rule           Rule
    │           │           │              │
    └───────────┼───────────┴──────────────┘
                │
                ▼
     ┌──────────────────────┐
     │ Final Decision Engine│
     └──────────┬───────────┘
                │
        ┌───────┴───────┐
        ▼               ▼
  [ ELIGIBLE ]   [ NOT ELIGIBLE ]

```

---

## 📂 Project Directory Structure

```text
placement-eligibility-decision-engine/
├── .gitignore
├── README.md
└── src/
    ├── Main.java                 # Main application driver & console I/O
    ├── Candidate.java            # Candidate entity (profile & skills)
    ├── Job.java                  # Job entity (criteria & required skills)
    ├── EligibilityRule.java      # Abstract parent class for rules
    ├── PercentageRule.java       # Validates candidate percentage
    ├── BacklogRule.java          # Validates candidate backlog count
    ├── GraduationYearRule.java   # Validates graduation batch
    ├── SkillRule.java            # Validates all job skill requirements
    └── EligibilityChecker.java   # Orchestrates and evaluates all rules

```

---

## 🛠️ Compilation & Execution

### 1. Compile

Compile all Java source files from the project root:

```bash
javac src/*.java

```

### 2. Run

Launch the application:

```bash
java -cp src Main

```

---

## 🧪 Sample Execution

### Sample Input

```text
Rahul
78
0
2026
3
Java
SQL
HTML
2
Infosys
JavaDeveloper
65
0
2026
2
Java
SQL
TCS
GraduateEngineer
70
1
2026
2
Java
HTML
1

```

### Sample Output

```text
AVAILABLE JOBS
1. Infosys - JavaDeveloper
2. TCS - GraduateEngineer

================================
PLACEMENT ELIGIBILITY RESULT
================================

Candidate : Rahul
Company   : Infosys
Role      : JavaDeveloper

Percentage : PASS
Backlogs : PASS
Graduation Year : PASS
Skills : PASS

Final Result : ELIGIBLE
================================

```

---

## 📦 Git Commands to Push

```bash
git status
git add .
git commit -m "Complete placement eligibility decision engine"
git push

```

```

```