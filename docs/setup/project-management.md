# Project Management Workflow

Use GitHub Projects to plan and track the Project SENTINEL backlog.

## Create the Project Board

1. Navigate to the repository on GitHub and open the **Projects** tab.
2. Select **New project** and choose the **Board** template.
3. Name the project "SENTINEL Delivery" and set the visibility to **Private** until the submission is public.
4. Add columns for **Backlog**, **In Progress**, **In Review**, and **Done**.

## Define Issue Templates

1. Open `.github/ISSUE_TEMPLATE/` and create templates for **Feature**, **Bug**, and **Task** items.
2. Include required metadata:
   - Summary
   - Acceptance criteria
   - Definition of done
   - Test plan
3. Configure each template to auto-assign labels and default assignees when appropriate.

## Workflow Guidelines

- Create an issue for every backlog item before implementation.
- Link pull requests to issues using the `Closes #issue-number` convention.
- Keep the project board updated by moving cards during daily check-ins.
- Use labels to indicate scope (agent, service, infrastructure, documentation).

## Milestone Structure

- Create milestones for each development phase outlined in `DEVELOPMENT_PLAN.md`.
- Associate issues with milestones to visualize progress versus schedule.
- Review milestone burndown charts twice per week during the hackathon.
