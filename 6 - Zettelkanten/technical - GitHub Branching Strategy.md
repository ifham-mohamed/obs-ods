
2025-03-05 17:45

Status:

Tags:


# technical - GitHub Branching Strategy


Below is an enhanced set of branch naming examples based on your UDINE project needs—with the task ID “UD-10” and a short description (“creating category model”). Each example includes a brief explanation of when and why you’d use that branch type.

---

### Main Branches

- **Main (or Production) Branch:**\
  **Name:** `main`\

  **Usage:**
  - Contains only production‑ready, thoroughly tested code.
  - Deployments or releases are made from this branch.
  - Example Scenario: After completing features and fixes in dev (and after QA), you merge them into main for production.

- **Development Branch:**\
  **Name:** `dev`\
  
  **Usage:**
  - Serves as the integration branch for ongoing work.
  - All feature, bug fix, or chore branches branch off from dev.
  - Example Scenario: Before starting work on the “creating category model” task, you create a branch off dev. When the task is complete and tested, you merge it back into dev for further integration and testing.

---

### Supporting Branches

1. **Feature Branch (New Functionality):**\

   **Name Example:**

   - `feature/UD-10-dev-create-category-model`\

   **Usage:**
   - Use when you’re adding new functionality.
   - Branch off from `dev` for a new feature.
   - The branch name includes the task ID (`UD-10`) followed by a concise description.
   
   - **Real-World Context:** When a product manager assigns a new feature (e.g., a category model for organizing products), you create this branch, work on it, and merge it back into dev after passing code review and tests.

2. **Fix Branch (Bug Fixes During Development):**\
   
   **Name Example:**

   - `fix/UD-10-dev-fix-category-model`\
   
   - **Usage:**
   - Use when you discover and need to fix a bug in the new functionality during development.
   - Branch off from `dev` to address the bug.
   - The naming convention helps indicate that this fix relates to the task (`UD-10`) and is being addressed within the development cycle.
   
   - **Real-World Context:** Suppose testers find an issue with the category model's behavior on dev; you would create this fix branch to address the bug and then merge the fix back into dev.

3. **Hotfix Branch (Urgent Production Fixes):**\

   **Name Example:**

   - `hotfix/UD-10-fix-prod-category-error`\
   
   - **Usage:**
   - Use when an urgent bug affecting production is discovered.
   - Branch off from `main` since the problem exists in your live code, apply the fix, and then merge the hotfix into both `main` and `dev` to ensure consistency.
   
   - **Real-World Context:** If a critical error in the category model causes a production outage, you’d immediately create a hotfix branch, apply the correction, and quickly merge it back into main (and then into dev) for further integration.

4. **Release Branch (Preparing a New Release):**\

   **Name Example:**

   - `release/v1.2.0`\
   
   - **Usage:**
   - Use when you’re ready to stabilize a new version of your code.
   - Branch off from `dev` once all new features and fixes are integrated and ready for final testing.
   - Final adjustments and testing occur in the release branch, which is then merged into `main` once it’s confirmed to be production‑ready.
   - **Real-World Context:** At the end of a sprint or milestone, you branch a release from dev, perform final QA, and then merge it into main, tagging it with a version number.

5. **Chore Branch (Non-Feature Tasks):**\

   **Name Example:**

   - `chore/UD-10-dev-update-dependencies`\
   
   - **Usage:**
   - Use for tasks such as dependency updates, refactoring, or documentation that aren’t new features or bug fixes.
   - Branch off from `dev`, complete the chore, and merge it back.
   
   - **Real-World Context:** When the team needs to update libraries or perform routine maintenance that doesn’t directly impact functionality, a chore branch is created using a similar naming style.

---

### Summary Table

| **Branch Type**       | **Example Name**                           | **When to Use**                                                     |
| --------------------- | ------------------------------------------ | ------------------------------------------------------------------- |
| **Main**              | `main`                                     | Production‑ready code, deployments, releases.                       |
| **Development (Dev)** | `dev`                                      | Integration of new work, from which all other branches are created. |
| **Feature**           | `feature/UD-10-dev-create-category-model`  | Developing new features (e.g., adding a category model).            |
| **Fix**               | `fix/UD-10-dev-fix-category-model`         | Fixing bugs found during development.                               |
| **Hotfix**            | `hotfix/UD-10-fix-prod-category-error`     | Urgent fixes for production issues.                                 |
| **Release**           | `release/v1.2.0`                           | Finalizing a release from dev for production deployment.            |
| **Chore**             | `chore/update-dependencies -with-mongoose` | Routine tasks such as refactoring, updates, or documentation.       |

---

These naming conventions keep branch names clear and self‑documenting. They also help link your development work directly to tracked tasks (using the task ID like UD-10), which is a practice seen in many real-world teams (refer to best practices discussed on [phoenixNAP](https://phoenixnap.com/kb/git-branch-name-convention)  and [DEV Community](https://dev.to/jps27cse/github-branching-name-best-practices-49ei) ).

Using these conventions consistently across your project will improve team collaboration, ease of code review, and clarity when tracking the progress of individual tasks.


# Reference