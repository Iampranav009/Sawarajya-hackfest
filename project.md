# Swarajya Hack Fest — Website Build Prompt (Antigravity / Cursor)

> **Goal:** Build a single-page hackathon landing website for **Swarajya Hack Fest** — a national-level hybrid cloud hackathon organized by AWS Cloud Club JDIET.
> **Stack:** HTML + CSS + Vanilla JS (single file) OR Next.js/React — your choice.
> **Time target:** Under 30 minutes.

---

## 🎨 Design System

### Color Palette
| Token | Value | Usage |
|-------|-------|-------|
| `--black` | `#0a0a0a` | Page background |
| `--saffron` | `#FF6B00` | Primary accent, CTAs, highlights |
| `--saffron-light` | `#FF9040` | Hover states, gradients |
| `--saffron-glow` | `rgba(255,107,0,0.25)` | Glow effects, glass borders |
| `--white` | `#FFFFFF` | Body text |
| `--muted` | `rgba(255,255,255,0.55)` | Secondary text |
| `--glass-bg` | `rgba(255,255,255,0.05)` | Glass card backgrounds |
| `--glass-border` | `rgba(255,107,0,0.3)` | Glass card borders |

### Typography
- **Display / Headings:** `Cinzel` (Google Fonts) — regal, historic feel matching the event name
- **Body / UI:** `DM Sans`
- Hero title "SWARAJYA HACK FEST" → very large, bold, letter-spaced, saffron gradient text

### Aesthetic Direction
- **Dark + Saffron** — like fire against a night sky
- **Glassmorphism cards** — `backdrop-filter: blur(12px)`, saffron-tinted borders
- **3D / depth effects** — subtle perspective transforms on card hover, floating elements
- **Particle / ember background** — canvas-based floating particles/embers in the hero (orange/saffron dots drifting upward, low opacity)
- **Smooth scroll** — `scroll-behavior: smooth`
- **Fade-in-up animations** — sections animate in as user scrolls (use `IntersectionObserver`)
- Navigation: **Sticky glassmorphism navbar** — blurred dark background, saffron underline on active link

---

## 🧱 Page Sections (in order)

### 1. Navbar (Sticky, Glassmorphism)
- Logo left: `☁ AWS Cloud Club JDIET` (small text, white)
- Nav links right: `Home | About | Rounds | Prizes | FAQ | Contact`
- On mobile: hamburger menu
- Background: `rgba(10,10,10,0.75)` + `backdrop-filter: blur(16px)` + bottom border saffron glow
- Smooth scroll to each section on click

---

### 2. Hero Section
- **Background:** Use the provided poster image (`1000304679.jpg`) as the full-width hero background with a dark overlay (`linear-gradient(to bottom, rgba(0,0,0,0.55), rgba(0,0,0,0.85))`)
- **Canvas particle layer** on top of the background — subtle saffron/orange embers floating upward
- **Center content:**
  - Small pill badge: `🏆 National Level Hackathon`
  - Main title: `SWARAJYA` (huge, Cinzel font, saffron gradient)
  - Subtitle: `HACK FEST`
  - Tagline: `The Ultimate Arena for Cloud Innovators`
  - Meta line: `Hybrid Cloud Hackathon · Online 24h + Offline Finals`
  - Prize badge (glass card): `💰 Prize Pool ₹20,000`
  - Two CTA buttons:
    - **`Register Now →`** (filled saffron, links to Google Form — placeholder `#register`)
    - **`Learn More ↓`** (outlined white, smooth scrolls to About section)
  - Countdown timer: `Registration closes: 14 March 2026, 11:00 PM` — live JS countdown showing Days / Hours / Minutes / Seconds in glass boxes

---

### 3. About Section
- Section title: `About the Event`
- Two columns (stack on mobile):
  - **Left:** Short paragraph:
    > *"Swarajya Hack Fest is a hybrid coding hackathon organized by AWS Cloud Club – JDIET in collaboration with the Department of Computer Science, JDIET. The event aims to encourage students to build innovative, scalable, cloud-based solutions using modern technologies and AWS services — promoting problem-solving, innovation, teamwork, and real-world application development."*
  - **Right:** Four glass stat cards in a 2×2 grid:
    - `24 Hours` — Online Coding
    - `₹20,000` — Prize Pool
    - `40 Teams` — Offline Finals
    - `2–3 Members` — Per Team

---

### 4. Rounds / Timeline Section
- Section title: `Event Rounds`
- Two large glass cards side by side (stack on mobile), each with a saffron accent border:

**Card 1 — Round 1: Online Hackathon**
- Icon: 💻
- Dates: `15 – 16 March 2026`
- Format: `24-Hour Coding Challenge`
- Details list:
  - Online inauguration via Google Meet
  - Problem statement announcement
  - 24-hour development window
  - 2 mentorship sessions
  - Submission via Google Form (GitHub repo + deployment link + description)
  - Top 30–35 teams shortlisted

**Card 2 — Round 2: Offline Final Round**
- Icon: 🏛️
- Date: `18 March 2026`
- Venue: `JDIET Campus, Yavatmal`
- Details list:
  - Top 40 teams present offline
  - Live demo + architecture walkthrough
  - Judged on: Innovation, Technical Quality, AWS Usage, Presentation
  - Trophies + Certificates awarded

Below the cards, a **horizontal timeline bar** with 4 milestones:
1. `Registration Open` → Now
2. `Registration Closes` → 14 March 2026, 11:00 PM
3. `Round 1 (Online)` → 15–16 March 2026
4. `Round 2 (Offline Finals)` → 18 March 2026

---

### 5. Prizes Section
- Section title: `Prize Pool`
- Subtitle: `Total Prize Pool Worth ₹20,000`
- Three podium-style glass cards (center card slightly larger for 1st place):

| Place | Prize |
|-------|-------|
| 🥇 1st Place | ₹10,000 + Trophy + Certificate |
| 🥈 2nd Place | ₹6,000 + Trophy + Certificate |
| 🥉 3rd Place | ₹4,000 + Trophy + Certificate |

- Below: small note: `All participants receive Participation Certificates. Shortlisted teams receive Certificates of Merit.`

---

### 6. Eligibility & Rules Section
- Section title: `Rules & Eligibility`
- Glass container with two columns of bullet points:
  - Currently enrolled students (UG or PG)
  - Teams of 2–3 members (no solo)
  - Code written only during the 24-hour window
  - Public GitHub repo required
  - AI tools (GitHub Copilot, AWS Kiro) are allowed ✅
  - No plagiarism — immediate disqualification
  - Must attend at least one mentorship session
  - Submission: GitHub link + deployment URL + description

---

### 7. About AWS Cloud Club JDIET Section
- Section title: `About AWS Cloud Club – JDIET`
- Two columns:
  - **Left:** Text block:
    > *AWS Cloud Club – JDIET is a student-led technical initiative at JDIET, focused on building awareness and hands-on experience in cloud computing and modern technologies. The club conducts workshops, hackathons, technical sessions, and cloud learning initiatives under the guidance of the Department of Computer Science.*
  - **Right:** Glass card with social links:
    - 📸 Instagram: `@awscloudclub_jdiet`
    - 💼 LinkedIn: `AWS Cloud Club JDIET`
    - 🌐 `swarajyahackfest.vercel.app`

---

### 8. FAQ Section
- Section title: `Frequently Asked Questions`
- Accordion-style FAQ (click to expand/collapse, smooth height transition):
  1. Who can participate? → Currently enrolled UG/PG students
  2. What is the team size? → 2 to 3 members (no solo)
  3. Is there a registration fee? → 1st round is free. For shortlisted teams, 2nd round has a ₹300 fee
  4. What technologies can we use? → Any modern tech; AWS services are strongly encouraged
  5. Will there be mentorship? → Yes, two structured mentorship sessions during Round 1
  6. How is Round 1 conducted? → Online via Google Meet kickoff + 24-hour coding
  7. How are teams shortlisted? → Based on innovation, technical quality, AWS usage, feasibility
  8. What do we need to submit? → GitHub repo link + deployment URL (if available) + project description

---

### 9. Contact & Register Section
- Section title: `Get in Touch`
- Glass card centered:
  - 📞 AWS Cloud Captain: `+91 91563 32109`
  - 📞 Technical Lead: `+91 95794 33689`
  - 🌐 Website: `swarajyahackfest.vercel.app`
  - 📸 Instagram: `@awscloudclub_jdiet`
- Large saffron CTA button: **`Register Now — It's Free →`** → links to Google Form (use `#` as placeholder, swap with actual URL)

---

### 10. Footer
- Left: `© 2026 Swarajya Hack Fest · AWS Cloud Club JDIET · JDIET, Yavatmal`
- Right: Social icons (Instagram, LinkedIn)
- Center: `Powered by AWS Community`
- Top border: thin saffron gradient line

---

## ⚙️ Interactions & Animations

1. **Page load:** Hero content fades in + slides up (staggered: badge → title → subtitle → CTAs → timer)
2. **Scroll reveal:** All sections use `IntersectionObserver` — fade-in-up as they enter viewport
3. **Navbar:** Becomes more opaque on scroll (`scrollY > 50`)
4. **Cards hover:** Slight lift (`translateY(-6px)`) + saffron glow shadow intensifies
5. **CTA buttons:** Saffron shimmer/shine sweep animation on hover
6. **Countdown timer:** Updates every second in real-time
7. **FAQ accordion:** Smooth height transition on open/close
8. **Canvas particles (Hero):** ~60 small orange/saffron circles drifting upward, looping endlessly
9. **Timeline dots:** Pulse animation on the milestone markers

---

## 📋 Technical Notes

- **Single HTML file** — no separate CSS/JS files
- Import Google Fonts: `Cinzel` + `DM Sans` via `<link>` in `<head>`
- Google Form link: Replace all `href="#register"` with actual Google Form URL when available
- Poster image path: `./1000304679.jpg` (place image in same folder as HTML file)
- Mobile-first responsive — all sections stack on screens < 768px
- No external UI libraries needed — pure CSS glassmorphism + Vanilla JS

---

## 🔗 Key Data Reference

| Field | Value |
|-------|-------|
| Event Name | Swarajya Hack Fest |
| Tagline | The Ultimate Arena for Cloud Innovators |
| Organizer | AWS Cloud Club – JDIET |
| Co-organizer | Dept. of Computer Science, JDIET |
| Institution | Jawaharlal Darda Institute of Engineering & Technology, Yavatmal |
| Format | Hybrid (Online + Offline) |
| Prize Pool | ₹20,000 |
| 1st Prize | ₹10,000 |
| 2nd Prize | ₹6,000 |
| 3rd Prize | ₹4,000 |
| Registration Deadline | 14 March 2026, 11:00 PM |
| Round 1 | 15–16 March 2026 (Online, 24h) |
| Round 2 | 18 March 2026 (Offline, JDIET Campus) |
| Teams Shortlisted | Top 40 for offline round |
| Team Size | 2–3 members |
| Cloud Captain | +91 91563 32109 |
| Technical Lead | +91 95794 33689 |
| Website | swarajyahackfest.vercel.app |
| Instagram | @awscloudclub_jdiet |
| Register Link | [Google Form — insert URL] |