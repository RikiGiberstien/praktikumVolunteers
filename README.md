# Volunteer Management System

## Overview

A full-stack web application designed to streamline volunteer coordination, shift management, and administrative workflows.

The system provides dedicated management interfaces for domain managers and administrators, supporting volunteer activity creation, shift status updates, cancellation workflows, volunteer assignment visibility, and communication.

The application also incorporates reusable React components, AI-assisted dynamic form logic, a centralized notification mechanism, and a generic email service.

## System Features

- **Volunteer Activity Management:** Create, view, and update volunteer activities.
- **Domain and Subdomain Management:** Organize activities using hierarchical categories.
- **Dynamic Forms:** Display form fields according to the selected activity and its requirements.
- **Shift Status Management:** Support activity confirmation and cancellation workflows.
- **Volunteer Assignment Overview:** Display assigned volunteers and staffing capacity.
- **Administrative Dashboards:** Provide separate management interfaces for domain managers and the main administrator.
- **Email Notifications:** Send emails through a reusable client-server email mechanism.
- **Centralized Notifications:** Display consistent success, warning, and error messages throughout the application.
- **AI Integration:** Use an AI-powered service to determine dynamically whether working-hours fields should be displayed.

## My Contributions

### 1. Reusable Generic Modal Component

Developed a reusable React modal component to reduce code duplication and provide a consistent interface across the application.

The component supports configurable titles, sizes, visibility, close and confirmation callbacks, button labels, and dynamic content through `children`.

Technical implementation includes:

- React Hooks, including `useState` and `useEffect`.
- Separate visibility and animation states to support closing animations.
- Synchronization between parent-controlled state and internal component state.
- Keyboard dismissal using the Escape key.
- Background scroll locking while the modal is open.
- React Portal rendering under `document.body`.
- Click-outside dismissal while preserving clicks inside the modal.

The component can be reused for viewing activity details, adding notes, composing messages, and confirming actions.

### 2. Unit Testing Practices and Code Quality

Studied and presented practical unit-testing concepts to support a quality-focused development process.

Prepared and demonstrated sample test files illustrating test structure, test cases, and verification of expected component behavior.

Topics covered included:

- Unit testing and test isolation.
- Arrange–Act–Assert structure.
- Positive and negative test scenarios.
- Edge cases and invalid inputs.
- Regression testing.
- Code coverage.
- Planning test cases before and during implementation.

This work promoted greater awareness of testability, maintainability, and regression prevention within the development process.

### 3. Domain Manager Dashboard

Developed a dashboard that enables domain managers to manage volunteer activities under their responsibility.

Key implementation details:

- Dynamic loading, display, and updating of activity data.
- Activity creation forms built with reusable UI components.
- Hierarchical domain and subdomain selection.
- Configurable recurring activity days.
- Activity notes with saved updates and communication to volunteers.
- Modal interfaces for activity details and assigned-volunteer information.

#### AI-Assisted Dynamic Form Logic

Integrated an AI-powered service to determine whether start-time and end-time fields should appear in the activity creation form.

When a subdomain is selected, the frontend sends a request to a dedicated backend API. The backend service constructs a prompt, sends it to the AI model, validates the result, and returns a decision to the client.

The form then adapts its fields according to the response.

The implementation includes:

- A dedicated AI communication service.
- A backend controller.
- A dedicated API endpoint.
- Prompt engineering for structured model responses.
- Response validation against the expected data format.
- Dynamic updates to the form based on the result.

This approach separates AI-assisted decision logic from the UI and supports future extensions to business rules.

### 4. Central Administration Dashboard

Developed a central management interface for the main administrator, providing visibility and control over activities across the system.

#### Management Table and Filtering

- Display activity details, dates, times, locations, statuses, and assigned volunteers.
- Filter activities by domain and status.
- Support free-text search and filtering by workflow state.

#### Approval and Cancellation Workflows

- Confirm volunteer activities.
- Review cancellation requests.
- Approve or reject cancellation requests.
- Update activity statuses through server communication.

#### Staffing Information

- Display assigned volunteers.
- Compare available capacity with actual assignments.
- Indicate whether an activity is fully staffed, partially staffed, or unstaffed.

#### Asynchronous State Management

Implemented handling for loading states, communication errors, and duplicate actions during asynchronous requests.

The implementation separates data management, filtering logic, and presentation components to improve maintainability and support future development.

### 5. Generic Email Notification System

Developed a reusable email-sending mechanism integrated across the frontend and backend.

#### Frontend

Created an Email Modal that accepts a recipient address, subject, and message body, then submits the request asynchronously through an API.

#### Backend

Implemented a layered email workflow comprising:

- A dedicated router for the email endpoint.
- A controller for request validation and response handling.
- An Email Service that handles message delivery using Nodemailer and SMTP.

Also developed an HTML email template with consistent styling and support for Hebrew right-to-left text layout.

The implementation emphasizes separation of responsibilities, environment-based configuration for sensitive settings, and communication-error handling.

### 6. Generic Notification System

Developed a reusable notification mechanism to replace browser alerts with consistent, styled application messages.

The notification component supports:

- Dynamic message content.
- Success, warning, and error types.
- User-triggered dismissal.
- Automatic dismissal using `setTimeout`.

Implemented centralized notification management using React Context API, allowing components throughout the application to trigger notifications through a shared interface.

This reduced duplication and improved consistency in user feedback across the application.

## Technologies and Concepts

- **Frontend:** React, React Hooks, Context API
- **Backend:** Node.js, Express, REST APIs
- **Database:** PostgreSQL
- **Email:** Nodemailer, SMTP, HTML email templates
- **AI:** AI model integration, prompt engineering, response validation
- **UI Architecture:** Reusable components, React Portals, dynamic forms
- **Development Practices:** Separation of responsibilities, asynchronous state management, unit-testing practices, modular design

## Architecture and Engineering Principles

The project emphasizes reusable components, separation of responsibilities, and clear communication between frontend and backend services.

The implemented components and services support consistent UI behavior, centralized notifications, structured email delivery, AI-assisted form decisions, and maintainable administrative workflows.

## Summary of My Contributions

My work focused on six areas:

1. Developing a reusable React modal component.
2. Preparing and presenting practical unit-testing examples and development guidance.
3. Building a domain manager dashboard with dynamic forms and AI-assisted field selection.
4. Developing a central administration dashboard with filtering, approval workflows, and staffing information.
5. Implementing a generic email notification system across the frontend and backend.
6. Creating a centralized notification system using React Context API.

These contributions demonstrate practical experience in frontend development, backend integration, reusable component design, AI integration, asynchronous workflows, and software quality practices.
