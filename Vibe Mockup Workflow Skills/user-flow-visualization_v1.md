# User Flow Visualization with Mermaid Diagrams

**Skill Name:** `user-flow-visualization`  
**Version:** `1.0.0`  
**Last Updated:** December 18, 2024  
**Author:** Markus Dejmek  
**Category:** UX Design / User Experience  
**Workflow Position:** Step 2 of 3 (Vibe Mockup Workflow)

## Overview

This skill helps you map out the user journey through your application and visualize it using Mermaid diagrams. A clear user flow is the blueprint for your mockups and ensures a logical, user-friendly experience. Use this skill after completing your Lean Canvas and before creating mockups.

**Duration:** 20-40 minutes  
**Output:** User flow diagram (Mermaid) and complete screen list saved to GitHub

## Process

### Step 1: Identify the Primary Goal
What is the primary goal the user wants to achieve when using your application?

### Step 2: List the Main Steps
Break down the user's journey into sequential steps or actions.

### Step 3: Identify Decision Points
Look for places where the user makes a choice that affects the flow (Yes/No branches, multiple options).

### Step 4: Describe Each Step
For each step, describe what the user does and what the system does in response.

### Step 5: Visualize the Flow
I will create a Mermaid diagram representation showing the complete user flow.

## Mermaid Diagram Notation

Mermaid uses a simple syntax that renders as visual flowcharts:

**Basic Syntax:**
```
graph TD
    Start[Starting Point] --> Action[User Action]
    Action --> Decision{Decision Point?}
    Decision -->|Yes| PathA[Path A]
    Decision -->|No| PathB[Path B]
    PathA --> End[End Point]
    PathB --> End
```

**Node Types:**
- `[Rectangle]` - Screen or user action
- `{Diamond}` - Decision point with Yes/No paths
- `((Circle))` - Start/End points
- `-->` - Flow direction
- `-->|Label|` - Labeled path (for decisions)

## Example

Here's an example for a simple login flow:

```mermaid
graph TD
    Start((User Visits App)) --> Landing[Landing Page]
    Landing --> Decision{Has Account?}
    Decision -->|Yes| Login[Login Screen]
    Decision -->|No| Signup[Sign Up Screen]
    
    Login --> Auth{Valid Credentials?}
    Auth -->|Yes| Dashboard[Dashboard]
    Auth -->|No| Error[Error Message]
    Error --> Login
    
    Signup --> Form[Fill Registration Form]
    Form --> Verify[Email Verification]
    Verify --> Dashboard
    
    Dashboard --> End((Session Active))
```

This renders as a visual flowchart showing:
- Entry point (User Visits App)
- Decision points (Has Account?, Valid Credentials?)
- Multiple paths (Login vs Signup)
- Error handling (Invalid credentials loop back)
- End state (Session Active)

## Output

I will provide:
1. A complete user journey description
2. Mermaid diagram code showing the complete flow
3. List of all screens/pages needed
4. Key interactions and decision points

The Mermaid diagram will render automatically on GitHub, in documentation tools, and most markdown viewers.

## Automatic Save to GitHub

After completing your user flow, I will **automatically save your work to GitHub**.

I will:
1. Update your project directory in the vibe-mockup repository
2. Save your User Flow as `user-flow.md` (including the Mermaid diagram)
3. Update any existing files (Lean Canvas)
4. Commit and push to GitHub
5. **Report which files were uploaded** and provide the GitHub URL

You can also manually save at any point by typing:

```
save session
```

## Next Steps

Once complete and saved, move to the mockup-generation skill to create visual specifications and a clickable prototype for each screen.
