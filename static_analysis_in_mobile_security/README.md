Background Context

Mobile applications are among the most widely used software in the world - and among the most targeted. Every APK contains layers of compiled bytecode, native libraries, resource files, and configuration data that together define how an application behaves. Understanding these layers is a fundamental skill for any mobile security professional.

Static analysis lets you examine an application's structure, permissions, and logic without ever running it. Combined with dynamic analysis -monitoring function calls, memory operations, and runtime behavior, you gain a complete picture of what an application is truly doing, beyond what its interface suggests.

In this project, you will work directly with real APK files. You will decompile bytecode, analyze native libraries, inspect manifest files, and reverse engineer obfuscated code using industry-standard tools. You will learn how attackers find hidden methods, extract secrets, and identify vulnerabilities and how defenders use the same techniques to harden applications before they ship. By mastering both static and dynamic analysis, you will be equipped to assess the security of any Android application, uncover hidden risks, and understand the full attack surface of mobile software.

"You cannot secure what you do not understand."

Resources
Read or watch:

    intro-to-mobile-app-pentesting-static-analysis-tools
    Static Analysis on Android
    Mobile Pentest Static Analysis Tools
    Mitigate OWASP Top 10 Android Risks with Static Analysis
    OkHttp
    Mobile App Security Testing with MobSF
    Mobile pen-testing training - Static Code Analysis

Tools

Dynamic Analysis Tools:

    Frida Official Site
    GDB
    Ghidra
    IDA Pro

Android Studio

    Android Studio

APK Analysis Tools:

    APKTool
    jadx
    Dex2jar GitHub
    JD-GUI Official Site

Programming and Scripting:

    Python

Learning Objectives

At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

    How can you use reverse engineering tools to analyze native libraries and APK bytecode?
    What techniques help in extracting and understanding obfuscated or optimized code?
    How do you decompile and analyze an APK file to find vulnerabilities or hidden methods?
    What role do resources and manifest files play in understanding an app’s structure?
    How can dynamic analysis tools monitor function calls and memory operations during runtime?
    How do you use profiling tools to detect performance issues or vulnerabilities?
    How do you debug and profile native code to detect memory leaks or errors?
    How do you use debugging tools with native and Java code to uncover potential security flaws?
    How does static analysis help identify security risks in mobile applications?
    How do you analyze obfuscated APKs and overcome challenges in their reverse engineering?
    How do you ensure the security and integrity of your analysis process?

Requirements
General

    Allowed Tools: Ghidra, JADX, APKTool, Frida, IDA Pro, Android Studio Profiler, Valgrind, GDB, Python, NumPy, JMH.
    Environment: All analyses should be conducted on an Android emulator or a physical device within a secure, controlled environment.
    Backup: Regularly back up APK files, scripts, and key data before and during the analysis process.
    Execution Compatibility: Ensure all scripts and tools can be executed and run on Kali Linux or a compatible analysis environment.
    Path Management: Use relative paths for all file references to avoid dependency on hardcoded paths.
    Integrity Checks: Validate APK and binary integrity before analysis to prevent issues due to corrupted or tampered files.
    Tool Configuration: Configure all monitoring and network tools correctly, including proxy and certificate settings, before beginning the analysis.
    Documentation: Maintain organized, clear, and detailed documentation for each step of the analysis, including findings and tool usage.
    Focus: Concentrate your analysis on the designated APK provided for the project.
    Local Execution: All work must be completed within the secure environment on the local machine or emulator; use of online tools or cloud services is not permitted for this project.
