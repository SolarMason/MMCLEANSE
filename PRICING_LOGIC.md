# NEPA-PRO Clean — Pricing & Profit Logic

**Target net hourly:** $65/hr minimum after per-visit overhead (typically achieves $67–78/hr blended)
**Per-visit overhead by size:**
- Small: $12 (supplies + travel + insurance allocation)
- Medium: $15
- Large: $18
- XL: $22

Cleaning has higher overhead than lawn care due to supply consumption, longer visits, higher liability indoors, and equipment wear.

## Time-on-site assumptions

| Tier | Weekly | Bi-Weekly | Monthly | Deep | Move-In/Out | Airbnb |
|---|---|---|---|---|---|---|
| Small | 1.5h | 1.7h | 2.1h | 3.0h | 3.5h | 2.0h |
| Medium | 2.5h | 2.9h | 3.5h | 5.0h | 5.5h | 3.0h |
| Large | 3.5h | 4.0h | 4.9h | 7.0h | 7.5h | 4.0h |
| XL | 5.0h | 5.75h | 7.0h | 10.0h | 10.5h | — |

## Recurring — verified $/hr (price − overhead) / hours

### Small
| Frequency | Price | Time | Net Labor | Net $/hr |
|---|---|---|---|---|
| Weekly | $125 | 1.5h | $113 | **$75.33** |
| Bi-Weekly | $140 | 1.7h | $128 | **$75.29** |
| Monthly | $175 | 2.1h | $161 | **$76.67** |

### Medium
| Frequency | Price | Time | Net Labor | Net $/hr |
|---|---|---|---|---|
| Weekly | $195 | 2.5h | $180 | **$72.00** |
| Bi-Weekly | $225 | 2.9h | $210 | **$72.41** |
| Monthly | $275 | 3.5h | $257 | **$73.43** |

### Large
| Frequency | Price | Time | Net Labor | Net $/hr |
|---|---|---|---|---|
| Weekly | $275 | 3.5h | $257 | **$73.43** |
| Bi-Weekly | $315 | 4.0h | $297 | **$74.25** |
| Monthly | $375 | 4.9h | $355 | **$72.45** |

### XL
| Frequency | Price | Time | Net Labor | Net $/hr |
|---|---|---|---|---|
| Weekly | $395 | 5.0h | $373 | **$74.60** |
| Bi-Weekly | $445 | 5.75h | $423 | **$73.57** |
| Monthly | $525 | 7.0h | $500 | **$71.43** |

## One-time — verified $/hr

### Deep Clean
| Size | Price | Time | Net $/hr |
|---|---|---|---|
| Small | $255 | 3h | **$78.33** |
| Medium | $415 | 5h | **$78.00** |
| Large | $575 | 7h | **$77.86** |
| XL | $815 | 10h | **$78.00** |

### Move-In / Move-Out
| Size | Price | Time | Net $/hr |
|---|---|---|---|
| Small | $275 | 3.5h | **$75.86** |
| Medium | $445 | 5.5h | **$78.18** |
| Large | $615 | 7.5h | **$79.40** |
| XL | $865 | 10.5h | **$80.29** |

### Airbnb Turnover
| Size | Price | Time | Net $/hr |
|---|---|---|---|
| Small | $175 | 2h | **$76.50** |
| Medium | $265 | 3h | **$83.33** |
| Large | $345 | 4h | **$80.75** |

## Specialty — verified $/hr (heavier overhead included)

### Post-Construction
| Tier | Price | Time | Materials/Disposal | Net $/hr |
|---|---|---|---|---|
| Light | $545 | 6h | $40 | **$80.83** |
| Standard | $895 | 10h | $50 | **$80.50** |
| Heavy | $1,395 | 16h | $75 | **$82.50** |

### Clean-Out (includes truck + dump fees in materials)
| Tier | Price | Time | Disposal | Net $/hr |
|---|---|---|---|---|
| Small | $445 | 4h | $80 | **$87.50** |
| Medium | $895 | 8h | $200 | **$83.13** |
| Large | $1,795 | 16h | $400 | **$84.06** |

### Organizing (light supplies included)
| Tier | Price | Time | Supplies | Net $/hr |
|---|---|---|---|---|
| Single Space | $245 | 3h | $15 | **$73.33** |
| Multi-Space | $475 | 6h | $25 | **$73.33** |
| Whole-Home | $925 | 12h | $40 | **$71.67** |

## Lowest net rate in entire grid: $71.43/hr (XL Monthly recurring)
**All cells clear $65/hr target with $5+ buffer.**

## Stripe billing model

- **Weekly subscription**: charged every 7 days, 1 visit per charge
- **Bi-Weekly subscription**: every 14 days
- **Monthly subscription**: every 30 days
- **One-time services**: single charge at booking

Customer self-serves all subscription changes via the Stripe customer portal link sent in every receipt email.

## Levers if you need to adjust

- **First-time deep clean upcharge**: Recommend customers start with a Deep Clean as their first service. Most do — that's free margin on the first visit.
- **Specific product surcharge**: If they request unusual products (e.g. premium eco brands), $15 add-on per visit.
- **Tight scheduling window upcharge**: For Airbnb hosts with <2-hour turnover windows, +$25/visit.
- **Distance surcharge**: Outside zip codes 184/185/186/187/188 → +$25/visit.
- **Move-out with damage cleaning**: Beyond standard scuffs (e.g., excessive grease in oven, mold) → upcharge $50–150 depending on severity. Note this in booking notes.
- **Holiday/weekend premium**: Sundays or major holidays → +20%.

## Annual revenue math (sanity check)

Realistic full route-day (5 recurring stops):
- 5 × Medium Bi-Weekly @ $225 = $1,125/day
- Run that 5 days/week = $5,625/week
- 50 weeks/year = **$281,250 annual** per crew on one weekday rotation

Realistic Airbnb host fleet (10 active properties, weekly turnover):
- 10 × Medium Airbnb @ $265 = $2,650/week
- 50 weeks = **$132,500 annual** from one bundle of host clients

A single move-out clean is roughly equivalent to 2.5 bi-weekly recurring stops in revenue. Pack 1 deep/move-out per day with 3 recurring on busy weeks and revenue jumps 30–40%.

## Bundle with lawn care

Customers on both NEPA-PRO Lawn Care recurring AND NEPA-PRO Clean recurring → 10% off cleaning rate.

Example: Customer at Medium Lawn Bi-Weekly ($70) + Medium House Bi-Weekly ($225). Without bundle: $295/visit. With bundle: $70 + $202.50 = $272.50/visit. You give up $22.50 to keep them locked into TWO services instead of one — strong customer-LTV trade.
