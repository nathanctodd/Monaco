# Optimal Racing Line on the Monaco Grand Prix Circuit 🏎️

This project models the **optimal racing line** around the iconic **Monaco F1 circuit**, using mathematical tools such as **Pontryagin’s Maximum Principle** and a **data assimilation-based control method**. Our objective: **minimize lap time** by computing the fastest trajectory through the track's tight and complex turns.

##  Overview

Formula 1 drivers are constantly seeking marginal gains — and the racing line plays a critical role. Using tools from the **calculus of variations**, we simulate and optimize a racing line that balances speed and control.

We explored three approaches:

- **Pontryagin's Maximum Principle (PMP)** applied to the full circuit
- **PMP on discretized intervals**
- A **Data Assimilation-inspired method** using a Stanley Controller to nudge the solver toward better solutions

## 📈 Methodology

### ❌ Initial PMP Attempt
A direct application of PMP led to instability issues due to the complex geometry of Monaco. Even simplified oval tracks failed to yield reliable results.

### 📉 Cost Function Creation
We extracted **GPS centerline data** from the Monaco track and interpolated it using `scipy` to generate a continuous curve. This served as the baseline for all optimization.

### ✅ Data Assimilation Approach
To overcome numerical instability, we adopted a **nudging strategy**:  
A **Stanley Controller** compares the current trajectory to a lookahead target, and adjusts the path iteratively using `solve_ivp` from SciPy. This approach yielded strong results.

📹 Check out a **demo of the data assimilation method** below:


https://github.com/user-attachments/assets/0565c737-eeda-4757-83ee-12f33c1b3983



## 🛠 Tech Stack

- Python (`scipy`, `numpy`, `matplotlib`)
- `solve_ivp` for solving ODEs
- Custom implementation of control strategies
- Interpolation of real GPS data

## 🚀 Next Steps

We're working on combining the **Data Assimilation method** with **PMP**, aiming for a **hybrid controller**. This would allow customizable optimization goals — like minimizing time, fuel use, or tire degradation.

---

### 🤝 Contributors

- Nathan Todd
- Trevor Larsen
- Cole Edgren
- Brandon Waits

---

Feel free to fork, clone, or open issues if you're interested in racing strategy, control systems, or applied math in motorsports!
