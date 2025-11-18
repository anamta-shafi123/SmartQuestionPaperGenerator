SMART PAPER GENERATOR – PROJECT REPORT

Frontend: Qt Framework
Backend: C++
Algorithms Used: Backtracking + Greedy Hybrid Approach


1. Introduction

Creating a fair and balanced question paper is a time-consuming task for teachers. They must ensure:

• Correct coverage of CLOs (Course Learning Outcomes)
• Balanced difficulty levels (Easy / Medium / Hard)
• Topic relevance for the selected course
• No repetition of previously used questions
• Total marks fulfillment

The Intelligent Question Paper Generator automates this problem using Data Structures and Algorithms.
The system stores questions in a structured question bank and generates question papers dynamically based on teacher-provided ratios for CLOs, difficulty levels, and total marks.

2. Features:

Automatic Paper Generation: Creates complete question papers based on teacher-selected difficulty levels, marks, and CLO distribution.
Topic-Based Filtering: Ensures only relevant questions from the chosen course and topics are included.
Balanced Difficulty: Maintains a fair mix of Easy, Medium, and Hard questions as per required ratios.
CLO Coverage Assurance: Guarantees that all specified Course Learning Outcomes are represented properly.
No Repetition of Questions: Automatically excludes any previously used questions.
Dynamic Customization: Teachers can set total marks, number of questions, and distribution preferences.
Clean & Printable Output: Generates a polished final question paper ready for printing or submission.
User-Friendly Interface: Easy for teachers to input requirements and generate papers quickly.

3. Data Structures Used & Justification
   
3.1 HashMap (topicSet)

Structure: unordered_map<string, set<int>> topicSet
Purpose:
- Stores topics as keys
- Stores sets of question IDs as values
Reason for Use:
- Provides O(1) average-time complexity
- Fast topic-based lookups
- Ideal for filtering questions by selected topic
  
3.2 HashSet (usedQuestions)

Structure: unordered_set<int> usedQuestions
Purpose:
- Ensures unique, non-repeated questions
Reason for Use:
- Fast membership checking
- Guarantees no repeated questions
  
3.3 Priority Queue (Min Heap)

Structure: priority_queue<Question, vector<Question>, compareMarks>
Purpose:
- Used in greedy phase for leftover mark fill
Reason for Use:
- Greedy relies on selecting minimum-mark elements
- Min-heap ensures optimal selection
  
3.4 Vectors

Structures:
- vector<Question> selectedQuestions
- vector<Question> filteredQuestions
Purpose:
- Stores filtered question sets and final selected questions
Reason for Use:
- Dynamic resizing
- Easy sequential access
- Efficient for storing filtered subsets
  
3.5 TopicTrie (Trie Data Structure)

Structure: Custom Trie class
Purpose:
- Auto-suggestion for topic names
Reason for Use:
- Fast prefix searching
- Makes UI interactive
  
4. Algorithmic Approach
   
4.1 Backtracking Algorithm (Phase 1)
Used for CLO ratios, difficulty ratios, topics, and total marks constraints.
Working:
- Select questions matching constraints
- Track remaining marks
- If constraint breaks → backtrack
- Continue until valid combination found
Why Backtracking?
- Handles complex constraints
- Ensures correctness
  
4.2 Greedy Algorithm (Phase 2)

Used after backtracking for remaining marks.
Working:
- Insert candidate leftover questions in min-heap
- Select smallest valid question
- Fill remaining marks
Why Greedy?
- Fast and optimal local decisions
  
4.3 Hybrid Benefit

Backtracking ensures correctness.
Greedy ensures optimization.
Together they create a robust generator.

5. System Workflow
   
Main Window
Contains four buttons:
- Add Question
- View Question Bank
- Generate Paper
- Exit
  
5.1 Add Question Window

User enters topic, course, CLO, difficulty, question text, marks.
System:
- Stores question
- Updates topicSet
- Updates Trie
  
5.2 View Question Bank

Displays questions searchable by topic, difficulty, CLO, and marks.

5.3 Generate Paper Window

User provides university, department, course, total marks, topics, CLO and difficulty ratios.
System generates paper, shows preview, allows PDF export.

6. Frontend and Backend Technologies
Frontend – Qt
- UI, buttons, input fields, preview window, PDF export

Backend – C++
- Uses STL data structures
- Efficient for algorithmic processing

7. Conclusion

The Smart Paper Generator automates exam paper creation using backtracking and greedy algorithms with efficient data structures such as HashMap, HashSet, Priority Queue, Vectors, and Trie.
It ensures accurate CLO and difficulty coverage, optimal question allocation, unique papers, and high performance.

