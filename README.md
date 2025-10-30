# study-timer-app3
집중력 향상 타이머 앱 프로젝트
```mermaid
graph TD
    subgraph User_Interaction_Console_IO
        A[시작·종료·중단 입력]
        B[과목 선택·중단 사유 입력]
    end

    subgraph Data_Management
        C[struct StudySession - 학습 세션 정보]
        D[struct Interruption - 중단 사유 정보]
        E[struct UserProfile - 사용자 프로필·보상]
        F[struct RewardItem - 어항 아이템 정보]
        G[파일 I/O - DB 대체]
    end

    subgraph Core_Logic
        H[집중력 지수 계산]
        I[최적 집중·휴식 추천]
        J[보상 포인트 계산]
    end

    subgraph Output_and_Visuals
        K[학습 리포트 출력 - 텍스트·아스키아트]
        L[어항·물고기 시각화 - 텍스트·아스키아트]
    end

    A -->|타이머 시작·종료| C
    B -->|중단 시점·사유| D
    C --> H
    D --> H
    H --> C
    C --> I
    I --> E
    C --> J
    E --> J
    J --> E
    C --> K
    E --> K
    F --> K
    E --> L
    F --> L
    C --> G
    D --> G
    E --> G
    F --> G
    G --> C
    G --> D
    G --> E
    G --> F
