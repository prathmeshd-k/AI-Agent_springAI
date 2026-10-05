# 🤖 AI Agent using Spring Boot & Spring AI

An AI-powered multi-domain assistant built using **Spring Boot, Spring AI, OpenAI, and Thymeleaf**.

The application can understand user requests and dynamically call custom Java tools to perform tasks such as travel planning, weather lookup, hotel search, flight search, order management, and inventory checking.

---

## 🚀 Features

### ✈️ Travel Assistant

- Search flights
- Search hotels
- Check weather forecasts
- Plan trips based on budget
- Combine information from multiple tools

### 🛒 Customer Support Assistant

- Check order status
- Cancel orders
- Check product inventory
- View available products

### 🧠 AI Agent / Function Calling

The application uses **Spring AI Tool Calling** to allow the AI model to dynamically select and execute Java methods based on the user's request.


Architecture:
                    USER
                      │
                      ▼
              ┌───────────────┐
              │   Thymeleaf   │
              │      UI       │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ ChatController│
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │  ChatService  │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │   ChatClient  │
              │  Spring AI    │
              └───────┬───────┘
                      │
                      ▼
                ┌───────────┐
                │ OpenAI API│
                └─────┬─────┘
                      │
             ┌────────┼─────────┐
             ▼        ▼         ▼
         Flight     Hotel    Weather
          Tool       Tool      Tool
             │        │         │
             └────────┼─────────┘
                      │
                      ▼
               Final AI Response

🛠️ Tech Stack:
| Technology   | Usage                           |
| ------------ | ------------------------------- |
| Java 21+     | Programming language            |
| Spring Boot  | Backend framework               |
| Spring AI    | AI integration and tool calling |
| OpenAI       | AI model                        |
| Thymeleaf    | Web UI                          |
| Tailwind CSS | UI styling                      |
| Maven        | Build and dependency management |
| Lombok       | Boilerplate reduction           |


Structure:
ai-agents-using-spring-ai/
│
├── README.md
├── .gitignore
│
└── ai-agent-backend/
    │
    ├── pom.xml
    ├── mvnw
    ├── mvnw.cmd
    │
    └── src/
        └── main/
            │
            ├── java/
            │   └── com.substring.agent.backend/
            │       │
            │       ├── AiAgentBackendApplication.java
            │       │
            │       ├── config/
            │       │   └── AiConfig.java
            │       │
            │       ├── controller/
            │       │   ├── ChatController.java
            │       │   └── ViewController.java
            │       │
            │       ├── model/
            │       │   ├── Flight.java
            │       │   ├── Hotel.java
            │       │   └── User.java
            │       │
            │       ├── service/
            │       │   └── ChatService.java
            │       │
            │       └── tools/
            │           ├── FlightTools.java
            │           ├── HotelTools.java
            │           ├── WeatherTools.java
            │           ├── OrderTools.java
            │           └── InventoryTools.java
            │
            └── resources/
                │
                ├── templates/
                │   └── chat.html
                │
                ├── application.yml
                └── application.properties


EXAMPLE PROMPT: Plan a complete trip from Delhi to Goa on 2026-08-21.
My total budget for a flight and one night hotel is ₹7000.
Search for suitable flights, find a hotel within my budget,
and check the weather in Goa for that date.
Then compare the options and give me your best recommendation.


What I Learned
Through this project, I explored:

Spring Boot application architecture
Spring AI
AI Agent development
Function / Tool Calling
OpenAI API integration
ChatClient
Conversational memory
REST APIs
Dependency Injection
Thymeleaf
Maven
Environment variable management
