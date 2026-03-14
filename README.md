## Monyet AI

**Monyet AI – Skill-based career helper**

Hey! This is the source code for **Monyet AI**, a playful little web app that helps people describe where they’re at in their career/skills, then routes them into the right experience. Think of it as a friendly, animated “onboarding” layer for humans, with an AI voice assistant baked in.

---

## ✨ What’s in the app

- **Skill selector landing** – a big, colorful question: “What describes you best?” with four choices (`Unskilled`, `Skilled`, `IDK`, `Entrepreneur`), each with its own emoji and copy.
- **Guided flow** – clicking a choice either:
  - **Redirects “Unskilled” users** straight into a dedicated `/unskilled-chat` experience, or  
  - **Shows a “survey loading” state** for the other options, with a celebratory card and spinner.
- **Ambient animations** – a wall of floating emoji (tools, jobs, rockets, charts, etc.) that drift around the background so the page feels alive instead of static.
- **Embedded AI voice assistant** – the ElevenLabs ConvAI widget is loaded via script and rendered as a custom `elevenlabs-convai` element, with a little speech-bubble prompt to encourage interaction.
- **Responsive layout** – designed to work on phones, tablets, and desktops without losing readability or fun.
- **Clean UI primitives** – cards, typography, and layouts built from a small set of reusable components for consistency.

---

## 🛠️ Built with

| Layer              | Tech |
|--------------------|------|
| Framework          | Next.js (App Router, `next@15`) |
| Language           | TypeScript + React (`react@19`) |
| Styling            | Tailwind CSS 4 + custom animation utilities |
| UI primitives      | Custom `Card` component (`@/components/ui/card`) + Geist font + Lucide ecosystem available |
| Build / lint       | TypeScript, ESLint (`eslint-config-next`) |
| Deployment target  | Optimized for platforms like Vercel (Next.js hosting) |

---

## 🧠 How it came together

1. **Define the core question** – started from a simple idea: “Let users self-identify their current skill situation in one click.”
2. **Scaffold the Next.js app** – created a fresh App Router project, wired up TypeScript, Tailwind 4, and global styles so the design system was ready from day one.
3. **Build the skill selector** – implemented the main page as a single `SkillSelector` client component with typed choices, card-based options, and a clear, bold call-to-action.
4. **Wire up routing & states** – added logic so:
   - “Unskilled” redirects to `/unskilled-chat` after a short delay, and  
   - all other options swap into a celebratory “survey is coming” screen.
5. **Layer in motion & delight** – added floating background emoji with different animation paths and opacities, plus card hover states and subtle scaling to make clicks feel rewarding.
6. **Integrate ElevenLabs ConvAI** – dynamically loaded the ConvAI script in a `useEffect`, declared the custom JSX intrinsic element so TypeScript is happy, and positioned the widget with a friendly helper bubble.

---

## ⚙️ Getting started

### **Prerequisites**

- **Node.js** 18+ (recommended)
- **pnpm / npm / yarn** – any modern package manager

### **Install dependencies**

```bash
# using npm
npm install

# or using pnpm
pnpm install
```

### **Run the dev server**

```bash
npm run dev
# then open http://localhost:3000 in your browser
```

### **Create a production build**

```bash
npm run build
npm start
```

### **Lint the code**

```bash
npm run lint
```

---

## 🔌 ElevenLabs ConvAI integration

The app uses the ElevenLabs ConvAI web widget via a `<script>` tag and a custom element:

- The script is loaded from `https://unpkg.com/@elevenlabs/convai-widget-embed` on the client.
- The widget is rendered as `<elevenlabs-convai>` with an `agent-id` attribute.
- A TypeScript JSX intrinsic element declaration lets you use that tag without type errors.

If you want to use your own agent, update the `agent-id` in the main page component.

---

## 💡 What I (you) can showcase with this

- How to embed **third‑party web components** (like ConvAI) into a **strict TypeScript + React** environment.
- How to structure a small **Next.js App Router** project around a single, high-impact page.
- How to design **playful, animated UIs** with Tailwind CSS 4 without sacrificing clarity.
- How to drive different **user flows** from a single selector component based on typed state.

---

## 🚀 Ideas for what’s next

- **Deeper flows for each choice** – build separate paths for `Skilled`, `IDK`, and `Entrepreneur` that ask targeted questions or route into different chat experiences.
- **Analytics & A/B testing** – track which choices users pick most often and experiment with copy, layout, or emoji sets.
- **Backend integration** – persist basic user intent or session info so follow-up interactions can be more personalized.
- **Accessibility & performance passes** – refine focus states, ARIA labels, and audit Lighthouse scores to keep things fast and inclusive.
- **Multi-language support** – localize the question, options, and assistant prompt for different regions.

---

*Thanks for checking out Monyet AI — have fun poking around the code!*
