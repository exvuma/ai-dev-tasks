# Rule: Generating a Feature Implementation Plan

## Goal

To guide an AI assistant in creating a detailed feature implementation plan in Markdown format, based on an initial user prompt. The plan should bridge the gap between a high-level feature request and actionable development tasks, providing clear guidance for implementation.

## Process

1.  **Receive Initial Prompt:** The user provides a brief description or request for a new feature or functionality.
2.  **Review Project Context:** Always reference `@project-overview.mdc`, `README.md`, and `apps/confetti-db-bootstrapper/README.md` to understand the confetti codebase patterns, domain concepts, and technical conventions before proceeding.
3.  **Ask Clarifying Questions:** Before writing the plan, the AI _must_ ask clarifying questions to gather sufficient detail. The goal is to understand the "what" and "why" of the feature, not necessarily the "how" (which the developer will figure out). **IMPORTANT: Use numbered/lettered options for all questions so users can respond with simple selections like "1a 2b 3c".**
4.  **Generate Plan:** Based on the initial prompt, project context, and the user's answers to the clarifying questions, generate a comprehensive implementation plan using the structure outlined below.
5.  **Save Plan:** Save the generated document as `plan-[feature-name].md` inside the `/docs/tasks` directory.
6.  **Auto-Generate Tasks:** After creating the plan, automatically call the `@generate-tasks.md` rule to create detailed implementation tasks based on the plan.

## Clarifying Questions Format

**ALWAYS structure clarifying questions with numbered/lettered options:**

### Example Format:

```
### 1. **Question **
What should the system do?
- a) Option A description
- b) Option B description
- c) Option C description

### 2. **Another Question**
How should users interact?
- a) Option A
- b) Option B
- c) Option C

**Please respond with your selections (e.g., "1a 2. BorC 3.abc")**
```

## Clarifying Questions (Examples)

The AI should adapt its questions based on the prompt, but here are some common areas to explore:

- **Problem/Goal:** "What problem does this feature solve for the user?" or "What is the main goal we want to achieve with this feature?"
- **Target User:** "Who is the primary user of this feature?"
- **Core Functionality:** "Can you describe the key actions a user should be able to perform with this feature?"
- **User Stories:** "Could you provide a few user stories? (e.g., As a [type of user], I want to [perform an action] so that [benefit].)"
- **Acceptance Criteria:** "How will we know when this feature is successfully implemented? What are the key success criteria?"
- **Scope/Boundaries:** "Are there any specific things this feature _should not_ do (non-goals)?"
- **Data Requirements:** "What kind of data does this feature need to display or manipulate?"
- **Design/UI:** "Are there any existing design mockups or UI guidelines to follow?" or "Can you describe the desired look and feel?"
- **Edge Cases:** "Are there any potential edge cases or error conditions we should consider?"

## Plan Structure

The generated plan should include the following sections:

1.  **Feature Overview:** Briefly describe the feature and the problem it solves. State the goal.
2.  **User Stories:** Detail the user narratives describing feature usage and benefits.
3.  **Functional Requirements:** List the specific functionalities the feature must have. Use clear, concise language (e.g., "The system must allow users to upload a profile picture."). Number these requirements.
4.  **Technical Approach:** Outline the high-level technical approach, including:
    - Database changes needed (new tables, modifications to existing tables)
    - API endpoints required
    - Frontend components to create/modify
    - Integration points with existing features
5.  **Implementation Phases:** Break down the implementation into logical phases or milestones.
6.  **Dependencies:** List any dependencies on other features, external services, or technical requirements.
7.  **Risks and Considerations:** Identify potential challenges, technical risks, or areas requiring special attention.
    - Risk of potentially conflicting with existing code-based patterns

## Plan Focus

Plans should focus on bridging business requirements with technical implementation strategy. They should provide enough detail to guide task generation while remaining high-level enough to be flexible during implementation.

## Target Audience

Assume the primary reader of the plan is a **junior developer**. Therefore, the plan should be explicit, unambiguous, and provide clear guidance for implementation within the confetti codebase context.

## Output

- **Format:** Markdown (`.md`)
- **Location:** `/docs/tasks/`
- **Filename:** `plan-[feature-name].md`

## Final Instructions

1. Do NOT start implementing the plan - focus on creating a clear roadmap for implementation
2. **ALWAYS use numbered options for clarifying questions** so users can respond with simple selections
3. Reference existing domain concepts (Elements, Tasks, Events, etc.) for context
4. After creating the plan, automatically call `@generate-tasks.md` to create detailed implementation tasks
5. The plan should serve as the bridge between user requirements and technical implementation tasks
