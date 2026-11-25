# Manual review: transactions flagged by 2+ checks

A random sample of 15 transactions flagged by 2 or more independent checks, reviewed by hand to check whether the flags reflect genuine anomalies or routine business patterns the checks can't distinguish on their own. Full sample in `spot_check_sample.csv`.

Back to [README](README.md).

---

**RowId: 4330269-NGA110625-821309**: EXTREME TOWING & RECOVERY, $100.00, Police Department
- Flagged by: round-number + duplicate
- Plausible innocent explanation: flat per-vehicle towing fee, routine for a police department.
- What I'd ask for: no follow-up needed: see vendor-recurrence note below.

**RowId: 50546127-102-812018**: SUSTAINED FARMS, $9,000.00, Mayor's Office of Education and Children
- Flagged by: round-number + threshold clustering
- Plausible innocent explanation: could be a legitimate flat-fee grant or contract payment.
- What I'd ask for: strongest candidate in the sample: request the contract/PO and confirm it wasn't split to avoid the $10k sign-off.

**RowId: 50515652-1905556671-743762**: CINTAS CORPORATION NO 2, $300.00, DOTI
- Flagged by: round-number + duplicate
- Plausible innocent explanation: uniform/facility-services vendor; $300 recurring supply orders are routine.
- What I'd ask for: no follow-up needed.

**RowId: 4329454-092025-817832**: COLORADO COALITION FOR THE HOMELESS, $4,500.00, Safety Administration
- Flagged by: round-number + duplicate
- Plausible innocent explanation: likely a recurring monthly service contract to a known nonprofit partner.
- What I'd ask for: confirm the payment matches the contract's monthly installment schedule, not one invoice paid twice.

**RowId: 50554107-M77842-831989**: TOWLIFT, $14,700.00, Department of Finance
- Flagged by: round-number + year-end timing
- Plausible innocent explanation: heavy machinery purchase booked to Finance for accounting purposes; December timing may reflect normal procurement lead time.
- What I'd ask for: confirm which department actually uses the equipment, and whether year-end budget pressure influenced timing.

**RowId: 4370817-0008653881-833223**: APEX SYSTEMS LLC, $9,467.72, Wastewater Management Division
- Flagged by: year-end timing + threshold clustering
- Plausible innocent explanation: a legitimate December consulting invoice.
- What I'd ask for: this combination is worth a closer look: request the engagement scope and confirm it isn't a larger contract split to stay under sign-off before year-end close.

**RowId: 3896609-SVC272553082-691951**: DH PACE COMPANY INC, $300.00, Denver Public Library
- Flagged by: round-number + duplicate
- Plausible innocent explanation: door/facility maintenance vendor; $300 service calls recurring across branches is routine.
- What I'd ask for: no follow-up needed.

**RowId: 50514221-INV66048-740561**: BIG TRUCK RENTAL LLC, $13,300.00, DOTI
- Flagged by: round-number + duplicate
- Plausible innocent explanation: equipment rental at a flat daily/weekly rate for a road/infrastructure project.
- What I'd ask for: confirm rental period and that it isn't two shorter rentals combined into one payment.

**RowId: 3916660-871565916-696478**: KONE INC, $700.00, Service Delivery and Administration
- Flagged by: round-number + duplicate
- Plausible innocent explanation: elevator/escalator maintenance vendor; $700 recurring service calls are standard.
- What I'd ask for: no follow-up needed.

**RowId: 4185275-1JUN25-775175**: JUSTICE AND MERCY LEGAL AID CENTER, $5,700.00, Human Rights - Community Relations
- Flagged by: round-number + duplicate
- Plausible innocent explanation: likely a recurring grant/contract disbursement to a legal aid nonprofit partner.
- What I'd ask for: confirm against the grant agreement's payment schedule.

**RowId: 4289297-PI4364-806996**: DRAGONFRUIT MEDIA GROUP, $4,500.00, Arts and Venues Division
- Flagged by: round-number + duplicate
- Plausible innocent explanation: design/advertising services billed at a flat project rate.
- What I'd ask for: quick check that this isn't the same campaign invoiced twice.

**RowId: 4123243-LO061225-759785**: EXTREME TOWING & RECOVERY, $100.00, Police Department
- Flagged by: round-number + duplicate
- Plausible innocent explanation: same vendor/pattern as above: routine flat-fee towing.
- What I'd ask for: see vendor-recurrence note below.

**RowId: 4186631-NG072425-779132**: EXTREME TOWING & RECOVERY, $200.00, Police Department
- Flagged by: round-number + duplicate
- Plausible innocent explanation: third occurrence of this vendor in the 15-row sample: a clear recurring flat-fee relationship, not an anomaly.
- What I'd ask for: see vendor-recurrence note below.

**RowId: 4019411-110250014712-728762**: EJ USA INC, $9,097.92, Wastewater Management Division
- Flagged by: duplicate + threshold clustering
- Plausible innocent explanation: the strongest candidate for genuine review in the sample: a non-round, invoice-like amount sitting just under the $10k threshold, paid twice separately.
- What I'd ask for: pull both invoices and confirm they're genuinely separate structural-materials deliveries, not one order split to avoid sign-off.

**RowId: 50512675-9022386610-737800**: VERIZON WIRELESS, $100.00, Police Department
- Flagged by: round-number + duplicate
- Plausible innocent explanation: flat monthly telephone service fee.
- What I'd ask for: no follow-up needed.

---

## False-positive pattern found in this review

The duplicate check has a systematic blind spot: vendors paid the same flat fee repeatedly (Extreme Towing at $100–$200 across three separate payments, Verizon at $100) trigger it every time purely because they're low-dollar, high-frequency, round-amount vendors , not because anything is wrong. A sharper version of this check would exclude payee/amount pairs recurring beyond some frequency threshold across the year, since high recurrence is itself evidence of a routine vendor relationship rather than a split payment.

Two transactions to escalate from this sample: SUSTAINED FARMS ($9,000, round-number + threshold clustering) and EJ USA INC ($9,097.92, duplicate + threshold clustering) both sit at the intersection of two independent signals with non-trivial dollar amounts, making them the most defensible candidates for actual follow-up.
