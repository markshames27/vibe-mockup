---
name: mockup-generation
description: Generates web application mockups based on a user flow, using ui.shadcn.com as a design reference. Use after the user flow has been defined.
---

# Mockup Generation Skill

## Overview

This skill helps you create visual mockups for each screen in your user flow. Mockups will be designed with a mobile-first approach and reference components from [ui.shadcn.com](https://ui.shadcn.com).

## Design Principles

**Mobile-First**: All mockups optimized for mobile devices first, then scaled for larger screens.

**Keep It Simple**: Don't create unnecessary screens or features. Use clear language and minimize form fields.

**Component Reference**: Reference components from [ui.shadcn.com](https://ui.shadcn.com) for consistent, accessible design.

## Process

### Step 1: Review the User Flow
Understand all screens needed, their purpose, and user actions on each.

### Step 2: Define Screen Components
For each screen, identify:
- Main content area
- Navigation elements
- Input fields (if applicable)
- Buttons and calls-to-action
- Supporting information

### Step 3: Create Mockup Descriptions
Describe each screen in detail, including layout, components, content, and visual hierarchy.

### Step 4: Specify Interactions
For each interactive element, describe what happens when the user interacts with it.

## Mockup Description Format

### Screen Name

**Purpose**: What is the user trying to accomplish?

**Layout**:
- Header area
- Main content area
- Footer or action buttons

**Components**:
- Component 1: Description
- Component 2: Description

**Interactions**:
- Button 1: Leads to Screen X
- Button 2: Submits form data

**Content Notes**:
- Placeholder text or dynamic content
- Validation rules
- Error messages

## Example Mockup

### Login Screen

**Purpose**: Allow users to authenticate and access their account.

**Layout**:
- Centered card container with logo at top
- Form fields in middle
- Action buttons at bottom

**Components**:
- Logo: Application logo (centered)
- Title: "Welcome Back" (h2)
- Email Input: Text field with label "Email"
- Password Input: Password field with label "Password"
- Login Button: Primary button "Sign In"
- Sign Up Link: Text link "Don't have an account?"

**Interactions**:
- Login Button: Submits credentials, navigates to Dashboard on success
- Sign Up Link: Navigates to Sign Up screen

**Content Notes**:
- Email field validates email format
- Password field has show/hide toggle
- Error messages appear below relevant field

## Output

I will provide:
1. Complete set of mockup descriptions for all screens
2. Visual representations or sketches of key screens
3. Component inventory
4. Interaction specifications
5. Notes on responsive behavior

## Saving Your Progress

At any point, you can save your work to GitHub by typing:

```
save session
```

I will save all your mockups and the complete project to the repository.

## Next Steps

You now have a complete visual specification ready for development. Use "save session" to preserve your complete project on GitHub.
