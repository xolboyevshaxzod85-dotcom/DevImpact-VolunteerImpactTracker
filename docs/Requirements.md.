# Requirements Engineering

## 1. Functional Requirements (FR)
1. **FR-01:** The system must allow a Project Manager (PM) to create a multi-step Project Charter.
2. **FR-02:** The system must generate a 5x5 Risk Matrix based on user input for Probability and Impact.
3. **FR-03:** The system must display a real-time Dashboard with KPIs (Total Projects, Active Volunteers, Ratified Charters).
4. **FR-04:** The system must allow Volunteers to browse approved projects and submit join requests.
5. **FR-05:** The system must support role-based access control (Admin, PM, Volunteer, Sponsor).

## 2. Non-Functional Requirements (NFR) with Metrics
* **Performance:** API endpoints for the Dashboard must return data in **under 200ms** under normal load.
* **Usability:** The multi-step Project Charter form must have a completion rate of **>80%** without requiring a user manual (measured by a maximum of 3 clicks per step).
* **Security:** All user passwords must be hashed using bcrypt with a minimum salt round of 10.

## 3. User Stories (INVEST Criteria)
1. As a PM, I want to view a KPI dashboard, so that I can quickly assess the organization's impact.
2. As a PM, I want to input basic project info (Title/Purpose), so that I can initiate a charter.
3. As a PM, I want to define team roles (RACI), so that responsibilities are clear.
4. As a PM, I want to map risks on a 5x5 matrix, so that I can prepare mitigation plans.
5. As a Volunteer, I want to register an account, so that I can access the platform.
6. As a Volunteer, I want to view open projects, so that I can apply to participate.
7. As a Sponsor, I want to review draft charters, so that I can ratify or reject them.
8. As a User, I want to securely log in using JWT, so that my data is protected.

## 4. Use Cases with Acceptance Criteria
### Use Case 1: Create Project Charter
* **Actor:** Project Manager
* **Acceptance Criteria:** PM can navigate through 3 steps (Info, Roles, Risks). System prevents moving to the next step if mandatory fields are empty. Data is saved to the database with a "Draft" status.

### Use Case 2: Ratify Charter
* **Actor:** Sponsor
* **Acceptance Criteria:** Sponsor clicks "Ratify". System updates the status from "Draft" to "Ratified". System triggers an email notification to the PM.

### Use Case 3: Volunteer Application
* **Actor:** Volunteer
* **Acceptance Criteria:** Volunteer clicks "Join" on a ratified project. PM sees the application in their dashboard. Project's "Volunteers Joined" count increments upon approval.
