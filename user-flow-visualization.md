---
name: user-flow-visualization
description: Helps a user describe and visualize a user flow using ASCII art. Use after the idea has been refined and before creating mockups.
---

# User Flow Visualization Skill

## Overview

This skill helps you map out the user journey through your application and visualize it using ASCII art. A clear user flow is the blueprint for your mockups.

## Process

### Step 1: Identify the Primary Goal
What is the primary goal the user wants to achieve when using your application?

### Step 2: List the Main Steps
Break down the user's journey into sequential steps or actions.

### Step 3: Identify Decision Points
Look for places where the user makes a choice that affects the flow (Yes/No branches).

### Step 4: Describe Each Step
For each step, describe what the user does and what the system does in response.

### Step 5: Visualize the Flow
I will create an ASCII art representation showing the complete user flow.

## ASCII Flow Notation

```
[Start] - Beginning of the flow
(Screen/Action) - A screen or user action
{Decision} - A decision point with Yes/No paths
[End] - End of the flow
--> - Flow direction
```

## Example

```
[Start]
  |
  v
(Login Screen)
  |
  v
{User has account?}
  |
  +--Yes--> (Dashboard)
  |
  +--No---> (Sign Up)
              |
              v
            (Dashboard)
  |
  v
[End]
```

## Output

I will provide:
1. Detailed description of each step
2. ASCII art visualization of the complete flow
3. List of all screens/pages needed
4. Key interactions and decision points

## Next Steps

Once complete, move to the mockup-generation skill to create visual specifications for each screen.
