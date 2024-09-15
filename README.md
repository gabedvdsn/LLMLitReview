# LLMLitReview

Assignment 3 literature review

### Question
I wanted to focus my question within the context of game development. Specifically, I am curious about what makes a programming language viable or not viable for games. In general, the language needs to be high level to accommodate for developer productivity and ease of use, as well as performant to accommodate complex frame updates that involve scripts, physics, sound, AI, etc... To what degree do different programming languages accommodate these needs, and how is that reflected in the development process? What is the history of programming languages within the scope of game development?

## My Conversation with Chat GPT-4o (Paid version)
### What makes a programming language viable or not viable for game development?
GPT had a lot to say about what makes a programming language viable or not viable for game development. The factors I was most interested in revolved around performance, memory management, platform compatibility, and the language's impact on the development cycle. Something I have learned over many years of game development is that the accessibility of a programming language, from IDE support to readability to library & tools, are crucial factors to consider. The choice of language does not necessarily lie in the hands of the developer, however, and rather depends a lot on the game engine of choice. This limitation can typically be offset by using compatible plugins to bind non-native scripts to the engine. 

In general, games require fast execution and optimized frame cycles. Intensive systems, such as physics simulations, rendering, and AI, rely heavily on platform hardware. DSLs (domain-specific languages) play a pivotal role within this context in game development. Shader graphs, for example, are a type of DSL that specifically handles the computation of shaders. Shader graph code runs directly on the GPU, which is optimal for rendering operations. 

Other capabilities, such as multi-threading and memory management, are important factors to consider as well. Direct control over memory allocation and manual garbage collection allows for performance optimizations, especially when considering the various capabilities and hardware specifications of different platforms. However, using a language that allows for these capabilities is not necessarily the correct decision. The scope of the game is the most important factor to consider when deciding what characteristics of one's programming language are necessary. A small title, such as a simple 2D platformer game, typically has no need for this level of hardware access. If not needed, the developer would almost always be better off choosing a higher-level language further from the hardware due to accessibility factors.

In general, low-level languages such as C++ are suitable for complex titles where hardware systems and script behavior can be monitored and manipulated manually. The target platform is also a point of consideration, as consoles are only compatible with source code written in C, C++, and C#. Most console publishers require that application source code go through their own toolchain, which means that unsupported languages are not compatible by default.

GPT's answer also touched on the following important topics:

    5. Development Speed and Ease of Use
    - High-level vs. Low-level programming: High-level languages like Python are easier and faster to write but might not provide the required performance for complex games. Low-level languages like C++ offer more control but can increase development time due to complexity.
    - Readability and Maintainability: Easier-to-read languages (like C#) can reduce development time and make it easier for teams to collaborate, maintain, and scale the codebase.

    7. Networking and Multiplayer Support
    - Multiplayer and networking capabilities: Modern games often include online multiplayer. A viable language must have robust support for networking libraries or features to handle server-client architectures, synchronization, and real-time communication.
    - Latency and Packet Management: Languages that allow efficient handling of network latency and packet management, like C++, are often preferred for real-time multiplayer games.

From this answer, it seems like the viability of the language greatly reflects the needs and scope of the game. Low-level languages, such as C++, are more suitable for very complex titles, such as AAA titles, where script behavior can be heavily monitored and manipulated. However, low-level languages are less readable and can impinge on the development process. The target platform needs to be considered. Consoles like Xbox and PlayStation are only compatible with C, C++, and C#.[^1]

#### Followup: Specifically, what characteristics of C++ make it so viable for game development?
I thought that GPT's answer was a convincing argument for the superiority of C++ over other development languages. I was curious as to what specifically makes it so viable.

    1. High Performance
    - Low-level Memory Control: C++ allows developers to manage memory manually through features like dynamic memory allocation and direct memory access (pointers). This level of control is crucial in games, where optimizing memory usage can significantly impact performance, especially in large, complex environments.
    - Optimized for Speed: C++ is compiled directly to machine code, which ensures that games can run as efficiently as possible without the overhead seen in interpreted or higher-level languages. This performance is vital for games requiring real-time rendering, physics simulations, and AI.
    
    3. Efficient Multithreading and Concurrency
    - Multithreading Support: Games often rely on multiple threads to perform different tasks simultaneously, such as handling physics, AI, and rendering on separate threads. C++ offers efficient multithreading capabilities via libraries like the C++ Standard Library, Boost, and platform-specific APIs. This makes it easier to optimize games for modern multi-core processors.
    - Concurrency: C++ provides control over thread management and synchronization primitives, which allows game developers to take full advantage of parallel processing, crucial for tasks like physics simulations and real-time rendering.
    
    5. Fine-grained Control Over Hardware
    - Close-to-Hardware Access: C++ allows developers to work closer to the hardware than higher-level languages, which is especially important in performance-critical applications like games. It supports direct interaction with the GPU for rendering, the CPU for processing, and other system resources (like input devices, sound cards, and storage).
    - Optimization: The ability to write platform-specific, low-level optimizations in C++ is one of the reasons it's preferred for developing AAA games. Developers can fine-tune their code to maximize hardware capabilities, whether it’s squeezing out performance on a console or optimizing for high-end gaming PCs.
    
    6. Memory Efficiency and Deterministic Behavior
    - Manual Memory Management: C++ gives developers precise control over memory allocation, which allows for more efficient use of system resources. This is critical in large open-world games, where memory use needs to be tightly controlled to prevent performance drops or crashes.
    - No Garbage Collection: Unlike languages with garbage collection (like C# or Java), C++ does not rely on automated memory management. This avoids the unpredictable pauses that can occur when the garbage collector runs, which could be detrimental in real-time applications like games.

The close-to-hardware access provided with C++ allows for optimized performance-critical systems, such as rendering (GPU) and input (peripherals). Since C++ is compiled directly into machine code, the overhead costs of interpreted or higher-level languages can be avoided, leading to very fast performance. Direct control over garbage collection and memory management provides precise control over memory allocation. This helps the program utilize resources efficiently. 

### To what degree do different programming languages accommodate the needs for ease-of-use and performance, and how is that reflected in the development process?
GPT's answer spoke directly about low-level vs mid-level vs high-level languages, and the manner in which each paradigm accommodates the above-mentioned needs. As mentioned in my previous question, low-level languages provide close-to-hardware access and precise control over various important systems. Game systems such as physics simulations and rendering systems are critically performance dependent, and are computationally intensive tasks when performed every frame. This access allows developers to fine-tune scripts to optimize for specific platforms and hardware requirements. This is especially important for a console because its hardware does not get upgraded (or changed, in general) over its lifetime. 

This low-level access is offset by accessibility. These languages require deep understanding of memory management, pointers, etc... These languages also necessitate handling memory leak and buffer overflow events. While this would not dissuade the use of low-level languages for proficient developers, the popularity of mid and high-level languages over low-level ones reflects this lack of popular accessibility. 

Mid-level languages, such as C# and Java, are very popular languages used in game development. The Unity game engine (the engine I personally use) uses C# natively. While these languages may not match the raw speed of low-level languages, they are often compiled to intermediate bytecode by the engine, which runs optimally on virtual machines. These languages utilize just-in-time compilation, which optimizes performance at runtime. This is very important in performance-heavy games, because JIT will analyze where the benefits of compilation outweigh the cost of compilation, which can have a profound effect on frame-dependent behaviors. These languages allow for faster development due to readability and abstraction capabilities, among other benefits.

High-level languages are very accessible and generally performant with systems that are not performance-critical. Systems such as rendering and physics simulations perform much slower due to the fact that they are typically interpreted languages or run in virtual machines. 

GPT concluded this question by saying:

    - High Performance, Lower Ease-of-Use: Languages like C++ provide unparalleled performance, making them essential for real-time games and AAA development, 
    but require skilled developers due to their complexity and the need for manual memory management.
    - Balanced Performance and Ease-of-Use: Mid-level languages like C# and Java offer managed memory, robust libraries, and more developer-friendly environments 
    while still delivering reasonable performance. They are popular in engines like Unity and for mobile games.
    - Ease-of-Use, Lower Performance: High-level and scripting languages like Python, Lua, and UnrealScript favor ease-of-use, enabling rapid development and 
    iteration but are typically not suited for performance-critical systems. These are ideal for less intensive tasks like scripting game mechanics or prototyping.

## History of programming languages in game development
Game development has transformed with computer technology and software over the decades. The largest driving factor certainly has to do with hardware. Games used to be programmed using assembly code, which allowed developers to interface at the lowest level with the hardware. This was necessary because of the poor specifications of computer hardware. GPUs were an especially potent bottleneck for performance; a 2kB memory could not feasibly support any sort of video game. Some games written in assembly are Pong (1972) and Space Invaders (1978). Even during the rise of C and home computers, some developers still used assembly for its unique and complete access to hardware, such as the original Age of Empires title (1997). This choice was made to optimize sprite loading.[^1]

As PCs became more prolific and their hardware improved, developers began using C in the 70s-80s. The advent of abstraction and more mainstream portability made development easier while still affording intimate access to hardware. As C++ was released and began seeing mainstream adoption in game development in the 90s, programming paradigms such as OOP became heavily influential in development. Furthermore, the Unreal Engine game engine was first released in 1998, which utilized C++. The mainstream adoption of game engines moving forward heavily impacted how games were developed, especially because it allowed the separation of engine logic from game logic. This vastly simplified the development process and allowed for more people to enter the game development scene. As game engines improved, native support for higher-level scripting languages also opened the door for the common person to pick up game development, even as a hobby. 

## References
[The Evolution of Programming Languages for Gaming](https://uforika.medium.com/the-evolution-of-programming-languages-for-gaming-a-journey-into-the-digital-worlds-04cfa673a6bd)\
[Comparison of Programming Languages in Game Development](https://www.researchgate.net/profile/Mirza-Masood/publication/342804594_Comparison_of_Programming_Languages_in_Game_Development/links/5f07031045851550509840f1/Comparison-of-Programming-Languages-in-Game-Development.pdf)

