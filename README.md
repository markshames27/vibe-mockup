# Vibe Mockup Workflow

A modular workflow for building web application mockups with AI assistance. This workflow guides you from initial idea refinement to detailed mockup generation through three focused skills.

## Quick Start

To begin a new project, use this prompt with your AI assistant:

```
I have an idea for a new web application. I want you to help me refine the idea, create a user flow, and generate mockups for it.

My idea is: [Your application idea here]

Please follow the Vibe Mockup Workflow defined at this GitHub repository: https://github.com/markshames27/vibe-mockup

Follow the guidelines and instructions in the README. Start with the first skill, "idea-refinement.md", and guide me through the process of creating a Lean Canvas for my idea.
```

Replace `[Your application idea here]` with your actual idea.

## Workflow Overview

The workflow consists of three sequential skills:

### 1. Idea Refinement (idea-refinement.md)
Creates a Lean Canvas to validate and structure your business model. Covers 9 key sections: Problem, Customer Segments, Unique Value Proposition, Solution, Channels, Revenue Streams, Cost Structure, Key Metrics, and Unfair Advantage.

**Duration**: 15-30 minutes  
**Output**: Completed Lean Canvas

### 2. User Flow Visualization (user-flow-visualization.md)
Maps out the complete user journey through your application with Mermaid diagrams. Identifies all screens, decision points, and interactions. Mermaid diagrams render beautifully on GitHub and in documentation tools.

**Duration**: 20-40 minutes  
**Output**: User flow diagram and screen list

### 3. Mockup Generation (mockup-generation.md)
Creates detailed, mobile-first mockup specifications for each screen. References components from [ui.shadcn.com](https://ui.shadcn.com) for consistent, accessible design.

**Duration**: 30-60 minutes  
**Output**: Complete mockup specifications for all screens

## How to Use the Workflow

### Step 1: Start with Idea Refinement
The AI will guide you through creating a Lean Canvas by asking clarifying questions for each section. Provide thoughtful, concise answers.

### Step 2: Move to User Flow Visualization
Once your Lean Canvas is complete, the AI will help you map out the user journey. You'll identify the primary goal, list main steps, identify decision points, and create a Mermaid diagram visualization that renders as a beautiful flowchart.

### Step 3: Generate Mockups
With your user flow defined, the AI will create detailed mockup descriptions for each screen, including layout, components, interactions, and responsive behavior.

### Step 4: Save Your Session
At any point during the workflow, you can save your progress to GitHub by typing:

```
save session
```

The AI will:
1. Create a new directory in this repository named after your project
2. Save all outputs (Lean Canvas, User Flow, Mockups) as markdown files
3. Commit and push the files to GitHub
4. Provide you with a link to your saved project

This allows you to:
- Resume work later from where you left off
- Share your progress with team members
- Track iterations and changes over time
- Keep a permanent record of your project

## Project Structure After Saving

When you save a session, your project will be stored in this structure:

```
vibe-mockup/
├── README.md
├── idea-refinement.md
├── user-flow-visualization.md
├── mockup-generation.md
└── projects/
    └── your-project-name/
        ├── lean-canvas.md
        ├── user-flow.md
        └── mockups.md
```

## Resuming a Saved Project

To resume work on a saved project, use this prompt:

```
I want to continue working on my Vibe Mockup project.

Please load my project from: https://github.com/markshames27/vibe-mockup/tree/main/projects/[your-project-name]

Review the current status and help me continue from where I left off.
```

## Guidelines and Best Practices

### For Best Results

**Be Specific**: Provide detailed answers to questions. The quality of your input directly affects the quality of the output.

**Iterate**: Don't expect perfection on the first pass. Use the AI to refine and improve your work through multiple iterations.

**Save Frequently**: Use "save session" after completing each skill to preserve your progress.

**Reference Previous Work**: When moving between skills, the AI will automatically reference your previous outputs for continuity.

### Design Principles

**Mobile-First**: All mockups are optimized for mobile devices first, then scaled for larger screens.

**Keep It Simple**: Focus on essential features and clear user flows. Avoid unnecessary complexity.

**Component-Based**: Reference ui.shadcn.com components for consistent, accessible, and production-ready designs.

**User-Centered**: Always consider the user's goals, pain points, and journey through your application.

## Skills Reference

Each skill file contains:
- **YAML Frontmatter**: Metadata including name and description
- **Overview**: What the skill does and when to use it
- **Process**: Step-by-step instructions
- **Output**: What you'll receive at the end
- **Next Steps**: How to proceed to the next skill

You can also use individual skills independently for specific purposes:
- Use **idea-refinement.md** alone to validate a business idea
- Use **user-flow-visualization.md** to redesign an existing application's flow
- Use **mockup-generation.md** to create mockups for a defined flow

## Example Projects
After using this workflow, you'll have:
1.  A validated business model (Lean Canvas)
2.  A clear user journey (User Flow with Mermaid diagram)
3.  Detailed screen specifications (Mockups)These deliverables are ready to:
- Share with stakeholders for feedback
- Hand off to a development team
- Use for building a prototype or MVP
- Guide user testing and iteration

## Support

For issues, suggestions, or contributions, please open an issue or pull request on this repository.

## License

This workflow is open-source and available under the MIT License.
