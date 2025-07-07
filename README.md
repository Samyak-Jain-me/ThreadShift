# CPU Scheduling Algorithms

An implementation of various CPU scheduling algorithms in C++. The algorithms include:

- First Come First Serve (FCFS)
- Round Robin (RR)
- Shortest Process Next (SPN)
- Shortest Remaining Time (SRT)
- Highest Response Ratio Next (HRRN)
- Feedback (FB)
- Feedback with varying time quantum (FBV)
- Aging

---

## 📸 Preview

<div style="display: flex; justify-content: center; flex-wrap: wrap; gap: 20px;">
  <img src="https://github.com/Samyak-Jain-me/ThreadShift/blob/main/Gantt%20Chart%20Image.png" width="400" alt="Overview Screenshot"/>
  <img src="https://github.com/Samyak-Jain-me/ThreadShift/blob/main/Gantt%20Chart%20Result%20Image.png" width="400" alt="FCFS Example"/>
  <img src="https://github.com/Samyak-Jain-me/ThreadShift/blob/main/Round%20Robin%20Simulator%20Image.png" width="400" alt="Round Robin Example"/>
  <img src="https://github.com/Samyak-Jain-me/ThreadShift/blob/main/Simulator%20Image.png" width="400" alt="Algorithm Comparison"/>
</div>




---

## 📑 Table of Contents

- [Algorithms](#algorithms)
  - [First Come First Serve (FCFS)](#first-come-first-serve-fcfs)
  - [Round Robin (RR)](#round-robin-with-varying-time-quantum-rr)
  - [Shortest Process Next (SPN)](#shortest-process-next-spn)
  - [Shortest Remaining Time (SRT)](#shortest-remaining-time-srt)
  - [Highest Response Ratio Next (HRRN)](#highest-response-ratio-next-hrrn)
  - [Feedback (FB)](#feedback-fb)
  - [Feedback with varying time quantum (FBV)](#feedback-with-varying-time-quantum-fbv)
  - [Aging](#aging)
- [Installation](#installation)
- [Input Format](#input-format)
- [Contributors](#contributors)

---

## 🧠 Algorithms

### ->First Come First Serve (FCFS)

Non-preemptive algorithm where the process that arrives first gets executed first. Simple but may cause performance issues if long processes come early.

### ->Round Robin with varying time quantum (RR)

Preemptive algorithm using time slices (quantum). With varying quantum, it can better balance CPU time across short and long processes.

### ->Shortest Process Next (SPN)

Non-preemptive algorithm where the process with the shortest burst time is selected next. Reduces average waiting time but can starve longer tasks.

### ->Shortest Remaining Time (SRT)

Preemptive version of SPN. A running process can be interrupted if a shorter one arrives. Useful when burst time is unknown in advance.

### ->Highest Response Ratio Next (HRRN)

Non-preemptive. Chooses the process with the highest response ratio, calculated as:
```
Response Ratio = (Waiting Time + Burst Time) / Burst Time
```
Favors long-waiting processes, reducing starvation.

### ->Feedback (FB)

Multi-level preemptive algorithm using priority queues. A process can be demoted to a lower-priority queue after execution.

### ->Feedback with varying time quantum (FBV)

Same as FB, but each queue uses a different time quantum, allowing for more fine-tuned control.

### ->Aging

Addresses starvation in priority-based systems by gradually increasing the priority of waiting processes. Ensures that all processes eventually get CPU time.

---

## ⚙️ Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/CPU-Scheduling-Algorithms.git
cd CPU-Scheduling-Algorithms

# Install compiler tools
sudo apt-get install g++ make

# Build the project
make

# Run the executable
./cpu_scheduling
```

---

## 📥 Input Format

1. **Line 1:** `"trace"` or `"stats"`
2. **Line 2:** List of scheduling policies with optional parameters (e.g., `2-4` for RR with q=4)
3. **Line 3:** Integer `T` – last instant of the simulation
4. **Line 4:** Number of processes `N`
5. **Next N Lines:** Process description

### Format per Algorithm:

- **For Algorithms 1–7:**
  ```
  Name, ArrivalTime, ServiceTime
  ```
- **For Algorithm 8 (Aging):**
  ```
  Name, ArrivalTime, Priority
  ```

👉 Processes are sorted by arrival time. In case of a tie, the one with the lower priority arrives first.

📎 Check the [testcases](https://github.com/yousefkotp/CPU-Scheduling-Algorithms/tree/main/testcases) folder for sample inputs.

---

## 👥 Contributors

<!-- Add your names or GitHub handles here -->
- [@Samyak-Jain-me](https://github.com/Samyak-Jain-me)
