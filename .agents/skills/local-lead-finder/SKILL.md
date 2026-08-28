---
name: local-lead-finder
description: Finds local-business sales opportunities for a simple brochure website or website refresh using public web evidence. Use when a vibe coder supplies a business type, location, target count, and optional existing-leads file and wants a reviewable lead list, not outreach.
---

# Local lead finder

## Input

Read the prompt-named Markdown input containing `business_type`, `location`,
`target_count`, `offer`, and optionally `existing_leads_file`. Ask for any missing
business type or location and stop. Default the target count to 10.

## Steps

1. Read the existing-leads file when supplied. Build exclusion keys from normalized
   business names, domains, and business phone numbers. If the file is missing or
   unreadable, report that limitation and continue only if the prompt permits it.
2. Search the public web for businesses matching the requested type and location.
   Prefer official business sites and public business listings. Do not use LinkedIn,
   people-search sites, private groups, gated sources, or sources that cannot be
   redistributed.
3. Verify that each candidate is a business in the requested category and geography.
   Record the supporting URL and retrieval date.
4. Include a phone number only when the source presents it as the business's public
   contact number. Never collect a named person's direct number, email, profile, or
   other personal data. Exclude a candidate when a business-level phone cannot be
   verified.
5. Inspect the candidate's web presence and assign exactly one need signal:
   - `no standalone website`: no business-owned website is found after checking the
     listing and searching the exact business name;
   - `social-only`: the business listing points only to a public social page;
   - `upgrade candidate`: a standalone site exists and has at least one observable
     problem: it fails to load, lacks HTTPS, is unusable on mobile, has no clear
     service description, or has no visible call/contact action.
   Do not label a site weak based only on taste, age, or visual style.
6. Exclude businesses already present in the existing-leads keys. Deduplicate the
   remaining candidates by normalized name, domain, and phone.
7. Rank `no standalone website` first, then `social-only`, then `upgrade candidate`.
   Within a group, prefer candidates supported by an official source plus a separate
   public listing. Do not infer budget, buying intent, or willingness to take a call.
8. Write the requested output as a Markdown table with: rank, business, category and
   location, public business phone, need signal, observable evidence, source URLs,
   retrieval date, and confidence with a short reason. Add sections for search scope,
   exclusions, limitations, and existing-lead matches removed.
9. Print the output path and a compact summary. If fewer than the target qualify,
   return the verified candidates and state `insufficient evidence for <target_count>
   leads`; never pad the list or weaken the criteria.

## Rules

- Produce research for human review only. Never call, message, draft personalized
  outreach, publish, purchase, or modify a CRM.
- Treat absence of a found website as medium confidence at most and describe the
  search performed; absence is not proof that no site exists.
- Cite every lead's evidence with public URLs and retrieval dates. Never describe a
  cached source as live.
- Record failed retrievals and uncertainty. Never invent businesses, phone numbers,
  website defects, sources, dates, prices, or evaluation results.

## Done when

The output file exists, every included lead matches the requested market, has a
verified public business phone and need signal, is not an excluded duplicate, and
every factual claim is sourced and dated.
