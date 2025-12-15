# VirtualPainter - Mockups & Clickable Prototype

**Project**: Paint Color Visualizer (VirtualPainter)  
**Date Created**: December 15, 2025  
**Workflow**: Vibe Mockup - Skill 3 (Mockup Generation)  
**User Flow**: Homeowner (End User)

---

## Overview

This document contains the complete clickable prototype for the **Homeowner (End User) flow** of VirtualPainter. The prototype consists of 9 interactive screens built with HTML5, Tailwind CSS, and Alpine.js.

**Technology Stack:**
- **HTML5** - Semantic markup
- **Tailwind CSS** (via CDN) - Utility-first styling
- **Alpine.js** (via CDN) - Lightweight interactivity
- **Mobile-First Design** - Optimized for 375px width (iPhone)
- **No Build Tools Required** - Just open HTML files in a browser

---

## Prototype Files

All prototype files are located in: `prototype/`

### HTML Files (9 screens)
1. `index.html` - Widget Landing
2. `upload.html` - Upload Photo Screen
3. `preview.html` - Photo Preview
4. `processing.html` - Processing Screen
5. `color-selection.html` - Color Selection Screen
6. `result.html` - Visualization Result
7. `download.html` - Download/Share Screen
8. `contact.html` - Contact Form
9. `thankyou.html` - Thank You Screen

### Screenshots
All screenshots are located in: `prototype/screenshots/`
- Mobile-first design (375x812px - iPhone size)
- 9 PNG screenshots, one for each screen

---

## How to Use the Prototype

### Option 1: Open Locally
1. Navigate to `prototype/` folder
2. Open `index.html` in any web browser (Chrome, Firefox, Safari, Edge)
3. Click through the interactive prototype

### Option 2: Test on Mobile
1. Transfer the `prototype/` folder to your phone
2. Open `index.html` in mobile browser
3. Experience the mobile-first design

### Option 3: Host on GitHub Pages
1. Push the prototype to GitHub
2. Enable GitHub Pages in repository settings
3. Share the public URL with stakeholders

---

## Screen Specifications

### Screen 1: Widget Landing (`index.html`)

**Purpose**: Introduce the VirtualPainter tool and encourage homeowners to start

**Layout**:
- Header: Blue gradient with paint brush icon
- Main content: Feature list with checkmarks
- CTA button: "Get Started - Upload Photo"
- Footer: "Powered by VirtualPainter"

**Components**:
- **Icon**: SVG paint brush icon in white circle
- **Heading**: "See Your House in Any Color!"
- **Feature List**: 3 features with green checkmark icons
  - AI-Powered Color Application
  - 12 Professional Colors
  - Before & After Comparison
- **CTA Button**: Large gradient blue button with arrow icon
- **Trust Badge**: Lock icon with "Your photo is secure and private"

**Interactions**:
- Click "Get Started" button → Navigate to `upload.html`

**Tailwind Classes**:
- `bg-gradient-to-b from-blue-50 to-white` - Background gradient
- `rounded-2xl shadow-2xl` - Card styling
- `hover:scale-105` - Button hover effect

**Alpine.js Behavior**: None (static page)

**Screenshot**: `screenshots/1-widget-landing.png`

---

### Screen 2: Upload Photo (`upload.html`)

**Purpose**: Let homeowners choose how to upload their house photo

**Layout**:
- Back button to previous screen
- Header: Blue gradient
- Progress indicator: Step 1 of 3
- Two upload options (Camera / File)
- Tips section at bottom

**Components**:
- **Back Button**: Arrow icon with "Back" text
- **Progress Indicator**: 3 circles showing current step
- **Camera Option**: Blue icon with "Take Photo" label
- **File Upload Option**: Green icon with "Choose from Gallery" label
- **Tips Box**: Blue background with photo tips

**Interactions**:
- Click "Back" → Navigate to `index.html`
- Click "Take Photo" → Navigate to `preview.html`
- Click "Choose from Gallery" → Navigate to `preview.html`
- Hover over options → Border changes to blue/green, icon animates

**Tailwind Classes**:
- `border-2 border-gray-200 hover:border-blue-500` - Interactive borders
- `group-hover:bg-blue-600` - Icon color change on hover
- `transition-all` - Smooth animations

**Alpine.js Behavior**:
- `x-data="{ selectedMethod: null }"` - Track hover state
- `@mouseenter` / `@mouseleave` - Update selected method

**Screenshot**: `screenshots/2-upload-photo.png`

---

### Screen 3: Photo Preview (`preview.html`)

**Purpose**: Let homeowners confirm their photo before processing

**Layout**:
- Back button
- Header: Blue gradient
- Progress indicator: Step 2 of 3
- Large photo preview area
- Quality check message (green)
- Two action buttons (Continue / Retake)

**Components**:
- **Photo Preview**: Placeholder with house icon
- **Quality Check**: Green box with checkmark and "Photo Quality: Good"
- **Continue Button**: Large gradient blue button
- **Retake Button**: Gray outline button

**Interactions**:
- Click "Back" → Navigate to `upload.html`
- Click "Continue - Process Photo" → Navigate to `processing.html`
- Click "Retake Photo" → Navigate to `upload.html`

**Tailwind Classes**:
- `aspect-[4/3]` - Maintain 4:3 aspect ratio
- `bg-green-50 border border-green-200` - Success message styling
- `transform hover:scale-105` - Button hover effect

**Alpine.js Behavior**:
- `x-data="{ photoApproved: false }"` - Track approval state

**Screenshot**: `screenshots/3-photo-preview.png`

---

### Screen 4: Processing (`processing.html`)

**Purpose**: Show AI processing status with loading animation

**Layout**:
- Header: Blue gradient
- Progress indicator: Step 3 of 3 (spinning)
- Large spinning loader animation
- Progress bar (0-90%)
- Status messages appearing sequentially

**Components**:
- **Spinning Loader**: Large circular spinner with lightbulb icon
- **Progress Bar**: Animated bar showing percentage
- **Status Messages**: 3 checkmarked items appearing progressively
  - "Uploading photo..."
  - "Detecting walls with AI..."
  - "Preparing color options..."

**Interactions**:
- Auto-redirect to `color-selection.html` after 3 seconds
- Progress bar animates from 0% to 90%

**Tailwind Classes**:
- `animate-spin` - Rotating loader
- `transition-all duration-300` - Smooth progress bar animation
- `animate-pulse` - Pulsing lock icon

**Alpine.js Behavior**:
- `x-data="{ progress: 0 }"` - Track progress percentage
- `x-init` - Auto-increment progress every 300ms
- `x-show` - Conditionally show status messages based on progress

**JavaScript**:
- `setTimeout()` - Auto-redirect after 3 seconds

**Screenshot**: `screenshots/4-processing.png`

---

### Screen 5: Color Selection (`color-selection.html`)

**Purpose**: Display 12 color options for homeowners to choose from

**Layout**:
- Back button
- Header: Blue gradient
- Progress indicator: Step 3 of 3
- 3x4 grid of color swatches
- Info message at bottom

**Components**:
- **Color Grid**: 12 color swatches in 3 columns
  - Classic White, Warm Beige, Soft Gray
  - Sage Green, Sky Blue, Coastal Blue
  - Terracotta, Charcoal, Navy Blue
  - Olive Green, Cream, Desert Sand
- Each swatch has:
  - Color square with border
  - Color name label below

**Interactions**:
- Click "Back" → Navigate to `preview.html`
- Click any color swatch → Navigate to `result.html`
- Hover over swatch → Border changes to blue, label changes color, scale increases

**Tailwind Classes**:
- `grid grid-cols-3 gap-4` - 3-column grid layout
- `aspect-square` - Square color swatches
- `hover:border-blue-500 hover:shadow-xl hover:scale-105` - Hover effects
- Custom colors: `bg-[#F5E6D3]`, `bg-[#B2C9AB]`, etc.

**Alpine.js Behavior**:
- `x-data="{ selectedColor: null }"` - Track selected color
- `@click` - Set selected color on click

**Screenshot**: `screenshots/5-color-selection.png`

---

### Screen 6: Visualization Result (`result.html`)

**Purpose**: Show before/after comparison with interactive slider

**Layout**:
- Back button ("Try Different Color")
- Header: Green gradient (success state)
- Before/after image with slider
- Slider control (range input)
- Color info box
- Two action buttons (Save & Continue / Try Different Color)

**Components**:
- **Before/After Comparison**: Split image with draggable slider
  - Left side: Original (gray)
  - Right side: With color (Sage Green)
  - White slider line with circular handle
- **Slider Control**: Range input (0-100)
- **Color Info Box**: Green background with color swatch and description
- **Action Buttons**: Blue CTA and gray secondary button

**Interactions**:
- Click "Try Different Color" → Navigate to `color-selection.html`
- Drag slider → Adjust before/after split position
- Click "Save & Continue" → Navigate to `download.html`

**Tailwind Classes**:
- `clip-path: inset()` - Create split image effect (via Alpine binding)
- `accent-blue-600` - Style range input
- `bg-gradient-to-br from-[#B2C9AB] to-[#8FAA88]` - Color overlay

**Alpine.js Behavior**:
- `x-data="{ sliderPosition: 50, showBefore: true }"` - Track slider position
- `x-model="sliderPosition"` - Bind range input to state
- `:style` - Dynamically apply clip-path based on slider position

**Screenshot**: `screenshots/6-visualization-result.png`

---

### Screen 7: Download/Share (`download.html`)

**Purpose**: Allow homeowners to save or share their visualization

**Layout**:
- Back button
- Header: Purple gradient
- Preview thumbnail with watermark
- Two action buttons (Download / Share)
- Success messages (conditional)
- Continue to quote button

**Components**:
- **Preview Thumbnail**: Colored house image with "VirtualPainter" watermark
- **Download Button**: Blue border button with download icon
- **Share Button**: Green border button with share icon
- **Success Messages**: Green/blue boxes appearing after action
- **CTA Button**: "Continue - Get Free Quote"

**Interactions**:
- Click "Back to Result" → Navigate to `result.html`
- Click "Download to Device" → Show success message, change button text
- Click "Share via SMS/Email" → Show success message, change button text
- Click "Continue - Get Free Quote" → Navigate to `contact.html`
- Click "Skip" link → Navigate to `contact.html`

**Tailwind Classes**:
- `group-hover:animate-bounce` - Bouncing download icon
- `x-transition` - Smooth appearance of success messages
- `bg-black bg-opacity-50` - Watermark styling

**Alpine.js Behavior**:
- `x-data="{ saved: false, shared: false }"` - Track action states
- `@click` - Toggle saved/shared states
- `x-show` - Conditionally show success messages
- `x-text` - Dynamically update button text

**Screenshot**: `screenshots/7-download-share.png`

---

### Screen 8: Contact Form (`contact.html`)

**Purpose**: Capture homeowner contact information for quote request

**Layout**:
- Back button
- Header: Orange gradient
- Selected color summary box
- Contact form (4 fields)
- Submit button
- Privacy notice
- "What happens next" section

**Components**:
- **Color Summary**: Green/blue gradient box with color swatch
- **Form Fields**:
  - Full Name (required)
  - Email Address (required)
  - Phone Number (required)
  - Additional Notes (optional)
- **Submit Button**: Orange gradient button
- **Privacy Notice**: Gray box with lock icon
- **Next Steps**: Numbered list (1-4)

**Interactions**:
- Click "Back" → Navigate to `download.html`
- Fill out form fields → Update Alpine state
- Click "Request Free Quote" → Validate form, navigate to `thankyou.html`
- Form validation → Show error messages if fields empty

**Tailwind Classes**:
- `focus:border-blue-500 focus:outline-none` - Input focus states
- `:class="errors.name ? 'border-red-500' : ''"` - Conditional error styling
- `resize-none` - Disable textarea resizing

**Alpine.js Behavior**:
- `x-data` - Form state (name, email, phone, message, errors)
- `x-model` - Two-way binding for form inputs
- `validate()` - Check required fields
- `submit()` - Validate and navigate to thank you page
- `@submit.prevent` - Prevent default form submission
- `x-show` - Show error messages conditionally
- `x-text` - Display error text

**Screenshot**: `screenshots/8-contact-form.png`

---

### Screen 9: Thank You (`thankyou.html`)

**Purpose**: Confirm quote request submission and set expectations

**Layout**:
- Header: Green gradient (success)
- Large success icon (bouncing)
- Thank you message
- "What's Next" section (4 steps)
- Selected color reminder
- Contact information
- Action buttons (Try Another Color / Close Window)
- Social proof (5 stars, rating)

**Components**:
- **Success Icon**: White circle with green checkmark, bouncing animation
- **Thank You Message**: Large heading with confirmation text
- **What's Next**: 4 numbered steps with icons
  1. We'll Review Your Request
  2. Expect Our Call
  3. Schedule Consultation
  4. Get Your Quote
- **Color Reminder**: Green/blue box with Sage Green swatch
- **Contact Info**: Phone and email with icons
- **Social Proof**: 5 yellow stars with "4.9/5 from 500+ happy customers"

**Interactions**:
- Click "Try Another Color" → Navigate to `index.html`
- Click "Close Window" → Close browser window

**Tailwind Classes**:
- `animate-bounce` - Bouncing success icon
- `text-yellow-400` - Star rating color
- `space-y-4` - Vertical spacing between steps

**Alpine.js Behavior**: None (static success page)

**Screenshot**: `screenshots/9-thank-you.png`

---

## Design System

### Color Palette

**Brand Colors:**
- Primary Blue: `#2563EB` (blue-600)
- Secondary Green: `#16A34A` (green-600)
- Accent Orange: `#EA580C` (orange-600)
- Accent Purple: `#9333EA` (purple-600)

**House Paint Colors (12 options):**
1. Classic White: `#FFFFFF`
2. Warm Beige: `#F5E6D3`
3. Soft Gray: `#D3D3D3`
4. Sage Green: `#B2C9AB`
5. Sky Blue: `#A7C7E7`
6. Coastal Blue: `#5B9AA0`
7. Terracotta: `#E07A5F`
8. Charcoal: `#3D3D3D`
9. Navy Blue: `#2C3E50`
10. Olive Green: `#808000`
11. Cream: `#FFFDD0`
12. Desert Sand: `#EDC9AF`

**UI Colors:**
- Background: `from-blue-50 to-white` gradient
- Success: `green-50`, `green-600`
- Error: `red-500`
- Gray Scale: `gray-50` to `gray-900`

### Typography

**Font Family**: System default (Tailwind default stack)
- `-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, ...`

**Font Sizes:**
- Headings: `text-2xl` (24px), `text-3xl` (30px)
- Body: `text-base` (16px)
- Small: `text-sm` (14px), `text-xs` (12px)

**Font Weights:**
- Bold: `font-bold` (700)
- Semibold: `font-semibold` (600)
- Medium: `font-medium` (500)
- Regular: `font-normal` (400)

### Spacing

**Padding:**
- Container: `p-6` (24px), `p-8` (32px)
- Buttons: `py-4 px-6` (16px 24px)
- Inputs: `px-4 py-3` (16px 12px)

**Margins:**
- Section spacing: `mb-6` (24px), `mb-8` (32px)
- Element spacing: `mb-2` (8px), `mb-4` (16px)

**Gaps:**
- Grid: `gap-4` (16px)
- Flex: `space-y-3` (12px), `space-y-4` (16px)

### Border Radius

- Cards: `rounded-2xl` (16px)
- Buttons: `rounded-xl` (12px)
- Inputs: `rounded-lg` (8px)
- Icons: `rounded-full` (50%)

### Shadows

- Cards: `shadow-2xl`
- Buttons: `shadow-lg`
- Hover: `hover:shadow-xl`

---

## Responsive Behavior

**Mobile (Default - 375px):**
- Single column layout
- Full-width buttons
- Touch-optimized tap targets (44px minimum)
- Stacked form fields

**Tablet (md: 768px):**
- Same as mobile (widget is embedded in company site)

**Desktop (lg: 1024px):**
- Same as mobile (widget is embedded in company site)
- Max-width: `max-w-md` (448px)
- Centered: `mx-auto`

---

## Interactive Features

### Animations
- **Button Hover**: Scale up (`hover:scale-105`)
- **Loading Spinner**: Continuous rotation (`animate-spin`)
- **Success Icon**: Bounce effect (`animate-bounce`)
- **Progress Bar**: Smooth width transition
- **Status Messages**: Fade in (`x-transition`)

### State Management (Alpine.js)
- **Upload Method**: Track camera vs file selection
- **Photo Approval**: Track if photo is approved
- **Processing Progress**: Auto-increment 0-90%
- **Selected Color**: Track which color is chosen
- **Slider Position**: Track before/after split (0-100)
- **Download/Share**: Track if actions completed
- **Form Data**: Track name, email, phone, message
- **Form Errors**: Track validation errors

### Form Validation
- **Required Fields**: Name, Email, Phone
- **Error Display**: Red border + error message below field
- **Submit Prevention**: Block submission if validation fails
- **Success Navigation**: Redirect to thank you page on valid submission

---

## Testing Checklist

### Functionality
- [ ] All navigation links work correctly
- [ ] Back buttons return to previous screen
- [ ] Form validation works (try submitting empty form)
- [ ] Auto-redirect works on processing screen
- [ ] Slider adjusts before/after split smoothly
- [ ] Download/Share buttons update text on click
- [ ] All hover effects work

### Responsive Design
- [ ] Looks good on mobile (375px)
- [ ] Looks good on tablet (768px)
- [ ] Looks good on desktop (1024px+)
- [ ] Touch targets are large enough (44px minimum)
- [ ] Text is readable at all sizes

### Browser Compatibility
- [ ] Works in Chrome
- [ ] Works in Firefox
- [ ] Works in Safari
- [ ] Works in Edge
- [ ] Works on iOS Safari
- [ ] Works on Android Chrome

### Performance
- [ ] Pages load quickly (no external dependencies except CDN)
- [ ] Animations are smooth (60fps)
- [ ] No console errors
- [ ] Images load properly

---

## Next Steps

### For User Testing
1. Share the prototype folder with stakeholders
2. Ask them to click through the entire flow
3. Gather feedback on:
   - Visual design
   - User flow clarity
   - Copy/messaging
   - Missing features
   - Confusing elements

### For Development
1. Convert prototype to production framework (React, Vue, Next.js)
2. Integrate with backend API
3. Add real image upload functionality
4. Integrate AI color application (Gemini 2.5 Flash via OpenRouter)
5. Connect to database for lead storage
6. Add email notifications
7. Implement analytics tracking

### For Iteration
1. Review user feedback
2. Update mockups based on feedback
3. Test with real homeowners
4. Refine color palette based on real paint brands
5. Add more features (trim colors, multiple walls, etc.)

---

## Files Included

```
prototype/
├── index.html                      # Screen 1: Widget Landing
├── upload.html                     # Screen 2: Upload Photo
├── preview.html                    # Screen 3: Photo Preview
├── processing.html                 # Screen 4: Processing
├── color-selection.html            # Screen 5: Color Selection
├── result.html                     # Screen 6: Visualization Result
├── download.html                   # Screen 7: Download/Share
├── contact.html                    # Screen 8: Contact Form
├── thankyou.html                   # Screen 9: Thank You
└── screenshots/
    ├── 1-widget-landing.png        # Screenshot of Screen 1
    ├── 2-upload-photo.png          # Screenshot of Screen 2
    ├── 3-photo-preview.png         # Screenshot of Screen 3
    ├── 4-processing.png            # Screenshot of Screen 4
    ├── 5-color-selection.png       # Screenshot of Screen 5
    ├── 6-visualization-result.png  # Screenshot of Screen 6
    ├── 7-download-share.png        # Screenshot of Screen 7
    ├── 8-contact-form.png          # Screenshot of Screen 8
    └── 9-thank-you.png             # Screenshot of Screen 9
```

---

**Created with**: Vibe Mockup Workflow  
**Date**: December 15, 2025  
**Technology**: HTML5 + Tailwind CSS + Alpine.js  
**Design**: Mobile-First, Responsive, Interactive
