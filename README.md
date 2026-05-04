# 🔍 SEO — Complete Developer Notes

> **Search Engine Optimization** is the discipline of making your website *discoverable, understandable, and trustworthy* to search engines — so users find you organically, without paid ads.

---

## Table of Contents

1. [What is SEO?](#what-is-seo)
2. [How Search Engines Work](#how-search-engines-work)
3. [The Three Types of SEO](#the-three-types-of-seo)
   - [On-Page SEO](#on-page-seo)
   - [Off-Page SEO](#off-page-seo)
   - [Technical SEO](#technical-seo)
4. [Implementing SEO with Next.js](#implementing-seo-with-nextjs)
   - [Metadata](#1--metadata)
   - [Sitemap](#2--sitemap)
   - [Robots.txt](#3--robotstxt)
5. [Dynamic SEO](#dynamic-seo)
6. [Quick Reference Cheatsheet](#quick-reference-cheatsheet)

---

## What is SEO?

Imagine you open a beautiful shop — but you build it in a hidden alley with no signboard, no address, and no listing anywhere. People simply will not find it, no matter how great your products are.

**That's a website without SEO.**

SEO (Search Engine Optimization) is the process of improving your website so that search engines like Google can:
- **Discover** your pages through crawling
- **Understand** what each page is about
- **Rank** your pages when users search for related topics

Without SEO, your site may exist but only one page (or none at all) shows up in results — and even that, very low. With SEO applied correctly, every page becomes a separate entry point. One page can rank for `"buy shoes"`, another for `"best running shoes"`, another for `"how to clean shoes"` — multiplying your surface area in search results.

> **In short:** SEO transforms your website from invisible to discoverable — from one unclear result to many targeted, ranked pages.

---

## How Search Engines Work

Search engines operate in three sequential stages. Understanding them is fundamental to understanding *why* SEO works.

```
[ Your Website ] ──► Crawling ──► Indexing ──► Ranking ──► [ User Sees You ]
```

### 🕷️ Stage 1 — Crawling

Search engines deploy automated bots (called **spiders** or **crawlers**) that travel across the internet by following links — from page to page, site to site.

- If your pages are not linked (internally or from external sites), bots may never find them
- If your site structure is broken or your `robots.txt` blocks crawlers, pages get skipped entirely

> **Crawling = "Can the bot find your page?"**

### 📚 Stage 2 — Indexing

Once a page is discovered, Google tries to *understand* it. It reads:
- Your content, headings, and keywords
- Image alt texts
- Internal link structure
- Page metadata

All of this gets stored in Google's massive database — the **Index**. Think of it like being catalogued into a digital library. Pages that are unclear, blocked, or poorly structured may not be indexed at all.

> **Indexing = "Does Google understand your page?"**

### 🏆 Stage 3 — Ranking

When a user searches, Google scans its index and returns the most relevant, high-quality pages in order. This is where the real competition happens.

**Key ranking factors include:**

| Factor | What It Means |
|---|---|
| **Content Quality** | Is the content useful, accurate, and complete? |
| **Keyword Relevance** | Does it match what the user is searching for? |
| **Page Speed** | Does the site load quickly? |
| **Mobile Friendliness** | Is it usable on all screen sizes? |
| **Backlinks** | Do trusted websites link to you? |
| **User Experience** | Do users engage and stay, or bounce immediately? |
| **Search Intent Match** | Does the page answer the *real* question behind the search? |

> **Ranking = "How high does your page appear?"**

---

## The Three Types of SEO

```
                    ┌─────────────────────────────────────┐
                    │              SEO                    │
                    └───────────┬────────────┬────────────┘
                                │            │
                    ┌───────────▼─┐  ┌───────▼──────┐  ┌──────────────────┐
                    │  On-Page    │  │  Off-Page    │  │  Technical SEO   │
                    │  SEO        │  │  SEO         │  │                  │
                    └─────────────┘  └──────────────┘  └──────────────────┘
                    Content &        Trust &            Crawlability &
                    structure        authority          infrastructure
```

---

### On-Page SEO

On-page SEO is about optimizing **everything inside a web page** — your content, structure, and HTML elements — so search engines and users can immediately understand what the page is about.

**Core on-page elements:**

| Element | Purpose | Best Practice |
|---|---|---|
| `<title>` tag | Primary ranking signal; shown in browser tab & search results | Include main keyword; keep under 60 chars |
| `<meta name="description">` | Shown below title in search results; affects CTR | Write a compelling summary; 150–160 chars |
| `<h1>` heading | Tells Google the main topic of the page | One per page; include primary keyword |
| `<h2>`, `<h3>` headings | Structure and subtopics | Use naturally; don't keyword stuff |
| URL Slug | Signals page topic | Use short, readable, keyword-rich URLs |
| Image `alt` text | Tells bots what images contain | Descriptive, relevant, not stuffed |
| Internal links | Connects related content; helps crawling | Link to related pages naturally |
| Canonical URL | Tells Google which URL is the "real" one | Prevents duplicate content penalties |

**Classic HTML example (before frameworks):**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Best Running Shoes | Free Delivery</title>
  <meta name="description" content="Buy the best running shoes with comfort and durability at affordable prices.">
  <link rel="canonical" href="https://example.com/running-shoes" />
</head>
<body>
  <h1>Best Running Shoes</h1>
  <p>Find the best running shoes for men and women with high comfort and durability.</p>

  <h2>Top Features</h2>
  <p>Lightweight, breathable material, long-lasting sole.</p>

  <img src="shoes.jpg" alt="Best running shoes for men" />

  <a href="/shoes">Explore more shoes</a>
</body>
</html>
```

> ⚠️ **Keyword stuffing** (forcing too many keywords unnaturally) is penalized by Google. Write for humans first — keywords should flow naturally.

---

### Off-Page SEO

Off-page SEO is about building your website's **reputation and authority** outside your own pages — so search engines conclude that your content is worth trusting.

The most powerful off-page signal is the **backlink** — a link from another website pointing to yours.

**Not all backlinks are equal:**

```
High Authority Site links to you  ──►  Strong positive signal ✅
Random/Spammy Site links to you   ──►  Weak or negative signal ❌
Many low-quality links            ──►  May trigger spam filter 🚨
Few high-quality, relevant links  ──►  Significant ranking boost ✅
```

Think of it like real-world credibility — a recommendation from a respected expert in your field means far more than praise from a stranger.

**Common off-page SEO strategies:**

| Strategy | Description |
|---|---|
| **Guest Blogging** | Write valuable articles on reputable sites in your niche, with a link back to yours |
| **Digital PR** | Get mentioned or linked from news outlets and industry publications |
| **Content Marketing** | Publish genuinely useful content that people naturally want to share and link to |
| **Brand Mentions** | Getting mentioned by name, even without links, adds to trust signals |
| **Social Signals** | Shares and engagement on social platforms build indirect visibility |

> **The underlying principle:** Great content earns genuine backlinks. Low-quality or spammy link-building hurts more than it helps. Search engines are designed to reward trustworthiness — and they're getting better at detecting artificial signals every year.

---

### Technical SEO

Technical SEO ensures that your website's **infrastructure** is solid — that crawlers can access, understand, and efficiently process your pages. No matter how great your content is, poor technical SEO can prevent it from ever being indexed.

**Two foundational files:**

#### `sitemap.xml` — The Tour Guide

A sitemap lists all important URLs on your site, telling search engines exactly where to look.

```
sitemap.xml
├── /                     priority: 1.0, weekly
├── /about                priority: 0.8, monthly
├── /products             priority: 0.9, monthly
├── /blogs                priority: 0.7, weekly
└── /contact              priority: 0.6, yearly
```

Without a sitemap, crawlers have to discover pages on their own — meaning some pages, especially deeply nested ones, may never be found.

#### `robots.txt` — The Gatekeeper

This file tells search engine bots what they're allowed to crawl and what to skip.

```
User-agent: *           ← Applies to all bots
Allow: /                ← Allow everything by default

Disallow: /_next/       ← Skip Next.js internals
Disallow: /api/         ← Skip API routes
Disallow: /admin/       ← Skip admin panels

Sitemap: https://example.com/sitemap.xml   ← Point bots to your sitemap
```

> **Together:** The sitemap tells bots *where to go*, and robots.txt tells them *where not to go*. Misconfiguring either can silently break your SEO without any obvious error.

**Other critical technical SEO factors:**

| Factor | Why It Matters |
|---|---|
| **Core Web Vitals** | Google uses LCP, FID, CLS as direct ranking signals |
| **HTTPS** | Sites without SSL are flagged as insecure — ranking is penalized |
| **Mobile-First Indexing** | Google indexes your mobile version first |
| **Page Speed** | Slow pages lose rankings and users |
| **Structured Data (JSON-LD)** | Helps Google display rich snippets (stars, FAQs, breadcrumbs) |
| **Hreflang tags** | For multilingual sites — tells Google which language to serve to which region |

---

## Implementing SEO with Next.js

Next.js provides first-class SEO support through its Metadata API, built-in file conventions, and server-side rendering. Everything is handled at the framework level — no manual `<head>` tag management needed.

> ⚠️ **Critical rule:** Static metadata only works in **Server Components**. Never export `metadata` from a Client Component (`"use client"`). Next.js will silently ignore it.

---

### 1 — Metadata

The `metadata` export in Next.js automatically generates `<title>`, `<meta>`, Open Graph, and Twitter Card tags.

```ts
// app/page.tsx (Server Component)
import { Metadata } from 'next';

export const metadata: Metadata = {
  title: 'Automatorr | Automation, CRM & Technology Solutions — Sydney, Australia',
  description: 'Automatorr is Sydney\'s trusted technology partner. Delivering automation, CRM, managed IT, software engineering and global talent across Australia and APAC. Est. 2006.',
  alternates: {
    canonical: 'https://www.automatorr.com/',
  },
  keywords: [
    "automation services Australia",
    "workflow automation Sydney",
    "CRM implementation Australia",
    "RPA consulting",
    "managed IT services Sydney",
    "technology partner Australia"
  ],
  openGraph: {
    siteName: "Automatorr",
    locale: 'en_AU',
    url: 'https://www.automatorr.com/',
    title: 'Automatorr — Automation & Technology Solutions, Sydney',
    description: 'Automation, CRM, managed IT and global talent for Australian businesses. 50+ clients. Est. 2006.',
    images: [{
      url: 'https://www.automatorr.com/og/homepage.png',
      width: 1200,
      height: 630,
      alt: 'Automatorr — Automation & Technology Solutions, Sydney'
    }],
    type: 'website',
  },
  twitter: {
    site: "@automatorr_nair",
    card: 'summary_large_image',
    title: 'Automatorr — Automation & Technology Solutions, Sydney',
    description: 'Automation, CRM, managed IT and global talent for Australian businesses. 50+ clients. Est. 2006.',
    images: ['https://www.automatorr.com/og/homepage.png'],
  },
};
```

**Full metadata field reference:**

| Field | What It Does | Why It Matters |
|---|---|---|
| `title` | Page title in browser tab and search results | Primary ranking signal; directly affects CTR |
| `description` | Short summary shown under title in search | Improves click-through rate (does not affect ranking directly) |
| `alternates.canonical` | Declares the authoritative URL of the page | Prevents duplicate content from hurting rankings |
| `keywords` | Keyword hints for search engines | Minor signal today, but still useful for context |
| `openGraph.siteName` | Website brand name in social previews | Strengthens branding in shared links |
| `openGraph.locale` | Language and region (e.g. `en_AU`) | Helps target the right geographic audience |
| `openGraph.url` | Canonical URL for social sharing | Ensures correct link is used when shared |
| `openGraph.title` | Title shown in link previews on social platforms | Boosts engagement and clicks on social |
| `openGraph.description` | Description in social link previews | Gives users context before clicking |
| `openGraph.images` | Preview image (with dimensions and alt text) | Makes shared links visually rich and attractive |
| `openGraph.type` | Content type (`website`, `article`, `product`) | Helps platforms understand content format |
| `twitter.site` | Your Twitter handle | Adds credibility and branding |
| `twitter.card` | Card style (`summary_large_image`, `summary`) | Controls visual layout on Twitter/X |
| `twitter.title` | Title in Twitter card | Drives engagement |
| `twitter.description` | Description in Twitter card | Helps users understand content at a glance |
| `twitter.images` | Image in Twitter preview | Significantly increases click-through on Twitter |

---

### 2 — Sitemap

In Next.js, create `app/sitemap.ts` and it automatically generates `/sitemap.xml`.

```ts
// app/sitemap.ts
import { MetadataRoute } from 'next';

export default function sitemap(): MetadataRoute.Sitemap {
  const base = 'https://www.automatorr.com';
  const now = new Date();

  return [
    // Highest priority — homepage
    { url: base,                                      lastModified: now, changeFrequency: 'weekly',  priority: 1.0 },

    // Core sections
    { url: `${base}/about`,                           lastModified: now, changeFrequency: 'monthly', priority: 0.8 },
    { url: `${base}/solutions`,                       lastModified: now, changeFrequency: 'monthly', priority: 0.9 },
    { url: `${base}/services`,                        lastModified: now, changeFrequency: 'monthly', priority: 0.9 },

    // Solutions sub-pages
    { url: `${base}/solutions/coms`,                  lastModified: now, changeFrequency: 'monthly', priority: 0.8 },
    { url: `${base}/solutions/ai-bot`,                lastModified: now, changeFrequency: 'monthly', priority: 0.8 },
    { url: `${base}/solutions/invoice-automation`,    lastModified: now, changeFrequency: 'monthly', priority: 0.8 },
    { url: `${base}/solutions/contract-automation`,   lastModified: now, changeFrequency: 'monthly', priority: 0.8 },
    { url: `${base}/solutions/clockit`,               lastModified: now, changeFrequency: 'monthly', priority: 0.8 },
    { url: `${base}/solutions/creatio`,               lastModified: now, changeFrequency: 'monthly', priority: 0.8 },
    { url: `${base}/solutions/business-central`,      lastModified: now, changeFrequency: 'monthly', priority: 0.8 },
    { url: `${base}/solutions/compliance`,            lastModified: now, changeFrequency: 'monthly', priority: 0.8 },

    // Services sub-pages
    { url: `${base}/services/automation-services`,    lastModified: now, changeFrequency: 'monthly', priority: 0.8 },
    { url: `${base}/services/crm-services`,           lastModified: now, changeFrequency: 'monthly', priority: 0.8 },
    { url: `${base}/services/msp-services`,           lastModified: now, changeFrequency: 'monthly', priority: 0.8 },
    { url: `${base}/services/software-engineering`,   lastModified: now, changeFrequency: 'monthly', priority: 0.8 },
    { url: `${base}/services/global-talent`,          lastModified: now, changeFrequency: 'monthly', priority: 0.8 },

    // Content & engagement pages
    { url: `${base}/case-studies`,                    lastModified: now, changeFrequency: 'weekly',  priority: 0.7 },
    { url: `${base}/blogs`,                           lastModified: now, changeFrequency: 'weekly',  priority: 0.7 },
    { url: `${base}/hockey`,                          lastModified: now, changeFrequency: 'monthly', priority: 0.7 },

    // Lowest priority — rarely changes
    { url: `${base}/contact-us`,                      lastModified: now, changeFrequency: 'yearly',  priority: 0.6 },
  ];
}
```

**`changeFrequency` guide:**

| Value | Use When |
|---|---|
| `always` | Content changes with every visit (live dashboards, feeds) |
| `hourly` | News or real-time data pages |
| `daily` | High-volume content sites, e-commerce listings |
| `weekly` | Blogs, case studies, portfolio pages |
| `monthly` | Product or service pages that rarely change |
| `yearly` | Legal pages, contact pages, "about" pages |
| `never` | Archived or historical content |

---

### 3 — Robots.txt

In Next.js, create `app/robots.ts` and it generates `/robots.txt` automatically.

```ts
// app/robots.ts
import { MetadataRoute } from 'next';

export default function robots(): MetadataRoute.Robots {
  return {
    rules: {
      userAgent: '*',
      allow: '/',
      disallow: ['/_next/', '/api/', '/admin/'],
    },
    sitemap: 'https://www.automatorr.com/sitemap.xml',
  };
}
```

Or as a static file at `public/robots.txt`:

```txt
User-agent: *
Allow: /

# Block Next.js internals
Disallow: /_next/

# Block API and private routes
Disallow: /api/
Disallow: /admin/

# Sitemap location
Sitemap: https://www.automatorr.com/sitemap.xml
```

> 💡 **File location rule:**
> - `app/sitemap.ts` → auto-generates `/sitemap.xml`
> - `app/robots.ts` → auto-generates `/robots.txt`
> - `public/sitemap.xml` or `public/robots.txt` → static files served directly
>
> Use `app/` files for dynamic generation, `public/` for simple static config.

---

## Dynamic SEO

Static metadata works great for fixed pages, but what about **blog posts, product pages, or any URL with dynamic content**? That's where `generateMetadata` comes in.

Instead of writing metadata manually, Next.js fetches the data for that specific page and generates metadata from it — automatically, per page.

```ts
// app/blogs/[slug]/page.tsx
import { Metadata, ResolvingMetadata } from 'next';

type PageProps = {
  params: Promise<{ slug: string }>;
};

export async function generateMetadata(
  { params }: PageProps,
  parent: ResolvingMetadata
): Promise<Metadata> {
  const { slug } = await params;

  try {
    const response = await fetch(
      `https://your-api.com/blogs/${slug}`,
      { next: { revalidate: 3600 } }  // ISR: re-fetch every 1 hour
    );

    if (!response.ok) throw new Error('Failed to fetch blog post');

    const metapost = await response.json();
    const blogData = metapost.blogData;
    const baseUrl = 'https://bombaydecoratives.com';
    const postUrl = `${baseUrl}/blogs/${slug}`;

    return {
      title: blogData.title,
      description: blogData.subheading,
      keywords: blogData.tags,
      alternates: {
        canonical: postUrl,
      },
      openGraph: {
        title: blogData.title,
        description: blogData.subheading,
        url: postUrl,
        siteName: 'Bombay Decoratives',
        images: [{
          url: blogData.image,
          width: 1200,
          height: 630,
          alt: blogData.title,
        }],
        locale: 'en_US',
        type: 'article',
        publishedTime: metapost.createdAt,
        authors: ['Bombay Decoratives'],
      },
      twitter: {
        card: 'summary_large_image',
        title: blogData.title,
        description: blogData.subheading,
        images: [{
          url: blogData.image,
          alt: blogData.title,
          width: 1200,
          height: 675,  // 16:9 ratio
          type: 'image/jpeg',
        }],
      },
    };

  } catch (error) {
    console.error('Error generating metadata:', error);

    // Graceful fallback if API fails
    return {
      title: 'Blog Post | Bombay Decoratives',
      description: 'Read our latest blog post.',
    };
  }
}
```

### Dynamic Sitemaps for Dynamic Routes

When your site generates hundreds or thousands of URLs dynamically (e.g. `/blogs/post-1`, `/blogs/post-2`, ...), you can loop over all your content and generate sitemap entries for each one:

```ts
// app/sitemap.ts — Dynamic sitemap with all blog posts
import { MetadataRoute } from 'next';

export default async function sitemap(): Promise<MetadataRoute.Sitemap> {
  const base = 'https://bombaydecoratives.com';

  // Fetch all blog slugs from your CMS or database
  const res = await fetch(`${base}/api/blogs/all-slugs`);
  const slugs: string[] = await res.json();

  // Generate one sitemap entry per blog post
  const blogEntries: MetadataRoute.Sitemap = slugs.map((slug) => ({
    url: `${base}/blogs/${slug}`,
    lastModified: new Date(),
    changeFrequency: 'weekly',
    priority: 0.7,
  }));

  return [
    // Static pages
    { url: base,              lastModified: new Date(), changeFrequency: 'weekly',  priority: 1.0 },
    { url: `${base}/blogs`,   lastModified: new Date(), changeFrequency: 'weekly',  priority: 0.8 },

    // Dynamically generated blog post pages
    ...blogEntries,
  ];
}
```

> This pattern scales to any size — product pages, case studies, user profiles — anything driven by dynamic data can be automatically represented in your sitemap.

---

## Quick Reference Cheatsheet

```
SEO Type        | Controls                    | Next.js File
─────────────────────────────────────────────────────────────
On-Page         | Metadata, headings, content | app/page.tsx (metadata export)
Technical       | Sitemap, robots, speed      | app/sitemap.ts, app/robots.ts
Off-Page        | Backlinks, brand mentions   | (External — no code needed)
Dynamic SEO     | Per-page generated metadata | generateMetadata() function
```

| Task | Where |
|---|---|
| Static page metadata | `export const metadata` in a Server Component |
| Dynamic page metadata | `export async function generateMetadata()` |
| Sitemap (static) | `app/sitemap.ts` or `public/sitemap.xml` |
| Robots (static) | `app/robots.ts` or `public/robots.txt` |
| Structured data (JSON-LD) | Inline `<script type="application/ld+json">` in layout |
| OG image generation | `app/opengraph-image.tsx` (Next.js built-in) |

> **Remember:** Static metadata → Server Component only. `generateMetadata` → also Server Component only. Client Components (`"use client"`) cannot export metadata — Next.js will silently ignore it.
