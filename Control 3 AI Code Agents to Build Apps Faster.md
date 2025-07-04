FROM YT July 2025
### Control 3 AI Code Agents to Build Apps Faster (Claude x Gemini x Copilot)
Zen Van Riel
https://www.youtube.com/watch?v=yl3-164nQyc 

## Project Starting Point

After running the scaffolding commands, all three agents will work simultaneously on the MAIN branch. The scaffolding should create:
- A Next.js 14 project with the tech stack configured
- Directory structure with exclusive ownership areas for each agent
- Single git repository (no separate branches needed)
- Basic configuration files

The key is that each agent has EXCLUSIVE write access to their directories, preventing conflicts while allowing them to read/import from each other's work.# AI Agent Orchestration Prompt

I need you to first provide project scaffolding commands, then create 3 separate markdown file artifacts for orchestrating the building of an AI Learning Tracker web app using 3 AI coding agents simultaneously. I'll be the human "puppet master" coordinating between them, reviewing their work, and helping when they get stuck. The agents will use Git as their primary communication method.

## Step 1: Project Scaffolding

Before creating the markdown files, please provide the commands and steps needed to scaffold a Next.js project that will support:
- The tech stack listed below
- Directory structure that matches the agent ownership areas
- Git initialization (single branch, no separate branches needed)
- Any necessary configuration files
- Note: No shared communication file needed - Git history IS the communication

## Step 2: Create Agent Mission Files

After providing the scaffolding instructions, create these as 4 distinct artifacts:

## Project Overview

**App Name**: AI Learning Tracker
**Purpose**: A web application that helps users track their learning progress, get AI-generated review questions, and visualize their learning journey.

## Core Features (in priority order)

1. *Topic Management*
   - Add new learning topics with categories
   - Edit/Delete topics
   - Set learning goals per topic

2. *Progress Tracking*
   - Daily progress notes with markdown support
   - Time spent tracking
   - Progress percentage per topic
   - Quick-add progress widget

3. *AI Review System*
   - Generate review questions based on progress notes (via OpenRouter API)
   - Different question types (multiple choice, open-ended)
   - Track quiz performance
   - Spaced repetition suggestions

4. *Analytics Dashboard*
   - Learning streak tracker
   - Time spent per topic charts
   - Progress over time visualization
   - Weekly/Monthly summaries

## Tech Stack

- **Frontend**: Next.js 14 with App Router, TypeScript, React
- **Styling**: Tailwind CSS + shadcn/ui components
- **Database**: SQLite with Drizzle ORM (stored in `./database/learning-tracker.db`)
- **AI Integration**: OpenRouter API for question generation
- **Charts**: Recharts for visualizations
- **State Management**: Zustand for client state
- **Testing**: Vitest for unit tests, Playwright for E2E


## Agent Assignments

Create 3 separate markdown files with the following structure:

### For Each Agent-Specific File:

Each file should contain:

#### 1. Mission Brief
- Their role in the project
- Primary responsibilities
- Success criteria

#### 2. Exclusive File Ownership
*Claude Code owns these exact paths:*
- `/app/api/**/*` (all API routes)
- `/lib/db/**/*` (database schema and queries)
- `/lib/ai/**/*` (OpenRouter integration)
- `/.env.example`
- `/middleware.ts`

*GitHub Copilot owns these exact paths:*
- `/app/(app)/**/*` (all UI pages)
- `/components/**/*` (all React components)
- `/hooks/**/*` (custom React hooks)
- `/lib/store/**/*` (Zustand stores)
- `/styles/**/*` (any custom styles)

*Gemini CLI owns these exact paths:*
- `/tests/**/*` (all test files)
- `/lib/utils/**/*` (utility functions)
- `/lib/types/**/*` (shared TypeScript types - Gemini can read from anywhere to create these)
- `/scripts/**/*` (build and dev scripts)
- `/.github/**/*` (CI/CD workflows)
- All config files in root (`*.config.ts`, `*.config.js`)

#### 3. Simplified PRD Tasks
Instead of full PRDs, each agent gets a concise task list with:
- Feature name
- 3-5 bullet points of requirements
- Expected file outputs
- API contract (if applicable)

#### 4. Git Communication Protocol
- Commit message format: `[YOUR_AGENT] Clear description`
- Handoff format: `[YOUR_AGENT] Implemented auth API, needs frontend forms from COPILOT`
- Cross-boundary change: `[YOUR_AGENT] Modified /path/to/file - Added missing field for integration`
- Check others' work: `git log --oneline -20` and `git show [commit-hash]`
- Always `git pull --rebase` before starting new work
- Commit every 1-3 files or logical unit of work

#### 5. Testing Approach
- Claude Code: Writes API route tests in `/tests/api/`
- GitHub Copilot: Writes component tests in `/tests/components/`
- Gemini CLI: Writes integration and E2E tests, sets up test infrastructure

#### 6. Environment Variables
Each agent documents their required env vars in .env.example:
```
# Added by [AGENT_NAME]
# Description: [WHAT IT'S FOR]
VARIABLE_NAME=example_value
```

Example variables needed:
- DATABASE_URL (for SQLite)
- OPENROUTER_API_KEY (for AI questions)



### Key Safeguards to Prevent Issues:

1. **Exclusive Directory Ownership**: Each agent owns specific directories completely - NO overlap
2. **Frequent Small Commits**: Every 1-3 files, enables real-time awareness of others' work
3. **Git as Single Source of Truth**: No separate communication files - git log shows all activity
4. **Descriptive Commit Messages**: Replace the need for separate documentation
5. **TODO Comments in Code**: For specific integration points that need attention
6. **Type Definition Sharing**: Shared types go in `/lib/types/` which all can read but only Gemini creates

## Human Coordinator Responsibilities

You will:
1. Run the scaffolding commands
2. Monitor git log for conflicts or issues
3. Help resolve any import/dependency issues
4. Provide .env values when needed
5. Run the dev server to test integration
6. Watch for commit messages requesting help or signaling handoffs

## Output Format

Please create 3 separate markdown file artifacts:

1. *claude-code-mission.md* - Self-contained instructions for Claude Code with exclusive ownership of backend/API files
2. *copilot-mission.md* - Self-contained instructions for GitHub Copilot with exclusive ownership of UI/component files  
3. *gemini-cli-mission.md* - Self-contained instructions for Gemini CLI with exclusive ownership of tests/utils/config files


Want more prompts and real AI coding/systems? Check out https://www.skool.com/ai-engineer

