# Convira

> GPT-4 powered AI chatbot platform for service businesses. Captures leads 24/7, answers questions in 95+ languages, and books appointments automatically -- no code required.

<p align="center">
  <a href="https://convira.chat">Website</a>
  .
  <a href="https://convira.chat/blog">Blog</a>
  .
  <a href="https://convira.chat/blog/ai-chatbot-wordpress">WordPress Setup Guide</a>
</p>

---

## What is Convira?

Convira is an AI chatbot SaaS platform built for service businesses that cannot afford to miss a lead. It acts as a 24/7 AI sales rep -- responding to visitors instantly, qualifying and capturing leads, and booking appointments without human involvement.

Unlike generic chatbot builders, Convira is designed specifically for service businesses -- plumbers, dentists, lawyers, real estate agents, contractors -- and agencies managing multiple client accounts.

**Core positioning:** Built for service businesses that cannot afford to miss leads.

---

## Features

### Lead Capture & Conversion
- **GPT-4 powered conversations** -- natural, context-aware responses grounded in your actual content
- **Lead qualification** -- automatically identifies and captures high-intent prospects
- **Appointment booking** -- connects to calendar systems, books slots without back-and-forth
- **3x better conversion** than traditional web forms
- **Human escalation** -- complex queries flagged and routed to a human agent with full context

### Multilingual & Global
- **95+ languages supported** including dialects and regional variants
- Automatic language detection -- responds in the visitors language without configuration

### No-Code Setup
- **Live in under 5 minutes** -- no developers, no page builders, no plugins required
- Connect your website content, and Convira indexes it automatically
- Widget deployment via a single script tag in your site header

### For Agencies
- **White-label options** -- run Convira under your own brand for clients
- **Multi-account management** -- manage multiple client chatbots from one dashboard
- Each client chatbot is fully isolated (see Architecture below)

### Integrations (12+ Data Sources)

| Source | What it provides |
|---|---|
| Website pages & blog posts | Your sites text, headings, FAQs |
| PDFs | Brochures, menus, documentation |
| Google Business Profile | Hours, reviews, services, location |
| Social media | Posts and responses |
| YouTube | Video transcripts |
| Help centers | Knowledge base articles |

---

## Architecture

Conviras backend is designed around **session-based multi-tenancy** with strict data isolation at every layer.

### Multi-Tenancy & Isolation

- **Row-Level Security (RLS)** -- Every database query is scoped by chatbot_id. A bug in application code cannot leak one customers data to another.
- **Session-based context** -- Each visitor starts an isolated session. The chatbot only loads data belonging to that customers chatbot.
- **Separate vector embeddings** -- Content is embedded per-chatbot with isolated namespaces. Similarity search is always tenant-scoped.
- **Per-chatbot rate limiting** -- Throttles are enforced at the tenant level so one chatty customer does not degrade experience for others.

### Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Next.js 14 (App Router) |
| Styling | Tailwind CSS + shadcn/ui |
| Animation | Framer Motion |
| Database | Supabase (PostgreSQL + RLS) |
| Auth | Supabase Auth |
| Payments | Stripe |
| AI/LLM | GPT-4 via OpenAI API |
| Hosting | Vercel |
| Domain/DNS | Cloudflare |

### How the Chatbot Works

1. **Question to Embedding** -- Visitors question is converted to a vector using OpenAIs embedding model.
2. **Similarity Search** -- Embedding finds the most relevant content chunks from the customers indexed data.
3. **GPT-4 Response** -- Retrieved content + conversation history + system prompt -> GPT-4 generates a grounded, accurate response.
4. **Lead Action** -- If intent matches a capture pattern (pricing inquiry, booking request, demo ask), Convira collects contact details and qualifies the lead.

---

## Performance Stats

| Metric | Value |
|---|---|
| Conversion lift vs. forms | **3x better** |
| Support queries automated | **80%** |
| Support cost reduction | **Up to 60%** |
| E-commerce conversion increase | **35%** |
| Languages supported | **95+** |
| Setup time | **Under 5 minutes** |
| Monthly organic visitors | **27,000+** |
| Blog posts | **27** |
| Free tools built | **17** |

---

## How Convira Ranks

Convira publishes in-depth comparisons across the chatbot space on their own blog:

- **#1 Best Overall** -- Best Conversational AI Chatbots 2026 (vs. Intercom Fin, Drift, Chatbase, CustomGPT, Dante AI, BotSonic, Tidio, Kommunicate)
- **#1 Best Overall for AI-Powered Support** -- Best No-Code Chatbot Builders 2026 (vs. Tidio, Intercom, Drift, Zendesk AI, Freshdesk, ChatBot.com, ManyChat, Botpress, Landbot)

---

## Use Cases

| Industry | How Convira Helps |
|---|---|
| **Real estate** | Answer property FAQs, qualify buyers, book viewings |
| **Home services** | Capture emergency leads, schedule jobs, provide quotes |
| **Medical/Dental** | Handle appointment requests, answer insurance questions |
| **Legal** | Qualify leads, explain services, route to attorneys |
| **E-commerce** | Reduce cart abandonment, answer product questions 24/7 |
| **Agencies** | White-label for clients, manage multiple accounts |

---

## Deployment on WordPress

Convira works on any WordPress site -- shared hosting, managed WordPress, self-hosted -- without a plugin, without a page builder, and without touching your themes code in ways that could break things. The deployment is a single script tag added to your sites header.

### How the WordPress Integration Works

When you connect a WordPress site to Convira, the platform:

1. **Fetches your content** -- Pages, posts, product descriptions, FAQ sections, everything you have published becomes part of the chatbots knowledge base.
2. **Chunks and indexes** -- Content is split into semantic sections and converted to vector embeddings. This lets the chatbot retrieve the right information when a visitor asks a question, rather than guessing from a generic prompt.
3. **Syncs continuously** -- When you publish a new blog post or update a service page, Convira picks up the changes automatically. Your chatbot stays current without any manual work.
4. **Serves the widget** -- A lightweight widget loads on your site, ready to chat with every visitor from the first second they arrive.

### Why No Plugin Matters

Most chatbot services for WordPress require you to install a plugin -- which means plugin compatibility issues with your theme, regular plugin updates to maintain security, a plugin slowing down your page load times, and limited customization options.

Convira avoids all of that. The widget is a standard `<script>` tag, the same way you would add Google Analytics or a live chat tool. It loads asynchronously so it does not block your page. You can deploy it through your themes header file, or through a tag manager like Google Tag Manager if you would rather not touch code directly.

### What the Chatbot Can Answer From Your WordPress Content

Once connected, the chatbot draws from everything on your site:

| Content Type | What the Chatbot Uses It For |
|---|---|
| Service pages | Answering what do you charge for X, do you offer Y |
| Blog posts | Answering industry questions with your own expertise |
| Contact page | Helping people find the right email or phone number |
| FAQs | Expanding on answers, handling follow-up questions naturally |
| Pricing page | Handling objection questions before they become abandons |
| Google Business Profile | Showing correct hours, services, and location |

### For Service Businesses With Multilingual Visitors

If your WordPress site serves a multilingual community -- a dental practice with Spanish-speaking patients, a contractor serving immigrant neighborhoods, a law firm with international clients -- Conviras 95+ language support becomes immediately practical.

The chatbot detects the visitors language automatically from their message. If someone asks do you take new patients? in Spanish, the chatbot responds in Spanish using content from your site. You do not configure separate bots for each language. The knowledge base stays in your language; Convira translates on the fly while grounding answers in your actual content.

### Getting Started

1. **Sign up** at convira.chat -- free trial, no credit card required
2. **Add your WordPress site** -- enter your URL, Convira pulls in your content automatically
3. **Customize the widget** -- match your brand colors and set your greeting message
4. **Add the script tag** -- one line in your header, or use a tag manager like Google Tag Manager
5. **Go live** -- the chatbot starts responding to visitors within minutes

For a complete walkthrough with screenshots, see the **How to Build an AI Chatbot on WordPress** guide -- a 20-minute step-by-step covering everything from signup to your first live conversation.

### WordPress-Specific Use Cases

**Local service business** -- A plumber in a diverse city captures leads in English, Spanish, Mandarin, and more without hiring multilingual staff. The chatbot qualifies the lead (whats the issue, where are you located, when do you need it) and books the appointment directly -- no phone tag.

**E-commerce with WooCommerce** -- Answer product questions at 2 AM. Reduce cart abandonment by handling objections (does this come with a warranty?) before the customer leaves. Route high-intent buyers to your sales team with full context already collected.

**Membership or course sites** -- Handle common questions about access, billing, and content without burning admin hours. Route billing disputes and technical issues to the right person with the conversation history attached.

**Agency: White-Label for clients** -- Run the chatbot under your agencys brand. Manage multiple client WordPress sites from one Convira dashboard. Each clients data and chatbot behavior stays fully isolated -- one clients content never bleeds into anothers conversations.

---

## Resources

- Website -- https://convira.chat
- Blog -- https://convira.chat/blog
- WordPress Setup Guide -- https://convira.chat/blog/ai-chatbot-wordpress
- Contact -- convirachatbot@gmail.com

---

*Convira is a product of convira.chat. This repository is for informational purposes.*
