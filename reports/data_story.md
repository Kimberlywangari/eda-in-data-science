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
identical income-age relationship in both groups (r ≈ 0.49–0.50) — leavers were
simply concentrated at the younger, lower-income end of that same relationship.
**Distance from home** showed only a modest gap (9 km median for leavers vs. 7 km
for stayers, Chart 9) — a real but weak signal by comparison.

## Interpretation

Taken together, the evidence points toward **career stage as an underlying thread**
connecting several of these findings: younger, single, earlier-career employees
show up disproportionately among leavers, and their lower income and (slightly)
different commute patterns look like symptoms of that career stage rather than
independent causes. Overtime stands apart from this pattern — its effect size is
large and it isn't explained away by age in the same way the income gap was.

## Limitations and Caution

This is IBM's synthetic demo dataset, not real employee records, so these patterns
are illustrative rather than directly transferable to a real workforce without
validation. Several subgroups used in this analysis are thin (e.g., the HR
department at 63 employees), which limits how confidently we can generalize within
them. Most importantly: **every relationship reported here is a correlation, not a
demonstrated cause** — nothing in this EDA proves that reducing overtime would
reduce attrition, only that the two are strongly associated.

## Recommendation

**Audit and pilot-test overtime reduction in the highest-overtime teams.**
Overtime shows the largest, cleanest, and most actionable gap in this dataset
(30.5% vs. 10.4% attrition). Because it is something an organization can directly
influence — unlike age or marital status — the recommended next step is to identify
which departments or roles generate the most overtime, pilot workload
redistribution there, and measure whether attrition among that group falls in the
following review period, rather than assuming the relationship is causal before
testing it.