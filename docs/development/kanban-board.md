# Kanban board
[Link to Kanban board](https://gitlab.pg.innopolis.university/p.khramov/innolyceum/-/boards)

## Board Columns and Entry Criteria

Each column in the Kanban board has specific entry criteria that must be satisfied before an issue can be moved into it. 
**Definition of Done (DoD)**: An issue is considered complete once it reaches the **Done** column.

## To Do
**Entry Criteria:**
- The backlog item was groomed and reviewed.
- The issue was created using one of the templates: **User_Story**, **Bug_Report**, or **Technical_Task**.
- The label **Prioritization** was added.
- A **Story Points** label was assigned.
- The issue was added to a current sprint.
- The label **To Do** was added.

## In Progress
**Entry Criteria:**
- The issue description was revised to provide any missing implementation or design details.
- The issue was added to the current sprint.
- Developer or team member was **assigned**.

## In Review
**Entry Criteria:**
- All code related to the issue has been committed and pushed.
- A merge request (MR) has been opened and linked to the issue.
- A peer review by another team member has been requested or is in progress.

## Ready To Deploy
**Entry Criteria:**
- All comments from the peer reviewer have been addressed and resolved.
- The merge request has passed all stages of the CI/CD pipeline successfully.
- The code is ready to be deployed to the staging or production environment.

## User Tests
**Entry Criteria:**
- All unit and integration tests have been completed successfully.
- The issue-related changes have been deployed to the server.
- Manual testing was completed successfully on the deployed server environment.

## Done
**Entry Criteria:**
- All changes were deployed to the **production** environment.
- Acceptance criteria specified in the issue were verified in production.
- No critical bugs or regressions were found during user testing.