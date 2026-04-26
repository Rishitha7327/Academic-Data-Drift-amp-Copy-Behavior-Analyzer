📊 Academic Data Drift & Copy Behavior Analyzer
🚀 Overview

This project explores how student academic data behaves when copied and modified. It mainly focuses on understanding the difference between shallow copy and deep copy, and how improper copying can lead to data drift and inconsistency.

Instead of just performing operations, this program simulates a real-world scenario where university data is duplicated for analysis and then unintentionally altered.

🎯 Objective
Generate random student academic data
Apply transformations only on copied data
Analyze statistical changes using NumPy and Pandas
Detect data drift and identify copy-related issues
🧠 Key Concept

Not all copies are safe.
Shallow copy shares internal references, which can unintentionally modify original data. Deep copy avoids this issue.

🏗️ Data Structure Used

Each student record:

{
  "id": int,
  "marks": int,
  "attendance": int,
  "scores": [internal, assignment]
}
Stored as a list of dictionaries
scores is a nested list (important for copy behavior)
⚙️ Workflow
1. Data Generation
Randomly creates 10–15 student records
2. Copy Creation
Creates:
Shallow copy
Deep copy
3. Mutation (Applied only on copies)

Marks updated using:

marks = marks + sqrt(marks)
Scores list modified (nested structure)
Attendance adjusted

Mutation controlled using:

index % (roll_number % 3)
4. Analysis
Mean, Median, Standard Deviation (NumPy)
Manual mean calculation (without NumPy)
Normalization of marks

Drift calculation:

drift = abs(original_mean - modified_mean)
5. Pattern Detection
Detects:
Stable Data
Minor Drift
Critical Drift
Copy Failure
📌 Personalization Logic
Roll number is taken as input

Mutation rule:

modify indices where index % (roll_number % 3) == 0
Ensures unique output for each student
⚠️ Key Observation
❌ Shallow Copy Issue
Shares inner references
Modifying scores affects original data
Leads to Copy Failure
✅ Deep Copy Advantage
Fully independent copy
Original data remains unchanged
📊 Sample Output (Conceptual)
===== ORIGINAL DATA =====
...

===== SHALLOW COPY =====
... (values changed unexpectedly)

===== DEEP COPY =====
... (correct independent modification)

Drift Value: X.XX
Tuple: (mean, drift, std_dev)

Final Classification: Copy Failure Detected
🧪 Technologies Used
Python
NumPy
Pandas
math
random
copy module
📚 Learning Outcome
Understood the real difference between shallow and deep copy
Learned how nested structures affect memory behavior
Applied statistical analysis using NumPy
Explored concept of data drift in real systems
Improved debugging and data validation skills
💡 Final Thought

This project shows that:

Small implementation mistakes (like using shallow copy) can lead to serious data inconsistencies in real-world systems.

👩‍💻 Author

Name: M.Rishitha
Course: CSE205 – Hands-on Python
University: SRM University–AP
