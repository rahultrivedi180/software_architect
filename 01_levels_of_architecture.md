# Architectural Design – Software Engineering

main source: https://www.geeksforgeeks.org/software-engineering-architectural-design/

---

## System Category Consists of

- A set of components(eg: a database, computational modules) that will perform a function required by the system.
- The set of connectors will help in coordination, communication, and cooperation between the components.
- Conditions that defines how components can be integrated to form the system.
- Semantic models that help the designer to understand the overall properties of the system.

## Taxonomy of Architectural Styles

### 1] Data centered architectures:

- A data-centered architecture places data at the center with other components accessing and modifying this data
- Key characteristics:

  - Data is stored in a central repository (database, file system, etc.)
  - Client components operate independently of each other
  - Components communicate through the shared data store
  - Data store acts as the primary means of coordination

- Common examples:
  - Traditional database systems with multiple clients
  - Repository pattern implementations
  - Blackboard architectural pattern
- Advantages:
  - Components can be added or modified without affecting others
  - Data integrity and consistency are easier to maintain
  - Centralized data management and backup
- Disadvantages:

  - The central data store can become a performance bottleneck
  - Data store failure affects entire system
  - May require complex data access synchronization

- Best suited for:
  - Systems with high data integrity requirements
  - Applications where multiple components need to share data
  - Systems that require data persistence and historical tracking

### 2] Data flow architectures:

- Data flow architectures focus on the movement and transformation of data through a series of processing components
- Key characteristics:
  - Data flows through the system in a series of transformations
  - Components act as data transformers
  - Data flows are unidirectional
  - Components operate independently and in parallel
- Common patterns:
  - Pipe and Filter architecture
    - Each component (filter) processes input and produces output
    - Components connected by pipes that transmit data
    - Filters can be reused and reconfigured
  - Batch Sequential processing
    - Data processed in large batches
    - Sequential processing through multiple stages
- Advantages:
  - Easy to understand and maintain
  - Supports parallel processing
  - Components are reusable and modular
  - Easy to add new transformations
- Disadvantages:
  - May not be suitable for interactive applications
  - Can be inefficient for small data sets
  - May require data format conversion between components
  - Potential bottlenecks in sequential processing
- Best suited for:
  - Data processing applications
  - ETL (Extract, Transform, Load) systems
  - Stream processing systems
  - Signal processing applications
  - Compiler design
- Real-world examples:
  - Unix pipe commands
  - Audio/Video processing pipelines
  - Data analytics workflows
  - Message processing systems

### 3] Call and Return architectures:

- Call and Return architectures organize software into hierarchical structures where components interact through procedure calls
- Key characteristics:
  - Hierarchical organization of components
  - Well-defined interfaces between components
  - Clear separation of concerns
  - Structured control flow
- Common patterns:

  - Main program and subroutine

    - Single main program controls execution
    - Subroutines perform specific tasks
    - Hierarchical control structure

  - Object-Oriented
    - Encapsulation of data and behavior
    - Inheritance and polymorphism
    - Message passing between objects
  - Layered architecture
    - System organized into layers
    - Each layer provides services to layer above
    - Each layer uses services of layer below

- Advantages:
  - Easy to modify and scale individual components
  - Clear separation of concerns
  - Promotes code reuse
  - Easy to understand and maintain
  - Supports modular development
- Disadvantages:
  - Can lead to complex dependency management
  - May have performance overhead from multiple calls
  - Risk of tight coupling between components
  - May not handle concurrent operations well
- Best suited for:
  - Business applications
  - Enterprise software systems
  - Operating systems
  - Applications requiring clear hierarchical structure
- Real-world examples:
  - Java Enterprise applications
  - Traditional desktop applications
  - Web application backends
  - Operating system kernels

### 4] Object Oriented architecture

- Object Oriented architecture organizes the system as a collection of cooperating objects
- Key characteristics:
  - Objects encapsulate both data and behavior
  - Objects communicate through message passing
  - Strong emphasis on modularity and reusability
  - Support for inheritance and polymorphism
- Core principles:

  - Encapsulation
    - Information hiding within objects
    - Implementation details are private
    - Public interfaces for interaction
  - Inheritance
    - Allows code reuse through class hierarchies
    - Supports "is-a" relationships
    - Enables polymorphic behavior
  - Polymorphism
    - Objects can take multiple forms
    - Runtime method resolution
    - Flexible and extensible design

- Advantages:
  - High reusability of code
  - Easy maintenance and modification
  - Natural modeling of real-world entities
  - Strong support for modularity
  - Excellent for complex systems
- Disadvantages:
  - Can be overhead for simple problems
  - Potential for over-engineering
  - Learning curve for team members
  - Performance overhead in some cases
- Best suited for:
  - Large-scale enterprise applications
  - Systems with complex interactions
  - GUI-based applications
  - Games and simulations
- Real-world examples:
  - Java frameworks (Spring, Hibernate)
  - Modern game engines
  - Desktop applications
  - Android applications

### 5] Layered architecture

- Layered architecture organizes system components into horizontal layers, each providing a specific set of services
- Key characteristics:
  - Each layer has a distinct role
  - Layers communicate through well-defined interfaces
  - Changes in one layer minimally impact others
  - Support for separation of concerns
- Common layers:
  - Presentation layer (UI)
    - User interface components
    - User interaction handling
    - Display formatting
  - Application layer (Business)
    - Business logic
    - Workflow management
    - Process coordination
  - Domain layer
    - Business entities
    - Domain rules
    - Core functionality
  - Data layer
    - Data access
    - Storage management
    - CRUD operations
- Advantages:
  - Clear separation of concerns
  - Easy to modify individual layers
  - Supports parallel development
  - Enhanced maintainability
  - Good for testing and debugging
- Disadvantages:
  - Can introduce unnecessary complexity
  - Performance overhead from layer traversal
  - Risk of tight coupling between layers
  - May lead to "layer violation" temptations
- Best suited for:
  - Enterprise applications
  - Web applications
  - Large-scale systems
  - Systems requiring clear separation of concerns
- Real-world examples:
  - OSI network model
  - Enterprise web applications
  - Modern web frameworks (Django, Spring MVC)
  - Mobile application architectures
