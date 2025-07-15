# Software Requirements Specification (SRS)

**Project:** SnapFox  
**Version:** 1.0  
**Date:** July 15, 2025  
**Author:** Tab

---

## 1. Introduction

### 1.1 Purpose
This Software Requirements Specification (SRS) describes all requirements for SnapFox, a Firefox browser extension designed to capture and professionally edit screenshots directly within the browser. The document serves as a contract between stakeholders and the development team, providing a clear, unambiguous description of functional and non‑functional requirements.

### 1.2 Scope
SnapFox will enable users to quickly capture screenshots (full page, viewport, selected element, or free‑form area) and annotate them with text, arrows, shapes, and styling options. Screenshots can be copied to the clipboard or shared via popular applications such as Gmail, WhatsApp, and Facebook. The first release targets Firefox; future versions aim to support other browsers and integration with Visual Studio Code.

### 1.3 Definitions, Acronyms, and Abbreviations
- **SnapFox:** The Firefox extension described by this SRS.
- **FR:** Functional Requirement.
- **NFR:** Non‑Functional Requirement.
- **UI:** User Interface.
- **API:** Application Programming Interface.
- **DOM:** Document Object Model (web page structure).

### 1.4 References
- IEEE Std 830‑1998, IEEE Recommended Practice for Software Requirements Specifications.

### 1.5 Overview
Section 2 provides an overall description of the product environment and constraints. Section 3 lists the specific functional and non‑functional requirements. Section 4 details external interface requirements, and Section 5 describes design constraints and future enhancements.

---

## 2. Overall Description

### 2.1 Product Perspective
SnapFox will extend Firefox’s existing screenshot functionality with a professional editing workflow comparable to tools like PowerPoint or Canva. It operates entirely client‑side, storing no user data and requiring minimal permissions.

### 2.2 Product Functions
- Capture full‑page screenshots.
- Capture the visible viewport.
- Capture a selected DOM element.
- Capture a free‑form user‑drawn area.
- Annotate screenshots with text, arrows, and shapes.
- Customize annotation color, font, and stroke thickness.
- Undo/redo editing actions.
- Copy edited screenshots to the clipboard.
- Share screenshots via Gmail, WhatsApp, and Facebook using respective share intents or Web APIs.
- Launch editing window automatically after a capture.
- Access features through a toolbar icon and sidebar interface.

### 2.3 User Classes and Characteristics
Primary users are Firefox users, including business professionals, developers, and educators who need to illustrate concepts within a web page.

### 2.4 Operating Environment
SnapFox runs on Firefox version 110 or later on Windows, macOS, and Linux desktops. It relies on standard WebExtension APIs available in modern browsers.

### 2.5 Design and Implementation Constraints
- Must comply with Mozilla Add‑ons policies for WebExtensions.
- Implemented primarily in JavaScript/TypeScript.
- Uses a client‑side canvas library (e.g., Fabric.js or Konva.js) for editing.
- Clipboard permission is requested on installation.
- All processing is local; no external servers are used.

### 2.6 Assumptions and Dependencies
- Users have an active internet connection for sharing via web‑based platforms.
- Users operate a fully updated version of Firefox.
- No reliance on cloud services; functionality is self‑contained.

---

## 3. Specific Requirements

### 3.1 Functional Requirements
1. **FR‑1:** The system shall provide options to capture full page, viewport, DOM element, or free‑form area.
2. **FR‑2:** The system shall display a preview window with editing tools immediately after a capture.
3. **FR‑3:** The system shall allow adding text annotations with selectable font style, size, and color.
4. **FR‑4:** The system shall allow drawing arrows and geometric shapes with adjustable stroke thickness and color.
5. **FR‑5:** The system shall provide undo and redo capabilities for all editing actions.
6. **FR‑6:** The system shall copy the edited screenshot to the clipboard on user command.
7. **FR‑7:** The system shall enable sharing the screenshot via Gmail, WhatsApp, and Facebook through available Web APIs.
8. **FR‑8:** The system shall request clipboard permission only once during installation.
9. **FR‑9:** The system shall provide a toolbar button in the Firefox UI to initiate captures.
10. **FR‑10:** The system shall open its UI in a sidebar consistent with Firefox’s native screenshot feature.

### 3.2 Non‑Functional Requirements
11. **NFR‑1: Performance:** The time from capture initiation to editable preview shall not exceed 500 ms for pages up to 5 MB.
12. **NFR‑2: Usability:** The editing interface shall mimic familiar graphics tools (e.g., PowerPoint, Canva) to minimize learning curve.
13. **NFR‑3: Reliability:** The extension shall operate without crashes under normal use across the latest three Firefox versions.
14. **NFR‑4: Security:** All processing remains local; no user data is transmitted externally.
15. **NFR‑5: Portability:** Codebase shall target the WebExtension standard to facilitate future support for Chrome, Edge, etc.
16. **NFR‑6: Maintainability:** Code shall follow ESLint/Prettier guidelines and include unit tests for core modules.
17. **NFR‑7: Accessibility:** All UI elements shall be navigable via keyboard and comply with WCAG 2.1 AA.

---

## 4. External Interface Requirements

### 4.1 User Interfaces
The extension adds a toolbar icon. Clicking it displays options to choose the capture mode. After capture, an editing window opens with a canvas workspace, tool palette, and property panel. The UI will use a modern, responsive design consistent with Firefox Photon guidelines.

### 4.2 Hardware Interfaces
Not applicable; SnapFox interacts only with standard desktop hardware via the browser.

### 4.3 Software Interfaces
SnapFox interfaces with the following software components:
- Firefox WebExtension APIs (tabs, windows, activeTab, notifications, clipboard).
- Web Clipboard API for copying images.
- Share Intent APIs for Gmail, WhatsApp, Facebook where available.

### 4.4 Communications Interfaces
SnapFox does not require external network communication in its first release.

---

## 5. Design Constraints
Development must adhere to the Mozilla Add‑ons policies, including restrictions on permitted APIs and required review processes. All code shall be published under an open‑source license (e.g., MIT).

---

## 6. Future Enhancements
- Browser support for Chrome, Edge, and Safari.
- Integration with VS Code for annotated code screenshots.
- Support for image export formats beyond PNG (e.g., SVG, WebP).
- Plugin architecture for custom annotation tools.
- Cloud synchronization of annotation
