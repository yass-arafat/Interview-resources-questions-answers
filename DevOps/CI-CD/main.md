### What CI & CD atually do when developer commit to a branch?

### Continuous Integration (CI)

CI focuses on automating the integration and testing of your code to ensure it works well with the existing codebase. When you commit or push to a branch (e.g, develop or main), a CI pipeline is triggered. Here’s what happens step-by-step:

1. **Trigger the Pipeline:**
   A CI/CD tool (e.g., GitHub Actions, GitLab CI, Jenkins, CircleCI) detects the commit and starts a predefined workflow.
   The workflow is defined in configuration files (e.g., .github/workflows/ci.yml).

2. **Checkout the Code:**
   The CI server pulls the latest code from the branch to a clean environment (e.g. a virtual machine or container).

3. **Install Dependencies:**
   The pipeline installs all required libraries, tools, and dependencies (e.g., via pip install for Python projects).

4. **Run Automated Tests:**
   The CI server runs your test suite to verify that: Your code works as intended. New changes don’t break existing functionality. Examples: Unit tests, integration tests, or end-to-end tests.

5. **Static Code Analysis (Optional):**
   The pipeline may include linting tools (e.g., flake8) or static analysis tools (e.g., mypy) to enforce code quality standards.

6. **Build Artifacts:**
   For complex projects, CI may compile the code or package it into build artifacts (e.g., Docker images, .zip files, .jar files).

7. **Results and Feedback:**
   The CI system provides feedback:
   ✅ Success: All tests pass.
   ❌ Failure: Tests fail, and the developer is notified with logs to debug.
   This feedback loop ensures issues are detected early in development.

### Continuous Deployment/Delivery (CD)

CD focuses on automating the process of deploying tested code to a target environment.

After CI completes successfully, the CD pipeline takes over. Here’s what happens next:

1. Decide Deployment Type 
**Continuous Delivery:** Deploys to a staging environment for manual approval before going live.
**Continuous Deployment:**Automatically deploys to production after passing tests.
2. Build the Application (if not already done in CI)
   Package the application as a deployable artifact (e.g., Docker image, binary).
3. Push Artifacts to a Repository
   If you’re using Docker, the image is pushed to a container registry (e.g., Docker Hub, AWS ECR).
   For non-containerized apps, the build is stored in an artifact repository.
4. Deploy to Target Environment
   Deploy the application to a staging or production environment, such as:
   Kubernetes Cluster
   AWS ECS/Fargate
   Heroku or Azure App Service
   Bare-metal or virtual servers
5. Run Post-Deployment Checks
   Health checks ensure the app is running correctly (e.g., hitting the /health endpoint of your app).
   Smoke tests verify basic functionality after deployment.
6. Notify Team
   The CD system notifies the team of the successful deployment or alerts them in case of failure.
