# git-repository-cia-2..
contributing friend git hub [project

Q1. Git Scenario – Tag and Release
You're ready to release version 1.0. Here’s how you can do it:

1. Tag the release as v1.0
You can create a tag using the following command:
git tag -a v1.0 -m "Release version 1.0"
This creates an annotated tag named v1.0 with a message describing the release.

2. Push the tag to GitHub
Once the tag is created, push it to the remote GitHub repository using:
git push origin v1.0
This makes the tag available on GitHub.

3. Create a release on GitHub from the tag

Steps:
Go to your GitHub repository in a browser.
Click on “Releases” (usually on the right sidebar or under “Code”).
Click “Draft a new release.”
In the “Tag version” dropdown, select the v1.0 tag you created.
Add a title and description (e.g., "Initial stable release").
Click “Publish release.”
This links the tag to a release page, useful for versioning and distributing binaries or source code.

Q2. JQL – Overdue & SLA Queries
Assuming you're using Jira Service Management with SLA fields enabled:

a. Show all issues that are overdue by more than 2 days
due <= -2d
Explanation: Shows all issues with a due date at least 2 days in the past (i.e., overdue).

b. List all issues that must be resolved within 48 hours
If you have an SLA called “Time to resolution”, the query would be:
"SLA Name" = "Time to resolution" AND "Time to resolution" <= remaining("48h")
If you're using a custom field or label:
labels = sla_48hr OR "Custom SLA Field" <= 48h
(Replace "Custom SLA Field" with the actual field name.)

c. Find issues with a due date within this week
due >= startOfWeek() AND due <= endOfWeek()
This filters issues that are due anytime during the current calendar week.

How JQL Helps with SLA Enforcement

JQL (Jira Query Language) enables teams to:
Track SLA metrics by querying issues approaching or breaching SLAs.
Automate alerts for SLA breaches using filters + automation rules.
Prioritize tickets based on time left to resolve or response deadlines.
Generate reports and dashboards to monitor performance against SLAs.
Ensure accountability by identifying overdue tickets and bottlenecks.
In service-based teams, this improves response times, customer satisfaction, and operational transparency.
