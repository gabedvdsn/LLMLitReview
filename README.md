# LLMLitReview

Assignment 3 literature review

### Question
I wanted to focus my question within the context of game development. Specifically, I am curious about what makes a programming language viable or not viable for games. In general, the language needs to be high level to accommodate for developer productivity and ease of use, as well as performant to accommodate complex frame updates that involve scripts, physics, sound, AI, etc... To what degree do different programming languages accommodate these needs, and how is that reflected in development? What characteristics of programming languages are most important to support performant gameplay?

## My Conversation with Chat GPT-4o (Paid version)
### What makes a programming language viable or not viable for game development?
GPT had a lot to say about what makes a programming language viable or not viable for game development. Much of its answer lay outside the scope of my direct line of questioning, such as community & tools, learning curve, and suitability for different game genres. It also spoke on game engine support & language integration, which I believe is not as much of any issue given the availability of plugins to support non-native languages. I was most interested in what it had to say about performance requirements and platform compatibility.

    1. Performance
    Real-time computation: Games, especially 3D or real-time ones, require fast execution to handle physics calculations, rendering, and AI. Languages like C++ are popular in game development because of their ability to offer low-level memory management and performance optimizations.
    Multithreading: Modern games often require parallel processing for tasks like rendering, physics, AI, and networking. Languages with strong multithreading capabilities are more suited for handling these needs efficiently.
    2. Memory Management
    Manual vs. Automatic Memory Management: Languages that offer fine-grained control over memory allocation (like C++ and C) are preferred for performance-critical parts of a game (e.g., large game worlds, simulations). On the other hand, languages with garbage collection (e.g., Java, C#) may introduce performance issues like garbage collection pauses, though these issues have been mitigated in many cases.
    Memory Efficiency: Games need to be optimized for a variety of devices (consoles, PCs, mobile), making memory efficiency critical. Languages that give developers control over memory allocation are often favored in this context.
    3. Platform Compatibility
    Cross-platform development: Many games need to be developed for multiple platforms (PC, consoles, mobile). Languages that are supported by game engines with multi-platform capabilities (like C# in Unity or C++ in Unreal Engine) are highly viable.
    Toolchain support: The programming language should integrate well with development tools (e.g., game engines, debuggers, profiling tools) to ensure smooth game creation and deployment across different platforms.
