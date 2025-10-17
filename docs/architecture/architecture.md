# Architecture

## Static view

The system architecture is illustrated in a [UML Component Diagram](docs/architecture/static-view)

- **Django** handles core logic, **Wagtail** manages content, and connectors manage access to DB/cache.**Django** handles core logic, **Wagtail** manages content, and **connectors** abstract DB/cache access.
- Components have clear responsibilities, making the codebase easy to modify, test, and analyze.
- Loose coupling allows parts to evolve independently, improving maintainability and scalability.

## Dynamic view

The dynamic behavior of our system is illustrated using a [UML Sequence Diagram](docs/architecture/dynamic-view), showcasing the events page request flow. This non-trivial scenario involves Wagtail, Redis, Django, and Postgres, demonstrating multiple transactions and our cache-first strategy.

**Performance (based on integration tests):**

- Main page response time:
  - With cache: ~1 second
  - Without cache: ~2 seconds
- Events list (AJAX): ~1 second

These results confirm that our caching strategy significantly improves responsiveness and meets our performance requirements.

## Deployment view

Our system is deployed using a containerized architecture to support modularity and scalability.  
[Deployment Diagram](docs/architecture/deployment-view)

**Deployment Overview:**

- The application runs on a Linux Debian “Bookworm” server for stability and security.
- The system is split into **three containers**:
  1. **Web container** – hosts Django and Wagtail (main app logic and CMS).
  2. **PostgreSQL container** – handles persistent data storage.
  3. **Redis container** – manages caching to boost performance.

**Deployment Notes for the Customer:**

- Use Docker or Docker Compose to launch all services with isolated configurations.
- Each service can be updated or scaled independently, reducing downtime and complexity.
- This setup allows future infrastructure changes (e.g. moving DB to managed service) with minimal app-side changes.