# Khala Event Platform

Welcome to the Khala Event Platform! 🚀 This project is a complete, full-stack event management system built on a modern, cloud-native microservices architecture. It allows users to discover, view, and register for events through a seamless and responsive web interface. The entire platform is designed for scalability, maintainability, and is fully deployed on Microsoft Azure.

This project was developed as a ky-education (EC-Ubtildningar) assignment for the "Cloud Services and Distributed Systems" course, with the ambitious goal of meeting the criteria for a "Godkänd" (G), or "VG-level"—the highest grade.

<https://ecutbildning.se/>

---

## What is Khala?

The Khala platform is composed of a frontend application and a suite of specialized backend microservices that work together to deliver a feature-rich user experience.

* **Frontend (Ventixe):** A sleek and modern user interface built with Next.js and React. It provides a platform for users to browse events, view details in non-intrusive modals, and sign up for event packages.
* **Backend Microservices:** A collection of four independent, single-responsibility services built with .NET and ASP.NET Core. They handle specific business domains like events, images, and locations.

The architecture is designed to be robust and scalable, leveraging the power of distributed systems to ensure that each part of the application can be developed, deployed, and scaled independently.

---

## The Origin: A G-Level Ambition

This project was created to fulfill the requirements of a university-level course on cloud services and distributed systems. The primary objective was to build a Minimum Viable Product (MVP) of an event system based on a microservices architecture. The challenge was to interpret a provided design file and make informed decisions on the features and technology required for a fully functional, high-quality application.

The goal was to go beyond the basic requirements and strive for a "G-level" (Godkänd) submission by implementing  concepts such as:

* **Known Design Patterns:** Applying Clean Architecture, Repository, and Factory patterns.
* **Robust Security:** Securing APIs and sensitive data using Azure Key Vault and API keys.
* **Advanced Features:** Implementing user authentication with email verification.
* **Full CI/CD Automation:** Setting up automated deployment pipelines for all services.

---

## Architecture and System Components

The Khala platform is built on a microservices architecture. The frontend application, **Ventixe**, acts as the user's entry point and communicates with the backend services through a Backend-for-Frontend (BFF) layer, which is securely managed by Azure API Management.

### 1. **Ventixe** (Frontend)
The user-facing application, providing the complete event discovery and registration experience.
* **Technology**: Next.js 15, React 19, TypeScript, Tailwind CSS.
* **Key Features**:
    * **BFF Pattern:** Next.js API routes act as a secure proxy to the backend microservices.
    * **Dynamic UI:** Uses SWR for real-time data fetching, caching, and state management.
    * **Modern UX:** Features intercepted routes for modal dialogs, creating a fluid user experience without page reloads.
    * **Deployment:** Hosted on Azure Static Web Apps with a CI/CD pipeline in GitHub Actions.

### 2. **Forge** (Event Service)
The core service for managing event data.
* **Technology**: .NET 9, ASP.NET Core, Entity Framework Core, Azure SQL.
* **Responsibility**: Manages all data related to events and their associated packages.
* **Architecture**: Follows Clean Architecture principles to keep business logic independent of infrastructure concerns.

### 3. **CloakVision** (Image Service)
A dedicated service for managing and serving images securely.
* **Technology**: .NET 9, ASP.NET Core.
* **Responsibility**: Handles image metadata and provides secure, temporary access to images stored in **Azure Blob Storage** by generating Shared Access Signature (SAS) URLs.

### 4. **NexusPoint** (Location Service)
A microservice responsible for providing location data for events.
* **Technology**: .NET 9, ASP.NET Core, Entity Framework Core, Azure SQL.
* **Responsibility**: Manages and serves location information, which is linked to events in the Forge service.

### 5. **VoidMail** (Email Service - *Implied*)
Though not detailed, a service like `voidmail/api/` is part of the architecture, responsible for handling transactional emails, such as sending information regarding event and packages.

---

## 🤖 A Note on AI-Powered Development

Transparency is a core value of this project. It's important to acknowledge the significant role that AI, specifically Google's Gemini Pro, played throughout the development process.

Rather than simply generating code, the AI acted as a **co-pilot and programming partner**. This collaboration involved:

* **Problem-Solving:** Working through complex logical challenges and debugging issues.
* **Architectural Discussion:** Serving as a sounding board for design decisions and exploring alternative approaches.
* **Best Practice Advice:** Providing guidance on industry standards, security, and optimal implementation strategies.
* **Documentation generation using Copilot inside VsCode and Github information generation using Google Pro Gemini, like this text for an example.**

While AI helped accelerate the creation of initial documentation and boilerplate code, the final implementation was a human-driven effort. The AI's primary contribution was to elevate the development process by facilitating deeper technical discussions and ensuring a high-quality, well-architected final product. This project demonstrates a modern workflow where human architectural vision is enhanced and refined through a collaborative partnership with artificial intelligence.
