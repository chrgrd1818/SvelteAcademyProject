flowchart TD
    %% Detailed Quiz & Progress Tracking Flow
    A[Student Opens Lesson] --> B
    
    subgraph B [Lesson Components]
        direction LR
        B1["📄 Document Reading<br/>(Scroll Tracking)<br/>- Estimated: 10 min"]
        B2["✅ Mark Complete<br/>(Manual Toggle)"]
        B3["🧠 Take Quiz<br/>(Practice or Graded)"]
        
        B1 --> B2 --> B3
    end
    
    B --> C{Quiz Type}
    
    C -->|Practice| D["Practice Quiz<br/>- Unlimited Attempts<br/>- Instant Feedback<br/>- No Grade Impact"]
    C -->|Graded| E["Graded Quiz<br/>- 2 Attempts Max<br/>- Score Recorded<br/>- Passing: 80%"]
    
    D --> F
    E --> F
    
    subgraph F [Quiz Attempt Flow]
        F1["Question 1 of 5<br/>- Multiple Choice<br/>- Flag for Review"]
        F1 --> F2["Submit Answer<br/>(Auto-save)"]
        F2 --> F3["Next Question<br/>(or Previous)"]
        F3 --> F4["Review Before Submit<br/>(Flagged Questions)"]
        F4 --> F5["Final Submission"]
    end
    
    F5 --> G
    
    subgraph G [Results & Analysis]
        direction LR
        G1["📊 Score: 85% PASS<br/>Correct: 17/20<br/>Time: 14:32"]
        G2["📈 Performance Breakdown<br/>By Topic/Module"]
        G3["🔍 Review Answers<br/>Correct/Incorrect<br/>Explanations"]
        
        G1 --> G2 --> G3
    end
    
    G --> H{Achieve Passing Score?}
    
    H -->|Yes| I
    H -->|No| J
    
    subgraph I [Success Path]
        I1["🎉 Lesson Complete!<br/>Badge: Quick Learner"]
        I2["📈 Update Progress<br/>- Lesson: ✓<br/>- Module: 3/5 Complete<br/>- Course: +5%"]
        I3["🔓 Unlock Next<br/>Lesson 2.4 Available"]
        I4["🏆 Check Achievements<br/>- Module 2 Complete?<br/>- Streak Bonus?<br/>- Course Milestone?"]
        
        I1 --> I2 --> I3 --> I4
    end
    
    subgraph J [Retry/Review Path]
        J1["📉 Score: 65% FAIL<br/>Attempts: 1/2 Used"]
        J2["📚 Review Materials<br/>- Weak Areas Highlighted<br/>- Suggested Reading"]
        J3["🔄 Retry Available?<br/>Yes → Retry Quiz<br/>No → Study & Contact"]
        
        J1 --> J2 --> J3
    end
    
    I4 --> K["Course Progress Dashboard<br/><br/>Course: Web Development 101<br/>══════════════════════════<br/>Overall: ███████░░░░ 70%<br/>────────────────────<br/>Module 1: ██████████ 100% ✓<br/>Module 2: ████████░░ 80%<br/>Module 3: ████░░░░░░ 40%<br/>Module 4: ░░░░░░░░░░ 0% 🔒"]
    
    J3 -->|Retry| F
    J3 -->|No Retry| L["Contact Instructor<br/>or Study Resources"]
    
    K --> M["Achievement Showcase<br/><br/>🏆 Module Master (3)<br/>⭐ Perfect Score (5)<br/>🔥 7-Day Streak<br/>🚀 Quick Learner (10)"]
    
    L --> N["Return to Course<br/>Syllabus"]
    
    M --> O{Continue Learning?}
    O -->|Yes| P["Next Lesson<br/>or Select from Syllabus"]
    O -->|No| Q["Exit to Dashboard<br/>(Progress Saved)"]
    
    %% Styling
    classDef lesson fill:#bbdefb,stroke:#1976d2
    classDef quiz fill:#c8e6c9,stroke:#388e3c
    classDef results fill:#fff3e0,stroke:#f57c00
    classDef success fill:#e8f5e8,stroke:#2e7d32
    classDef failure fill:#ffebee,stroke:#c62828
    classDef progress fill:#f3e5f5,stroke:#7b1fa2
    
    class B lesson
    class D,E,F quiz
    class G results
    class I success
    class J failure
    class K,M progress
