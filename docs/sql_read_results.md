# SQL Query Results — Day 8

## Query 1: All Students (ordered by prereq_score DESC)
SELECT * FROM students ORDER BY prereq_score DESC;
(6, 'Lina Barakat', '2024B', 'Jordan', 95.0)
(12, 'Sara Mahmoud', '2025A', 'Jordan', 93.5)
(1, 'Aisha Al-Rashidi', '2024A', 'Jordan', 91.0)
(10, 'Dina Saleh', '2024B', 'Egypt', 89.0)
(5, 'Tariq Farouk', '2024A', 'Palestine', 88.5)
(3, 'Nour Mansour', '2024A', 'Jordan', 84.0)
(14, 'Maya Qassem', '2025A', 'Palestine', 82.0)
(8, 'Rania Odeh', '2024B', 'Jordan', 80.0)
(2, 'Omar Khalil', '2024A', 'Jordan', 78.5)
(11, 'Faris Awad', '2025A', 'Jordan', 77.0)
(7, 'Sami Nabulsi', '2024B', 'Palestine', 72.0)
(15, 'Hamza Tawfiq', '2025A', 'Jordan', 70.0)
(4, 'Yasmin Haddad', '2024A', 'Jordan', 67.0)
(9, 'Khalil Jaber', '2024B', 'Jordan', 61.5)
(13, 'Yousef Al-Ahmad', '2025A', 'Jordan', 55.0)


## Query 2: Students with prereq_score >= 80
SELECT * FROM students WHERE prereq_score >= 80;
('Lina Barakat', 'Jordan', 95.0)
('Sara Mahmoud', 'Jordan', 93.5)
('Aisha Al-Rashidi', 'Jordan', 91.0)
('Dina Saleh', 'Egypt', 89.0)
('Tariq Farouk', 'Palestine', 88.5)
('Nour Mansour', 'Jordan', 84.0)
('Maya Qassem', 'Palestine', 82.0)
('Rania Odeh', 'Jordan', 80.0)


## Query 3: Average Score by Cohort
SELECT cohort, AVG(prereq_score) AS avg_score FROM students GROUP BY cohort;
('2024A', 5, 81.8)
('2024B', 5, 79.5)
('2025A', 5, 75.5)


## Query 4: Students + Projects (non-missing)
SELECT students.*, projects.* FROM students
JOIN projects ON students.id = projects.student_id
WHERE projects.project_score IS NOT NULL;
('Aisha Al-Rashidi', '2024A', 'Laptop Verify', 1, 'submitted', 95.0)
('Aisha Al-Rashidi', '2024A', 'Python Env', 2, 'submitted', 88.0)
('Aisha Al-Rashidi', '2024A', 'PR Hygiene', 3, 'submitted', 92.0)
('Dina Saleh', '2024B', 'Laptop Verify', 1, 'submitted', 90.0)
'late', 68.0)
('Sara Mahmoud', '2025A', 'Laptop Verify', 1, 'submitted', 94.0)
('Sara Mahmoud', '2025A', 'Python Env', 2, 'submitted', 91.0)
('Tariq Farouk', '2024A', 'Laptop Verify', 1, 'submitted', 91.0)
'late', 68.0)
('Sara Mahmoud', '2025A', 'Laptop Verify', 1, 'submitted', 94.0)
('Sara Mahmoud', '2025A', 'Python Env', 2, 'submitted', 91.0)
'late', 68.0)
('Sara Mahmoud', '2025A', 'Laptop Verify', 1, 'submitted', 94.0)
'late', 68.0)
('Yousef Al-Ahmad', '2025A', 'Laptop Verify', 1, 'late', 52.0)

## Interpretation

**Question 1:** Which cohort had the highest average pre-work score? What might that tell you about how cohorts differ?
The cohort with the highest average pre-work score is 2024B, with Lina Barakat having the highest score of 95.0.


**Question 2:** Looking at Query 2 results: how many students scored 80 or above? Does anything about their countries surprise you?Based on Query 2, 7 students scored 80 or higher:Lina Barakat (95.0),Sara Mahmoud (93.5),Aisha Al-Rashidi (91.0),Dina Saleh (89.0),Tariq Farouk (88.5),Nour Mansour (84.0),Maya Qassem (82.0)


**Question 3:** From the JOIN results (Query 4): choose one student and describe their project submission pattern. What does the data tell you about this learner?

Sara Mahmoud submitted 3 projects:
Laptop Verify: Submitted on time.
Python Env: Submitted on time.
Laptop Verify: Submitted on time.
Based on Query 3, the cohort 2025A had the lowest average score with 75.5.