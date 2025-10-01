# AskMe System - Anonymous Q&A Platform

![C++](https://img.shields.io/badge/C++-17-blue.svg)
![OOP](https://img.shields.io/badge/Object_Oriented-Design-success.svg)


A sophisticated question and answer system implementing core OOP concepts, featuring anonymous interactions and threaded conversations.

## Features

### **User Management**
- Secure registration/login system
- Profile customization
- Anonymous question permissions
- User activity tracking

### **Question System**
- Public/anonymous questioning
- Threaded conversations
- Answer editing
- Question deletion
- Interactive feeds
- Multi-level parent-child questions

### **Data Management**
- Persistent storage in text files
- Automatic data reloading
- Atomic database updates
- Data consistency checks

## Installation

### **Prerequisites**
- C++17 compatible compiler
- CMake 3.12+ (recommended)

### **Build & Run**
```bash
# Clone the repository
git clone https://github.com/gamal1osama/Ask-Me-project.git
cd askme-system

# Create build directory and compile
mkdir build && cd build
cmake ..
make

# Run the application
./Ask-Me-project
```

### **Configuration**
Update file paths in `ReadFileLines()` and `WriteFileLines()` functions to match your system.

## Usage

### **Main Menu:**
```
1) Print Questions To Me
2) Print Questions From Me
3) Answer Question
4) Delete Question
5) Ask Question
6) List Users
7) View Feed
8) Logout
```

### **Key Operations:**
- **Ask Question:** Start new threads or reply to existing ones
- **Answer Question:** Provide answers to pending questions
- **Feed View:** Browse all answered questions
- **User Listing:** Discover system users and their IDs

## Architecture 🏛️

### **Data Model**

#### **Users**
```csv
id,username,password,name,email,allow_anonymous
```

#### **Questions**
```csv
id,parent_id,from_user,to_user,is_anonymous,question,answer
```

## Class Structure

| Class            | Responsibility                            |
|-----------------|----------------------------------------|
| `User`         | User metadata and preferences management |
| `Question`     | Question lifecycle and threading        |
| `UsersManager` | Authentication and user operations      |
| `QuestionsManager` | Core Q&A functionality                |
| `AskMeSystem`  | Main application controller             |

## Examples

### **User Registration**
```cpp
User new_user;
new_user.ReadUser("new_user", 1001);
// Creates entry: 1001,new_user,pass123,New User,user@email.com,1
```

### **Question Creation**
```cpp
Question q;
q.SetQuestionId(2001);
q.SetQuestionText("What's your favorite design pattern?");
q.SetFromUserId(1001);
q.SetToUserId(200);
```

### **Threaded Conversation**
```
Question 101: What programming language should I learn first?
-- Thread 201: Why C++ specifically?
-- Thread 202: What about Python for beginners?
```

## Roadmap 
- ✅ JSON data storage
- ✅ Password encryption
- ✅ Email notifications
- 🚧 Search functionality
- 🚧 GUI interface
- 🚧 Unit testing framework
- 🚧 REST API integration

