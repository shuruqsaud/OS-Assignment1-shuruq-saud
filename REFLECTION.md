# Reflection Questions

## Instructions
Answer the following questions about your learning experience. Each answer should be **at least 5-7 sentences** and show your understanding.

---

## Question 1: What did you learn about multithreading?

**Your Answer:** From this assignment, I learned how multithreading allows multiple tasks to run concurrently within the same program. I understood how threads are created using the Runnable interface and executed using Thread.start(). I also learned how threads share resources and how this improves performance compared to using separate processes. Additionally, I learned about thread coordination using methods like Thread.join() to control execution order. This assignment helped me understand how scheduling works in real systems, especially using Round-Robin. Overall, I gained practical experience in managing threads and observing their behavior during execution.

[Write your answer here. Discuss specific concepts like thread creation, thread states, how threads execute concurrently, what surprised you, etc.]

---

## Question 2: What was the most challenging part of this assignment?

**Your Answer:** The most challenging part of this assignment was implementing the waiting time feature correctly. It was difficult to track exactly how long each process stays in the ready queue without making mistakes. Since processes keep leaving and re-entering the queue, calculating the correct waiting time required careful thinking. I also found it confusing to decide where to update the waiting time in the code. Another challenge was understanding how threads execute step by step in the scheduler. This made debugging slightly harder because timing plays a big role. Overall, the complexity of tracking time and thread behavior made this part the hardest.

[Describe the specific challenge. Was it understanding the code? Implementing a feature? Using Git? Explain what made it difficult and how it relates to the course concepts.]

---

## Question 3: How did you overcome the challenges you faced?

**Your Answer:** I overcame these challenges by breaking the problem into smaller steps and testing each part separately. For the waiting time, I used System.currentTimeMillis() and carefully tracked when each process entered and left the queue. I also added helper methods like updateWaitingTime() to make the logic clearer. When I faced confusion, I reviewed the lecture materials and reread the code multiple times. Running the program frequently helped me verify if my changes were working correctly. I also used print statements to debug and understand the flow of execution. With practice and testing, I was able to fix the issues and complete the feature successfully.

[Describe your problem-solving approach. Did you read documentation? Ask for help? Debug systematically? What resources did you use? What strategies worked?]

---

## Question 4: How can you apply multithreading concepts in real-world applications?

**Your Answer:** Multithreading is widely used in many real-world applications to improve performance and responsiveness. For example, web servers use threads to handle multiple client requests at the same time without delay. Another example is in mobile applications, where threads are used to keep the user interface responsive while performing background tasks like downloading data. In gaming, threads are used to manage different components such as graphics rendering, physics calculations, and user input simultaneously. Operating systems also rely heavily on multithreading to manage multiple running programs efficiently. The concepts from this assignment, such as scheduling and time sharing, are directly used in these systems.

[Give specific examples from real applications you use (web browsers, games, mobile apps, etc.). Explain why threads are useful in those scenarios. Connect to what you learned in this assignment.]

---

## Additional Reflections (Optional)

### What would you like to learn more about?

[Any topics related to threading, concurrency, or operating systems that you're curious about?]

---

### How confident do you feel about multithreading concepts now?

[Rate yourself and explain: Beginner / Intermediate / Confident]

[Explain your rating - what do you understand well? What needs more practice?]

---

### Feedback on the assignment

[Any comments about the assignment? Was it helpful? Too easy/hard? Suggestions for improvement?]
