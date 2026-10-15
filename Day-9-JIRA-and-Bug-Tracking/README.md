# Day 9: JIRA & Bug Tracking Tools


## 2. Learning Objectives
- Set up a practice JIRA account and project.
- Understand Bug, Story, Task, Epic, and Sub-task.
- Create clear bug reports with steps, expected/actual results, and evidence.
- Understand workflow statuses and transitions.
- Compare Scrum and Kanban boards.
- Write JQL queries, save filters, and explore dashboards.

## 3. Recommended Sequence
1. Follow the setup guide and create a practice project.
2. Explore the interface and issue types.
3. Review the bug-report template and sample bug spreadsheet.
4. Inspect workflow transitions and board behavior.
5. Test JQL examples and explore dashboards.
6. Complete the practice checklist and learning notes.

## 4. Bug Report Essentials
A good report includes a clear summary, environment, preconditions, numbered reproduction steps, expected result, actual result, priority/severity according to team rules, and relevant safe evidence.

## 5. Issue Types
- **Bug:** observed behavior differs from expected behavior.
- **Story:** user-focused requirement.
- **Task:** discrete piece of work.
- **Epic:** larger body of related work.
- **Sub-task:** smaller work item under a parent issue.

## 6. Workflow
A possible bug lifecycle is To Do/Open → In Progress → Fixed/Resolved → Retest → Done/Closed. If retesting fails, the issue may be reopened or returned to development. Actual statuses and transitions depend on project configuration.

## 7. Scrum vs Kanban
Scrum organizes selected work into time-boxed sprints with a backlog and sprint planning. Kanban visualizes continuous flow, often through To Do, In Progress, and Done, and may use work-in-progress limits.

## 8. JQL Examples
- `issuetype = Bug`
- `issuetype = Bug AND resolution IS EMPTY`
- `assignee = currentUser()`
- `created >= -7d ORDER BY created DESC`
- `status IN ("To Do", "In Progress")`

Field values and status names must match your own project. Save and share filters only where permissions allow.

## 9. Deliverables Checklist
- [ ] Practice project created
- [ ] 20 or more bugs actually created and issue keys recorded
- [ ] Workflow transitions reviewed
- [ ] Scrum and Kanban boards explored
- [ ] JQL queries tested and filters saved
- [ ] Dashboard gadgets explored
- [ ] Learning notes updated

## 10. Accuracy Note
The examples and templates in this repository are practice materials. They do not prove that a live JIRA project or issue was created. Mark work complete only after verifying it in your own account. JIRA menus, permissions, issue hierarchy, statuses, and gadgets can vary by plan and project configuration.
