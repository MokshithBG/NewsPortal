# NewsPortal
This application is used to see latest dev news

# Prompt Masters Hackathon — Build Prompt

You are an expert frontend engineer and UI/UX designer. Build a polished, production-quality MVP called **DevPulse** (you may choose a better professional name if needed) — a digital newspaper focused specifically on **coding and AI/LLM news**.

## IMPORTANT CONTEXT

This is a 90-minute hackathon project at a PU/pre-university level.

The most important requirement is:

> **Build a working, polished, reliable MVP. Do NOT over-engineer the project.**

Do not add unnecessary backend services, databases, authentication, complex infrastructure, or additional APIs.

The project must remain frontend-only.

---

# 1. TECH STACK

Use:

* React
* Vite
* JavaScript
* Tailwind CSS
* React Router if routing is needed
* NewsData.io API

Do NOT use:

* Backend
* Database
* Gemini API
* OpenAI API
* External proxy services
* RSS
* Authentication
* Unnecessary third-party services

The NewsData API has already been tested successfully.

---

# 2. ENVIRONMENT VARIABLE

The NewsData API key must come from:

```env
VITE_NEWSDATA_API_KEY=YOUR_API_KEY
```

Never hardcode the API key directly into source files.

Do not expose or commit `.env` to GitHub.

Make sure `.gitignore` contains:

```text
.env
.env.local
```

---

# 3. NEWS API

Use the NewsData.io latest-news API.

The API response contains fields such as:

```text
article_id
link
title
description
creator
language
country
category
pubDate
image_url
source_id
source_name
source_url
source_icon
duplicate
```

Primarily use:

```text
title
description
link
image_url
creator
source_name
source_url
pubDate
category
article_id
duplicate
```

Do not depend on the `content` field because the available API plan does not provide the full article.

---

# 4. NEWS FILTERING

Do NOT simply display every article returned under the generic `technology` category.

The website is specifically for:

### 💻 Coding

and

### 🤖 AI / LLM

Avoid unrelated technology news such as:

* Phones
* Cars
* Scooters
* Appliances
* Consumer products
* General business news
* Entertainment
* Social media news
* Unrelated technology stories

Focus on:

### Coding

Examples:

* Programming languages
* JavaScript
* TypeScript
* React
* Node.js
* Python
* C++
* Web development
* Developer tools
* GitHub
* Open source
* Software engineering
* Frameworks
* Developer platforms
* APIs

### AI / LLM

Examples:

* Artificial intelligence
* Large language models
* Generative AI
* AI agents
* Machine learning
* AI coding tools
* AI models
* LLM releases
* AI developer tools
* AI research relevant to developers

Use sensible keyword-based filtering on the article title, description, and keywords when available.

Do not make the filtering system unnecessarily complicated.

---

# 5. THREE PAGES ONLY

The application must have exactly three main pages.

## PAGE 1 — HOME / NEWS

This is the main newspaper homepage.

There must be **NO "See More" or "Read More" button on the article cards on this page.**

The homepage should focus on discovering news.

---

## HEADER / NAVIGATION

Create a professional newspaper-style navigation bar.

It should contain:

* Project logo/name
* Home
* Coding
* AI / LLM
* Our Sources
* Language selector

The navigation should be sticky or remain easily accessible while scrolling if this can be implemented cleanly.

---

# 6. BREAKING NEWS / LIVE NEWS TICKER

Immediately below the main navigation/header, add a **newspaper-style scrolling latest-news ticker**, inspired by the visual concept used by professional news websites such as Times of India.

It should look like a real news portal's breaking/latest-news strip.

### Design:

* A thin horizontal bar
* Strong red accent/background
* A label such as:

**LATEST**

or

**BREAKING NEWS**

* Headlines should continuously move horizontally from right to left
* Use the latest articles retrieved from NewsData.io
* Headlines should be clickable
* Clicking a headline should navigate to its Article Details page
* The ticker should loop continuously
* Keep the animation smooth and subtle
* Do not make it distracting or excessively fast

Example visual structure:

```text
┌──────────────────────────────────────────────────────────────┐
│ 🔴 LATEST │  New AI model released...  •  React update...   │
└──────────────────────────────────────────────────────────────┘
```

The ticker should use the actual fetched article titles rather than hardcoded fake news.

If there are not enough articles, gracefully display the available articles without breaking the animation.

On mobile, ensure the ticker remains usable and does not overflow the page.

---

# 7. HOMEPAGE HERO SECTION

Create a newspaper-style featured story area.

Show one prominent article with:

* Large image
* Category
* Headline
* Short description
* Source
* Date

The hero article should feel visually important.

---

# 8. HOMEPAGE NEWS SECTIONS

Create two clearly separated sections:

## CODING

Display relevant coding/development articles.

## AI / LLM

Display relevant AI and LLM articles.

Cards should contain:

* Image
* Category badge
* Headline
* Short description
* Source
* Date

Again:

### NO "Read More" or "See More" button on these cards.

The user can click the card/headline itself to navigate to the Article Details page.

---

# 9. PAGE 2 — ARTICLE DETAILS

This is where the user gets the detailed view of an individual article.

The layout should resemble a professional digital newspaper article page.

Suggested desktop layout:

```text
------------------------------------------------
|                                              |
| Category                                     |
| Large Article Headline                       |
|                                              |
| Source • Author • Date                       |
|                                              |
| -------------------  ----------------------- |
| |                 |  |                     | |
| |                 |  | Article information | |
| |     IMAGE       |  | / description       | |
| |                 |  |                     | |
| -------------------  ----------------------- |
|                                              |
| Article description / available preview      |
|                                              |
|             [ READ MORE → ]                  |
|                                              |
------------------------------------------------
```

The **Read More** button exists ONLY on this page.

When clicked, it must open the original article using the `link` field supplied by NewsData.io.

Open the original article in a new browser tab.

Do NOT scrape or reproduce the full article.

Clearly indicate that the user is being taken to the original publisher.

Example:

> Read the complete article from the original publisher.

Then:

**[ READ MORE → ]**

---

# 10. PAGE 3 — OUR SOURCES

Create a clean sources/attribution page.

Explain that the platform aggregates news metadata and links users back to the original publishers.

Display sources obtained from the articles.

For each source, show when available:

* Source icon
* Source name
* Source website

Do not invent sources.

Use the actual:

```text
source_name
source_url
source_icon
```

data received from NewsData.

The page should feel like a legitimate newspaper's "Sources & Attribution" page.

---

# 11. UI / UX DESIGN

The website should NOT look like a basic student API project.

Take visual inspiration from professional digital newspapers and editorial websites such as:

* India Today
* Times Now
* The Verge
* TechCrunch
* Wired

Do NOT copy their branding, logos, exact layouts, or copyrighted assets.

Instead, take inspiration from:

* Editorial hierarchy
* Typography
* Grid system
* Featured-story layouts
* News-card layouts
* Section headings
* Navigation
* Spacing
* Visual hierarchy
* Breaking-news ticker
* Professional appearance

The final UI should feel like:

> **A modern digital newspaper specifically designed for developers.**

---

# 12. VISUAL STYLE

Use a professional editorial design.

Prioritize:

* Strong typography
* Excellent spacing
* Clean card layouts
* Consistent border radius
* Subtle borders
* Good whitespace
* Clear hierarchy
* High-quality responsive layout
* Professional navigation
* Smooth hover effects
* Subtle transitions

Avoid:

* Excessive gradients
* Excessive animations
* Huge glowing elements
* Generic AI-looking designs
* Too many colors
* Overly rounded everything
* Unnecessary 3D effects

The design should feel:

**Editorial + trustworthy + modern + premium.**

The red accent used by the latest-news ticker should complement the overall design rather than dominate the entire interface.

---

# 13. RESPONSIVENESS

The website must work properly on:

* Desktop
* Laptop
* Tablet
* Mobile

The breaking-news ticker must also work properly on mobile without causing horizontal page overflow.

---

# 14. LANGUAGE SELECTOR

Add a language selector in the navigation.

Include:

* English
* Kannada
* Hindi
* Tamil
* Telugu

IMPORTANT:

Do not build a complicated translation system or use another API.

For the MVP, the language selector can be implemented as a UI-ready feature/static interface if full translation would introduce unnecessary risk.

The core English news experience must always work.

Do NOT allow the language feature to break the main application.

---

# 15. LOADING STATE

When news is being fetched, display a polished loading state.

Use skeleton cards rather than simply showing:

> Loading...

Make the loading state visually consistent with the final article cards.

---

# 16. ERROR HANDLING

If the NewsData API fails:

Display a friendly message such as:

> We couldn't load the latest developer news right now.

Provide a:

**Retry**

button.

Do not let the application crash.

---

# 17. MISSING IMAGES

Some articles may have:

```text
image_url: null
```

Handle this gracefully.

Create a professional fallback image/placeholder.

Never show a broken image icon.

---

# 18. DUPLICATE ARTICLES

The API can return:

```text
duplicate: true
```

Avoid displaying duplicate articles when practical.

Do not spend excessive time creating a complicated deduplication system.

---

# 19. ARTICLE ROUTING

Use React Router or an equivalent simple approach.

Suggested routes:

```text
/
/article/:id
/sources
```

The article detail page should identify the selected article using its `article_id`.

Do not refetch unnecessary data if the article information is already available in application state.

If the page is refreshed and the article is unavailable in state, handle it gracefully.

---

# 20. SEARCH / FILTER

If time permits, add a simple search field on the Home page.

It should allow users to search the currently loaded articles by:

* Title
* Description
* Category

Also provide simple filtering:

```text
All
Coding
AI / LLM
```

Do NOT build an advanced search engine.

If this feature risks the core functionality, prioritize the core news feed instead.

---

# 21. DATA MODEL

Normalize the API response into a simple frontend structure similar to:

```js
{
  id: article_id,
  title,
  description,
  image: image_url,
  source: source_name,
  sourceUrl: source_url,
  sourceIcon: source_icon,
  author: creator,
  date: pubDate,
  category,
  originalUrl: link
}
```

Keep the data structure clean and easy to understand.

---

# 22. COMPONENT STRUCTURE

Keep components reasonably organized.

For example:

```text
src/
├── components/
│   ├── Navbar
│   ├── NewsTicker
│   ├── HeroArticle
│   ├── NewsCard
│   ├── NewsSection
│   ├── LoadingSkeleton
│   └── Footer
│
├── pages/
│   ├── Home
│   ├── ArticleDetails
│   └── Sources
│
├── services/
│   └── newsApi
│
├── App
└── main
```

Do not create dozens of unnecessary components.

---

# 23. FOOTER

Create a professional footer containing:

* Project name
* Short description
* Navigation links
* Sources link
* Attribution
* Simple copyright-style text

Do not make the footer unnecessarily large.

---

# 24. PERFORMANCE

Keep the application lightweight.

Do not add unnecessary packages.

Do not introduce complicated architecture.

Avoid unnecessary API calls.

Fetch the news once and reuse the data where practical.

The news ticker should reuse the already-fetched news data instead of making another API request.

---

# 25. DO NOT ADD GEMINI

Do NOT integrate Gemini or any other AI API in this version.

The project is intentionally being presented as an MVP.

Potential future AI features can include:

* AI-powered article summaries
* AI categorization
* "Why should developers care?"
* Personalized developer news
* AI-powered recommendations
* Multilingual AI summaries
* Trending technology detection

These are future roadmap items, not required for the current MVP.

---

# 26. FINAL HACKATHON PRIORITY

The project has only 90 minutes.

Therefore:

### PRIORITY ORDER

1. NewsData API integration
2. Home page
3. Latest-news ticker
4. Article Details page
5. Read More → original source
6. Sources page
7. Professional UI polish
8. Responsive design
9. Loading/error states
10. Search/filter
11. Language selector
12. Optional enhancements

If time becomes limited, STOP adding features and polish the working MVP.

---

# FINAL DESIGN GOAL

When a judge opens the website, it should immediately feel like:

> **"This is a real developer newspaper, not just an API demo."**

The experience should resemble a professional digital news portal, with strong editorial hierarchy and a recognizable **latest-news ticker**, while remaining focused exclusively on **Coding and AI/LLM news**.

Keep the functionality simple, but make the presentation excellent.

**Working + polished + reliable is more important than feature count.**
