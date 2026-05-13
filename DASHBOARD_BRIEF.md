# Power BI Dashboard Challenge: India's Footprint in Low Earth Orbit

## Background

Your husband ran a Spark analysis on live data from Space-Track.org — 
the US Space Force's public orbital tracking database. The dataset contains 
every man-made object currently tracked in Low Earth Orbit (LEO): active 
satellites, defunct spacecraft, rocket bodies, and debris fragments.

This is real data. Not a tutorial. Not Kaggle. Live US Space Force tracking 
data pulled via API on May 2026.

## The Context

India just produced its first space tech unicorn — Skyroot Aerospace, valued 
at $1.1 billion in May 2026 — and is preparing its first private orbital rocket 
launch. India's space economy is targeting $44 billion by 2033.

But space is getting crowded. Of 61,274 tracked objects in LEO today, more than 
half are debris. Every piece of debris travelling at 28,000 km/hour is a 
potential collision risk for any satellite — including the ones India wants 
to launch.

The question this dashboard should answer:

> **How has India contributed to the LEO environment — and what does that mean 
> for its space ambitions?**

## The Dataset

File: `leo_data_may2026.csv`  
Rows: 61,274 objects  
Source: Space-Track.org (US Space Force)

### Key columns to know:

| Column | What it means | Example |
|---|---|---|
| `OBJECT_NAME` | Name of the object | ARYABHATA, PSLV DEB |
| `OBJECT_TYPE` | What kind of object | PAYLOAD, DEBRIS, ROCKET BODY |
| `COUNTRY_CODE` | Which country launched it | IND, US, PRC, CIS |
| `LAUNCH_DATE` | When it was launched | 1975-04-19 |
| `PERIAPSIS` | Lowest point of orbit in km | 144.8 |
| `APOAPSIS` | Highest point of orbit in km | 152.4 |
| `INCLINATION` | Angle of orbit to equator | 97.8 |
| `DECAY_DATE` | When it fell back to Earth | null if still up there |

### Country codes to know:
- `IND` = India
- `US` = United States
- `CIS` = Russia / Soviet Union
- `PRC` = China
- `FR` = France
- `JPN` = Japan

### Altitude bands to create:
| Band | Altitude | Significance |
|---|---|---|
| Very Low | Below 300km | Decaying fast, unstable |
| Low — Skyroot zone | 300–500km | Where Skyroot's Vikram-1 is targeting |
| Medium | 500–800km | Most congested band |
| High | 800–1200km | Where older ISRO satellites live |
| Very High | Above 1200km | Long-lived objects |

---

## The Dashboard

Build a Power BI dashboard that tells this story visually.

### Page 1 — The Big Picture
- Total objects in LEO by type (PAYLOAD vs DEBRIS vs ROCKET BODY) — donut chart
- Top 15 countries by total objects — bar chart
- World map showing object count by country of origin
- A headline KPI card: "61,274 objects tracked in LEO today"

### Page 2 — The Congestion Problem
- Objects by altitude band — stacked bar showing debris vs payload vs rocket body
- Highlight the Skyroot zone (300–500km) — how crowded is it?
- Debris ratio by country (debris ÷ total objects) — who is most irresponsible?
- Filter by object type

### Page 3 — India's Story
- India's objects over time — line chart by launch year
- India's debris vs payload by decade — clustered bar chart
- India's altitude distribution — where are Indian objects sitting?
- Key callout: The 2001 PSLV-C3 event — one launch, 366 debris objects
- India's debris ratio by decade showing the dramatic improvement:
  - 2000s: 28.46 debris per payload
  - 2010s: 3.85
  - 2020s: 0.19

### Page 4 — The So What
- What is Kessler Syndrome? — text visual explaining the cascade risk
- Which altitude bands are most at risk — objects per 100km band
- India's legacy objects still in Skyroot's target zone — table
- A closing statement on what responsible launch looks like

---

## Key Findings to Highlight

These are the findings from the Spark analysis — your dashboard should 
make these visible and understandable to a non-technical audience:

1. **52% of LEO is debris** — more junk than useful satellites
2. **India is 6th in LEO** — 659 objects, ahead of Japan
3. **One event explains India's debris history** — the 2001 PSLV-C3 upper 
   stage fragmentation created 366 debris objects in a single incident
4. **India's 2020s debris ratio is 0.19** — among the cleanest of any 
   spacefaring nation, dramatically improved from 28.46 in the 2000s
5. **Skyroot's target zone carries 6,140 debris objects** — 114 left by 
   India itself

---

## Design Guidance

- Use a dark theme — space is dark. Navy, black, with electric blue and 
  white accents feels right for this topic
- Every chart needs a one-line insight label — not just a title. 
  Not "Objects by Country" but "The US dominates LEO with 23,154 objects — 
  but India's ratio is improving fastest"
- The audience is: a smart non-technical person who cares about India's 
  future. No jargon without explanation.
- Mobile-friendly layout if possible

---

## Why This Dashboard Matters

Space tech companies like Digantara (space debris tracking), Pixxel 
(satellite imaging), and Skyroot (launch vehicles) all need people who 
can make complex orbital data understandable to operators, investors, 
and policymakers.

A Power BI engineer who has already visualised live Space Force data — 
and told a clear story from it — walks into any of these companies with 
proof, not promises.

This is not a tutorial dashboard. This is a portfolio piece.

---

*Data pulled by Mohit Agarwal, May 2026*  
*Source: Space-Track.org — US Space Force public orbital catalog*  
*Analysis: Apache Spark 4.0.2 on Google Colab*
