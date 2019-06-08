
# Table of Contents

1.  [Introduction](#org189c7ea)
2.  [Session 1: The Good Code](#orgccb652d)
    1.  [Info](#org1df9c91)
    2.  [Summary](#orgf50d154)
    3.  [Notes:](#org0df199b)
        1.  [Not good code](#org88e9c11)
        2.  [Good Code](#orgbc70630)
        3.  [Deadlines](#orgbb4bcd4)
        4.  [Quantity vs quality](#org821bb76)
        5.  [Naming](#orgf0e7401)
        6.  [Functions](#orgf395025)
    4.  [Questions](#orgd7398e4)
3.  [Session 2: Mesh isn't just for the club (anymore)](#org8dc7079)
    1.  [Info](#orgd9ab5d1)
    2.  [Summary](#org15cb32c)
    3.  [Notwes:](#orga46ba63)
        1.  [Terms](#org2a3d477)
        2.  [Problems](#org08b5565)
        3.  [Agnostic configuration](#org2173341)
        4.  [Mesh definition](#org55d9e06)
        5.  [Case studies](#orgc88c47a)
        6.  [Problems](#org94e2789)
        7.  [Where do you start?](#org96d3c4c)
    4.  [Questions](#org26c1d90)
4.  [Session 3: CircuitPython: Python on microcontrollers](#org6747cb4)
    1.  [Info](#org128555c)
    2.  [Summary](#org58ae881)
    3.  [Notes:](#org634decb)
        1.  [Where does your code run?](#orge1bc053)
        2.  [microPython](#org6205454)
        3.  [CircuitPython](#orgd480dc5)
        4.  [Hardware for CircuitPython](#org255e9a6)
        5.  [Community](#orgbcb92e0)
    4.  [Questions](#org4937465)
5.  [Session 4: Securing the cloud: How not to end up in the news](#orgad062d5)
    1.  [Info](#org1603f55)
    2.  [Summary](#org57e978b)
    3.  [Notes:](#org8b8cb75)
        1.  [Why are we here?](#org9dcc03e)
        2.  [Previous data breaches](#org97874ed)
        3.  [The Cloud really is secure](#org5e54ef8)
        4.  [What can we do?](#org0bcfd1b)
        5.  [Shared responsibility](#orga5ba5bf)
        6.  [Best practices](#orgfc4ff33)
    4.  [Questions](#org1acd709)
6.  [Session 5: Short on time? Accelerate your data science with GPUs](#orgbfae3b7)
    1.  [Info](#org3870562)
    2.  [Summary](#org58fca8d)
    3.  [Notes:](#org9562dca)
        1.  [When do you need a GPU?](#orgad610d3)
        2.  [Challenge: Day in a life of a data scientist](#orgf5338b5)
        3.  [Performance](#orgbf523ff)
        4.  [RAPIDS Ecosystem](#orgd5c0ce5)
        5.  [Conclusion](#org1d67a6e)
    4.  [Questions](#org2089ee8)
7.  [Session 6: How Design Systems can improve your design/engineering process](#orgb53821a)
    1.  [Info](#org71c64db)
    2.  [Summary](#org03bb8df)
    3.  [Notes:](#org8233736)
        1.  [When there is growth in a team](#org40fad92)
        2.  [Design Systems](#org24d222d)
        3.  [How to solve implementation issues](#orgc027a37)
        4.  [Component documentation](#org7980f01)
    4.  [Questions](#orgd3da361)
8.  [Session 7: Smart Community: What can we do to make this an actual reality](#org49a9db9)
    1.  [Info](#org5891424)
    2.  [Summary](#orgc866a1b)
    3.  [Notes:](#orgf18f48f)
        1.  [Smart city vs Smart Community](#orgdf0c8b3)
        2.  [Why become a smart community?](#org1b7af6d)
        3.  [What are we doing?](#org652ffca)
        4.  [What the taskforce is working on](#org142de06)
9.  [Session 8: fiasco.getInstance()](#org75a121e)
    1.  [Info](#orgcda2a3b)
    2.  [Summary](#org75225e7)
    3.  [Notes:](#org534df95)
        1.  [Singleton design pattern](#org6ec1eaa)
        2.  [Drawbacks](#org350c474)
        3.  [What problem is it trying to solve?](#org3d31fe9)
        4.  [How do you get around this problem?](#orgc8bca36)
        5.  [So why is it still used?](#org7e457ec)
        6.  [Code with empathy](#orgffd1413)


<a id="org189c7ea"></a>

# Introduction

This is a compilations of my notes on the talks I attended at Maritime Devcon 2019


<a id="orgccb652d"></a>

# Session 1: The Good Code


<a id="org1df9c91"></a>

## Info

-   Speaker: Chris Dail


<a id="orgf50d154"></a>

## Summary

Some pointers and tips on what good code is and how to write it.


<a id="org0df199b"></a>

## Notes:


<a id="org88e9c11"></a>

### Not good code

Don't repeat code.
Use the right tool.
Broken window effect:
  Bad code causes carelessness.
  Leads to more bad code.
  AKA If it is already bad, you probably won't do much to make it any better.


<a id="orgbc70630"></a>

### Good Code

1.  Qualities of good code

    -   Readability
        -   Why is this the most important?
            1.  you are not the only person that will be reading your code.
            2.  Future you will also have to read your code.
            3.  Reading vs Writing Code (70% / 30% when developing)
    -   Simple
        1.  Easily understood
        2.  Simple architecture and abstractions (low complexity)
        3.  One thing should do one thing
    -   No surprises
        -   Relates to simplicity.


<a id="orgbb4bcd4"></a>

### Deadlines

We plan to fix it in the next release, but that doesn't often happen.
Code reviews: don't let more bad code slip through.


<a id="org821bb76"></a>

### Quantity vs quality

average 15-50 bugs per 1000 lines of code
Therefore, less code means fewer bugs.
Cannot be done artificially

-   Needs to be readable
-   Quality - Fewer LOC, but make it more meaningful
-   Keep it simple


<a id="orgf0e7401"></a>

### Naming

Names should reveal the intent and have meaningful distinctions, no noisy (redundant) words.
Make it human readable/searchable. Follow conventions.

-   Variables/Classes: Nouns
-   Methods/Functions: Verbs, be descriptive and don't worry about length.
    -   Reading a function name should give you an idea of what it does.
-   Libraries/modules: Don't do things like utils, of course it is a util. Use something that describes what it does.


<a id="orgf395025"></a>

### Functions

-   Functions should do just one thing.
-   Keep them short (20 lines)
-   Avoid side effects (with global state)

1.  Classes and Objects

    -   The class should have one theme
    -   Single level of abstraction
    -   Avoid "Junk Drawer" classes (like a util class)

2.  Magic numbers

    -   Use constants defined in a single place to enhance readability.
    -   Explains what the number is.

3.  Comments

    -   Explains the intent of the code.
    -   Answer why, not what or how.
    -   Only add comments when it will enhance readability
    -   If you need to write a lot of comments, maybe the code should be refactored.
    -   Avoid redundant comments that just say what the code is doing.
    -   Avoid misleading comments that lie about what the code is doing.
    -   References to bug numbers should not be necessary, use vcs

4.  Version Control

    -   VC History should be treated like code
        -   It should be readable, you should be able to know what the purpose of the commit is from the name.
        -   Should read like a story
    -   Use Small commits
    -   Small PRs

5.  Formatting

    -   Keep files short
    -   keep lines short
    -   Low levels of indentation
    -   Use whitespace to separate paragraphs of code
    -   Vars should be declared close to where they are used.
    -   Instance variables at the top of class

6.  Error handling

    -   Exceptions should be exceptional
    -   Behave in reasonable ways instead of throwing errors
        -   EX/ Return an empty list when no records found
    -   Early return for invalid cases
    -   No empty catch blocks

7.  Scout Rule

    -   Leave it cleaner then when you found it.

8.  When in Rome

    -   Follow the code style of the codebase you are in
    -   Follow the conventions of the language
    -   It is important to keep the code consistent.
    -   Linters help with this.

9.  DRY - Don't repeat yourself

    -   Reuse code - Functions, Libraries, classes
    -   Redundant comments
    -   Multi-developer teams
        -   Duplication of validation/util functions
        -   Centralize and make reuse easy
        -   Always look before you write, someone may have already implemented it.

10. Copy and Paste

    -   Creates repetition
        -   You can duplicate a bug
    -   You may not understand the code being copied.
        -   If you don't fully understand the code you may be introducing a new bug
    -   Reuse with a function

11. Clever Code

    -   Be wary of "clever" code (aka, cute, magic)
    -   It is likely hard to read/debug
    -   The dull, straightforward way may be boring, but it can be better if it is easy to understand.
    -   Keep in mind the level of experience on your team

12. Why is it hard for people to write good code?

    -   BBC: Pillars of Computational Thinking
        -   Decomposition
        -   Abstraction
        -   Pattern recognition
        -   Algorithms
    -   Good code is more art then math
        -   Creating code that is easy to read and understand is more art then math
    -   Good code tells a story
        -   The code describes the application, it describes the purpose.
        -   The computer takes it literally, it may work but the computer can't determine the purpose


<a id="orgd7398e4"></a>

## Questions

1.  What about WIP commits when you need to switch over to work on something else
    -   You can make a WIP commit and don't push it, you can amend it later
    -   git stash
2.  What languages make good code easy?
    -   Not PHP or VB
    -   It depends on the developer
    -   Kotlin > Java, you can be more expressive
3.  A lack of understanding causes messier code.


<a id="org8dc7079"></a>

# Session 2: Mesh isn't just for the club (anymore)


<a id="orgd9ab5d1"></a>

## Info

-   Speaker: Josh Cormier


<a id="org15cb32c"></a>

## Summary

An overview of what a mesh network is and how it works. It covers mesh service, control planes, and proxies.


<a id="orga46ba63"></a>

## Notwes:


<a id="org2a3d477"></a>

### Terms

-   What is a distributed system?
    -   A group of related, yet independently resourced processes.
    -   Okay, but why?
        -   Resilience
            -   Fault tolerance
        -   Performance
            -   Horizontal scaling, More throughput
        -   Economics
            -   Scale up individual sections of the system
            -   Scale down lightly use apis
-   Microservices
    -   Services that do not share
        -   Different databases
        -   Not tightly coupled
        -   Can run independant of each other
        -   You should not need to deploy code in a certain order


<a id="org08b5565"></a>

### Problems

-   Coordination issues
    -   race conditions
    -   deadlock
    -   Handling dropped packets/network hostility
-   Deploy without downtime
    -   ability to make changes to specific services without side effects
-   Resilience
-   Configuration
-   Observability
    -   Monitoring
    -   Storage constraints on telemetry data


<a id="org2173341"></a>

### Agnostic configuration

-   A service is able to run regardless of where it is
-   Pulling metrics instead of pushing. (just have an endpoint)
-   Relying on the environment to transport telemetry.
-   examples:
    -   Docker logging to stdout
    -   Prometheus log pulling


<a id="org55d9e06"></a>

### Mesh definition

-   Noun: A weblike pattern or construction
-   Verb: to coordinate closely
-   Service mesh:
    -   Service level
    -   Data plane
    -   Control plane: Configuration, routing where things go.
    -   Service discovery and telemetry.
-   Each application container has a proxy that directs traffic on the mesh.
-   Mesh nodes (proxies) act like a load balancer for how instance a would connect with other instances.


<a id="orgc88c47a"></a>

### Case studies

-   Discoverability: The mesh control plane defines the architecture
-   Retry failure:
    -   4 layers deep with 5 retries at each level
    -   Load overwhelmed the second layer which lead to 5<sup>3</sup> retries per request.
    -   A single error would cause exponential requests
    -   Had to restart to flush queues
    -   How could a mesh have helped?
        -   All communication goes through the service mesh.
        -   Distributed circuit breakers managed by control plane (Stop new requests to a single instance/service to allow recovery)
    -   Resolution:
        -   Tried to disable retries
            -   The fix was in the code, not at the network layer.
        -   With a mesh service the proxy handles the retry logic. The service sends requests to the proxy.
-   Security: Encrypting traffic
    -   Moving from no encryption to having encryption
    -   All communications go through the service mesh, so the tls encryption can be handled without modifying the service or the host.
    -   Zero trust networking
-   New feature roll out
    -   Add now features in a safe manner
    -   Feature flags are okay, but they can be a cause of spaghetti code
        -   Controlling features on a per customer basis,
        -   Negatively effect readability
    -   Service mesh: Traffic distribution
        -   This has the ability to shape traffice
            -   A/B deployments
            -   Percentage based routing
            -   Tenant based routing
            -   Ghost Traffic
                -   Send a mirror traffic to a new version of the service to see how it is handled
                -   The mesh can discard responses from the mirrored service
        -   If there is a failure, not all of the requests are effected.


<a id="org94e2789"></a>

### Problems

-   Latency
    -   Unavoidable
    -   Adds extra hops
-   Resource cost
    -   A proxy is required for every instance of a service
    -   Just managing a mesh service will add resource cost on servers
-   Additional maintenance


<a id="org96d3c4c"></a>

### Where do you start?

1.  Pick a mesh service

    -   There is no industry standard
    -   It is a big investment, you could get locked in

2.  Open standards

    -   Mesh services
        -   SMI <https://smi-spec.io> (for K8s)
    -   Telemetry
        -   Opentelemetry (<https://opentelemetry.io>)


<a id="org26c1d90"></a>

## Questions

1.  What is the resiliency of a mesh?
    -   It depends on your orchestration system
    -   The service should be handling some errors
2.  How do you deploy to clusters?
    -   Helm
3.  Availability concerns of the mesh? What happens if the mesh fails?
    -   You can leave a failover configuration in the service.
    -   The orchestration layer should handle that.
4.  What are your thoughts on the depth of services and apis?
    -   Shouldn't go too deep, maybe 5? Each layer eats time.


<a id="org6747cb4"></a>

# Session 3: CircuitPython: Python on microcontrollers


<a id="org128555c"></a>

## Info

-   speaker: Dave Astels
    -   Freelances for Adafruit


<a id="org58ae881"></a>

## Summary

An overview of the origins of CircuitPython and the type of hardware that it can run on.


<a id="org634decb"></a>

## Notes:


<a id="orge1bc053"></a>

### Where does your code run?

-   Cloud?
-   Desktop?
-   Raspberry pi?
-   Microcontrollers? <&#x2013; YAS


<a id="org6205454"></a>

### microPython

-   It is a from-scratch implementation of Python 3.4 targetting MCUs
-   Supported by Micro:bit
-   Bytecode VM
-   JIT or AOT
-   Targeted for professional developers
    -   Can be awkward to use
    -   Not that easy for kids/teachers/beginners


<a id="orgd480dc5"></a>

### CircuitPython

-   Fork of microPython (By Adafruit)
-   Targetting Microchip/Atmel SAMD21/51
-   Aimed at education, beginners, makers, kids
-   Can be run on Pi with a shim layer
-   Features:
    -   Almost full python implementation, has most of the standard lib
    -   Easy to use
    -   REPL via USB/Serial
    -   MCU/SPI Flash shows up as USB
    -   The VM can auto-restart when files change
    -   Hardware abstractions to bring ease of use (abstract board pins and things like i2c)


<a id="org255e9a6"></a>

### Hardware for CircuitPython

-   Adafruit boards were the first
-   Arduino, Sparkfun, Particle
-   And many other independant boards
-   Some boards:
    -   Teensy M0 (SAMD21)
    -   CircuitPlayground Express (SAMD21)
        -   good for education
        -   has baked in hardware
            -   leds
            -   speaker
            -   ir
            -   alligator clip friendly
    -   Feather M4 Express (SAMD51)
    -   Feather M4 AirLift (SAMD51)
        -   Built-in ESP32 for wifi
    -   PyPortal (SAMD51)
        -   Also has ESP32 for Wifi
        -   The bottom side is a tft touchscreen (<https://www.adafruit.com/product/4116>)
    -   MetroM4 Grand Central (SAMD51)
        -   Arduino Mega form factor
    -   PyGamer (SAMD51)
        -   Made to be a game platform


<a id="orgbcb92e0"></a>

### Community

-   Learning guides on Adafruit (<https://learn.adafruit.com/>)
-   Discord server (<https://adafru.it/discord>)
-   Forums (<https://forums.adafruit.com/>)
-   Github (<https://github.com/adafruit/circuitpython>)


<a id="org4937465"></a>

## Questions

1.  Where can you buy the hardware?
    -   BJW Electronics in Moncton
    -   adafruit.com
    -   buyapi.ca
2.  Can it run Numpy?
    -   Maybe???
3.  Is there mechanisms for hardware interrupts?
    -   No, not yet, but it is supported in microPython
4.  Is there anything more than print statements for debugging? Maybe interactive debugging?
    -   No, there isn't due to resource restrictions.
    -   It is mostly just print statements.


<a id="orgad062d5"></a>

# Session 4: Securing the cloud: How not to end up in the news


<a id="org1603f55"></a>

## Info

-   Speaker: Matt Taylor
    -   Works at Akiri
-   slides: <https://github.com/matt-taylor-nb/securing-the-cloud>


<a id="org57e978b"></a>

## Summary

An overview of security tools available on AWS and how to use them.


<a id="org8b8cb75"></a>

## Notes:


<a id="org9dcc03e"></a>

### Why are we here?

-   This is about securing cloud platforms
-   This is not about writing secure code/applications
-   What will be covered:
    -   Look at some breaches
    -   Common security misconceptions
    -   Best practices
    -   Look at some AWS native tools


<a id="org97874ed"></a>

### Previous data breaches

1.  Reasons to use the cloud

    -   Easy
    -   cost efficient
    -   secure
    
    But is it that secure?

2.  Accenture

    -   Lost data from open S3 buckets
    -   Fixed it in one day

3.  GoDaddy

    -   Unprotected S3 bucket
    -   GoDaddy did not respond to the researcher

4.  SpyPhone

    -   Unprotected S3 Bucket

5.  Facebook

    -   third party company, 540+ Mil user accounts

6.  NS government

    -   Teen took advantage of Freedom of Information portal
    -   Incrementing id
    -   250 raw, unredacted documents were attained


<a id="org5e54ef8"></a>

### The Cloud really is secure

-   AWS itself hass never been compromised
-   All of the above mentioned breaches were the result of poor configurations
-   AWS provides the building blocks, they are secure, but people can use them in an insecure way.


<a id="org0bcfd1b"></a>

### What can we do?

-   Understand what your responsibility is in the Cloud
-   Ask lots of questions
-   Don't leave your s3 bucket open
    -   The default is now private (previously it was public)
-   remember that security is everyone's responsibility


<a id="orga5ba5bf"></a>

### Shared responsibility

-   AWS is responsible for security of the cloud
-   We are responsible for security in the cloud


<a id="orgfc4ff33"></a>

### Best practices

1.  AWS Account Setup

    -   Use a group email address
        -   This will be the root account, it will have access to everything
        -   If it is an individual email, that person will own the account
    -   Use a company phone number
    -   Configure alternate contact info
        -   Billing, security, etc
    -   Answer all Security Challenge Question
        -   For recovering the account.

2.  User Accounts

    -   Lock away the Root account
        -   It should only be used for initial setup
    -   Use individual IAM User accounts, NEVER share accounts.
        -   This will be used for day to day activities
        -   Assign permissions based on usage
        -   Permissions are granted as a white list, by default all permissions are denied
    -   Operate under a least privileged mode for accounts
    -   Assign permissions to groups and add users to groups
    -   Have a documented plan for user creation, permission change, and user removal

3.  Infrastructure

    -   Don't open to the public internet anything that doesn't need it
    -   Separate your workload into private networks
        -   Using VPCs
    -   Encrypt and backup your data
    -   Avoid snowflake deployments
        -   Keep your configuration in code
            -   EX/ Terraform
    -   Have an approval process for new infrastructure
        -   Doesn't need to be a huge thing, but a sanity check is good.
    -   Look up Service Best Practices
        -   There are 150 different services on AWS, know how to best use each of them
    -   Use instance profiles instead of credentials
        -   They work like user accounts in IAM
        -   It authenticates through the IAM service
        -   You can restrict access to different services
        -   Removes the need for hardcoded credentials

4.  Monitering/Auditing/Reporting

    -   CloudTrail, an infrastructure auditing service
        -   It records actions taken in AWS
    -   To get alerts from CloudTrail configure it to use cloudwatch
        -   You can use this to set alarms based on security events
    -   Use AWS Config
        -   Allows you to set AWS wide rules (Like banning public S3 buckets)
        -   It will send an alert when the rules are being broken
    -   Use Guard Duty
        -   AWS IDS
    -   Test your security

5.  Extra credit

    -   Use a third party service to test your security
    -   Verify the security of any 3rd parties that you trust your data with
        -   Many breaches come from third party companies
        -   It doesn't matter who the third party is, it is your data, you are responsible (that is how the public will see it)
    -   Use AssumeRole for access
        -   Cross-Account Access
        -   This is how you use multiple accounts
        -   You can have all logging in a separate account
    -   Use separate AWS Accounts for workload
        -   Different one for development, staging, and productio
    -   Trusted Advisor
        -   Gives advice on your setup.
        -   Tells you if you are violating best practices


<a id="org1acd709"></a>

## Questions

1.  When do we use AssumeRole?
    -   If you are using multiple accounts for managing AWS you should definitely look into AssumeRole.


<a id="orgbfae3b7"></a>

# Session 5: Short on time? Accelerate your data science with GPUs


<a id="org3870562"></a>

## Info

-   Speaker: Axel-Christion Guei
    -   Machine learning specialist at Teledyne Caris


<a id="org58fca8d"></a>

## Summary

A walkthrough of how using RAPIDS and GPUs can increase the productivity of data scientists.


<a id="org9562dca"></a>

## Notes:


<a id="orgad610d3"></a>

### When do you need a GPU?

-   When training a DNN
-   Playing video games
-   Mining bitcoin


<a id="orgf5338b5"></a>

### Challenge: Day in a life of a data scientist

1.  Goal: Identify astropysical sources in the night sky

2.  Datasets:

    -   set of metadata containing 11 features describing each object
    -   Time series observations with 6 features /object
    -   19 GB of data
    -   14 different astrophysical objects to detect.

3.  Tasks:

    -   Define performance goal
    -   Conduct data analysis and ETL
    -   Train several ML models
    
    ETL: Extract Transform Load
    
    -   Extract the data from a source
    -   Transform the data so it is meaningful
    -   Load the data into a destination

4.  A cause of slowness

    -   Too many data transfers between CPU and Memory

5.  A solutiong: GPUs

    -   Software stacks:
        -   Hadoop (job distribution framework)
        -   Spark (in-memory processing)
        -   Nvidia Rapids (GPU framework)
    -   Rapids loads the data directly into the GPU memory, so there is less overhead there.


<a id="orgbf523ff"></a>

### Performance

Using on GPU the data loading time is drastically reduced.
The GPU trained about 5 times faster than the CPU.


<a id="orgd5c0ce5"></a>

### RAPIDS Ecosystem

-   Numba
-   CuPy
-   Dask (allow jobs to be distributed)


<a id="org1d67a6e"></a>

### Conclusion

1.  Pros

    -   More than 100% performance boost
    -   More cost effective then large cpu clusters
    -   Easy integration with popular DL frameworks
    -   Highly scalable
    -   Python API available

2.  Cons

    -   High GPU memory usage
    -   cuDF does not cover all pandas API yet


<a id="org2089ee8"></a>

## Questions

1.  Can we use this on a GPU instance?
    -   Yes, there are images available on AWS


<a id="orgb53821a"></a>

# Session 6: How Design Systems can improve your design/engineering process


<a id="org71c64db"></a>

## Info

-   Speaker: Kolton Gagnon
    -   Works at Cvent


<a id="org03bb8df"></a>

## Summary

An overview of how you can use a design system to improve the consistency and efficiency of the design and development process.


<a id="org8233736"></a>

## Notes:


<a id="org40fad92"></a>

### When there is growth in a team

Without having a process in place for design there can be design rot. An increased team size can increase complexity.


<a id="org24d222d"></a>

### Design Systems

-   Figma
-   Highly reused components can be turned into master components.
-   Changes to the component will change in all instances of the component.
-   Changes can be published to your team

Using this there is increased efficiency, consistency, and structure


<a id="orgc027a37"></a>

### How to solve implementation issues

-   There are inconsistencies between the design and the code
-   Options:
    1.  A components folder
        -   What happens when more projects need to use these components?
        -   Copy and pasting is probably going to happend
    2.  Components Repo + NPM
        -   That way the components can be installed by NPM
        -   There are issues if the everything is in one NPM package then they all need to be upgraded with one version.
    3.  How does React do it?
        -   Use separate versions for each components in the repo
        -   You can use Lerna to manage npm versions


<a id="org7980f01"></a>

### Component documentation

-   Storybook creates a library for each and every component
-   You can change the props of a component using Knobs
-   Documentation can be embeded in notes
-   Figma designs can be integrated into storybook


<a id="orgd3da361"></a>

## Questions

1.  Can you change the colour of your component based on where it is used?
    -   Yes, you can set it to take a theme


<a id="org49a9db9"></a>

# Session 7: Smart Community: What can we do to make this an actual reality


<a id="org5891424"></a>

## Info

-   Speaker: Book Sadprasid
    -   Works for Ignite Fredericton


<a id="orgc866a1b"></a>

## Summary

What Fredericton is doing to be a more tech savvy city


<a id="orgf18f48f"></a>

## Notes:


<a id="orgdf0c8b3"></a>

### Smart city vs Smart Community

-   What is the difference?
    -   Smart city: makes cities work better.
        -   Greater efficiency in municipal services
        -   focused on technology
    -   Smart community: Making better cities
        -   Make the lives of the citizens better
        -   Focused on Community and growth

Smart communities use technology as a means to an end, putting more effort into

-   Developing a workforce
-   Crafting an innovation ecosystem
-   Expanding access to digital skills and tech
-   Engaging citizens and businesses

Smart communities are all about the people


<a id="org1b7af6d"></a>

### Why become a smart community?

-   better parking
-   better energy management
-   better real-time services


<a id="org652ffca"></a>

### What are we doing?

-   Digital Fredericton project
    -   Putting more services online
    -   Working with tech companies like Hotspot parking


<a id="org142de06"></a>

### What the taskforce is working on

1.  Building on digital Fredericton

    -   Establish development zones
        -   labs, sandboxes, centres of excellence
    -   Early adoption policies
    -   Open data concepts
    -   Align with academia
    -   Analyze elements for economic growth
    -   Digital product development zone

2.  Digital product development living lab

    Use the city of Fredericton as a test bed for tech companies

3.  Collaborations and citizen involvement

    -   Fred-e Hack
        -   Smart city hackathon
        -   using iot sensor network


<a id="org75a121e"></a>

# Session 8: fiasco.getInstance()


<a id="orgcda2a3b"></a>

## Info

-   Speaker: Colin Casey


<a id="org75225e7"></a>

## Summary


<a id="org534df95"></a>

## Notes:


<a id="org6ec1eaa"></a>

### Singleton design pattern

-   Protected constructor
-   Static getInstance() method


<a id="org350c474"></a>

### Drawbacks

-   Global state
-   Un-testable code
-   hidden dependencies

The singleton is an antipattern. 


<a id="org3d31fe9"></a>

### What problem is it trying to solve?

In a project there can be a large object dependency graph.
Adding a singleton does not need to make large changes to that graph. The singleton is a dependency, but it will be hidden from you in that dependency graph.


<a id="orgc8bca36"></a>

### How do you get around this problem?

Use dependency injection.


<a id="org7e457ec"></a>

### So why is it still used?

-   Managing objects is hard
-   :shrug: it works


<a id="orgffd1413"></a>

### Code with empathy

-   Your code will likely be used/maintained by others
-   Implementing a singleton may negatively impact one of those people.
-   Using a singleton is like peeing in the pool.

