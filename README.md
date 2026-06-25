Project: Automated Lead Scoring & Routing System (Deskflow ROI Calculator)

I designed and implemented an automation workflow in Make.com to handle ROI calculator submissions. Each submission triggered a custom webhook that captured the visitor’s details (name, email, company, team size, ROI value).

I then enriched the data using an HTTP Request module connected to a company enrichment API, extracting industry, employee count, and HQ country. I built a lead scoring model using variables and math logic that factored in team size, ROI value, industry verticals, and email domain quality.

Based on the score, I routed leads through a Router module:

Hot Leads (≥80 points): Automatically created CRM contacts with a “Hot” tag, sent Slack notifications to the sales team, and triggered immediate follow‑up tasks.

Warm Leads (40–79 points): Added to CRM with a “Warm” tag and placed into a nurture list.

Disqualified Leads (<40 points or generic emails): Logged into a datastore with rejection reasons, without creating CRM entries.

I also implemented error handling so that if the enrichment API failed, the system still processed leads with a flag noting “Enrichment Failed.” Finally, I used a Make.com Datastore to log every processed lead with timestamp, score, and routing decision for full auditability.
