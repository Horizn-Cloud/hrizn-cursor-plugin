---
name: hrizn-mcp
description: Use Hrizn (Content Operating system for Automotive Dealerships) MCP on a granted rooftop — live inventory, dealer context, IdeaClouds, content pages, OEM-compliance checks, Social Hub posts/reviews, and Market Maker. Apply when the user asks about Hrizn, a dealership lot, listings, articles, reviews, or local-market pricing.
---

# Hrizn MCP

Hrizn is the Content Operating system for Automotive Dealerships. This plugin talks to **live rooftop data**, not help-doc search. Tool names and arguments come from `tools/list`. Do not invent extra tools.

## Before any rooftop work

1. The user signs in with **OAuth** when Cursor prompts. Do not ask for `hzk_` API keys.
2. Rooftops are granted in Hrizn Dealership Manager → **MCP** (Teams+ sites with API access). If tools return a grant / 403 / `mcp_grant_required` error, send them there to save dealerships, then reconnect.
3. Call `list_connected_sites` when more than one rooftop may be in play. Use that list’s `site_id` and capability flags on later calls. Do not assume Market Maker or Social Hub posting is enabled.

## What this MCP can do

Use Hrizn tools instead of guessing VINs, prices, published URLs, or brand voice.

**Dealership briefing** — `get_dealer_context` for Dealer DNA, brand-voice metadata (not prompts), staff, CTAs, marketing, and target geography. Confirm `suggested_timezone` with the user before scheduling Social Hub posts.

**Inventory** — Search the lot (`find_vehicles`), mix/aging (`get_inventory_stats`, `get_inventory_health`), and one vehicle (`get_vehicle`). Treat returned stock/VIN/price as source of truth.

**Content & IdeaClouds** — List/get pages; find live URLs to cite (`find_content_to_cite`); opportunities (`get_content_opportunities`, `get_content_recommendation`). For new work: find or `create_ideacloud`, wait with `wait_for_ideacloud`, review outline/cluster/selection, then create only after the user confirms the selection. Page types: IdeaCloud → `create_content`; also `create_model_landing`, `create_comparison`, `create_sales_event` after resolving YMMT via inventory or `list_vehicle_*` (never invent year/make/model/trim). Use `list_layouts` when visual templates matter. Poll with `wait_for_content`, not tight loops.

**OEM compliance** — Guidance on automotive ad language, not legal advice. Check pasted copy (`check_compliance`) or existing Hrizn content (`trigger_content_compliance` → `wait_for_content_compliance`). Apply replacements only with `apply_compliance_fixes` after the user confirms.

**Social Hub** — Presence, posts, and reviews when the rooftop has Social Hub. Posting: `prepare_social_post` → `wait_for_media_session` if media is processing → `finalize_social_post`. Review replies: `generate_review_reply` then `publish_review_reply` only after confirmation. Reconnect accounts in Dealership Manager → Social Profiles, not in chat.

**Market Maker** — Local listings, days supply, competitive set, pricing vs market, price-cut candidates, stocking gaps, appraisal, vehicle position, options/packages. Only when `list_connected_sites` shows market access (Unlimited). Bounded results; do not treat them as a full national census.

## Mutations

Tools that create, publish, delete, or overwrite require the user to confirm. Honor `dry_run`, `user_confirmed`, and `preview_token` when the tool schema includes them. Preview first; never set confirmation flags unless the user explicitly approved that preview.
