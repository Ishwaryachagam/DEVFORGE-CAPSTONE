# DevForge – Intelligent Software Development Assistant

> **Complete Capstone Project**: Automated Code Generation, Real Code Execution, Debugging, Optimization, Testing, and Technical Documentation.

DevForge is a full-stack localhost web application designed for automated software engineering workflows across five major programming languages: **C, C++, Python, Java, and JavaScript**.

---

## 🎨 Visual Design & Architecture

DevForge features a dark developer theme matching professional development tools:
- **Background**: Deep Navy / Black (`#0B0E17`, `#0D111D`)
- **Accents**: Neon Cyan (`#06B6D4`) and Royal Purple (`#7928CA`) gradients
- **Components**: Glowing borders, rounded cards, developer code panels, live terminal output, collapsible sidebar, top workflow bar, and persistent dashboard cards.

---

## 🚀 Key Modules & Capabilities

1. **Module 1 – Requirement Analysis & Prompt Processing**:
   - Takes natural-language requirements (e.g., *"Create a program to calculate the average of five student marks."* or *"Create a program to find the largest of three numbers."*).
   - Target language selector: **C, C++, Python, Java, JavaScript**.
   - Outputs: **Requirement Summary, Task, Inputs, Expected Output, Functional Requirements, Constraints, and Selected Language**.
   - One-click transition to Code Generation.

2. **Module 2 – Automated Code Generation**:
   - Compiles requirements into production-ready code in the selected language.
   - Code panel with: Line numbers, syntax highlighting, filename tab, Copy, Download, Regenerate, and "Run in Execution Workbench".
   - Shows: **Explanation, Algorithm, Sample Input, and Sample Output**.

3. **Module 3 – Debugging & Code Optimization**:
   - **Debugging**: Diagnoses faults, outputting: **Issue Detected, Cause, Explanation, Suggested Fix, and Corrected Code**.
   - **Optimization**: Compares original vs optimized code, showing **Complexity Before vs After** and detailed **Improvements Made**.

4. **Module 4 – Real Code Execution**:
   - Executes code using safe local compilers and interpreters:
     - **Python**: Real execution via `python`
     - **JavaScript**: Real execution via `node`
     - **C**: Real compilation & execution via MinGW `gcc`
     - **C++**: Real compilation & execution via MinGW `g++`
     - **Java**: Real environment detection; clearly reports if JDK (`javac`) is required.
   - Real terminal output panel with stdout, stderr, exit code, and execution time in ms.

5. **Module 5 – Automated Testing**:
   - Generates structured test cases: **Normal Cases, Boundary Cases, and Invalid Input Cases**.
   - **Real Execution**: Runs test cases locally, asserting outputs and showing actual **PASS / FAIL** badges and runtime.

6. **Module 6 – Documentation & README Builder**:
   - Compiles **Program Overview, Features, Requirements, Algorithm, Code Explanation, Inputs/Outputs, Usage Instructions, Examples, and full Markdown README.md**.
   - One-click Copy and Download `README.md`.

7. **Dashboard Statistics & Activity History**:
   - Real-time counters: **Requirements, Programs Generated, Executions, Success Rate, Time Saved**.
   - Real timestamped activity feed.
   - Floating expandable `assistant.sh` terminal drawer in bottom right.

8. **Secure API Settings**:
   - API keys are stored on the backend server and never leaked to client-side code.
   - Works 100% out of the box with the built-in intelligent multi-language engine even before an API key is provided.

---

## 💻 How to Run on Localhost

### Prerequisites
- **Node.js** (v18 or newer installed)
- Optional: Python 3.x, MinGW GCC/G++, JDK for executing code in those respective languages.

### Quick Start (Single Command)

In your terminal, navigate to the project directory:
```bash
cd C:\Users\Akhila\.gemini\antigravity\scratch\intelligent-dev-assistant
```

Start both the backend server and frontend development server simultaneously:
```bash
npm start
```

Open your browser and navigate to:
```
http://localhost:5173
```

- **Frontend**: `http://localhost:5173` (Vite + React)
- **Backend**: `http://localhost:5000` (Node.js Express API)
- **Login Credentials**: Default user `chandu` / `varshini@gmail.com` (password: `password123`).

---

## 📁 Project Structure

```text
intelligent-dev-assistant/
├── server/
│   ├── server.js          # Express server with compiler runners & LLM endpoints
│   ├── smartEngine.js     # Context-aware 5-language code intelligence engine
│   └── temp/              # Isolated temporary execution sandbox
├── src/
│   ├── components/
│   │   ├── LandingPage.jsx         # Landing page (Screenshot 1)
│   │   ├── Auth.jsx                # Split-screen Sign In / Register (Screenshot 2)
│   │   ├── Overview.jsx            # 8-stage workflow & metrics (Screenshot 3)
│   │   ├── Sidebar.jsx             # Left developer sidebar
│   │   ├── Header.jsx              # Workspace header & status pill
│   │   ├── RequirementAnalysis.jsx # Module 1: Requirement Analysis
│   │   ├── CodeGenerator.jsx       # Module 2: Code Generation
│   │   ├── CodeExecution.jsx       # Module 4: Real Local Execution
│   │   ├── Debugger.jsx            # Module 3: Diagnostics & Fixes
│   │   ├── Optimization.jsx        # Module 3: Code Refactoring
│   │   ├── Testing.jsx             # Module 5: Test Case Suite & Runner
│   │   ├── Documenter.jsx          # Module 6: Documentation & README
│   │   ├── Settings.jsx            # API & Compiler diagnostics
│   │   └── Profile.jsx             # Developer profile for chandu
│   ├── utils/
│   │   └── api.js                  # Frontend API client
│   ├── App.jsx                     # Root router & workflow controller
│   └── index.css                   # Custom dark SaaS theme stylesheet
├── start.cjs                       # One-command dual-server launcher
├── package.json
└── vite.config.js                  # Vite bundler with /api proxy to port 5000
```
