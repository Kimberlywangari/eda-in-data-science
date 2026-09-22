# Data Story: What Drives Attrition in the IBM HR Analytics Dataset

## Observed Findings

Of 1,470 employees in this dataset, 237 (16.1%) left the company — a meaningfully
imbalanced split that shaped how every comparison below was read (proportions
within groups, not raw counts).

The clearest signal in the data is **overtime**: employees who work overtime leave
at a rate of 30.5%, compared to 10.4% for those who don't — roughly three times
higher, and based on a reasonably sized comparison (416 vs. 1,054 employees)
(Chart 7). **Marital status** shows a similarly sized gap — Single employees leave
at 25.5%, versus 10.1% for Divorced and 12.5% for Married employees (Chart 8) — and
this pattern held for both genders when broken down further, ruling out a
gender-driven artifact (Chart 11).

**Income** also differs by attrition status: employees who left had a median
monthly income of $3,202, against $5,204 for those who stayed (Chart 6). However,
plotting Age against MonthlyIncome by attrition status (Chart 10) showed an almost
identical income-age relationship in both groups (r ~ 0.49-0.50) — leavers were
simply concentrated at the younger, lower-income end of that same relationship.
**Distance from home** showed only a modest gap (9 km median for leavers vs. 7 km
for stayers, Chart 9) — a real but weak signal by comparison.

A department-level breakdown (Chart 12) adds a final piece: overtime rate is
nearly identical across Sales, R&D, and HR (27-29%), but attrition rate is not —
Sales sits highest at 20.6%, R&D lowest at 13.8%, despite R&D being the larger
department.

## Interpretation

Taken together, the evidence points toward **career stage as an underlying thread**
connecting several of these findings: younger, single, earlier-career employees
show up disproportionately among leavers, and their lower income and (slightly)
different commute patterns look like symptoms of that career stage rather than
independent causes. Overtime stands apart from this pattern — its effect size is
large and it isn't explained away by age. But overtime alone doesn't explain
*where* attrition concentrates: since overtime rates are similar across
departments while attrition rates aren't, something specific to Sales is likely
compounding the overtime effect there.

## Limitations and Caution

This is IBM's synthetic demo dataset, not real employee records, so these patterns
are illustrative rather than directly transferable to a real workforce without
validation. Several subgroups used in this analysis are thin (e.g., the HR
department at 63 employees), which limits how confidently we can generalize within
them. Most importantly: **every relationship reported here is a correlation, not a
demonstrated cause** — nothing in this EDA proves that reducing overtime would
reduce attrition, and the Sales-specific gap suggests an unmeasured factor (e.g.
sales-target pressure) may also be at play.

## Recommendation

**Target overtime reduction at Sales first, not company-wide.**

Overtime is strongly linked to attrition across the company — employees working
overtime leave at roughly three times the rate of those who don't (30.5% vs.
10.4%). But overtime alone doesn't explain where attrition is worst: all three
departments run a similar overtime rate (27-29%), yet Sales loses employees at
20.6%, well above R&D's 13.8% despite R&D being the larger department. That gap
points to something specific to Sales — likely target-driven pressure or role
structure — compounding the effect of overtime itself.

**Concrete next step:** launch a workload and overtime audit within Sales
specifically, broken down by role (Sales Executive vs. Sales Representative), and
pilot workload redistribution there. Track whether Sales attrition falls in the
following review period before deciding whether to extend the intervention to
other departments.

This is a correlational finding, not a proven cause — the recommendation is to
pilot and measure in the department where the evidence is strongest, not to
assume the fix will work before testing it.