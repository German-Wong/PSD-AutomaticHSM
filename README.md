# PSD-AutomaticHSM
Notes on research done for Proteus Senior Design Project Automatic HSM

              Key concept: Finite State Machine (FSM) (state-machine.com)

Sep 29, 2023

The behavior of each Active Object in the QP real-time embedded frameworks is specified by means of a modern finite state machine (UML statechart), which is a very effective, elegant and powerful technique of specifying event-driven behavior. 

Basic Finite State Machine: 

The main challenge in programming event-driven systems, such as Active Objects, is to identify the appropriate action to execute in response to a given event. Determined by two factors: 

By the nature of the event
By the current context or sequence of past events in which the system was involved

Event-action paradigm handles context manually by storing past events in variables and flags. But results in convoluted conditional logic called “spaghetti” code. 

Techniques based on state machines reduce the paths through code and simplify. State machine makes event handling dependent on both the nature of the event and the context (state) of the system. 

States are equivalence classes of past histories of a system, equivalent in the sense that the future behavior of the system given any of these past histories will be identical. It is the minimum information that captures only the relevant aspects of future behavior and abstracts away all irrelevant aspects.

Hierarchical State Machine
Hierarchical state machines (statecharts) specify state machines, which extends the traditional automata theory in several ways. 

UML state machines introduce hierarchically nested states by avoiding repetition. The nesting allows substates to define the differences in behavior from the superstates, promoting sharing and behavior.

Supporting entry and exit actions for states which provides guaranteed initialization and clean-up similar to constructors and destructors for classes. Exit actions, similar to destructors, are always executed in exact reverse order. Entry and exit actions combined with state nesting complicate the transition sequence.

The Importance of an Event-Driven Framework

State machines require a framework. Must provide: a run-to-completion (RTC) execution context for each state machine, queuing of events, and event-based timing services. Such as a Real-Time Embedded Framework, state machines would be like cars with no roads or gas stations. 

The relationship between an event-driven framework and state machines is mutually synergistic. On one hand, the framework provides the thread context and event queuing that the state machines need to process the events in a run-to-completion fashion. On the other hand, state machines provide the structure and clear design for the event-driven behavior running inside the framework. State machines are also the most constructive part of the design amenable to modeling and automatic code generation. 
