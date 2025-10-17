# Continuous Deployment

## CD Workflow Files

- [gitlab-ci.yml](https://gitlab.pg.innopolis.university/p.khramov/innolyceum/-/blob/back_dev/.gitlab-ci.yml?ref_type=heads) — Includes the `deploy` job that runs after testing stages, responsible for deploying the website to the server.

## Deployment Strategy

- **Recreate / Replace**: The deployment strategy involves fully recreating or replacing the existing application instance to ensure a clean and up-to-date environment.

## Tools and Scripts Used

- **SSH remote deploy**: Securely connects to the target server for remote deployment and management.
- **Docker Compose orchestration**: Manages multi-container Docker applications to build, run, and update the environment reliably.
- **Test coverage reporting**: Generates and reports test coverage data as part of the pipeline to ensure code quality.
- **Docker image lint & patch build**: Lints Docker images for best practices and applies patch builds as part of the deployment process.

## Deployment Logs and Status

You can track deployment logs and status in the same [GitLab Pipelines page](https://gitlab.pg.innopolis.university/p.khramov/innolyceum/-/pipelines). Look for the `deploy` stage or job at the bottom of each pipeline.