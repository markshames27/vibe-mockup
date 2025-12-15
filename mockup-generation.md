---
name: mockup-generation
description: Generates web application mockups and clickable prototypes based on a user flow, using Tailwind CSS and Alpine.js. Use after the user flow has been defined.
---

# Mockup Generation Skill

## Overview

This skill helps you create visual mockups and a **clickable interactive prototype** for each screen in your user flow. Mockups will be designed with a mobile-first approach using industry-standard tools that LLMs excel at generating.

**Output**: A fully functional, clickable HTML prototype that works immediately in any browser—no installation or build tools required.

## Technology Stack

We use the most LLM-friendly stack for accurate, error-free code generation:

**HTML5 + Tailwind CSS + Alpine.js**

### Why This Stack?

✅ **LLM-Optimized**: These technologies have the most training data, resulting in accurate code generation  
✅ **No Build Tools**: Works directly via CDN—just open HTML files in a browser  
✅ **Professional Design**: Tailwind produces modern, beautiful UIs instantly  
✅ **Interactive**: Alpine.js adds reactivity without complexity  
✅ **Mobile-First**: Responsive by default with Tailwind's utilities  
✅ **Fast to Generate**: LLMs can create complete prototypes quickly  
✅ **Easy to Test**: No server needed, just open in browser  
✅ **Developer-Ready**: Easy to convert to React/Vue/Next.js later

### What You'll Get

- **Tailwind CSS**: Utility-first CSS framework for rapid, consistent styling
- **Alpine.js**: Lightweight JavaScript for interactivity (dropdowns, modals, forms)
- **shadcn-inspired components**: Accessible, beautiful UI components
- **Mobile-first responsive design**: Optimized for all screen sizes
- **No backend required**: Pure frontend prototype

## Design Principles

**Mobile-First**: All mockups optimized for mobile devices first, then scaled for larger screens.

**Keep It Simple**: Don't create unnecessary screens or features. Use clear language and minimize form fields.

**Component-Based**: Use consistent, reusable components throughout the prototype.

**Accessible**: Semantic HTML and ARIA attributes for screen readers.

## Process

### Step 1: Review the User Flow
Understand all screens needed, their purpose, and user actions on each.

### Step 2: Define Screen Components
For each screen, identify:
- Main content area
- Navigation elements
- Input fields (if applicable)
- Buttons and calls-to-action
- Interactive elements (dropdowns, modals, etc.)
- Supporting information

### Step 3: Create Mockup Descriptions
Describe each screen in detail, including layout, components, content, and visual hierarchy.

### Step 4: Specify Interactions
For each interactive element, describe what happens when the user interacts with it.

### Step 5: Build Clickable Prototype
I will create a working HTML prototype with:
- All screens implemented as HTML pages
- Navigation between screens
- Interactive elements (buttons, forms, dropdowns, modals)
- Mobile-first responsive design
- Tailwind CSS for styling
- Alpine.js for interactivity
- Professional, modern appearance

The prototype will be:
- **Fully clickable** - Navigate between all screens
- **Interactive** - Forms, buttons, dropdowns, and modals work
- **Responsive** - Optimized for mobile, tablet, and desktop
- **No backend** - Pure frontend, no server required
- **Ready to test** - Open in any browser and interact immediately

### Step 6: Generate Screenshots
I will capture screenshots of each screen to provide visual documentation alongside the code.

## Mockup Description Format

### Screen Name

**Purpose**: What is the user trying to accomplish?

**Layout**:
- Header area
- Main content area
- Footer or action buttons

**Components**:
- **Component 1**: Description (e.g., Button, Input, Card)
- **Component 2**: Description (e.g., Dropdown, Modal, Navigation)

**Interactions**:
- Button 1: Leads to Screen X
- Button 2: Opens modal
- Form: Validates and navigates to Screen Y

**Tailwind Classes**:
- Key utility classes for styling
- Responsive breakpoints (sm:, md:, lg:)

**Alpine.js Behavior**:
- State management (x-data)
- Click handlers (@click)
- Conditional rendering (x-show, x-if)

**Content Notes**:
- Key copy or messaging
- Visual considerations

---

## Prototype Structure

The clickable prototype will be organized as:

```
prototype/
├── index.html          # Landing/first screen
├── screen-2.html       # Second screen
├── screen-3.html       # Third screen
├── ...
└── screenshots/
    ├── screen-1.png
    ├── screen-2.png
    └── ...
```

### Basic Template Structure

Each HTML file will follow this structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Screen Name</title>
    <!-- Tailwind CSS via CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Alpine.js via CDN -->
    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
</head>
<body class="bg-gray-50 min-h-screen">
    <!-- Screen content here -->
</body>
</html>
```

### Features Included

**Navigation**: Click buttons to move between screens

**Form Interactions**: Input fields, dropdowns, checkboxes work with validation

**Visual Feedback**: Hover states, active states, loading indicators

**Modals & Overlays**: Pop-ups and dialogs using Alpine.js

**Responsive Design**: Adapts to mobile (default), tablet (md:), and desktop (lg:)

**State Management**: Alpine.js handles component state (open/closed, selected, etc.)

**Animations**: Smooth transitions using Tailwind and Alpine

## Output

I will provide:
1. **Detailed mockup descriptions** for each screen
2. **Layout specifications** with Tailwind classes
3. **Component inventory** with Alpine.js behaviors
4. **Interaction specifications** (click handlers, navigation)
5. **Complete clickable prototype** (HTML files)
6. **Screenshots** of each screen (mobile and desktop views)
7. **Instructions** for opening and testing the prototype
8. **Responsive behavior notes** for different screen sizes

## Testing Your Prototype

Once generated, you can:
1. **Open `index.html`** in any web browser (Chrome, Firefox, Safari, Edge)
2. **Click through** all screens and interactions
3. **Test forms** - Fill out inputs, submit, see validation
4. **Try modals** - Open/close dialogs and overlays
5. **Test responsive** - Resize browser or use dev tools (F12 → Device Toolbar)
6. **Test on mobile** - Open on your phone or tablet
7. **Share with stakeholders** - Send files or host on GitHub Pages
8. **Get feedback** - Use as a reference for user testing

## Example Components

### Button with Navigation
```html
<a href="dashboard.html" 
   class="bg-blue-600 hover:bg-blue-700 text-white font-semibold py-3 px-6 rounded-lg transition">
    Get Started
</a>
```

### Interactive Modal
```html
<div x-data="{ open: false }">
    <button @click="open = true" 
            class="bg-blue-600 text-white px-4 py-2 rounded">
        Open Modal
    </button>
    
    <div x-show="open" 
         class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center">
        <div class="bg-white p-6 rounded-lg max-w-md">
            <h2 class="text-xl font-bold mb-4">Modal Title</h2>
            <p class="mb-4">Modal content here</p>
            <button @click="open = false" 
                    class="bg-gray-600 text-white px-4 py-2 rounded">
                Close
            </button>
        </div>
    </div>
</div>
```

### Form with Validation
```html
<form x-data="{ email: '', submitted: false }" 
      @submit.prevent="submitted = true">
    <input type="email" 
           x-model="email"
           required
           class="w-full border border-gray-300 rounded-lg px-4 py-2 mb-4"
           placeholder="Enter your email">
    
    <button type="submit" 
            class="w-full bg-blue-600 text-white py-2 rounded-lg">
        Submit
    </button>
    
    <div x-show="submitted" class="mt-4 text-green-600">
        Thank you! We'll be in touch.
    </div>
</form>
```

## Automatic Save to GitHub

After completing your mockups and prototype, I will **automatically save everything to GitHub**.

I will:
1. Update your project directory in the vibe-mockup repository
2. Save your Mockup specifications as `mockups.md`
3. Save all HTML prototype files to `prototype/` folder:
   - `index.html`, `screen-2.html`, etc.
4. Save all screenshots to `prototype/screenshots/` folder
5. Update any existing files (Lean Canvas, User Flow)
6. Commit and push to GitHub
7. **Report which files were uploaded** with a complete file list and provide the GitHub URL

You can also manually save at any point by typing:

```
save session
```

## Next Steps

You now have a complete visual specification and **working clickable prototype** ready for:
- **User testing** - Get real feedback on the flow and interactions
- **Stakeholder presentations** - Demo the working prototype
- **Development handoff** - Developers can reference or convert the code
- **Design iteration** - Easy to modify and improve based on feedback

All files are automatically saved to GitHub with a detailed report of what was uploaded.

## Why This Approach Works

**For You**: Get a working prototype you can click through and test immediately

**For Stakeholders**: See and interact with the actual product flow

**For Developers**: Clear reference with production-ready code patterns

**For LLMs**: Optimal stack for accurate, error-free code generation

**Result**: Professional, interactive prototypes in minutes, not hours.
