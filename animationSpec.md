
# Campus Sports Society Website  
**Animations Specification Document**  
**Version:** 1.0  
**Stack:** Astro + Tailwind CSS + GSAP (ScrollTrigger)  
**Inspiration:** High-energy student section (MUSS style)

---

## 1. Animation Philosophy

- **Energy first** — Animations should feel powerful, fast, and slightly chaotic (matching the “movement / chaos” brand).
- **Purposeful** — Every animation must guide attention or create emotion. No random floating effects.
- **Performance** — Prefer GPU-accelerated properties (`transform`, `opacity`). Keep total JS light.
- **Mobile-friendly** — Reduce intensity or disable complex effects on small screens if needed.
- **Primary Library:** **GSAP + ScrollTrigger** (best choice for Astro).

---

## 2. Priority Ranking

| Priority | Animation Type                     | Must Implement? | Impact |
|----------|------------------------------------|------------------|--------|
| P0       | Hero Entrance Timeline             | Yes              | Extreme |
| P0       | Scroll-triggered section reveals   | Yes              | High |
| P1       | Parallax on Hero background        | Yes              | High |
| P1       | Button hover + click micro-interactions | Yes         | Medium |
| P1       | Staggered card / grid reveals      | Yes              | High |
| P2       | Text split / character reveal      | Recommended     | High |
| P2       | Smooth scroll (Lenis optional)     | Nice to have     | Medium |
| P3       | Magnetic buttons / cursor effects  | Optional         | Medium |
| P3       | Page transition / loader           | Optional         | Medium |

---

## 3. Detailed Animation List

### 3.1 Hero Section Animations (Highest Priority)

**Goal:** Create an immediate “wow” and emotional impact.

1. **Hero Entrance Timeline** (on page load)
   - Background image: Fade in + slight scale from 1.1 → 1
   - Red overlay: Fade in
   - Logo (“THE MUSS”): Scale up from 0.8 + fade in + slight bounce
   - Tagline: Fade up + slight y movement
   - CTA buttons: Staggered fade up + scale
   - Scroll indicator: Fade in after everything else

2. **Parallax Effect**
   - Background image moves slower than scroll (classic parallax)
   - Foreground logo / text can have opposite subtle movement

3. **Optional Advanced**
   - SplitText on the main logo/title (character by character reveal)
   - Subtle continuous floating or breathing scale on the logo

---

### 3.2 Scroll-Triggered Animations

Use **GSAP ScrollTrigger** for all of these.

| Element                        | Animation Type                  | Details |
|--------------------------------|---------------------------------|---------|
| Section titles                 | Fade up + slight y              | Stagger if multiple lines |
| Mission statement              | Large text reveal (clip or fade)| Strong entrance |
| Quick Links cards              | Staggered fade up + scale       | From bottom, 0.1s delay each |
| Event cards                    | Fade up + slight rotation       | Alternating left/right optional |
| Teams / Sports grid            | Stagger scale + fade            | Nice pop effect |
| Gallery images                 | Fade + scale from 0.9           | Masonry friendly |
| Final CTA section              | Big text scale + button bounce  | Strong call to action |

**Recommended easing:** `power3.out` or `power2.out`  
**Scrub option:** Use light scrub on parallax only. Most reveals should be one-time.

---

### 3.3 Micro-Interactions (Hover & Click)

These make the site feel alive and premium.

1. **Primary Buttons**
   - Hover: Scale 1.05 + slight brightness increase
   - Active/Click: Scale 0.97 (press effect)
   - Optional: Small red glow or underline expand

2. **Cards (Events, Teams, Quick Links)**
   - Hover: Scale 1.03 + lift (translateY -8px) + stronger shadow
   - Image inside card: Slight zoom (scale 1.08)

3. **Navbar Links**
   - Hover: Color change to red + underline slide in from left

4. **Logo**
   - Subtle scale or color shift on hover

5. **Social Icons**
   - Scale + rotate slightly on hover

---

### 3.4 Advanced / High-Impact Animations (Recommended)

| Animation                        | Description                                      | Difficulty | Recommendation |
|----------------------------------|--------------------------------------------------|------------|----------------|
| SplitText / Character Reveal     | Logo or big headlines animate letter by letter   | Medium     | Strongly recommended for Hero |
| Clip-path Text Reveal            | Text appears from a mask / wipe                  | Medium     | Excellent for mission statement |
| Magnetic Buttons                 | Button slightly follows mouse                    | Medium     | Nice premium feel |
| Smooth Scroll (Lenis)            | Buttery scrolling experience                     | Easy       | Recommended |
| Image Reveal on Scroll           | Images clip or wipe in                           | Medium     | Good for gallery |
| Counter / Number Animation       | If you show stats (members, events, etc.)        | Easy       | Nice touch |
| Cursor Follower (optional)       | Custom cursor with red accent                    | Medium     | Only if it fits the chaotic energy |

---

### 3.5 Page Load / Transition (Optional but Powerful)

- Simple preloader with logo + progress or just a red flash
- Or a clean fade-in of the entire page
- Avoid long loaders — this is a student society site, not a luxury brand

---

## 4. Technical Implementation Guidelines for the Agent

### Required Setup
```bash
npm install gsap
```

Then in the component or layout:
```js
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);
```

### Best Practices
- Always use `gsap.context()` in Astro for proper cleanup
- Prefer `transform` and `opacity` only
- Use `will-change: transform` sparingly
- Disable heavy animations on `prefers-reduced-motion`
- Test on mobile — reduce stagger times and parallax strength

### Recommended Timeline Structure (Hero Example)
```js
const tl = gsap.timeline({ defaults: { ease: "power3.out" } });

tl.from(".hero-bg", { scale: 1.15, duration: 1.8 })
  .from(".hero-overlay", { opacity: 0, duration: 1 }, "-=1.4")
  .from(".hero-logo", { scale: 0.7, opacity: 0, duration: 1.1 }, "-=1")
  .from(".hero-tagline", { y: 40, opacity: 0, duration: 0.9 }, "-=0.6")
  .from(".hero-cta", { y: 30, opacity: 0, stagger: 0.15, duration: 0.7 }, "-=0.5");
```

---

## 5. Animation Intensity by Section

| Section              | Intensity | Notes |
|----------------------|-----------|-------|
| Hero                 | Very High | Main wow moment |
| Mission Statement    | High      | Emotional |
| Quick Links          | Medium    | Clean stagger |
| Events               | Medium    | Engaging |
| Teams Grid           | Medium-High | Energetic |
| Gallery              | Medium    | Visual focus |
| Final CTA            | High      | Conversion focused |
| Footer               | Low       | Subtle only |

---

## 6. What to Avoid

- Endless looping animations that distract
- Heavy particle systems
- 3D / WebGL (overkill for this project)
- Animations that delay content readability
- Too many simultaneous animations

---

## 7. Success Criteria

The final site should feel:
- Powerful and energetic within the first 2 seconds
- Smooth and premium while scrolling
- Responsive and delightful on hover
- Fast (no jank)

---

**End of Animations Specification Document**

This document gives the agent everything needed to implement a high-end animation system that matches the MUSS-inspired energy.
