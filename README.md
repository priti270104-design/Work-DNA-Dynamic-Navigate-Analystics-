# Work-DNA-Dynamic-Navigate-Analystics-
# WorkDNA 🧬

**WorkDNA** is a supportive work pattern awareness assistant designed to help you maintain a sustainable relationship with your work. Unlike traditional productivity tools that focus on "doing more," WorkDNA helps you understand your mental effort and prevents burnout through AI-powered insights and real-time monitoring.

---

## 🌟 Core Philosophy
> "Work sustainable, not just hard."

WorkDNA moves beyond simple task tracking. It calculates a dynamic **Burnout Score** based on task duration and mental effort, providing a gentle "check-in" when your workload becomes unsustainable.

---

## 🚀 Key Features

-   **Intelligent Task Tracking**: Log tasks with duration, deadlines, and a subjective **Effort Score** (1-5).
-   **Burnout Analysis (The "DNA" Logic)**: A custom algorithm that analyzes your daily workload and mental strain to categorize your burnout risk (Low, Medium, High).
-   **AI Work Insights**: Powered by **Google Gemini**, providing personalized, warm, and supportive suggestions based on your actual work patterns.
-   **Automated Alerts**: Integration with **AWS SNS** to send email notifications when your burnout score enters the "High" zone.
-   **Event-Driven Architecture**: Uses **AWS EventBridge** to trigger serverless cloud functions (**Lambda**) for every task action.
-   **Secure Authentication**: Full user lifecycle management (Signup, Login, Sessions) powered by **AWS Cognito**.
-   **Dark Mode**: A sleek, premium UI that adapts to your environment.

---

## 🛠️ Tech Stack

### Frontend
-   **Languages**: HTML5, Vanilla CSS3, JavaScript (ES6+).
-   **Design**: Custom design system with glassmorphism, dynamic animations, and responsive layouts.
-   **State**: LocalStorage for session management and persistence.

### Backend
-   **Runtime**: Node.js with Express.
-   **AI**: Google Generative AI (Gemini 2.0 Flash).
-   **API**: RESTful architecture with JWT token verification.

### Infrastructure (AWS)
-   **Database**: Amazon DynamoDB (NoSQL) for high-performance task storage.
-   **Identity**: Amazon Cognito for secure user authentication.
-   **Events**: Amazon EventBridge for cross-service communication.
-   **Compute**: AWS Lambda for serverless background processing.
-   **Messaging**: Amazon SNS for real-time burnout alerts.
-   **Observing**: Amazon CloudWatch for observing the notifications and triggers.

---

## 🏗️ Workflows & Architecture

WorkDNA uses a modern, event-driven serverless architecture:

1.  **Frontend** interacts with the **Express API**.
2.  **API** saves tasks to **DynamoDB** and emits events to **EventBridge**.
3.  **EventBridge** rules trigger **Lambda** functions for secondary processing (Logging, Analytics).
4.  If the **Burnout Algorithm** detects high risk, the API publishes a message to **SNS**, which emails the user immediately, **CloudWatch** will observe the notifications and triggers. 
5.  **Gemini AI** is called on-demand to provide deep-pattern analysis of task history.

---

## ⚙️ Installation & Setup

### Prerequisites
-   **Node.js**: v18 or higher.
-   **AWS Account**: IAM user with permissions for DynamoDB, Cognito, EventBridge, and SNS.
-   **Gemini API Key**: Obtainable from [Google AI Studio](https://aistudio.google.com/).

### Steps

1.  **Clone the Repository**:
    ```bash
    git clone https://github.com/your-username/workdna-v4.git
    cd workdna-v4
    ```

2.  **Install Dependencies**:
    ```bash
    npm install
    ```

3.  **Configure Environment Variables**:
    Create a `.env` file in the root directory:
    ```env
    PORT=3000
    GEMINI_API_KEY=your_gemini_key
    AWS_REGION=us-east-1
    AWS_ACCESS_KEY_ID=your_key
    AWS_SECRET_ACCESS_KEY=your_secret
    DYNAMODB_TABLE_NAME=WorkDNATasks
    COGNITO_USER_POOL_ID=your_pool_id
    COGNITO_CLIENT_ID=your_client_id
    SNS_TOPIC_ARN=your_sns_arn
    ```

4.  **Run Locally**:
    ```bash
    npm start
    ```
    Access the app at `http://localhost:3000`.

---

## 📖 Related Documentation
-   [AWS Setup Guide](file:///d:/Project/WorkDNA_v4/AWS_SETUP.md) - Detailed instructions for infrastructure configuration.

---

## 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
