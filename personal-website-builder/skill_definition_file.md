---
name: personal-website-builder
description: Help users design, build, and deploy personalized websites (Academic, Creative Portfolio, or 3D Interactive Room) using AI and deploy them to Vercel.
---

# Personal Website Builder Skill

This skill guides AI agents and users through creating customized personal websites based on design preferences, generating single-file prototypes, and deploying them online via Vercel.

---

## Workflow Steps

### Step 1: Visual Direction Selection
Ask the user to choose one of the three primary design directions:
1. **Academic Homepage**: Clean typography, structured layout for bio, publications, research, projects, and contact info.
2. **Creative Portfolio**: Expressive design, bold headers, accent colors, project stories, smooth interactions, and generous white space.
3. **3D Interactive Room**: A 3D isometric room built with Three.js (no external assets or imported models), where interactive furniture acts as navigation.

---

### Step 2: Information & Content Gathering
Collect essential details from the user:
* Name & Tagline / Short Bio
* Key Projects / Research Papers
* Social & Contact Links (GitHub, Email, LinkedIn, X, etc.)
* Color preference (Warm, Dark Mode, Minimalist, Cyberpunk, etc.)

---

### Step 3: Code Generation Prompt Templates

#### Option A: 3D Interactive Room (Three.js)
```text
Build a small isometric personal room in Three.js. 
- Use simple code-defined geometry for the room, desk, bookshelf, plant, and laptop.
- Interaction Rules:
  - Clicking the DESK opens the 'Projects' HTML overlay panel.
  - Clicking the BOOKSHELF opens the 'About / Research' HTML overlay panel.
  - Clicking the LAPTOP opens the 'Contact' HTML overlay panel.
- Visual Style: Warm colors, soft lighting, and subtle hover highlight effects when objects are hovered.
- Responsive Design: Keep text panels readable and adapt gracefully to mobile/phone viewports.
- Constraint: Deliver as a SINGLE complete HTML file (with inline CSS & Three.js imported via CDN). Use NO external 3D models, generated images, video, or backend. Start with a fully functional working preview.
```

#### Option B: Academic Homepage
```text
Build a clean, high-readability academic personal homepage.
- Sections: Short Bio, Research Interests, Selected Publications/Projects, Teaching, and Contact Links.
- Style: Generous white space, clear serif or clean sans-serif typography, subtle borders, high contrast.
- Single HTML file with embedded CSS/JS.
```

#### Option C: Creative Portfolio
```text
Build a modern, bold creative portfolio website.
- Sections: Expressive Hero Header, Featured Works (Card Grid with hover effects), Interactive Timeline/Experience, and Contact Modal.
- Style: Bold typography, warm/vivid accent colors, smooth scroll transitions, responsive layout.
- Single HTML file with Tailwind CSS (via CDN) and vanilla JS.
```

---

### Step 4: Vercel Deployment Guidance

Guide the user through deploying the generated website to Vercel using environment tokens:

1. **Obtain Vercel Token**:
   - Go to `Vercel → Account Settings → Tokens`.
   - Create a new token (e.g., `workshop-token`) with appropriate scope and expiry.
2. **Local Environment Setup**:
   - Create a local environment file (e.g., `.env.local` or `.env.display.local`, excluded from Git/uploads):
     ```env
     VERCEL_TOKEN=your_vercel_token_here
     ```
3. **Trigger Deployment**:
   - Run deployment commands via Vercel CLI or Agent CLI:
     ```bash
     npx vercel --token=$VERCEL_TOKEN --prod --yes
     ```
4. **Custom Domain & HTTPS Setup (Optional)**:
   - Provide steps for adding custom domains via Cloudflare, Vercel, Alibaba Cloud, or Tencent Cloud DNS settings.
   - Verify HTTPS and live deployment status.