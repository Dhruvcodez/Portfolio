# AI-Orchestrated F1 Telemetry: Real-Time Pit-Wall Dashboard 🏎️📊

> *Note: To protect proprietary portfolio code from direct duplication, the raw source code for this live data pipeline is kept private. A full technical walkthrough, architecture review, and code breakdown are available upon request.*

## The "AI Orchestrator" Approach
I am not a traditional software developer; I operate as an AI Generalist and Systems Orchestrator. This real-time, full-stack data visualization pipeline was built without manually writing the underlying syntax or solving complex mathematical equations. 

Instead, I acted as the Product Manager and Systems Architect. I defined the business logic, mapped out the data-flow requirements, and directed Large Language Models (LLMs) to generate, test, and deploy the functional system. This project demonstrates how non-technical strategists can leverage AI as a collaborative engineering partner to deliver complex, production-grade applications from scratch.

## System Architecture (The Data Flow)
The goal was to mirror a professional Formula 1 pit-wall telemetry feed with zero perceived latency. The system runs on a clean, four-tier architecture:

1. **The Ingestion Layer (UDP Listener):** The F1 simulation engine broadcasts high-frequency raw telemetry packets over the local network (UDP port `20777`).
2. **The Processing Layer (Python Backend):** A multithreaded Python server intercepts the binary stream, parses packet headers, and normalizes complex nested data structures (such as mapping custom C-type objects and handling legacy F2 compound IDs).
3. **The Transport Layer (Server-Sent Events):** Uses a lightweight HTTP SSE stream (`/stream`) rather than heavy bi-directional WebSockets, perfectly optimized for continuous, unidirectional server-to-client telemetry broadcasts.
4. **The Presentation Layer (Vanilla Frontend):** A high-performance web dashboard built with HTML5 Canvas and CSS Grid that updates smoothly at native browser refresh rates.

## Key Features
* **2x2 Dynamic Tyre Matrix:** Independent, real-time temperature tracking for all four wheels, dynamically color-coding (Blue -> White -> Red) based on cold, optimal, and overheating operating thresholds.
* **Smart Tyre Compound Detection:** A dynamic UI badge that accurately resolves tire compounds (Soft, Medium, Hard, Intermediate, Wet) across different racing categories (F1 vs. F2).
* **Live Speed & Input Trace:** A rolling telemetry canvas tracking vehicle speed, throttle application, and braking inputs over a continuous time window.
* **Session & Delta Tracking:** Real-time sector splits, lap history logs, and live delta comparisons against session benchmarks.

## AI Collaboration & Problem Solving
The primary engineering hurdles involved debugging asynchronous data flows and unexpected schema behaviors. Here is how I orchestrated solutions:
* **Resolving the F2 Compound Mismatch:** The dashboard initially failed to display F2 tire compounds correctly. By analyzing how different categories format their data, I recognized that F2 cars omit modern visual paint IDs in favor of raw chemical IDs. I directed the AI to write a robust fallback routing algorithm that dynamically maps F2 chemistry without breaking F1 visual tracking.
* **Probing the "Black Box" Temperature Bug:** When implementing individual wheel temperatures, the data flatlined. Rather than digging through code syntax, I instructed the AI to build a raw memory probe script. By analyzing the output together, we discovered the library mapped temperatures to custom named objects (`FL`, `FR`, `RL`, `RR`) instead of standard arrays. I then orchestrated a targeted rewrite of the extraction logic to resolve the mismatch instantly.

## Technical Specifications
* **Language & Runtime:** Python 3.8+, Flask
* **Communication Protocol:** Server-Sent Events (SSE) at 10 Hz update frequency
* **Frontend:** Vanilla JavaScript, HTML5 Canvas, CSS Grid
