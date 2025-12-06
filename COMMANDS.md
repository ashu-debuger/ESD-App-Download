# Tasker Command Reference 📘

> *The Complete & Exhaustive Guide to Every Single Tasker Command*

Welcome to the **definitive** command reference for Tasker by Mantra. This document covers **every possible command, filter, and interaction** available in the Tasker ecosystem — from slash commands to natural language bot conversations.

---

## 🌟 Why Tasker is the Rock-Solid Choice

Before we dive into commands, here's why Tasker stands out:

| Feature              | Tasker                       | Others                 |
| -------------------- | ---------------------------- | ---------------------- |
| **Zoho Cliq Native** | ✅ Built-in integration       | ❌ External plugins     |
| **Natural Language** | ✅ "I'm done with design"     | ❌ Strict commands only |
| **Real-time Sync**   | ✅ Mobile ↔ Cliq instant      | ⚠️ Delayed sync         |
| **Smart Reminders**  | ✅ Push + Cliq DM             | ⚠️ Single channel       |
| **Recurring Tasks**  | ✅ Daily/Weekly/Monthly       | ❌ Manual recreation    |
| **Collaboration**    | ✅ Roles: Owner/Editor/Viewer | ⚠️ All-or-nothing       |
| **Offline First**    | ✅ Works without internet     | ❌ Cloud-only           |
| **Free & Private**   | ✅ No subscriptions           | 💰 Premium-gated        |

**We're the rock-solid one because:**
- 🔒 **Your data, your control** — Firebase backend you can audit
- ⚡ **Blazing fast** — Native Flutter + optimized Firestore
- 🤝 **Team-ready** — Role-based collaboration built-in
- 🧠 **Actually smart** — NLP understands casual language
- 🔔 **Never miss a deadline** — Multi-channel reminders

---

## 📋 Table of Contents

1. [Slash Commands Overview](#slash-commands-overview)
2. [/tasker — General Commands](#tasker--general-commands)
3. [/taskertask — Task Management](#taskertask--task-management)
4. [/taskerproject — Project Management](#taskerproject--project-management)
5. [TaskerBot Natural Language](#taskerbot-natural-language)
6. [Dashboard Widget](#dashboard-widget)
7. [Quick Reference Tables](#quick-reference-tables)

---

## Slash Commands Overview

Tasker provides **3 slash commands** in Zoho Cliq:

| Command          | Purpose                        | Example               |
| ---------------- | ------------------------------ | --------------------- |
| `/tasker`        | General, help, account linking | `/tasker help`        |
| `/taskertask`    | All task operations            | `/taskertask create`  |
| `/taskerproject` | All project operations         | `/taskerproject list` |

---

## /tasker — General Commands

The hub command for help, status, and account management.

### Basic Commands

| Command             | Description                          |
| ------------------- | ------------------------------------ |
| `/tasker`           | Shows the main menu with all options |
| `/tasker help`      | Displays complete help guide         |
| `/tasker about`     | About Tasker by Mantra               |
| `/tasker commands`  | Shows all available commands         |
| `/tasker tips`      | Pro tips for power users             |
| `/tasker shortcuts` | Quick shortcuts reference            |
| `/tasker status`    | Check your connection status         |

### Account Linking

| Command               | Description                          |
| --------------------- | ------------------------------------ |
| `/tasker link <code>` | Link your Cliq account to Tasker app |
| `/tasker link ABC123` | Example with 6-character code        |

**How to get your linking code:**
1. Open Tasker App → Settings
2. Tap "Zoho Cliq Integration"
3. Generate Code (valid 10 minutes)
4. Use `/tasker link <code>` in Cliq

### Redirect Commands

These commands redirect you to the appropriate specialized slash command:

| Command            | Redirects To               |
| ------------------ | -------------------------- |
| `/tasker create`   | `/taskertask create`       |
| `/tasker list`     | `/taskertask list`         |
| `/tasker my tasks` | `/taskertask list`         |
| `/tasker complete` | `/taskertask complete`     |
| `/tasker assign`   | `/taskertask assign`       |
| `/tasker search`   | `/taskertask list`         |
| `/tasker overdue`  | `/taskertask list overdue` |
| `/tasker projects` | `/taskerproject list`      |
| `/tasker project`  | `/taskerproject`           |

---

## /taskertask — Task Management

Complete task lifecycle management.

### Creating Tasks

| Command                           | Description                            |
| --------------------------------- | -------------------------------------- |
| `/taskertask`                     | Shows task menu with clickable options |
| `/taskertask create`              | Opens interactive task creation form   |
| `/taskertask create "Task Title"` | Quick create with just title           |

**Form Fields (when using create form):**
- 📝 **Title** — Task name (required, max 100 chars)
- 📄 **Description** — Details (optional, max 500 chars)
- 📁 **Project** — Assign to project or "Personal"
- 🎯 **Priority** — Urgent / High / Medium / Low
- 📅 **Due Date** — Deadline picker
- 🏷️ **Tags** — Comma-separated labels
- 🔔 **Reminders** — Enable/Disable push notifications
- 🔄 **Recurrence** — None / Daily / Weekly / Monthly
- 🔁 **Repeat Every** — Interval (e.g., every 2 days)
- 📆 **Repeat Until** — End date for recurrence
- 🔐 **Encrypt Description** — For sensitive info

### Listing Tasks

| Command                        | Description            |
| ------------------------------ | ---------------------- |
| `/taskertask list`             | All your tasks         |
| `/taskertask list pending`     | Only pending tasks     |
| `/taskertask list completed`   | Only completed tasks   |
| `/taskertask list in_progress` | Only in-progress tasks |
| `/taskertask list overdue`     | Tasks past due date    |

### List with Filters

Combine filters for precise results:

| Filter Syntax      | Description        | Example          |
| ------------------ | ------------------ | ---------------- |
| `status:<value>`   | Filter by status   | `status:pending` |
| `priority:<value>` | Filter by priority | `priority:high`  |
| `project:<id>`     | Filter by project  | `project:abc123` |

**Priority Values:**
- `urgent` — 🔴 Urgent Priority
- `high` — 🟠 High Priority
- `medium` — 🟡 Medium Priority
- `low` — 🟢 Low Priority

**Combined Filter Examples:**

```
/taskertask list status:pending priority:high
/taskertask list priority:urgent
/taskertask list project:abc123 status:pending
/taskertask list status:completed priority:medium
```

### Completing Tasks

| Command                          | Description                  |
| -------------------------------- | ---------------------------- |
| `/taskertask complete`           | Opens form to select task    |
| `/taskertask complete <task_id>` | Complete specific task by ID |
| `/taskertask done`               | Alias for complete           |
| `/taskertask done <task_id>`     | Alias with task ID           |

**Form Fields:**
- 📋 **Select Task** — Dropdown of pending tasks
- 📝 **Completion Notes** — Optional notes (max 500 chars)

### Assigning Tasks

| Command                                | Description           |
| -------------------------------------- | --------------------- |
| `/taskertask assign`                   | Opens assignment form |
| `/taskertask assign <task_id> <email>` | Direct assignment     |

**Form Fields:**
- 📋 **Select Task** — Dropdown of your tasks
- 👤 **Assign To** — Contact picker from Cliq

### Viewing Task Details

| Command                         | Description               |
| ------------------------------- | ------------------------- |
| `/taskertask details`           | Opens task selection form |
| `/taskertask details <task_id>` | View specific task        |
| `/taskertask info`              | Alias for details         |
| `/taskertask info <task_id>`    | Alias with task ID        |
| `/taskertask view`              | Alias for details         |
| `/taskertask view <task_id>`    | Alias with task ID        |

### Deleting Tasks

| Command                        | Description                    |
| ------------------------------ | ------------------------------ |
| `/taskertask delete`           | Opens delete confirmation form |
| `/taskertask delete <task_id>` | Delete specific task           |
| `/taskertask remove`           | Alias for delete               |
| `/taskertask remove <task_id>` | Alias with task ID             |

**Form Fields:**
- 📋 **Select Task** — Task to delete
- ⚠️ **Confirm** — Type "DELETE" to confirm

### Update Tasks (Coming Soon)

| Command                        | Description                       |
| ------------------------------ | --------------------------------- |
| `/taskertask update`           | Task update feature (coming soon) |
| `/taskertask update <task_id>` | Update specific task              |
| `/taskertask edit`             | Alias for update                  |
| `/taskertask edit <task_id>`   | Alias with task ID                |

---

## /taskerproject — Project Management

Team collaboration and project organization.

### Creating Projects

| Command                                | Description                 |
| -------------------------------------- | --------------------------- |
| `/taskerproject`                       | Shows project menu          |
| `/taskerproject create`                | Opens project creation form |
| `/taskerproject create "Project Name"` | Quick create with name      |

**Form Fields:**
- 📁 **Project Name** — Name (required, max 25 chars)
- 📝 **Description** — Details (optional, max 25 chars)

### Listing Projects

| Command               | Description       |
| --------------------- | ----------------- |
| `/taskerproject list` | All your projects |

### Inviting Members

| Command                                             | Description                       |
| --------------------------------------------------- | --------------------------------- |
| `/taskerproject invite`                             | Opens invite form                 |
| `/taskerproject invite <project_id> <email>`        | Invite with default role (editor) |
| `/taskerproject invite <project_id> <email> <role>` | Invite with specific role         |

**Roles:**
- 👑 `owner` — Full access (create, edit, delete, invite)
- ✏️ `editor` — Can create and edit tasks
- 👁️ `viewer` — Read-only access

**Form Fields:**
- 📁 **Select Project** — Project dropdown
- 👤 **Select User** — Contact picker
- 🎭 **Role** — Owner / Editor / Viewer
- 💬 **Message** — Personal invitation message (optional)

**Examples:**
```
/taskerproject invite abc123 john@company.com
/taskerproject invite abc123 john@company.com editor
/taskerproject invite abc123 sarah@company.com owner
/taskerproject invite abc123 viewer@company.com viewer
```

### Viewing Project Details

| Command                               | Description                  |
| ------------------------------------- | ---------------------------- |
| `/taskerproject details`              | Opens project selection form |
| `/taskerproject details <project_id>` | View specific project        |
| `/taskerproject info`                 | Alias for details            |
| `/taskerproject info <project_id>`    | Alias with project ID        |

**Details Displayed:**
- 📊 Statistics (total tasks, completed, pending, progress %)
- 👥 Team members with roles
- ℹ️ Created by and creation date

### Viewing Project Members

| Command                               | Description                   |
| ------------------------------------- | ----------------------------- |
| `/taskerproject members`              | Opens project selection form  |
| `/taskerproject members <project_id>` | View specific project members |

---

## TaskerBot Natural Language

Chat naturally with TaskerBot in DMs. Just say what you need!

### Greetings

| Say This         | What Happens                     |
| ---------------- | -------------------------------- |
| "Hi"             | Friendly greeting                |
| "Hello"          | Friendly greeting                |
| "Hey"            | Friendly greeting                |
| "Good morning"   | Daily briefing with task summary |
| "Good afternoon" | Daily briefing                   |
| "Good evening"   | Daily briefing                   |
| "Howdy"          | Friendly greeting                |

### Getting Help

| Say This           | What Happens             |
| ------------------ | ------------------------ |
| "Help"             | Shows all bot commands   |
| "What can you do?" | Shows capabilities       |
| "How do I..."      | Shows help guide         |
| "Commands"         | Lists available commands |

### Viewing Tasks

| Say This                 | What Happens          |
| ------------------------ | --------------------- |
| "What's on my plate?"    | Lists your tasks      |
| "Show my tasks"          | Lists all tasks       |
| "Show me my tasks"       | Lists all tasks       |
| "List tasks"             | Lists all tasks       |
| "My tasks"               | Lists all tasks       |
| "Pending tasks"          | Lists pending tasks   |
| "Tasks for today"        | Today's tasks         |
| "Tasks for tomorrow"     | Tomorrow's tasks      |
| "Tasks for this week"    | This week's tasks     |
| "What should I work on?" | Lists pending tasks   |
| "What's left?"           | Shows remaining tasks |
| "What's pending?"        | Shows pending tasks   |

### Daily Briefing

| Say This            | What Happens        |
| ------------------- | ------------------- |
| "Briefing"          | Shows daily summary |
| "What's happening?" | Daily summary       |
| "What's up?"        | Daily summary       |
| "What's new?"       | Daily summary       |
| "Summary"           | Task summary        |
| "Daily update"      | Daily report        |
| "Daily report"      | Daily report        |
| "Daily status"      | Daily report        |
| "Morning report"    | Daily briefing      |
| "Today's tasks"     | Today's agenda      |
| "Today's agenda"    | Today's schedule    |
| "Today's schedule"  | Today's schedule    |

### Completing Tasks

| Say This                      | What Happens        |
| ----------------------------- | ------------------- |
| "Done with [task name]"       | Marks task complete |
| "Completed [task name]"       | Marks task complete |
| "Finished [task name]"        | Marks task complete |
| "I'm done with [task name]"   | Marks task complete |
| "I've completed [task name]"  | Marks task complete |
| "I have finished [task name]" | Marks task complete |
| "Mark [task] as done"         | Marks task complete |
| "Mark [task] as complete"     | Marks task complete |
| "Check off [task]"            | Marks task complete |
| "✅ [task name]"               | Marks task complete |

**Examples:**
```
Done with design review
I'm done with the homepage
Finished client meeting prep
Mark quarterly report as complete
```

### Editing Tasks

| Say This             | What Happens    |
| -------------------- | --------------- |
| "Edit [task name]"   | Opens edit form |
| "Update [task name]" | Opens edit form |
| "Modify [task name]" | Opens edit form |
| "Change [task name]" | Opens edit form |
| "✏️ [task name]"      | Opens edit form |

### Creating Tasks

| Say This                       | What Happens               |
| ------------------------------ | -------------------------- |
| "Create a task [title]"        | Creates new task           |
| "Create task [title]"          | Creates new task           |
| "Add a task [title]"           | Creates new task           |
| "New task [title]"             | Creates new task           |
| "Remind me to [action]"        | Creates task with reminder |
| "I need to [action]"           | Creates task               |
| "Don't forget to [action]"     | Creates task               |
| "Don't let me forget [action]" | Creates task               |
| "Todo: [title]"                | Creates task               |
| "Task: [title]"                | Creates task               |

**With Priority:**
```
Remind me to call client urgent
I need to review contract high priority
Create task submit report asap
```

**With Due Date:**
```
Remind me to call John tomorrow at 5pm
I need to finish the report by Friday
Create task send invoice due next Monday
```

### Assigning Tasks

| Say This                 | What Happens        |
| ------------------------ | ------------------- |
| "Assign [task] to @user" | Assigns task        |
| "Give [task] to @user"   | Assigns task        |
| "@user should [task]"    | Creates and assigns |
| "@user needs to [task]"  | Creates and assigns |
| "@user can you [task]"   | Creates and assigns |

### Viewing Projects

| Say This           | What Happens        |
| ------------------ | ------------------- |
| "Show projects"    | Lists your projects |
| "Show my projects" | Lists your projects |
| "List projects"    | Lists all projects  |
| "My projects"      | Lists your projects |
| "What projects?"   | Lists your projects |

### Productivity Stats

| Say This          | What Happens             |
| ----------------- | ------------------------ |
| "My stats"        | Shows your statistics    |
| "Statistics"      | Shows productivity data  |
| "How am I doing?" | Shows progress           |
| "Productivity"    | Shows productivity stats |
| "Progress"        | Shows progress report    |

---

## Dashboard Widget

The Tasker Dashboard Widget provides at-a-glance information in Zoho Cliq.

### Widget Sections

| Section           | Content                               |
| ----------------- | ------------------------------------- |
| **Overview**      | Total tasks, pending, completed count |
| **Today's Tasks** | Tasks due today                       |
| **Overdue**       | Tasks past due date                   |
| **Projects**      | Your active projects                  |

### Widget Buttons

| Button     | Action                   |
| ---------- | ------------------------ |
| ➕ New Task | Opens task creation form |
| 📋 My Tasks | Lists all your tasks     |
| 📁 Projects | Lists your projects      |
| 🔄 Refresh  | Refreshes widget data    |
| ❓ Help     | Shows help guide         |

---

## Quick Reference Tables

### All /tasker Commands

| Command               | Description      |
| --------------------- | ---------------- |
| `/tasker`             | Main menu        |
| `/tasker help`        | Help guide       |
| `/tasker about`       | About info       |
| `/tasker commands`    | Command list     |
| `/tasker tips`        | Pro tips         |
| `/tasker shortcuts`   | Quick shortcuts  |
| `/tasker status`      | Connection check |
| `/tasker link <code>` | Account linking  |

### All /taskertask Commands

| Command                            | Description          |
| ---------------------------------- | -------------------- |
| `/taskertask`                      | Task menu            |
| `/taskertask create`               | Create task form     |
| `/taskertask create "title"`       | Quick create         |
| `/taskertask list`                 | All tasks            |
| `/taskertask list pending`         | Pending only         |
| `/taskertask list completed`       | Completed only       |
| `/taskertask list in_progress`     | In progress          |
| `/taskertask list overdue`         | Overdue tasks        |
| `/taskertask list priority:urgent` | Urgent tasks         |
| `/taskertask list priority:high`   | High priority        |
| `/taskertask list priority:medium` | Medium priority      |
| `/taskertask list priority:low`    | Low priority         |
| `/taskertask list project:<id>`    | Project tasks        |
| `/taskertask complete`             | Complete form        |
| `/taskertask done`                 | Complete form        |
| `/taskertask assign`               | Assign form          |
| `/taskertask details`              | View details form    |
| `/taskertask info`                 | View details form    |
| `/taskertask view`                 | View details form    |
| `/taskertask delete`               | Delete form          |
| `/taskertask remove`               | Delete form          |
| `/taskertask update`               | Update (coming soon) |
| `/taskertask edit`                 | Update (coming soon) |

### All /taskerproject Commands

| Command                                     | Description           |
| ------------------------------------------- | --------------------- |
| `/taskerproject`                            | Project menu          |
| `/taskerproject create`                     | Create project form   |
| `/taskerproject create "name"`              | Quick create          |
| `/taskerproject list`                       | All projects          |
| `/taskerproject invite`                     | Invite form           |
| `/taskerproject invite <id> <email>`        | Quick invite (editor) |
| `/taskerproject invite <id> <email> owner`  | Invite as owner       |
| `/taskerproject invite <id> <email> editor` | Invite as editor      |
| `/taskerproject invite <id> <email> viewer` | Invite as viewer      |
| `/taskerproject details`                    | Details form          |
| `/taskerproject details <id>`               | View project          |
| `/taskerproject info`                       | Details form          |
| `/taskerproject info <id>`                  | View project          |
| `/taskerproject members`                    | Members form          |
| `/taskerproject members <id>`               | View members          |

### Priority Reference

| Value    | Display  | Use Case           |
| -------- | -------- | ------------------ |
| `urgent` | 🔴 Urgent | Critical deadlines |
| `high`   | 🟠 High   | Important tasks    |
| `medium` | 🟡 Medium | Standard tasks     |
| `low`    | 🟢 Low    | Nice to have       |

### Role Reference

| Role     | Icon | Permissions          |
| -------- | ---- | -------------------- |
| `owner`  | 👑    | Full access + invite |
| `editor` | ✏️    | Create + edit tasks  |
| `viewer` | 👁️    | Read-only            |

### Status Reference

| Status        | Icon | Meaning       |
| ------------- | ---- | ------------- |
| `pending`     | ⬜    | Not started   |
| `in_progress` | 🔄    | Working on it |
| `completed`   | ✅    | Done          |

---

## 💡 Pro Tips

1. **Link First** — Use `/tasker link <code>` before anything else
2. **Forms are Friendly** — Just type the command without parameters for interactive forms
3. **Natural Language** — Chat with TaskerBot like a human, not a robot
4. **Use Filters** — Combine filters: `/taskertask list priority:high status:pending`
5. **Set Reminders** — Enable reminders when creating tasks
6. **Recurring Tasks** — Use daily/weekly/monthly for habits
7. **Project Collaboration** — Invite team members with appropriate roles

---

## 🔗 Quick Links

- **Download App**: [GitHub Releases](https://github.com/ashu-debuger/ESD-App-Download/releases/latest)
- **Main Documentation**: [README.md](README.md)
- **Support**: Chat with TaskerBot or use `/tasker help`

---

*Made with ❤️ by Mantra Team*

*Document Version: 1.0 | Last Updated: 2025*
