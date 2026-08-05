# claude-code-skills

A collection of [Claude Code](https://claude.com/claude-code) skills for QA engineering workflows — test design, automation, bug investigation, performance review, and QA documentation.

Skills live in `.claude/skills/` and are automatically available to Claude Code when working in this project. Each skill defines a persona and process that Claude follows when invoked, either automatically (based on its description) or explicitly via `/<skill-name>`.

## Skills

| Skill | Description |
|---|---|
| [`api-test-generator`](.claude/skills/api-test-generator/SKILL.md) | Designs comprehensive API test strategies and generates production-ready API tests covering functional, contract, security, integration, and negative scenarios. |
| [`bug-investigator`](.claude/skills/bug-investigator/SKILL.md) | Investigates failed tests, production bugs, and application issues by analyzing evidence, identifying probable root causes, and recommending next debugging steps. |
| [`exploratory-testing`](.claude/skills/exploratory-testing/SKILL.md) | Creates structured exploratory testing charters, risk-based testing sessions, and investigation checklists. |
| [`performance-review`](.claude/skills/performance-review/SKILL.md) | Reviews performance test results, identifies bottlenecks, analyzes trends, and recommends optimizations. |
| [`playwright-generator`](.claude/skills/playwright-generator/SKILL.md) | Generates production-ready Playwright tests following QA automation best practices. |
| [`pr-description`](.claude/skills/pr-description/SKILL.md) | Writes pull request descriptions based on the diff between the current branch and main. |
| [`pr-review-qa`](.claude/skills/pr-review-qa/SKILL.md) | Reviews pull requests from a QA perspective — testing gaps, automation impact, and regression risks. |
| [`qa-documentation`](.claude/skills/qa-documentation/SKILL.md) | Creates QA documentation such as test strategies, test plans, release reports, and quality assessments, tailored to the target audience. |

## Usage

### 1. Navigate to your project

Open your terminal and go to your project directory:

```bash
cd my-project
```

### 2. Copy the `.claude` folder

Copy the `.claude` folder from this repository into the root of your project.

Your project structure should look like this:

```text
my-project/
├── src/
├── tests/
├── package.json
└── .claude/
    └── skills/
        ├── api-test-designer/
        ├── bug-investigator/
        ├── exploratory-testing/
        ├── performance-review/
        ├── playwright-generator/
        ├── pr-review-qa/
        └── qa-documentation/
```

### 3. Start Claude Code

From your project directory, run:

```bash
claude
```

### 4. Ask Claude to perform a task

For example:

> Generate Playwright tests for the Login page.

or

> Create Playwright tests for the Checkout flow.

Claude will analyze your request and automatically load the most appropriate skill based on its description.

### 5. (Optional) Explicitly invoke a skill

If you want to ensure a specific skill is used, reference it by name.

For example:

> Use the **playwright-generator** skill to generate Playwright tests for the Login page.

or

> Using the **playwright-generator** skill, create Playwright tests for this feature.

This helps Claude select the intended skill when multiple skills could apply.

## Adding a new skill

Create a new folder under `.claude/skills/<skill-name>/` with a `SKILL.md` file 

The structure will look like

.claude/
└── skills/
    └── skill-name/
        └── SKILL.md

The SKILL.md file must contain:

```markdown
---
name: skill-name
description: One-line description of what the skill does and when to use it.
---

Skill instructions and process go here.
```
