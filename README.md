# ResearchAI 🔬🤖

<p align="center">
  <strong>Autonomous, Evidence-Grounded AI Research Agent for Android</strong>
</p>

<p align="center">
  <em>Turn complex research questions into structured, verified scientific investigations with verifiable provenance, citation tracking, and live agent orchestration.</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" alt="Platform: Android" />
  <img src="https://img.shields.io/badge/Kotlin-2.2.10-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white" alt="Kotlin" />
  <img src="https://img.shields.io/badge/Jetpack%20Compose-Material%203-4285F4?style=for-the-badge&logo=jetpackcompose&logoColor=white" alt="Jetpack Compose" />
  <img src="https://img.shields.io/badge/Target%20SDK-API%2037%20(Android%2017)-E37400?style=for-the-badge" alt="API 37" />
  <img src="https://img.shields.io/badge/Backend-FastAPI%20%7C%20Python-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="Backend" />
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License: MIT" />
</p>

---

## 🌟 Overview

**ResearchAI** is an advanced, production-oriented AI research agent system built natively for Android. 

Unlike conventional conversational chatbots that present unverified answers, **ResearchAI** executes a structured, observable scientific research loop:
1. **Hypothesis & Query Formulation**: Breaks ambiguous questions into concrete objectives and constraints.
2. **Task Graph Planning**: Creates dependent research tasks with bounded execution and error recovery.
3. **Scholarly Retrieval**: Gathers academic literature, clinical trials, and domain-specific papers (e.g., Europe PMC, PubMed).
4. **Evidence & Trust Layer**: Extracts claims, maps statements to exact source passages, and flags contradictory findings or knowledge gaps.
5. **Synthesis & Reporting**: Generates citation-backed, versioned research reports with full audit logs.

> 🛡️ **Core Design Principle**: The agent never presents unverifiable assertions. Every finding records what tools actually executed, raw source metadata, extraction provenance, and associated confidence metrics.

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│             Android Client (Kotlin + Jetpack Compose)       │
│    Screens · Navigation · ViewModels · Live Agent Monitor   │
└──────────────────────────────┬──────────────────────────────┘
                               │ HTTPS / JSON & SSE
┌──────────────────────────────▼──────────────────────────────┐
│                  Backend API Gateway (FastAPI)              │
│       Request Validation · Auth Tokens · Session Router     │
└──────────────────────────────┬──────────────────────────────┘
                               │
┌──────────────────────────────▼──────────────────────────────┐
│                    Research Orchestrator                    │
│    Planner ──▶ Task Graph ──▶ Tool Execution ──▶ Synthesis  │
└──────────────┬───────────────────────────────┬──────────────┘
               │                               │
┌──────────────▼──────────────┐ ┌──────────────▼──────────────┐
│        Research Tools       │ │      Persistent Storage     │
│ Scholarly Search · PMC/ArXiv│ │ Projects · Tasks · Evidence │
│ Claim Extractor · Comparator│ │ Scoped Memory · Documents   │
└─────────────────────────────┘ └─────────────────────────────┘
```

---

## ✨ Key Features

- **📱 Sleek, Modern Mobile Workspace**: Developed with modern Material 3 and dynamic theming, optimized for edge-to-edge layouts and phone/tablet form factors.
- **🧭 Transparent Orchestration**: Inspect the active planner, dependency graph, running tools, and execution timelines in real time.
- **📑 Evidence Explorer**: Review cited abstracts, DOI identifiers, author credentials, and opposing claims side-by-side.
- **🗂️ Project & Version Management**: Full version history, project restoration, and reproducible research trails.
- **🔒 Zero-Leak Security Architecture**: API keys, credentials, and privileged tools execute exclusively on the backend—never bundled inside the client APK.

---

## 📁 Repository Layout

```
ResearchAI/
├── app/                                    # Android Application
│   ├── src/main/
│   │   ├── AndroidManifest.xml             # Manifest & system permissions
│   │   └── java/com/example/researchai/
│   │       ├── MainActivity.kt             # Application entry point
│   │       ├── ResearchAIApp.kt            # App root composable
│   │       ├── navigation/                 # Navigation graphs & routes
│   │       │   └── AppNavigation.kt
│   │       ├── screens/                    # Screen composables & views
│   │       │   └── HomeScreen.kt
│   │       └── ui/theme/                   # Theme, Color palettes, Typography
│   └── build.gradle.kts                    # App-level build script (Gradle Kotlin DSL)
│
├── gradle/
│   ├── libs.versions.toml                  # Version Catalog for centralized dependencies
│   └── wrapper/                            # Gradle wrapper binaries
│
├── backend/                                # Planned Python FastAPI Orchestration Engine
│   ├── app/
│   │   ├── agent/                          # Planning & execution engines
│   │   ├── tools/                          # Scholarly search & extraction tools
│   │   └── api/                            # REST & Streaming endpoints
│
├── LICENSE                                 # MIT License
└── README.md
```

---

## 🚦 Roadmap & Milestone Status

| Phase | Description | Status |
| :---: | :--- | :---: |
| **Phase 1** | **Android Foundation & Build Stability**<br>Resolve overloads, establish `AppNavigation`, verify `Pixel 8` APK build. | **Completed ✅** |
| **Phase 2** | **Screen Architecture & Jetpack Navigation**<br>Type-safe navigation routes, Dashboard, Workspace, Evidence, Reports. | **In Progress 🔄** |
| **Phase 3** | **State Management & Clean Architecture**<br>ViewModels, UI state models, Repository patterns, Coroutines & Flow. | *Planned* |
| **Phase 4** | **FastAPI Backend Foundation**<br>Async API gateway, health checks, schemas, and local test harness. | *Planned* |
| **Phase 5** | **Database & Authentication**<br>PostgreSQL persistence, users, research runs, claims, and event logs. | *Planned* |
| **Phase 6** | **Deterministic Research Agent**<br>Task graph builder, tool executor, bounded execution limits. | *Planned* |
| **Phase 7** | **Scholarly Search & Evidence Layer**<br>Europe PMC / PubMed tool integrations, claim-to-passage mapping. | *Planned* |
| **Phase 8** | **Live Streaming & Memory**<br>SSE real-time events, activity feed, scoped project memory. | *Planned* |
| **Phase 9** | **Reports & Publication Export**<br>Markdown & PDF export, hypothesis logs, citation bibliographies. | *Planned* |
| **Phase 10** | **Hardening & Production Deployment**<br>Security audits, rate limiting, CI/CD, signed release builds. | *Planned* |

---

## 🛠️ Getting Started

### Prerequisites

- **Android Studio**: Ladybug / Koala Feature Drop or newer.
- **Java Development Kit**: JDK 17 or JDK 21.
- **Android SDK**: Compile SDK 37 (Android 17 / Vanilla Ice Cream / Cinnamon Bun).
- **Test Device / Emulator**: Pixel 8 AVD recommended.

### Building from Source

1. **Clone the repository**:
   ```bash
   git clone https://github.com/kit29-25bad095/ResearchAI.git
   cd ResearchAI
   ```

2. **Build the Debug APK**:
   ```bash
   # On Windows (PowerShell / Command Prompt)
   .\gradlew assembleDebug

   # On macOS / Linux
   ./gradlew assembleDebug
   ```

3. **Run Unit Tests**:
   ```bash
   .\gradlew testDebugUnitTest
   ```

4. **Launch on Connected Device or Running Emulator**:
   ```bash
   .\gradlew installDebug
   ```

---

## 🤝 Contributing

Contributions, feedback, and architectural discussions are welcome!
1. Fork the Project.
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`).
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`).
4. Push to the Branch (`git push origin feature/AmazingFeature`).
5. Open a Pull Request.

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.
