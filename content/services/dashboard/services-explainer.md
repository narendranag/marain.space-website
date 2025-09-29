<!-- ========================================================= -->
<!-- PROMPT: MARIAN SPACE SERVICES EXPLAINER DASHBOARD         -->
<!-- Purpose: Build an interactive, text-led explainer          -->
<!-- dashboard that helps users explore Marain Space’s          -->
<!-- five core services.                                        -->
<!-- ========================================================= -->

You are designing an **Explainer Dashboard** for **Marain Space** — a consulting collective blending anthropology and AI.  
The goal is to create a **text-led, visually calm, interactive experience** that helps visitors understand each service deeply and intuitively.

### 🎯 **Goal**
Guide visitors through Marain Space’s five interlocking services — showing:
1. What each service does  
2. How it works (inputs + tools)  
3. What it delivers (outcomes + artifacts)  
4. How they connect as a system

This is not a sales funnel — it’s an **educational and reflective** tool that builds trust through clarity and elegance.

---

### 🧱 **Structure**

#### **1. Overview Section (Hero)**
- Title: “🧭 Our Services — Designing clarity and empathy into every decision”
- Short intro paragraph (from the Services page)
- Visualization:  
  - Option A: Circular architecture (Mindstate → Lens Infinite → Strategem Weavers → Concord Table → Praxis Engine)  
  - Option B: Scroll-based timeline (Insight → Strategy → Dialogue → Practice)
- CTA: “Explore Each Service” → scrolls to detail cards

#### **2. Interactive Service Cards**
For each service (five total):
- Title + Icon (🧠 🔭 🧵 🕊️ ⚙️)
- Tagline (italic subheading)
- Description (1–2 paragraphs)
- Tabs or collapsible panels:
  - **Purpose**: high-level goal  
  - **How It Works**: list of inputs and tools  
  - **What You Get**: outcomes and deliverables  
  - **Examples**: 2–3 short applied scenarios
- Button: “See How It Fits” → highlights its position in the system

#### **3. System Map**
- Simple diagram showing relationships:
  - Mindstate → Lens Infinite → Strategem Weavers → Concord Table → Praxis Engine
- Hover/click highlights connections and dependencies
- Text explanation: “A living architecture — Insight → Strategy → Dialogue → Practice”

#### **4. Reflection / CTA Panel**
- Quote: *“Our task is not to predict the future, but to act wisely in its direction.”*
- Buttons:
  - **Begin a Dialogue** → contact form or scheduling link
  - **Explore Case Studies** → future content placeholder

---

### 🧭 **Content Source**
Use the copy from the “Services” markdown file:
- Titles
- Descriptions
- “How It Helps” → **Inputs & Tools**
- “Outcome” → **Deliverables**

Ensure **tone is preserved**:  
human, thoughtful, empathetic, clear.

---

### 🧠 **Interactivity / Features**
- Smooth scrolling transitions between sections
- Expand/collapse animations for each service panel
- Highlight pathway between services when one is selected
- Optional: simple knowledge graph showing dependencies (using D3.js or Cytoscape)

---

### 🎨 **Design Guidelines**
- **Typography**: Serif (titles), Sans-serif (body)
- **Color palette**: Warm neutrals, deep navy/charcoal text, indigo or teal accents
- **Layout**: Spacious, responsive, no stock imagery
- **Mood**: Calm, intelligent, reflective
- **Animations**: Gentle fade-ins, no motion overload

---

### 🧰 **Tech Stack Options**
- **Streamlit / Dash** (Python-based, quick prototype)
- **Next.js + Tailwind / Chakra UI** (production web)
- **Observable / D3.js** (data-driven visualization layer)
- Store service metadata as JSON for easy updates.

Example JSON structure:
```json
{
  "service": "Mindstate Analysis",
  "tagline": "Reading the hidden architectures of identity and meaning.",
  "purpose": "Decode emotional and cultural forces shaping behavior.",
  "inputs": ["Ethnographic interviews", "Narrative surveys", "Social discourse"],
  "tools": ["GPT-4 NLP analysis", "Semiotic frameworks", "Pattern recognition"],
  "deliverables": ["Mindstate Map", "Identity Archetypes", "Narrative Briefs"],
  "examples": ["Mapping sustainability attitudes", "Understanding trust divides"]
}
```

### 🧪 Optional MVP Prompt for LLM Integration

If you want to make it semi-intelligent, add a “Compare Services” or “Which service fits me?” section:

Prompt Example:

```text
Given this user scenario: [text], recommend which Marain Space service(s) would provide the most value. Explain your reasoning clearly, referencing relevant inputs, tools, and outcomes.”

This can be implemented with OpenAI’s GPT-4 API using the structured service JSON as context.

Deliverables
- Responsive dashboard or microsite
- Service data stored as JSON or markdown
- Interactive navigation
- Animated system map
- Clear CTAs linking to contact and case study pages

Success Criteria
- Users can understand all five services in <5 minutes
- Each service page feels human, calm, and confident
- Visual clarity reinforces conceptual clarity
- No friction: it should feel like a guided conversation, not a menu
```

