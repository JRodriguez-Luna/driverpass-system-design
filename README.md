# DriverPass System Design Project

**Course:** CS 255 – System Analysis and Design  
**Institution:** Southern New Hampshire University  
**Type:** Academic Project

---

## Overview

DriverPass is a fictional company that wanted a web-based platform to help customers prepare for and pass their DMV driving tests. This project involved working through the full systems analysis and design lifecycle — from gathering client requirements to producing a complete set of UML diagrams and a technical system design document.

The goal was not to build the application, but to **design it properly** — understanding what the client needed, translating that into system requirements, and communicating the architecture through industry-standard UML diagrams.

---

## What's in This Repo

| File | Description |
|------|-------------|
| `CS 255 Client Presentation - Submit.pptx` | Slide deck summarizing the client's needs and proposed system |
| `CS 255 System Design Document - Submit.pdf` | Full system design document including all UML diagrams and technical requirements |
| `UML Use Case Diagram.pdf` | Standalone use case diagram showing system actors and interactions |
| `Module Seven - UML Activity Diagram.jpeg` | Activity diagrams for user registration and lesson scheduling flows |

---

## System Summary

The DriverPass platform was designed to support:

- **Customer account registration** with payment processing
- **Lesson scheduling** with automatic driver and vehicle assignment
- **Practice tests** with progress tracking
- **Admin controls** for managing users, drivers, vehicles, and reports
- **DMV content sync** to keep test material current

### Actors
- **Customer** – registers, purchases packages, schedules lessons, takes practice tests
- **Admin (Liam)** – manages accounts, assigns drivers/vehicles, generates reports
- **Employee** – assists with scheduling and customer support
- **DMV** – external system that provides updated content
- **Third-Party Payment** – external payment processor (e.g., Stripe/PayPal)

---

## UML Diagrams Included

### Use Case Diagram
Shows all system actors and the actions they can perform, including `<<extends>>` relationships for payment processing and report downloading.

### Activity Diagrams
Two flows are modeled:
1. **User Registration** – from visiting the site → filling personal info → payment approval → account creation
2. **Schedule a Lesson** – from login → selecting a date/time → availability check → reservation confirmation

### Sequence Diagram
Models the "Schedule a Lesson" interaction step-by-step across four participants: Customer, System, Database, and Driver/Vehicle.

### Class Diagram
Defines the core data model with these classes and their relationships:
- `Customer` → makes → `Reservation`
- `Customer` → purchases → `Lesson Package`
- `Reservation` → assigned → `Driver`
- `Reservation` → uses → `Vehicle`
- `Customer` → takes → `Practice Test`
- `Administrator` → manages → `Vehicle`

---

## Proposed Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | React |
| Backend | Node.js + Express |
| Database | PostgreSQL |
| Hosting | AWS (cloud-based, no on-premise servers) |
| Payments | Stripe or PayPal |
| Security | HTTPS encryption |

The PERN stack was selected for its scalability, cross-device compatibility, and ease of integration with third-party APIs like payment processors and the DMV.

---

## Skills Demonstrated

- **Systems Analysis** – translating a client interview into functional and non-functional requirements
- **UML Diagramming** – use case, activity, sequence, and class diagrams
- **Software Architecture** – proposing a tech stack and cloud infrastructure appropriate to business needs
- **Technical Documentation** – writing a structured system design document for a development team

---

## Notes

This is a design-only project. No code was written as part of this assignment. The diagrams and documents represent the analysis and design phases of the software development lifecycle (SDLC).
