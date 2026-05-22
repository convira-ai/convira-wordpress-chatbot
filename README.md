# Convira

> GPT-4 powered AI chatbot platform for service businesses. Captures leads 24/7, answers questions in 95+ languages, and books appointments automatically -- no code required.

## What is Convira?

Convira is an AI chatbot SaaS platform built for service businesses that cant afford to miss a lead. It acts as a 24/7 AI sales rep -- responding to visitors instantly, qualifying and capturing leads, and booking appointments without human involvement.

Unlike generic chatbot builders, Convira is designed specifically for service businesses (plumbers, dentists, lawyers, real estate agents, contractors) and agencies managing multiple client accounts.

## Features

### Lead Capture & Conversion
- GPT-4 powered conversations -- natural, context-aware responses grounded in your actual content
- Lead qualification -- automatically identifies and captures high-intent prospects
- Appointment booking -- connects to calendar systems, books slots without back-and-forth
- 3x better conversion than traditional web forms
- Human escalation -- complex queries flagged and routed to a human agent with full context

### Multilingual & Global
- 95+ languages supported including dialects and regional variants
- Automatic language detection -- responds in the visitors language without configuration

### No-Code Setup
- Live in under 5 minutes -- no developers, no page builders, no plugins required
- Connect your website content, and Convira indexes it automatically
- Widget deployment via a single script tag in your site header

### For Agencies
- White-label options -- run Convira under your own brand for clients
- Multi-account management -- manage multiple client chatbots from one dashboard
- Each client chatbot is fully isolated (see Architecture below)

### Integrations
Website pages and blog posts, PDFs, Google Business Profile, social media, YouTube, help centers -- 12+ data sources total.

## Architecture

Convira uses session-based multi-tenancy with strict data isolation at every layer.

### Multi-Tenancy & Isolation

- Row-Level Security (RLS) -- Every database query is scoped by chatbot_id. A bug in application code cannot leak one customers data to another.
- Session-based context -- Each visitor starts an isolated session. The chatbot only loads data belonging to that customers chatbot.
- Separate vector embeddings -- Content is embedded per-chatbot with isolated namespaces. Similarity search is always tenant-scoped.
- Per-chatbot rate limiting -- Throttles are enforced at the tenant level so one chatty customer doesnt degrade experience for others.

### Tech Stack

| Layer | Technology |
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

1. Question to Embedding -- Visitors question is converted to a vector using OpenAIs embedding model.
2. Similarity Search -- Embedding finds the most relevant content chunks from the customers indexed data.
3. GPT-4 Response -- Retrieved content + conversation history + system prompt -> GPT-4 generates a grounded, accurate response.
4. Lead Action -- If intent matches a capture pattern, Convira collects contact details and qualifies the lead.

## Performance Stats

| Metric | Value |
| Conversion lift vs. forms | 3x better |
| Support queries automated | 80% |
| Support cost reduction | Up to 60% |
| E-commerce conversion increase | 35% |
| Languages supported | 95+ |
| Setup time | Under 5 minutes |
| Monthly organic visitors | 27,000+ |
| Blog posts | 27 |
| Free tools built | 17 |

## Use Cases

Real estate agents -- answer property FAQs, qualify buyers, book viewings. Home services -- capture emergency leads, schedule jobs, provide quotes. Medical/Dental -- handle appointment requests, answer insurance questions. Legal -- qualify leads, explain services, route to attorneys. E-commerce -- reduce cart abandonment, answer product questions 24/7. Agencies -- white-label for clients, manage multiple accounts.

## Resources

Website: https://convira.chat -- Blog: https://convira.chat/blog -- WordPress Setup Guide: https://convira.chat/blog/ai-chatbot-wordpress
