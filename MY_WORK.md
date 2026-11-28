# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | [Abdulrhman Mohamed Ahmed Ibrahim] |
| **Student ID** | [446052690] |
| **University Email** | [446052690]@std.psau.edu.sa |
| **GitHub Username** | [Abdulrhman192006] |
| **Repository Link** | [https://github.com/Abdulrhman192006/OS-Assignment3-Abdulrhman-Mohamed] |
 
---

## 🎥 Video Link

**Video Link**: [(https://drive.google.com/drive/folders/1capynm9jovkKAy5pJi0BdeqE0wlbQc1S?hl=ar)]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [November 26, 2026, 4:00 PM]
**What I did**: Understand and inspect the provided starter project and initlized a new repo

**Details**: I started by reading the project documentation and inspected the SchedulerSimulationSync.java source code. I identified the main components of the simulation and the problems, including ReadyQueue, SharedStats, Process, and CpuWorker. I focused on understanding how processes are added to the ready queue, how CPU workers execute them and then i initlized a new repo to start implementing the features.

**Challenges**: Understanding how multiple CPU worker threads interact with the ready queue and when the race conditon happens when several threads can access shared data concurrently.

**Solution**: I traced the execution flow and identified which variables and data structures were shared between threads. This helped me find out which operations required synchronization.

**Time spent**: 40 minutes

---

### Entry 2 - [November 26, 2026, 9:30 PM]
**What I did**:Protect the ready queue using ReentrantLock.

**Details**:I added a ReentrantLock to the readyQueue class to protect its shared list and map data structures. I used the lock when adding processes, removing processes, retrieving process information.I also used try finally catch blocks to guarantee that the lock is released.

**Challenges**:The main challenge was ensuring that operations involving the queue's list and map remained consistent when multiple CPU workers accessed them concurrently.

**Solution**:I protected the related operations using the same lock. This ensured that only one thread could modify or inspect the protected queue structures at a time.

**Time spent**: 1 hour

---

### Entry 3 - [November 27, 2026, :10:00 AM]
**What I did**:Protect shared statistics against race conditions.

**Details**:I added a reentrantLock to the SharedStats class. I used it to protect updates and reads of contextSwitchCount, completedProcessCount, and totalServiceTime. I modified the increment, addition, and getter methods acquire the lock and release it in a finally block.

**Challenges**:Multiple process and CPU threads can update the statistics concurrently. Without synchronization, two threads could read and modify the same value at the same time, causing lost updates or inconsistent results.

**Solution**:I placed each shared statistics operation inside a critical section protected by statsLock. This makes each individual operation made by a thread mutually exclusive and ensures that updates are not lost.

**Time spent**: 1 hour

---

### Entry 4 - [November 27, 2026, :2:00 PM]
**What I did**:Use a counting semaphore to coordinate CPU workers and the ready queue.

**Details**:I initilized a counting semaphore named available in the ReadyQueue class. Its initial permit count is zero. Whenever a process is added to the queue, the producer releases a permit. CPU workers call acquire() method through the take() method before attempting to retrieve a process.

**Challenges**:CPU workers should not continuously check whether the queue contains a process because repeated checking wastes CPU time when the queue is empty.

**Solution**:I used Semaphore.acquire() to make a worker wait when no process is available. Adding a process releases a permit and allows a waiting worker to continue. I also added a wake up mechanism for CPU workers when all processes have completed.

**Time spent**: 2 hours

---

### Entry 5 - [November 27, 2026, :8:00 PM]
**What I did**:Test the synchronized scheduler and verify the shared values.

**Details**:I compiled and executed the updated Java program. I examined the verification output, process summary, and shared statistics. I checked that the synchronization changes did not prevent processes from being executed and that the simulation could finish without any error or WatchDog.

**Challenges**:Verifying a concurrent program requires checking more than whether it runs successfully. The shared counters and process completion results must also remain consistent.

**Solution**:I used the verification section provided by the starter project where i have added it in the starteroutput.txt to compare expected and observed values. I also checked the busy waiting poll count and the process summary.

**Time spent**:30 mintues

---

### Entry 6 - [Optional - Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: 5 hours

**Most challenging part**:The most challenging part was coordinating multiple CPU worker threads while keeping the ready queue and shared statistics consistent. I had to understand how race conditions could occur and how to protect shared data using locks. Implementing the semaphore based waiting mechanism was also challenging because CPU workers needed to wait efficiently and wake up correctly.

**Most interesting learning**:The most interesting thing I learned was how synchronization concepts work in a real multithreaded application. I learned how ReentrantLock provides mutual exclusion and how a counting semaphore coordinates threads without busy waiting.

**What I would do differently next time**:Next time I would spend more time analyzing the starter code and planning the synchronization strategy before implementing the changes. I would also test the program after each feature instead of waiting until the end.

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer: This assignment helped me understand why synchronization is necessary in multithreaded programs. I learned that sharing data between threads can cause race conditions when multiple threads access or modify the same resource concurrently. I also learned how a reentrantLock can protect a critical section and provide mutual exclusion. Another important concept I learned was the difference between busy waiting and blocking synchronization. Using a semaphore allows a thread to wait until a resource becomes available instead of continuously checking its availability.

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:  The most challenging part was understanding how the CPU workers interact with the ready queue while processes are being added, removed and executed concurrently. The queue contains two related data structures: a list and a map, so protecting only one of them would not be sufficient. I needed to make sure that operations on these structures remained consistent. Another challenge was coordinating workers when the queue became empty and when all processes had finished. I addressed these problems by using a lock for the queue operations and a semaphore for process availability.

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:**I overcame the challenges by breaking the implementation into smaller steps instead of changing everything at once. I reviewed the assignment instructions and documentation to understand how locks and semaphores should work. After each change, I compiled and ran the program to check for errors and verify the results. I also checked the verification output and process summary to identify synchronization problems. This approach helped me understand the implementation and fix issues without any unnecessary changes happens.

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** Synchronization is important in applications where multiple threads access shared resources at the same time. For example, a banking application must protect account balances during deposits and withdrawals to prevent lost updates. Ticket booking systems use synchronization to prevent two customers from booking the same seat. Print servers use queues and synchronization to organize print requests from multiple users. Databases also use locks and other concurrency control mechanisms to maintain data consistency when multiple transactions access the same records.

### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

In the original starter, multiple CPUs selected the same process, and CPU-2 and CPU-3 threw an `IllegalThreadStateException` when they attempted to start the same thread again. The simulation eventually triggered the watchdog because processes were lost and the shared statistics were not updated correctly. This happened because the ready queue and shared data were accessed concurrently without proper synchronization.

Verification block of the **original starter**:
```
Exception in thread "CPU-2" java.lang.IllegalThreadStateException
    at java.base/java.lang.Thread.start(Thread.java:1389)
    at CpuWorker.run(SchedulerSimulationSync.java:283)

Exception in thread "CPU-3" java.lang.IllegalThreadStateException
    at java.base/java.lang.Thread.start(Thread.java:1389)
    at CpuWorker.run(SchedulerSimulationSync.java:283)

WATCHDOG: the simulation did not finish (23 s).
A process was lost, or a CPU is blocked forever,
or the 'completed' counter lost an update.

Context switches: expected ?? observed ?? MISMATCH
Completed processes: expected ?? observed ?? MISMATCH
Total service time: expected ????? observed ????? MISMATCH
Busy-waiting polls: expected ? observed ??? MISMATCH
```

Verification block of **my final version**:
```
═══ VERIFICATION (expected values are computed from YOUR seed) ═══
Context switches (quanta executed) expected 28 observed 28 ✔
Completed processes expected 15 observed 15 ✔
Total service time (ms) expected 43926 observed 43926 ✔
Busy-waiting polls (must be 0) expected 0 observed 0 ✔
✔ All shared values are consistent.
```

**Explanation of the timeline:**
CPU-1, CPU-2, and CPU-3 accessed the ready queue concurrently.Because queue access was not properly protected,all three CPUs selected P1 instead of selecting three different processes. CPU-1 successfully started P1, but CPU-2 and CPU-3 attempted to start the same Java Thread again, resulting in `IllegalThreadStateException`.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

I used one seentrantLock called statsLock to protect the three shared statistics: contextSwitchCount, completedProcessCount, and totalServiceTime, including their update and getter methods. I chose one lock because it makes synchronization simpler and easier to maintain, although it can cause unnecessary blocking when different statistics are updated independently. The ReadyQueue uses a separate ReentrantLock to protect its linked list and map because they are independent shared resources.
    
| Critical section (variable / method) | Lock used | Why it needs protection |
ReadyQueue.add()	ReadyQueue.lock  	Protects adding a thread to the list and its process to the map.
ReadyQueue.poll()	ReadyQueue.lock	  Prevents multiple CPUs from removing or accessing the same queue entry simultaneously.
ReadyQueue.processOf() ReadyQueue.lock	Protects access to the shared process map.
ReadyQueue.snapshot()	ReadyQueue.lock	Prevents reading the queue while another thread modifies it.
contextSwitchCount and its update getter methods	statsLock	Prevents lost updates and inconsistent reads.
completedProcessCount and its update getter methods	statsLock	Ensures completed process updates are synchronized.
totalServiceTime and its update getter methods	statsLock	Prevents concurrent updates from overwriting each other

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

In the original starter, CPUs repeatedly checked the ready queue when it was empty which is called busy waiting and wastes CPU time. The original run triggered the watchdog after 23 seconds and the busy waiting polls value was displayed as unreadable question marks in the terminal output so I cannot report its exact number. In my final implementation, the `available` semaphore represents the number of available processes and starts at zero because the ready queue is initially empty. After the 15 initial `add()` calls, its value is 15 assuming no CPU has acquired a permit yet. The last CPU calls `wakeAllCPUs()`, which releases `totalCPUs` permits to wake blocked CPUs so they can check the completion condition and terminate.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
The classical synchronization problem is the Producer-Consumer problem, also known as the Bounded-Buffer problem. The main program acts as a producer when it initially adds processes to the ready queue, while the CPU workers act as consumers when they retrieve processes. However, CPU workers can also act as producers when they re enqueue processes that are not finished.

**Semaphores for a bounded queue (name and initial value)**:
For a bounded queue with capacity K, three semaphores are required: `empty`and initially K to count available empty slots. `full` and initially 0 to count occupied slots. And `mutex` initially 1 to provide mutual exclusion when accessing the buffer.

**Deadlock scenario and prevention**:
A deadlock can occur if a producer acquires the mutex before waiting for an empty slot while the queue is full. The producer keeps holding the mutex while waiting but the consumer cannot acquire the mutex to remove an item and create an empty slot. This situation creates hold-and-wait and circular-wait conditions. To prevent it, the producer should wait on `empty` before acquiring `mutex` and the consumer should wait on `full` before acquiring `mutex` breaking the hold and wait condition.
## Summary

**Key concepts I understood through these questions:**
1.Race conditions occur when multiple threads access and modify shared data without proper synchronization.
2.Locks and critical sections provide mutual exclusion and protect shared resources from concurrent modifications.
3.Semaphores coordinate threads and allow them to block instead of wasting CPU time through busy waiting.

**Concepts I need to study more:**
1. Deadlock conditions, prevention, and avoidance techniques.
2. Lock fairness, bounded waiting, and advanced concurrency mechanisms.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
