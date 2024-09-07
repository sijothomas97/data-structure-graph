# Social Network Graph Management Application

## Introduction

This C# console application implements a graph structure to represent a social network. Each node in the graph represents a person, and directed edges represent friendships between people. The application allows users to manage a social network by inserting people, establishing friendships, and displaying the direct and indirect friends of a person. This application is divided into three tasks:

- **Task A**: Implements the basic graph structure and supports node and edge insertion.
- **Task B**: Extends the graph to handle social network functionalities such as adding people, displaying friends, and managing friendships.
- **Task C**: Expands the social network application by allowing the removal of people and displaying both direct and indirect friends.

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Classes and Methods](#classes-and-methods)
- [Examples](#examples)
- [Dependencies](#dependencies)
- [Troubleshooting](#troubleshooting)
- [Contributors](#contributors)
- [License](#license)

## Features

### Task A: Basic Graph Implementation
1. **GraphNode Class**: Represents each node in the graph, which contains an ID and an adjacency list of directed edges.
2. **Graph Class**: Manages the graph structure, supporting node insertion and edge addition.
3. **Node and Edge Counting**: Computes the total number of nodes and edges in the graph.

### Task B: Social Network Management
1. **Add a Person**: Add a person to the graph by providing their name.
2. **Add a Friendship**: Establish a direct friendship (directed edge) between two people.
3. **Display People**: Display all the people (nodes) present in the graph.
4. **Display Direct Friends**: Show all direct friends (adjacent nodes) of a specific person.

### Task C: Advanced Social Network Operations
1. **Remove a Person**: Remove a person from the graph and all associated edges.
2. **Display Direct and Indirect Friends**: Show both direct and indirect friends of a person, accessible through a graph traversal.

## Installation

1. **Clone or Download the Project**:
   - Clone the repository:
     ```bash
     git clone https://github.com/your-username/social-network-graph.git
     ```
   - Or download the ZIP file and extract it to a folder on your computer.

2. **Open the Project in Visual Studio**:
   - Open the `.sln` file in Visual Studio.

3. **Build the Solution**:
   - In Visual Studio, click on `Build > Build Solution` or press `Ctrl+Shift+B` to compile the code.

4. **Run the Project**:
   - Press `F5` to run the application in Debug mode.

## Usage

### Console Application

Once you run the application, you will be presented with a menu to manage the social network graph. The operations are divided into three main sections:

1. **Task A Operations**: 
   - Insert nodes (people).
   - Add directed edges (friendships).
   - Display the number of nodes and edges.

2. **Task B Operations**:
   - Add a person by name.
   - Add a friendship between two people.
   - Display the names of all people in the graph.
   - Display the direct friends of a person.

3. **Task C Operations**:
   - Remove a person from the graph.
   - Display direct and indirect friends of a person.

### Example Menu
```
1. Add a Person to the Network
2. Add a Friendship Between Two People
3. Display All People in the Network
4. Display Direct Friends of a Person
5. Remove a Person from the Network
6. Display Direct and Indirect Friends of a Person
7. Exit
```

### Example Input/Output
- Add a person:
  ```
  Enter the name of the person: John
  ```

- Add a friendship:
  ```
  Enter the name of the person: John
  Enter the name of their friend: Jane
  ```

- Display direct friends of a person:
  ```
  Enter the name of the person: John
  Output: Jane, Alex
  ```

- Display direct and indirect friends:
  ```
  Enter the name of the person: Trace
  Output: Jose, Sidney, Coe
  ```

## Classes and Methods

### 1. **GraphNode Class**
Represents a node in the graph with an ID (or name for Task B and C).
- **Fields**:
  - `ID`: Stores the unique identifier of the node (name in Task B).
  - `AdjList`: A linked list that holds IDs of adjacent nodes.
  
- **Methods**:
  - `AddEdge(GraphNode to)`: Adds a directed edge to another node.
  - `GetAdjList()`: Returns the adjacency list of the node.

### 2. **Graph Class**
Manages the graph and handles node/edge operations.
- **Fields**:
  - `Nodes`: A list of graph nodes (people in Task B and C).
  
- **Methods**:
  - `AddNode(int id)` or `AddNode(string name)`: Adds a node to the graph.
  - `AddEdge(int from, int to)` or `AddEdge(string from, string to)`: Adds a directed edge between two nodes.
  - `GetNodeByID(int id)` or `GetNodeByName(string name)`: Retrieves a node by its ID or name.
  - `NumNodesGraph()`: Returns the total number of nodes in the graph.
  - `NumEdgesGraph()`: Returns the total number of edges in the graph.
  - `RemoveNode(string name)`: Removes a node and associated edges from the graph.
  - `DisplayDirectFriends(string name)`: Displays all direct friends of a given person.
  - `DisplayIndirectFriends(string name)`: Displays both direct and indirect friends using graph traversal (BFS or DFS).

## Examples

### Example 1: Adding Nodes and Edges
```csharp
Graph graph = new Graph();
graph.AddNode("John");
graph.AddNode("Jane");
graph.AddEdge("John", "Jane");
```

### Example 2: Displaying Direct Friends
```csharp
graph.DisplayDirectFriends("John");
// Output: Jane
```

### Example 3: Displaying Direct and Indirect Friends
```csharp
graph.DisplayIndirectFriends("Trace");
// Output: Jose, Sidney, Coe
```

## Dependencies

- **C# .NET Core**: Ensure you have the correct version of the .NET Core SDK installed for compiling and running the application.
- **Visual Studio**: This project is designed to be developed and run in Visual Studio.

## Troubleshooting

- **Node Not Found**: If a node or edge is not found, ensure that the names or IDs being used are correct.
- **Graph Traversal Issues**: For indirect friends, ensure that the traversal (BFS/DFS) is correctly implemented and terminates properly.

## Contributors
- [sijothomas97](https://github.com/sijothomas97)

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
