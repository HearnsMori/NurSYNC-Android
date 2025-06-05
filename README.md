# NurSYNC

**Seek Your Nursing Capability**

NurSYNC is a web-based learning platform tailored for nursing students. It offers dynamic educational tools, resource libraries, and analytics dashboards designed to enhance the academic journey and practical decision-making skills of future nurses.

---

## Features

### Apache Kafka
- Streaming data through kafka enables parallel computing to the nursync chat bot

### Frontend
- **Built with:** HTML, CSS, and JavaScript
- **Responsive UI:** More responsive for desktop, also available in phone and are more responsive in landscape
- **Interactive Elements:** Flashcards, quizzes, and notes to reinforce learning

### Backend
- **Powered by:** Node.js
- **Data Streaming with Apache Kafka:** Enables parallel computing and efficient handling of real-time events
- **Secure Authentication:** Signup and login routes for account control

## Architecture
- Utilize advance computing: Cloud Computing and Parallel Computing

### App Architecture

The application is built on a **cloud-first architecture** utilizing **Gemini API** and a **MongoDB cloud database** for scalable, real-time performance.

- **Authentication** is secured via **JWT (JSON Web Token)**, allowing token-based access for protected API endpoints.
- The **API** follows a standard **CRUD structure** (Create, Read, Update, Delete), and communicates using **JSON** format for requests and responses.
- This enables seamless interaction with the database from both client-side and system agents.

---

### Main System Feature – NurSYNC Bot with Kafka Integration

A standout feature of this system is the **AI Bot's integration with Apache Kafka**, a **distributed event streaming platform** designed for high-throughput and fault-tolerant data flow.

#### Why Kafka?

Kafka is used to implement **parallel computing**, which allows the system to process multiple tasks or requests **simultaneously** rather than sequentially. This is essential when the AI generates responses based on complex logic or multi-model inference, which may take varying amounts of processing time.

---

### System Flow Overview

1. **User Input**
   - When a user interacts with the bot or requests an AI-generated response, the input is pushed into a **Kafka topic** as a message via a **Kafka producer**.
   - Each message represents a task or query to be processed.
   - Kafka is running locally on **port 9092**.

2. **Parallel Processing**
   - A **Kafka consumer**, running in the background, listens to this topic and consumes messages in real-time.
   - Kafka’s support for **partitioning** and **consumer groups** enables multiple messages (queries) to be processed in **parallel** across different threads or services.
   - This ensures that **high-volume requests** don't create bottlenecks.

3. **Message Output**
   - Each processed message (now a response) is **logged to the console**, allowing multiple prompts to be handled without delay.

---

### Additional Notes

- The full potential of Kafka is visible in the **console logs**, where for **one prompt**, there are **11 different results** shown.
- Currently, the multiple Kafka responses are **not yet utilized in the web interface**.
- This is due to implementation challenges with **WebSocket**, which is the best practice to fetch multiple server responses **seamlessly and without delay**.

---

## Core Capabilities

### Explore Our Features
- **Interactive Study Tools**
- **Progress Tracking**
- **Curriculum-Aligned Content**
- **Resource Library**

### Why Choose NurSYNC
- **Empowerment:** Build clinical decision-making confidence
- **Flexibility:** 24/7 self-paced access
- **Community Support:** Join a growing network of peers and mentors

---

## Developer

Developed and maintained by **Hearns Mori** and **Mark Lester Dula**

---

## Getting Started

### Prerequisites

- Node.js (>=14)
- Apache Kafka (Running locally or via Docker)
- npm or yarn

### Installation

```bash
git clone https://github.com/hearnsmori/nursyncv2.git
cd nursync
npm install
```

### Kafka Setup for Termux Environment (Run Locally with Minimum Effort)
- for termux user only
- if not run your kafka in port 9092, a port where our frontend comkunicates
Install required packages
```bash
pkg update && pkg upgrage
pkg install openjdk-18 python
```
Run zookeeper:
```bash
#To run the zookeeper on root dir
cd kafka
python3 zookeeper.py
```
Then run kafka:
```bash
#To run the kafka on root dir
cd kafka
python3 kafka.py
```
### .env Setup
- Create a .env file
```bash
SECRETKEY=[your secret key]
MONGO_URI=[your mongodb uri]
PORT=10000
GEMINI_API_KEY=[your gemini api key]
```
### Running the App

```bash
npm start
```

Access the app via `http://localhost:10000`

Access the 1st version of app (no parallel computing) at `https://nursync.onrender.com`

---

## License

© 2025 NurSYNC – All rights reserved.

---

## Location

Developed in the **Philippines**


