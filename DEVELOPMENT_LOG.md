# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [April 1, 2026, 2:30 PM]
**What I did**: Forked the repository and set up my student ID

**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (441234567)
- Compiled and ran the program successfully

**Challenges**: Had to install JDK first because javac wasn't recognized

**Solution**: Downloaded JDK 17 from Oracle website and set PATH variable

**Time spent**: 30 minutes

---

## Your Development Log:

### Entry 1 - [march 28, 2026, 4:00pm]
**What I did**:set up the project and explored the starter code  

**Details**: 
forked the repository from Github
set my student id in the code 
read and understood the process and schedulersimulation classes
ran the program to see how it work

**Challenges**: understanding how threads and the ready queue interact was confusing at first

**Solution**: reviewed the code step by step and traced execution flow 

**Time spent**: 45 minutes

---

### Entry 2 - [march 29, 2026, 6:30pm]
**What I did**: implement feature 1 (process priority)

**Details**: 
added priority filed to process class
genetated random priority (1-5)
display priority when process enters ready queue

**Challenges**: was unsure where exactly to display the priority

**Solution**: modified the addprocessToQueue method to print priority with process name 

**Time spent**: 1 hour

---

### Entry 3 - [march 30, 2026, 5:00pm]
**What I did**: implement feature 2

**Details**: added static variable for context switches
incremented it inside the scheduler loop
display total at the end of simulation

**Challenges**: did not know the correct place to increment the counter

**Solution**: placed it right after polling the next process from the queue

**Time spent**: 40 minutes

---

### Entry 4 - [march 31, 2026, 3:00pm]
**What I did**: implement feature 3

**Details**: added creation time, waiting time , and last ready time fileds
calculated waiting time using System.currentTimeMillis()
update waiting time before execution

**Challenges**: calculating eaiting time correctly without errors

**Solution**: tracked last ready time and updated it whenever process re-enters queue

**Time spent**: 1 hour

---

### Entry 5 - [april 1, 2026, 8:00pm]
**What I did**: tested and finalized the program 

**Details**: 
ran the simulation multiple times
verified all features are working correctly 
checked output formating and readability

**Challenges**: making sure all features work together without breaking anything

**Solution**: tested step by step after each modification 

**Time spent**: 50 minutes

---

### Entry 6 - [Optional - Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

---

## Summary

**Total time spent on assignment**: [X hours]

**Most challenging part**: 

**Most interesting learning**: 

**What I would do differently next time**: 
