# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

[Write your answer here. Consider: What is a process? What is a thread? How do they differ in terms of memory, resources, creation overhead? Why are threads more suitable for this simulation?]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:** In Round-Robin scheduling, when a process does not finish within its time quantum, it is removed from the CPU and placed back into the ready queue. This allows other processes to get a chance to execute.


[Write your answer here. Describe the specific behavior - where does the process go? When does it run again? Give an example from your actual program output showing a process that was re-queued.]

Example from my output:
```
[For example, in my program output, a process like P3 executes for one quantum and then is re-added to the queue:
P3 executing quantum [3000ms]
P3 yields CPU for context switch
.Paste a relevant snippet from your program output here showing a process being re-queued]
```

**Explanation of example:**
[Explain what's happening in the output snippet you pasted] After that, it appears again later in the ready queue and continues execution. This re-queuing behavior ensures fairness because no single process can use the CPU for too long. Each process gets equal opportunity to run in turns.

This mechanism is important because it prevents starvation and ensures all processes progress over time

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**A thread goes through several states during its lifecycle. For example, process P1 in my simulation follows these steps:

[Write your answer here. For each state, explain when P1 enters that state during the simulation. Use your understanding of the code to trace through the lifecycle.]

Runnable: When thread.start() is called, the thread becomes ready to run.
	•	Running: When the scheduler selects the thread and it starts executing the run() method.
	•	Waiting: During execution, the thread calls Thread.sleep() to simulate processing time, which puts it temporarily in a waiting state.
	•	Terminated: After the process finishes execution and its remaining time becomes zero, the thread ends.

  Also, the main thread uses thread.join() to wait until the current thread finishes before moving to the next process. This ensures proper scheduling order.

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: web server 

**Description**: 
A web server handles multiple client requests at the same time. Each user request (like opening a webpage) is processed using a separate thread. The server must respond to many users quickly and efficiently without delays.

**Why Round-Robin works well here**: 
Round-Robin scheduling gives each request a fixed time quantum, ensuring that all users are served fairly. No single request can monopolize the CPU, which keeps the server responsive and improves overall performance.

### Example 2: operating system 

**Description**: 
A multitasking operating system runs multiple applications simultaneously, such as browsers, music players, and background processes. Each application needs CPU time to execute its tasks.

**Why Round-Robin works well here**: 
Round-Robin allows each application to run for a short time slice before switching to another. This ensures fairness and prevents any single program from taking over the CPU. It also makes the system appear smooth and responsive to the user.
---

## Summary

**Key concepts I understood through these questions:**
1. 
2. 
3. 

**Concepts I need to study more:**
1. 
2. 
