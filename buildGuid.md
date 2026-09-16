Here’s a complete **UI + Product Specification Document**.  
This document is written so that any AI agent (or developer) can take it and fully design + build the website without needing extra questions.

---

# Campus Sports Society Website  
**UI & Product Specification Document**  
**Version:** 1.0  
**Inspired by:** [The MUSS – University of Utah](https://muss.utah.edu/)

---

## 1. Project Overview

**Goal:**  
Create a high-energy, motivational landing website for a **Campus Sports Society** that makes students feel part of a movement, not just a club.

**Primary Feeling:**  
Loud, chaotic, proud, inclusive, electric, student-owned.

**Target Audience:**  
University / college students (18–25 years old)

**Main Purpose of the Website:**
- Attract new members
- Build community identity
- Showcase events, teams, and culture
- Make joining feel exciting

**Tech Stack (Fixed):**
- Framework: **Astro 5**
- Styling: **Tailwind CSS**
- Animations: **GSAP + ScrollTrigger** (or CSS + Motion One)
- Deployment: **Vercel** or **Netlify** (free tier)
- No backend required in v1 (static site)

---

## 2. Design System

### 2.1 Color Palette

| Name              | Hex       | Usage                              |
|-------------------|-----------|------------------------------------|
| Primary Red       | `#BE0000` | Main brand, CTAs, accents          |
| Dark Red          | `#8B0000` | Hover states                       |
| Pure Black        | `#000000` | Backgrounds, header                |
| Near Black        | `#0A0A0A` | Section backgrounds                |
| White             | `#FFFFFF` | Text, logos                        |
| Off White         | `#F5F5F5` | Secondary text                     |
| Muted Gray        | `#A1A1AA` | Supporting text                    |

**Rule:** Use red sparingly but powerfully. Black + white should dominate.

### 2.2 Typography

| Element           | Font              | Weight     | Notes                          |
|-------------------|-------------------|------------|--------------------------------|
| Display / Hero    | Bebas Neue        | 400        | Very large, condensed, bold    |
| Headings          | Bebas Neue        | 400        | H1–H3                          |
| Body              | Inter             | 400–600    | Clean, readable                |
| Buttons           | Inter             | 600–700    | Uppercase optional             |

**Fallback fonts:** Impact, Arial Black, system-ui

### 2.3 Spacing & Layout

- Max content width: `1280px` (`max-w-7xl`)
- Section padding: `py-20 md:py-32`
- Border radius: Prefer `rounded-full` for buttons, `rounded-2xl` for cards
- Heavy use of full-bleed sections

### 2.4 Visual Style Rules

- High-contrast photography
- Red color overlays / multiply blend modes
- Subtle noise / grain textures
- Strong vertical rhythm
- Large typography
- Minimal text on hero
- Emotional, short, punchy copy

---

## 3. Site Structure (Single Page for v1)

```
1. Navbar (fixed)
2. Hero Section (100vh)
3. Mission / Statement Section
4. Quick Links / Actions
5. Events Preview
6. Teams / Sports Grid
7. Gallery / Culture
8. Join CTA (Final)
9. Footer
```

---

## 4. Detailed Section Specifications

### 4.1 Navbar

- Fixed at top
- Background: `bg-black/80` + `backdrop-blur-md`
- Logo on left (text or SVG)
- Links: Home, Events, Teams, Gallery, Join
- Primary CTA button on the right: “Join the Movement”
- Mobile: Hamburger menu

### 4.2 Hero Section (Most Important)

**Height:** `100svh` / `100vh`

**Layers (from back to front):**
1. Full-bleed high-energy photo (crowd / stadium / students)
2. Dark gradient overlay
3. Red multiply overlay (`bg-red-900/30 mix-blend-multiply`)
4. Subtle noise texture
5. Centered logo + text
6. Two CTA buttons
7. Scroll indicator at bottom

**Content:**
- Big logo treatment: “THE” (white) + “MUSS” (red) or campus name
- Short tagline: “This isn’t just a student section. It’s a movement.”
- Primary CTA: “Join the Chaos”
- Secondary CTA: “See Events”

**Animation:**
- Logo fades + scales in
- Text fades up
- Buttons appear with slight delay
- Subtle parallax on background image (optional)

### 4.3 Mission / Statement Section

Dark background.  
Large centered text:

> “We bring the noise.  
> We bring the passion.  
> We create the atmosphere that gives our teams a true home advantage.”

Keep it short and powerful.

### 4.4 Quick Links Section

4–6 cards in a grid:

Examples:
- Get Your Pass
- Match Day Tickets
- Rewards
- Game Day Guide
- Join WhatsApp / Discord
- Follow on Instagram

Each card: Image + Title + short description + arrow

### 4.5 Events Section

- Section title: “Upcoming Chaos”
- Horizontal or grid of event cards
- Each card: Date, Event name, Location, “Learn More” button

### 4.6 Teams / Sports Section

- Grid of sports (Football, Cricket, Basketball, etc.)
- Each item shows icon or photo + sport name
- Hover effect: slight scale + red border

### 4.7 Gallery / Culture Section

- Masonry or grid of high-energy photos
- Overlay text on some images
- Optional Instagram-style feed later

### 4.8 Final Join CTA

Full-width dark section with strong headline:

> “Ready to be part of something bigger?”

Big red button: “Become a Member”

### 4.9 Footer

Simple:
- Logo
- Quick links
- Social icons
- “Made by students, for students”
- Copyright

---

## 5. Content Tone Guidelines

- Short sentences
- High energy
- Inclusive (“every student is part of this”)
- Slightly chaotic / rebellious
- Never corporate or boring

**Good examples:**
- “Wear red. Bring noise.”
- “Be part of the chaos.”
- “This is a movement.”

**Avoid:**
- Long paragraphs
- Formal language
- Generic “Welcome to our club”

---

## 6. Technical Requirements for the Agent

1. Use **Astro** + **Tailwind CSS**
2. Make it fully responsive (mobile-first)
3. Optimize images (use Astro `<Image />` or proper formats)
4. Keep JavaScript minimal (use GSAP only where needed)
5. Semantic HTML
6. Good accessibility (alt texts, contrast, focus states)
7. Fast loading (Lighthouse score goal > 90)

---

## 7. Inspiration Reference

Primary reference:  
**https://muss.utah.edu/**

Key things to borrow:
- Full-screen emotional hero
- Layered image + red overlay technique
- Bold condensed typography
- Short, powerful messaging
- Sense of belonging and energy

Do **not** copy the design 1:1. Create an original version with the same spirit.

---

## 8. Deliverables Expected from the Agent

1. Complete Astro project
2. All sections implemented
3. Responsive design
4. Basic animations
5. Ready to deploy on Vercel/Netlify
6. Clean, well-commented code
7. Placeholder images (with clear comments where to replace)

---

## 9. Future Expansion (Out of scope for v1)

- Membership form
- Event registration
- Live social feed (Juicer or similar)
- Admin panel
- Multilingual support

---

**End of Document**

This document contains everything an agent needs to design and build the full website.
