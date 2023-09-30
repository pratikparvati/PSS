# Understanding the Core Components of Portable Stimulus Standard (PSS) Models

In the previous blog of our exploration into Portable Stimulus and Test Standard (PSS), we embarked on a journey to demystify this groundbreaking approach to semiconductor verification. We covered the basics, from understanding traditional verification methods to uncovering the advantages that PSS brings to the table. We also discussed the widespread adoption and enthusiastic industry support that PSS has garnered, as well as its promising future outlook. If you have followed along so far, thank you for joining us on this path of discovery.

In this blog we are going to take a deeper dive into the core components that make up PSS models. Whether you are new to PSS or looking to enhance your understanding, this blog will equip you with the knowledge necessary to comprehend and utilize this powerful verification methodology effectively. Throughout this blog, we will explore the elements, behavior abstraction mechanisms, modeling of data flow and system resources, and much more. By the end of this journey, you will have a solid grasp of the fundamental concepts that underpin PSS models, setting the stage for more advanced discussions in our upcoming blogs.

## I. Purpose of the PSS Model Components

To understand the purpose of PSS model components, we must first recognize that a PSS model is not a monolithic entity but a well-organized collection of elements designed to address various aspects of semiconductor verification. These components serve specific roles in defining and executing verification scenarios.

Think of these components as the building blocks of our verification strategy. Their primary purpose is to make our lives as verification engineers more manageable. Let's explore why we use these components:

### A. Modularity and Reusability

These components are like LEGO bricks for verification engineers. They allow us to take complex verification tasks and divide them into smaller, reusable parts. This modularity is like having a toolkit of specialized instruments that we can use across different projects and teams.

### B. Abstracting Behavior

Imagine you are an artist. Instead of painting every single detail, you use broad strokes to capture the essence of your subject. Similarly, these components help us abstract the behavior we want to verify. We don't need to get bogged down in the nitty-gritty technical details; we focus on the big picture.

### C. Scenario Creation

Just like in a movie, we have different scenes that tell a story. These components help us create various verification scenarios. Each scenario is like a different plotline, exploring different aspects of the device we are testing.

### D. Defining Relationships

Think of these components as the scriptwriters of our verification story. They define how different parts of the verification environment interact with each other. It's like choreographing a dance – everything needs to be in sync.

### E. Reusable Libraries

Imagine having a library of common phrases you can use in various languages. Similarly, these components help us create libraries of verification intent. We can share these libraries across teams and projects, ensuring consistency and saving time.

### F. Hierarchical Organization

We can organize these components in a tree-like structure. It's like breaking a big task into smaller sub-tasks. This hierarchical approach keeps things organized and makes it easier to manage complex verification scenarios.

## II. Elements of a PSS Model

when we dive into the world of Portable Stimulus Standard (PSS) models, we encounter a structured framework designed to bring order to the often complex task of semiconductor verification. These models consist of several essential elements, each serving a unique purpose. Let's explore these elements and their roles:


### A. Actions as Primary Behavior Abstractions

* **Atomic Actions**: Think of these as the fundamental actions that our verification environment can perform. They represent the basic building blocks of behavior, much like individual steps in a dance routine. Atomic actions are precise, well-defined, and map directly to operations performed by the device under test (DUT) or test environment.
* **Compound Actions**: These are like choreographed sequences of atomic actions. They encapsulate complex behaviors by defining relationships between specific actions. Compound actions specify the critical intent to be verified by specifying how various atomic actions interact.


```C
// Define Atomic Actions
action AtomicAction1 {
    // Specify the behavior of Atomic Action 1
    // This could involve sending a specific command to the DUT
}

action AtomicAction2 {
    // Specify the behavior of Atomic Action 2
    // This could involve reading a register value from the DUT
}

action AtomicAction3 {
    // Specify the behavior of Atomic Action 3
    // This could involve checking a signal value on the DUT
}

// Define a Compound Action
action CompoundAction {
    // Specify the behavior of the Compound Action
    // This involves sequencing Atomic Actions to perform a higher-level operation
    // For example, initializing the DUT
    AtomicAction1;
    AtomicAction2;
    AtomicAction3;
}
```

### B. Scenarios and Their Role

* Scenarios are like the scripts of our verification story. They define a set of possible situations or sequences of actions to be applied to the DUT. Each scenario represents a specific verification intent.
* Scenarios are composed of behaviors executed by components that make up the DUT or verification components that define the test environment. They specify how these behaviors interact and communicate with each other.

```C++
// Define actions
action AtomicAction1 {
    // Define behavior for AtomicAction1
}

action AtomicAction2 {
    // Define behavior for AtomicAction2
}

action AtomicAction3 {
    // Define behavior for AtomicAction3
}

// Define components
component Component1 {
    action actionA {
        // Define behavior for actionA
    }

    action actionC {
        // Define behavior for actionC
    }
}

component Component2 {
    action actionB {
        // Define behavior for actionB
    }
}

component Component3 {
    action actionD {
        // Define behavior for actionD
    }
}

// Define scenarios using CompoundActions
action Scenario1 {
    activity {
        AtomicAction1;
        AtomicAction2;
        Component1::actionA;
        Component2::actionB;
    }
}

action Scenario2 {
    activity {
        AtomicAction3;
        Component1::actionC;
        Component3::actionD;
    }
}
```

### C. Communication Between Actions

* Actions don't operate in isolation. They need to communicate and coordinate with each other. It's like actors in a play interacting to tell a story.

* PSS models define how actions communicate, exchange data, and share resources. This communication is critical for capturing the dynamic behavior of a semiconductor device accurately.

### D. PSS Model Components and Their Relationships

* PSS models consist of various components, each with a specific purpose. These components work together to create a coherent verification strategy.
* Understanding the relationships between these components is key to effective verification. It's like knowing how different instruments in an orchestra harmonize to produce beautiful music.

In summary, the elements of a PSS model are like the ingredients in a recipe. Atomic actions, compound actions, scenarios, and communication mechanisms are combined to create a verification strategy that accurately captures the behavior of semiconductor devices. These elements provide the flexibility and precision needed to tackle the complexities of modern verification challenges.


## III. Behavior Abstraction Mechanisms

Now that we have introduced the core elements of Portable Stimulus Standard (PSS) models, let's dive deeper into the behavior abstraction mechanisms that power these models.

### A. Actions and Their Significance

* Actions are the heart and soul of PSS models. They represent specific behaviors or sets of behaviors that our verification environment needs to enact.
* Think of actions as the verbs in our verification story. They encompass everything from reading and writing data to controlling the flow of operations.
* Actions are like the instructions given to actors in a play—they dictate what needs to happen at each moment in the verification process.

### B. Atomic Actions and Their Implementation

* Atomic actions are like the simplest, indivisible steps in our verification dance. They correspond directly to operations performed by the device under test (DUT) or the test environment.
* What makes atomic actions powerful is their explicit mapping of behavior to an implementation on the target platform. It's like having a detailed choreography that tells each dancer exactly how to move.
* These atomic actions come in several supported forms, ensuring compatibility with various verification platforms and technologies.

### C. Compound Actions and Their Role in Specifying Intent

* While atomic actions are the basic steps, compound actions are more like intricate dance routines. They encapsulate flows of other actions and define the critical intent to be verified.
* Compound actions provide the high-level structure for verification scenarios. They specify how different atomic actions interact, creating a coherent narrative for verification.
* It's similar to a director's vision for a play—how different scenes, dialogues, and actions come together to convey a compelling story.

## IV. PSS Model Rules and Processing Tools

In the world of Portable Stimulus Standard (PSS) models, there are certain rules and processing tools that play a crucial role in shaping the verification process. Let's delve into this aspect.

### A. Rules Governing PSS Model Creation

* Creating PSS models isn't a free-for-all creative process; there are rules in place to ensure consistency and effectiveness.
* These rules define how elements within a PSS model should be structured, connected, and configured. They act as the guiding principles that maintain the integrity of the verification strategy.
* Think of these rules as the grammar and syntax of the verification language. They ensure that your verification story is well-structured and coherent.

### B. Addressing Incomplete Specification of Intent

* In the real world, specifications might not always be complete. There might be gaps or uncertainties in the verification intent.
* This is where PSS processing tools come to the rescue. They have the intelligence to infer the execution of additional actions and model elements to make a partial specification complete and valid.
* It's akin to a skilled editor who fills in the missing pieces of a story, ensuring that the narrative flows seamlessly.

### C. Role of PSS Processing Tools in Scenario Generation

* PSS processing tools are like the directors and choreographers of our verification play. They take the script (PSS model) and turn it into live scenarios.
* These tools analyze the model, evaluate the hierarchy of activities, and infer actions and data flow objects as needed.
* The goal is to generate scenarios that implement the critical verification intent while adhering to data flow, scheduling, and resource constraints of the target device under test (DUT) and its associated test environment.

## V. Modeling Data Flow in PSS

Understanding how data flows within a Portable Stimulus Standard (PSS) model is fundamental to creating effective and robust verification strategies. Let's explore the intricacies of modeling data flow in PSS.

### A. Types of Data Flow Objects

* Data flow objects are the channel through which information travels within the PSS model. There are several types of data flow objects, each with its unique characteristics.
* *Buffers*: Buffers represent persistent data that can be written by one action and read by one or more other actions. This establishes a strict scheduling dependency between the producer and the consumer. The producer must complete its execution before the consumer can begin reading the buffer.
* *Streams*: Stream flow objects are used for transient data exchange between actions. The key feature of stream objects is that the producer and consumer actions execute in parallel. There's a one-to-one connection between them, ensuring synchronized data transfer.
* *States*: State flow objects represent the state of some element in the device under test (DUT) or test environment. Multiple actions may read or write the state object, but only one write action can execute at a time. Read actions can occur in parallel, but reads and writes are sequential.

```C++
// Define data flow objects
buffer Buffer1 {
    // Define properties and behavior for Buffer1
}

stream Stream1 {
    // Define properties and behavior for Stream1
}

state State1 {
    // Define properties and behavior for State1
}

// Define actions that use data flow objects
action ProducerAction {
    output Buffer1 bufferOutput; // Producer writes to Buffer1
    output Stream1 streamOutput; // Producer writes to Stream1
    output State1 stateOutput;   // Producer writes to State1

    // Define behavior for the producer action
}

action ConsumerAction {
    input Buffer1 bufferInput; // Consumer reads from Buffer1
    input Stream1 streamInput; // Consumer reads from Stream1
    input State1 stateInput;   // Consumer reads from State1

    // Define behavior for the consumer action
}
```
### B. Scheduling Dependencies and Constraints

* The choice of data flow object type influences the scheduling semantics within the PSS model.
* For buffers, the producer-consumer relationship enforces a strict scheduling constraint, ensuring that the producer completes before the consumer starts.
* Streams allow parallel execution of producer and consumer actions, fostering concurrency and efficiency.
* State objects maintain sequential access to maintain the integrity of the state.

### C. Data Flow Object Pools

* To manage data flow objects efficiently, they are grouped into pools.
* In buffer and stream types, the pool contains the number of objects needed to support communication between actions sharing the pool.
* For state objects, the pool contains only one object at any given time. All actions sharing a state object via a pool see the same value for the state object.

```C++
// Define a structure for mem_segment
struct mem_segment_s {
    // Define structure members here if needed
}

// Define a buffer for data
buffer data_buff_s {
    rand mem_segment_s seg; // Randomly generated mem_segment_s object
}
// Define a sub-component dma_sub_c
component dma_sub_c {
    // Define properties and behavior for dma_sub_c
    // ...
}

// Define the main dma_c component
component dma_c {
    dma_sub_c dmas1, dmas2; // Sub-components of dma_c

    // Define a pool for data buffers
    pool data_buff_s buff_p;

    // Bind all instances of data_buff_s to the pool
    bind buff_p {*};

    // Define an action mem2mem_a
    action mem2mem_a {
        input data_buff_s in_data;   // Input data buffer
        output data_buff_s out_data; // Output data buffer

        // Define behavior for the mem2mem_a action
        // ...
    }
}
```

Understanding data flow in PSS models enables verification engineers to design scenarios that reflect real-world data interactions in semiconductor devices. It allows for precise modeling of how information is shared, transferred, and processed, ultimately leading to comprehensive and effective verification strategies.

## VI. Modeling System Resources

In a Portable Stimulus Standard (PSS) model, the representation of system resources plays a pivotal role in ensuring the accurate and efficient verification of semiconductor devices. Let's delve into the key aspects of modeling system resources in PSS.

### A. Resource Objects and Their Purpose

* Within PSS models, we encounter something known as "resource objects." These aren't mysterious entities; think of them as fundamental building blocks that represent different aspects of your verification environment.
* Resource objects are user-defined data objects within the PSS model that represent system resources required for verification.
* These resources can encompass a wide range of elements, including hardware components, software packages, or testbench agents.
* Resource objects are essential for defining the functionality and availability of various system resources that actions within the model may require.


### B. Resource Pools and Their Role

* Now, imagine a resource object as a piece of a puzzle. To assemble the full picture, we group resource objects into "resource pools." These pools act as orchestrators, determining how resources are managed and accessed.
* The size of each resource pool corresponds to the number of available resource instances in your device under test (DUT) or test environment. It's akin to having a specific number of seats at the verification table.

### C. Locking Resources for Exclusive Access

* Sometimes, during the verification process, certain actions require undivided attention from a particular resource. To ensure this exclusive focus, actions can "lock" a resource.
* Think of it as reserving a room for a private meeting. While the room is locked, no one else can enter until the meeting concludes. Similarly, a locked resource is exclusively dedicated to the locking action until it completes its task.

### D. Sharing Resources for Non-Exclusive Access

* On the flip side, not all actions demand exclusive access to resources. Some can work collaboratively, sharing the same resource without conflict.
* Picture a communal workspace. Multiple people can utilize it simultaneously, as long as there's room. In the world of PSS, actions can similarly share resources, provided they don't exceed the resource pool's capacity.

Effectively modeling system resources in PSS empowers verification engineers to define how various components and agents interact with critical resources during the verification process. This level of control ensures that resources are allocated efficiently, minimizing contention and maximizing the effectiveness of verification scenarios. PSS provides a versatile framework for resource management, enabling engineers to mirror real-world resource interactions within semiconductor devices.

```C++
// Define a resource object for DMA channels
resource DMA_channel_s {
    rand bit[3:0] priority;
}

// Define a resource object for CPU cores
resource CPU_core_s {
    string core_name;
    int core_id;
}

// Define an action that performs a two-channel transfer
action two_chan_transfer {
    // Acquire locks on two DMA channels
    lock DMA_channel_s channel_A;
    lock DMA_channel_s channel_B;

    // Share a CPU core for control
    share CPU_core_s control_core;

    // Other actions or properties specific to the transfer
    // ...
}
```

## VII. Basic Building Blocks

Now that we have explored the realm of resource management in PSS models, let's delve into another crucial aspect: the basic building blocks that form the foundation of these models. If you are new to PSS, fear not - we will start from the ground up

### A. Components and Their Structural Role

* Think of a "component" as a fundamental structural element within a PSS model. In simpler terms, it's like a building block in your model's architecture.
* These components are often associated with specific parts of your verification environment or the device under test (DUT). They encapsulate various behaviors and functionalities related to these components.
* Each component declaration defines a unique type that can be instantiated within other components, creating a hierarchical structure.

### B. Hierarchical Component Instantiation

* PSS models embrace a hierarchical approach to modeling. This means that components can be instantiated within other components, forming a tree-like structure.
* This hierarchy allows you to manage and organize the complexity of your verification environment. You can break down intricate systems into more manageable subcomponents.
* It's akin to assembling a puzzle, where each piece (component) fits into the larger picture, contributing to the overall verification strategy.

```C++
// Define a basic component representing a building block
component basic_component {
    // Properties and behaviors related to this component
    bit[32] component_id;
    string description;
    
    // Action specific to this component
    action component_action {
        // Action implementation specific to this component
        // ...
    }
}

// Define a higher-level component that can contain other components
component higher_level_component {
    // Properties and behaviors specific to this higher-level component
    string component_name;
    
    // Hierarchical instantiation of basic components within this component
    basic_component sub_component1; // Instantiate a basic component
    basic_component sub_component2; // Instantiate another basic component
    
    // Action specific to this higher-level component
    action higher_level_action {
        // Action implementation specific to this higher-level component
        // ...
    }
}
```

## VIII. Evaluation and Inference

Now that we've covered the basic building blocks of a Portable Stimulus Standard (PSS) model, let's explore how these models are evaluated and how inference is used to create verification scenarios.

### A. Starting the PSS Model Evaluation

* The journey of a PSS model begins with its evaluation. This evaluation process typically starts with the top-level action, often referred to as the "root action." The root action serves as the entry point to the model. It's important to specify this action because it defines the context in which the entire model operates.

* Imagine it as the starting point of a road trip; you need to know where you are beginning your journey. In PSS modeling, you specify the root action to determine where your verification scenario begins.

```C++
// Define a basic component representing a building block
component basic_component {
    // Properties and behaviors related to this component
    bit[32] component_id;
    string description;
    
    // Action specific to this component
    action component_action {
        // Action implementation specific to this component
        // ...
    }
}

// Define a higher-level component that can contain other components
component higher_level_component {
    // Properties and behaviors specific to this higher-level component
    string component_name;
    
    // Hierarchical instantiation of basic components within this component
    basic_component sub_component1; // Instantiate a basic component
    basic_component sub_component2; // Instantiate another basic component
    
    // Action specific to this higher-level component
    action higher_level_action {
        // Action implementation specific to this higher-level component
        // ...
    }
}

component top_component {
    higher_level_component high_component1;
    // Define the top-level action, which serves as the root action for model evaluation
    action top_level_action {
        // This is the starting point of the PSS model evaluation
        // Specify the context and behavior for the entire model
        // ...
        higher_level_component::higher_level_action;
    }
}
```

### B. Hierarchical Activity Tree

* Once the root action is defined, the PSS model forms a hierarchical activity tree. This tree encompasses all the activities present in the model, including those within subcomponents. Think of this tree as the roadmap that guides the flow of actions and behaviors within your verification scenario.

* The hierarchical structure of the activity tree allows for a systematic and organized representation of the verification intent. It's similar to breaking down a complex task into smaller, manageable sub-tasks. Each component and action in the tree has its place and role in achieving the verification goal.


### C. Inferring Actions and Objects to Support the Model

* Inference is a fundamental concept in PSS modeling. It refers to the process of automatically generating additional actions, data flow objects, and resources to support the specified verification intent. In other words, inference ensures that your model is complete and valid by filling in the missing pieces.

* For instance, if an action requires a specific data flow object as input, the inference mechanism will automatically generate actions to provide that input. This helps in satisfying the data flow, scheduling, and resource constraints of the verification scenario.

* Inference is a powerful feature that simplifies the creation of complex scenarios. It eliminates the need to manually specify every detail, making PSS modeling more efficient and less error-prone.

As you explore PSS further, you will gain a deeper understanding of how the evaluation process and inference mechanism work together to generate comprehensive verification scenarios.

## IX. Constraints and Inference

In the context of PSS, "Constraints and Inference" are fundamental aspects of creating robust verification scenarios. These components help shape how actions and objects behave within the verification model, ensuring that the scenarios generated are meaningful, realistic, and fulfill the intended verification goals.

### A. Constraint Expressions on Data Flow and Resource Objects

* *Understanding Constraint Expressions* : In PSS, constraint expressions are like the rules that govern how actions and data flow objects interact. They define the conditions and limitations that ensure the scenarios remain consistent with real-world behaviors.

* *Ensuring Realism* : Constraints ensure that verification scenarios accurately mimic real-world situations. They allow you to specify limitations on data flow, resources, and behaviors, creating a testing environment that resembles the actual use of the product.

### B. Combining Constraints for Valid Scenarios

* *Harmonizing Constraints* : PSS often involves numerous constraints from different sources, such as action behaviors, data flow requirements, and resource limitations. Combining these constraints is akin to harmonizing a complex piece of music—each component must align to create a coherent composition.

* *Achieving Balance* : Balancing constraints is crucial. Too many constraints can make scenarios overly restrictive, while too few can result in unrealistic or unattainable scenarios. The goal is to find a sweet spot that ensures both feasibility and relevance.

### C. Ensuring Valid Solutions

* *Resolving Constraint Puzzles* : Valid solutions in PSS involve resolving constraint puzzles. It's about finding configurations and values for actions and objects that satisfy all defined constraints. This process is akin to solving a puzzle with many interlocking pieces.

* *Addressing Conflict* : Sometimes, constraints can conflict with each other, creating a puzzle with pieces that don't fit. Engineers must identify and address these conflicts to ensure that the verification process proceeds smoothly.

```C++
// Define a PSS component for my_ip_c
component my_ip_c {
    struct my_struct {
        rand int a;
    };

    action my_op {
        rand my_struct s;
    }
}

// Define a PSS component for pss_top
component pss_top {
    my_ip_c my_ip;

    // Define a struct your_struct
    struct your_struct {
        rand int a;
    };

    // Test action
    action test {
        rand your_struct s;

        // Constraint for your_struct literal
        constraint s == {.a == 2};

        // Instantiate my_ip_c::my_op as 'op'
        my_ip_c::my_op op;

        // Constraint for my_ip_c::my_struct literal
        constraint op.s == {.a == 3};

        activity {
            // Execute the my_ip_c::my_op action
            op;
        }
    }
}
```

Now, let's explore each subtopic in more detail with concise points

## X. Summary of PSS Model Concepts

* **PSS Components**: In this blog, we explored the key components that make up a Portable Stimulus Standard (PSS) model. These components define a set of scenarios used to verify semiconductor designs. They include actions, scenarios, and the communication between them.

* **Behavior Abstraction**: We delved into the central role of actions in PSS models. Actions are the primary abstraction mechanism for defining behaviors. We discussed atomic actions, which directly correspond to operations performed by the Design Under Test (DUT) or test environment, and compound actions, which encapsulate flows of other actions, specifying critical intent and relationships between actions.

* **Model Rules and Processing Tools**: Understanding the rules governing PSS model creation is vital. We explored how PSS processing tools use these rules to generate scenarios that implement the verification intent while considering data flow, scheduling, and resource constraints. We also discussed how tools handle partial intent specifications.

* **Modeling Data Flow in PSS**: Data flow is a fundamental aspect of PSS models. We introduced data flow objects, including buffers, streams, and states. Buffers represent persistent data with strict scheduling dependencies. Streams denote transient data exchanged in parallel, while states represent the state of elements in the DUT or test environment at a given time.

* **Modeling System Resources**: System resources play a critical role in PSS models. We discussed resource objects and their purpose, as well as resource pools, which define the set of actions with access to these resources. Locking and sharing resources for exclusive or non-exclusive access were also explained.

* **Basic Building Blocks**: PSS models are built using components that encapsulate elements of verification intent. We explained how components are hierarchically structured and how they can contain functions and class instances, serving as a foundation for reusable models.

* **Evaluation and Inference**: To comprehend how PSS models work, we covered the process of evaluating a model, starting with the top-level root action. Hierarchical activity trees are used to manage activities and infer actions and objects to support the model.

* **Constraints and Inference**: Constraint expressions on data flow and resource objects were introduced. We explored how these constraints are combined to ensure valid scenarios, with at least one valid solution required for a model to be considered valid.

* **Multiple Scenarios**: A single PSS model can yield multiple scenarios, each with its set of inferred actions, objects, and resources. These scenarios all implement the critical verification intent but may include additional behaviors.

* **Test Implementation**: We emphasized that PSS models are not just abstract representations; they translate into practical test implementations for the target semiconductor platform.

* **Importance**: Highlighting the significance of PSS models, we discussed how they enhance verification efficiency and coverage in the semiconductor industry.

* **Future Topics**: As a closing note, we pointed out that this blog provides a foundation for exploring advanced PSS concepts and applications. Readers are encouraged to dive deeper into the world of Portable Stimulus Standards.

* **Further Learning**: To expand their knowledge, readers are encouraged to explore additional resources and engage in discussions about PSS models, as this field continues to evolve.

## XI. Conclusion

In the realm of semiconductor verification, Portable Stimulus Standard (PSS) models offer a revolutionary approach. These models simplify complex verification challenges, enhancing productivity and test coverage.

As we have explored PSS components, from actions to scenarios, remember that PSS is your gateway to efficient verification. It's a dynamic field, so keep exploring, learning, and innovating.

PSS models are more than a standard; they are a catalyst for innovation in semiconductor verification. Embrace the opportunities and stay tuned for further discoveries.

Thank you for joining us on this enlightening journey.
