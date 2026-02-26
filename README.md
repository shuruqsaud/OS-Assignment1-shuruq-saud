# CS3701 Operating Systems - Assignment 1: Multithreading
## Round-Robin CPU Scheduler Simulation

### 📋 Assignment Overview

Welcome to Assignment 1! In this assignment, you will work with **Java threads** to simulate a **Round-Robin CPU scheduling algorithm**. This is your opportunity to:

- 🎯 Learn how threads work in practice
- 🔄 Understand CPU scheduling concepts
- 💻 Write, test, and document real concurrent code
- 📊 Analyze threading behavior
- 🌟 Develop professional software development practices including version control, documentation, and project presentation

**Important**: This assignment is worth **5 marks + 5 Bonus** (10% of your final grade).

---

## 🚀 Getting Started

### Step 1: Fork This Repository

1. **Create a GitHub account** using your **university email** (@std.psau.edu.sa)
   - Go to https://github.com
   - Click "Sign up"
   - Use your university email: `yourID@std.psau.edu.sa`
   - Verify your email address

2. **Fork this repository**:
   - Click the **"Fork"** button at the top right of this page
   - This creates your own copy of the repository
   - Your repository will be at: `https://github.com/YOUR_USERNAME/OS-Assignment1-YOUR_NAME`

3. **Rename your forked repository**:
   - Go to your forked repository Settings
   - Change the repository name to: `OS-Assignment1-YourFirstName-YourLastName`
   - Example: `OS-Assignment1-Mohammed-Ahmed`

4. **Make sure your repository is PUBLIC**:
   - Go to Settings → scroll down to "Danger Zone"
   - Verify visibility is set to "Public"
   - If private, click "Change visibility" → "Make public"

### Step 2: Clone Your Repository to Your Computer

```bash
git clone https://github.com/YOUR_USERNAME/OS-Assignment1-YourFirstName-YourLastName.git
cd OS-Assignment1-YourFirstName-YourLastName
```

### Step 3: Set Up Your Student ID

**⚠️ CRITICAL FIRST STEP ⚠️**

Open `SchedulerSimulation.java` and **immediately** change line 150:

```java
// BEFORE (DO NOT SUBMIT THIS):
int studentID = 123456789;

// AFTER (Use YOUR real ID):
int studentID = 441234567;  // Replace with YOUR actual student ID
```

**Save this change and commit it right away**:

```bash
git add SchedulerSimulation.java
git commit -m "Set my student ID: 441234567"
git push origin main
```

✅ This personalizes your assignment and prevents identical outputs!

---

## 📂 Repository Structure

Your repository should have these files:

```
OS-Assignment1-YourName/
├── README.md                    # This file - project overview
├── SchedulerSimulation.java     # Main code file (YOU WILL MODIFY THIS)
├── DEVELOPMENT_LOG.md           # Your development timeline (FILL THIS)
├── REFLECTION.md                # Your learning reflections (FILL THIS)
├── ANSWERS.md                   # Answers to assignment questions (FILL THIS)
└── .gitignore                   # Git ignore file (already configured)
```

---

## 💡 Understanding the Code

### What is Round-Robin Scheduling?

Round-Robin is a CPU scheduling algorithm where:
- Each process gets a **fixed time slice** (time quantum) to run
- If a process doesn't finish, it goes to the **back of the queue**
- The next process gets its turn
- This continues until all processes finish

**Think of it like**: A teacher calling on students one by one. Each student gets 2 minutes to speak. If they're not done, they go to the back of the line.

### Key Components

#### 1. **Process Class** (lines 10-88)
Represents a process that will run on the CPU:
- `name`: Process identifier (P1, P2, etc.)
- `burstTime`: Total time needed to complete
- `timeQuantum`: Maximum time allowed per turn
- `remainingTime`: How much time is left
- `run()`: What the process does when scheduled

#### 2. **SchedulerSimulation Class** (lines 90-167)
The scheduler that manages all processes:
- Creates multiple processes with random burst times
- Maintains a **queue** of ready processes
- Runs each process for one time quantum
- Re-queues processes that aren't finished
- Continues until all processes complete

### Threading Concepts You'll Learn

1. **Thread Creation**: `Thread thread = new Thread(process);`
2. **Starting Threads**: `thread.start();`
3. **Waiting for Completion**: `thread.join();`
4. **Thread Sleeping**: `Thread.sleep(milliseconds);`

---

## ✅ Your Tasks (4 Parts - 10 Marks Total)

### **Part 1: GitHub Account & Repository Setup (3 marks)**

1. **Create GitHub Account** using your university email (@std.psau.edu.sa)
   - Go to https://github.com/signup
   - Use your university email: `yourname@std.psau.edu.sa`
   - Verify your email address
   - Choose a professional username

2. **Fork the Starter Repository**:
   - Go to: `https://github.com/makopt/OS-Assignment1-Starter`
   - Click the **"Fork"** button at the top right
   - Wait for GitHub to create your copy

3. **Rename Your Repository**:
   - Go to Settings → Change repository name to:
   - `OS-Assignment1-YourFirstName-YourLastName`
   - Example: `OS-Assignment1-Mohammed-Ahmed`
   - **Verify repository is PUBLIC**

4. **Set Your Student ID** in line 150 of `SchedulerSimulation.java`:
   - Click on the file → Edit (pencil icon)
   - Replace `123456789` with YOUR actual student ID
   - Commit: `"Set my student ID: [YOUR-ID]"`

**Commit Examples**:
```bash
git add SchedulerSimulation.java
git commit -m "Set my student ID: 441234567"
git push origin main
```

### **Part 2: Code Implementation (3 marks)**

**Modify the code** to add these three features:

The starter code already includes several enhancements:
- **Color-Coded Output** for better readability
- **Visual Progress Bars** for process execution
- **Ready Queue Visualization** before each execution
- **Randomized Simulation** based on your student ID

**Your task** is to add these new features:

**Important Guidelines**:
- Make **one commit per feature** - do NOT commit everything at once!
- Test each feature before committing
- Add clear comments explaining your additions
- Keep the existing functionality working

**Commit Examples**:
- ✅ `"Feature 1: Added priority field to Process class"`
- ✅ `"Feature 2: Implemented context switch counter"`
- ✅ `"Feature 3: Added waiting time tracking and summary"`
- ❌ `"done"` or `"update"` or `"final version"` (too vague!)

#### 2.1: Feature 1 - Add Process Priority (1 mark)
- Add a `priority` field to the Process class (integer 1-5, where 5 is highest)
- Generate random priorities when creating processes
- Display priority when a process enters the ready queue
- Example output: `"P1 (Priority: 4) enters the ready queue..."`
- Add clear comments explaining your additions

#### 2.2: Feature 2 - Count Context Switches (1 mark)
- Add a static counter variable for context switches
- Increment the counter each time a new process starts running
- Display total context switches at the end of simulation
- Example: `"Total context switches: 47"`
- A context switch occurs every time the CPU switches to a different process

#### 2.3: Feature 3 - Track Waiting Time (1 mark)
- Add fields to track when each process was created and total time spent waiting
- Calculate waiting time for each process
- Use `System.currentTimeMillis()` to track time
- Display a summary table at the end showing:
  - Process Name
  - Burst Time
  - Waiting Time
- Format the output in a clear, readable table

**Commit after EACH feature**:
```bash
git add SchedulerSimulation.java
git commit -m "Added [feature name]: [brief description]"
git push origin main
```

### **Part 3: Documentation (2 marks)**

Complete these three markdown files in your repository to document your work and demonstrate your understanding:

#### 3.1: DEVELOPMENT_LOG.md (1 mark)
Track your development process with **minimum 5 entries**:
- Date and time of work session
- What you worked on (specific features or tasks)
- Challenges encountered during this session
- Solutions you implemented
- Time spent (approximate)
- **Template with example format is provided in the file!**
- Entries should be spread across different dates (not all at once)

#### 3.2: REFLECTION.md (0.5 marks)
Answer the **4 reflection questions** provided in the file:
1. What did you learn about multithreading from this assignment?
2. What was the most challenging part of this assignment and why?
3. How did you overcome the challenges you faced?
4. How can multithreading concepts be applied in real-world applications?
- Each answer: **minimum 5-7 sentences**
- Write in your own words, showing genuine reflection
- Connect concepts to your actual experience with the code

#### 3.3: ANSWERS.md (0.5 marks)
Answer the **4 technical questions** in the provided template:
- Each answer: **minimum 3-5 sentences**
- Include specific examples from your code or output
- Use proper technical terminology (thread, process, time quantum, context switch, etc.)
- Reference relevant parts of your code where appropriate

### **Part 4: Video Demonstration (2 marks)**

Create a **2-3 minute video** (not shorter, not longer) showing:

1. **Introduction (30 seconds)**:
   - State your name and student ID
   - Show your GitHub repository homepage
   - Verify repository is public and uses university email

2. **Code Walkthrough (1 minute)**:
   - Navigate through your repository files
   - Show your three modifications (priority, context switches, waiting time)
   - Briefly explain each feature you added

3. **Execution Demo (30 seconds)**:
   - Open your IDE (VS Code, IntelliJ IDEA, Eclipse, or similar)
   - Show the `SchedulerSimulation.java` file open in the IDE
   - Compile and run using your IDE's run button/feature
   - Show console output with your student ID and unique simulation parameters

4. **Concept Explanation (30 seconds)**:
   - Pick ONE threading concept you learned
   - Options: `Thread.start()`, `Thread.join()`, `Thread.sleep()`, or how the ready queue works
   - Explain it in your own words using your code as example

5. **Closing (10 seconds)**:
   - Show your commit history (at least 3 commits)
   - Thank you message

**Video Requirements**:
- Upload to **Google Drive** with public sharing link
- Set permissions to "Anyone with the link can view"
- Name: `StudentID_Assignment1_Demo.mp4` (or .mov, .avi)
- Show your face OR use clear voice narration
- Screen recording showing code and execution
- Good audio quality (test your microphone first!)

**Good commit examples**:
- ✅ "Part 1: Set student ID to 441234567"
- ✅ "Added priority field to Process class"
- ✅ "Implemented context switch counter"
- ✅ "Completed ANSWERS.md with all 4 questions"

**Bad commit examples**:
- ❌ "done"
- ❌ "update"
- ❌ "final version"

**Recording Tools**:
- **Mac**: QuickTime Player (File → New Screen Recording)
- **Windows**: Xbox Game Bar (Win + G) or OBS Studio
- **Linux**: SimpleScreenRecorder or OBS Studio

**Important Notes**:
- Use your IDE (VS Code, IntelliJ IDEA, Eclipse, etc.) to compile and run - NOT just terminal
- Make sure the IDE console output is clearly visible
- Show your unique simulation parameters: student ID, time quantum, and number of processes
- Explain concepts in your own words to demonstrate understanding

---

## � Recommended Development Environment

**We strongly recommend using Visual Studio Code (VS Code) as your IDE:**

### Why VS Code?
- **Download**: Visit [Visual Studio Code](https://code.visualstudio.com/download) and install for your OS
- **GitHub Integration**: Built-in Git support makes committing and pushing easier
- **Easy Setup**: Sign in to GitHub in VS Code (click account icon, bottom left)
- **Clone Repository**: Use File > Open Folder or Command Palette (Ctrl/Cmd+Shift+P) → "Git: Clone"

### Recommended Extensions:
- **GitLens** - Enhances Git capabilities and visualization
- **Java Extension Pack** - Provides Java language support, debugging, and project management
- **Markdown All in One** - Useful for editing documentation files

### Helpful Tutorials:
- [VS Code GitHub Integration](https://www.youtube.com/watch?v=i_23KUAEtUM)
- [Java Development in VS Code](https://www.youtube.com/watch?v=BB0gZFpukJU)

**Note**: You can use any IDE (IntelliJ IDEA, Eclipse, Notepad++, etc.), but VS Code is recommended for excellent GitHub integration.

---

## �🔑 Professional Development Practices

### Version Control (Critical for Success!)

Your repository must demonstrate professional Git usage:
- ✅ **Minimum 3 meaningful commits** spread over time
- ✅ Clear commit messages describing what changed
- ✅ Commits on **different dates/times** (not all at once!)
- ✅ One commit per feature - incremental progress

---

## 📝 Questions to Answer (in ANSWERS.md)

These questions help you demonstrate technical understanding. Each answer should be thoughtful and specific.

### Question 1: Thread vs Process
- **Explain the difference** between a thread and a process
- **Why did we use threads** in this assignment instead of separate processes?
- **Mention at least TWO specific differences** (e.g., memory sharing, creation overhead, communication speed)
- **Reference relevant parts** of `SchedulerSimulation.java` where appropriate
- Minimum: 3-5 sentences

### Question 2: Ready Queue Behavior
- In Round-Robin scheduling, **what happens when a process doesn't finish** within its time quantum?
- **Explain using a specific example** from YOUR program output
- **Copy a relevant snippet** from your terminal output showing a process being re-queued
- **Explain why this re-queueing behavior** is important for fairness in CPU scheduling
- Minimum: 3-5 sentences

### Question 3: Thread Lifecycle
- A thread typically goes through these states: **New, Runnable, Running, Waiting, Terminated**
- **Walk through these states** for one process (e.g., P1) from your simulation
- For each state, **explain WHEN P1 enters that state** during execution
- **Use specific method calls** from the code (`Thread.start()`, `Thread.join()`, `Thread.sleep()`) in your explanation
- Minimum: 3-5 sentences

### Question 4: Real-World Applications
- **Describe TWO real-world scenarios** where Round-Robin scheduling with threads would be useful
- For each scenario: **What is the application/system?** (e.g., web server, game engine, media player)
- For each scenario: **Why is Round-Robin scheduling appropriate?** (consider fairness, responsiveness, predictability)
- **Explain how the concepts** from this assignment apply to each scenario
- Minimum: 3-5 sentences

---

## 🎥 Video Demonstration Guide

### What to Include:

1. **Introduction (30 seconds)**:
   - "Hello, I'm [Your Name], student ID [Your ID]"
   - "This is my submission for CS3701 Assignment 1"
   - Show your GitHub repository homepage

2. **Code Walkthrough (1 minute)**:
   - Open your repository files
   - Briefly explain the main components
   - Show your modifications (priority, context switches, waiting time)

3. **Compilation & Execution (30 seconds)**:
   - Open terminal/command prompt
   - Compile: `javac SchedulerSimulation.java`
   - Run: `java SchedulerSimulation`
   - Show the output with your student ID

4. **Concept Explanation (30 seconds)**:
   - Pick ONE threading concept
   - Explain it clearly using your code as example
   - Show where it appears in your implementation

5. **Closing (10 seconds)**:
   - Show your commit history
   - "Thank you for watching!"

### Tips for a Good Video:
- ✅ Test your screen recording software first
- ✅ Close unnecessary tabs/windows
- ✅ Use a clear microphone
- ✅ Speak slowly and clearly
- ✅ Zoom in on code if needed
- ✅ Keep it under 3 minutes

---

## ⚠️ Academic Integrity

### Critical Warnings:

1. **AI-Generated Code**: 
   - Pure AI-generated submissions without understanding will receive **zero marks**
   - You may be asked to explain your code in person
   - You must be able to answer questions about your implementation

2. **Plagiarism**: 
   - Copying from classmates results in **zero marks for all parties**
   - Each student has unique output based on their student ID

3. **Commit History**: 
   - Single bulk commits show poor practice and will be penalized
   - Commits must be spread over different dates/times

4. **Video Authenticity**: 
   - You must be able to answer questions about your work
   - Video should show genuine understanding, not memorized explanations

### ✅ Best Practices:

1. **Start early** - Don't wait until the deadline
2. **Commit frequently** - After each small change  
3. **Test your code** - Make sure it compiles and runs correctly
4. **Ask questions** - Use Blackboard discussion or office hours
5. **Keep it simple** - Don't over-complicate your modifications
6. **Understand everything** - Be able to explain every line you write

---

## 📅 Submission Instructions

### What to Submit on Blackboard:

Submit **ONE text file** named: `YourName_StudentID_Assignment1.txt`

**Content of the text file**:
```
Student Name: Mohammed Ahmed Abdullah
Student ID: 442105123
GitHub Username: mohammed-ahmed-441
Repository Link: https://github.com/mohammed-ahmed-441/OS-Assignment1-Mohammed-Ahmed
Video Link: https://drive.google.com/file/d/1aBcDeFgHiJkLmNoPqRsTuVwXyZ/view?usp=sharing
Date Submitted: March 31, 2026
```

### Submission Checklist:

Before submitting, verify:
- ✅ Repository is PUBLIC
- ✅ Repository contains ALL required files
- ✅ Student ID is set correctly in code
- ✅ At least 3 commits with good messages
- ✅ All 3 documentation files completed
- ✅ Video is accessible (unlisted YouTube or public Google Drive)
- ✅ Code compiles without errors
- ✅ Screenshot shows your execution with your student ID

---

## 🏆 Grading Breakdown (10 Marks Total)

| Component | Marks | Criteria |
|-----------|-------|----------|
| **Part 1: GitHub Setup & Personalization** | 3.0 | GitHub account (university email 0.5), Repository forked & renamed (1.0), Student ID set (1.0), Repository public (0.5) |
| **Part 2: Code Implementation** | 3.0 | Feature 1: Priority (1.0), Feature 2: Context switches (1.0), Feature 3: Waiting time (1.0) - Code compiles, runs, has comments, separate commits |
| **Part 3: Documentation** | 2.0 | DEVELOPMENT_LOG.md (1.0), REFLECTION.md (0.5), ANSWERS.md (0.5) - All demonstrate understanding |
| **Part 4: Video Demonstration** | 2.0 | Length 2-3 min (0.5), Shows repo/code/execution (0.5), Concept explanation (0.5), Quality & accessibility (0.5) |
| **Professional Practices** | Included | Min 3 commits, spread over time, descriptive messages |
| **Total** | **10.0** | |

### Penalties:
- Late submission: **-2 marks per day**
- Missing video: **-2 marks**
- Single commit or all commits in last hour: **-1 mark**
- Private repository: **-1 mark**
- Not using university email: **-0.5 marks**
- AI-generated without understanding: **0 marks** (entire assignment)
- Plagiarism: **0 marks + academic misconduct report**

---

## 🆘 Getting Help

### If you have issues:

1. **Check the FAQ** in Blackboard
2. **Use the discussion forum** - other students may have similar questions
3. **Attend office hours**
4. **Email your instructor** with specific questions

### Common Issues & Solutions:

**Problem**: "javac is not recognized"
→ **Solution**: Install JDK and set PATH variable

**Problem**: "My repository is not accessible"
→ **Solution**: Go to Settings → ensure it's set to Public

**Problem**: "I can't fork the repository"
→ **Solution**: Make sure you're logged into GitHub with your university email

**Problem**: "Git push is rejected"
→ **Solution**: Make sure you're pushing to YOUR forked repository, not the original

---

## 📚 Learning Resources

### Java Threading Basics:
- Oracle Java Tutorials: [Concurrency](https://docs.oracle.com/javase/tutorial/essential/concurrency/)
- Your textbook: Chapter 4 - Threads & Concurrency

### Git & GitHub:
- [GitHub Guides](https://guides.github.com/)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)

### Round-Robin Scheduling:
- Your textbook: Chapter 5 - CPU Scheduling
- Wikipedia: [Round-robin scheduling](https://en.wikipedia.org/wiki/Round-robin_scheduling)

---

## 🎯 Success Tips

1. **Read the entire README** before starting
2. **Set your student ID first** - this is critical!
3. **Make small changes** and commit often
4. **Test after every change** - don't wait until the end
5. **Start the video early** - you might need multiple takes
6. **Explain concepts in your own words** - this shows understanding
7. **Keep backups** - copy your repository regularly
8. **Submit early** - don't wait for the last minute

---

## 📝 Final Checklist Before Submission

- [ ] Student ID set in code (line 150)
- [ ] Code compiles without errors
- [ ] Code runs and produces expected output
- [ ] All 3 features implemented (priority, context switches, waiting time)
- [ ] DEVELOPMENT_LOG.md completed (5+ entries)
- [ ] REFLECTION.md completed (4 questions answered)
- [ ] ANSWERS.md completed (4 questions answered)
- [ ] At least 3 meaningful commits
- [ ] Commits spread over different times/dates
- [ ] Repository is PUBLIC
- [ ] GitHub account uses university email
- [ ] Video recorded (2-3 minutes)
- [ ] Video uploaded to YouTube/Google Drive
- [ ] Video link added to README or submission file
- [ ] Screenshot of output included
- [ ] Text file prepared with all submission info
- [ ] Text file submitted on Blackboard

---

## 🎓 Deadline

**Due Date**: March 31, 2026, 11:59 PM

**Late Policy**: -2 marks per day late

---

Good luck with your assignment! Remember, the goal is to **learn about multithreading**, not just to complete the assignment. Take your time to understand each concept.

If you learn something new, you've succeeded! 🎉
