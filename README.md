# OneMeter

**Machine-level energy intelligence from a single ₹1,500 current clamp.**

Yuva Yodha Energy Tech Hackathon 2026 · Smart Manufacturing track

---

A typical Indian MSME has one electricity meter, at the main incomer. It reports
that the plant burned 48,000 kWh last month. It cannot say which of thirty machines
burned it. Sub-metering them all costs ₹5–7 lakh plus panel downtime, so nobody does it.

OneMeter clips one split-core CT around one cable and recovers per-machine
consumption from the aggregate signal alone (non-intrusive load monitoring), then
turns that into three things that move the electricity bill:

| | |
|---|---|
| **See**   | Per-machine kWh from one sensor. ₹1,500 instead of ₹6,00,000. |
| **Save**  | Specific energy consumption (kWh per unit output) baselined per machine. Drift means the machine is degrading *and* wasting — caught without a second sensor. |
| **Shift** | Maximum-demand breach prediction and time-of-day load scheduling, against a real published tariff (MSEDCL HT-I). |

## This repo

A visual prototype of the operator-facing interface — no backend. Everything is
client-side: the machine load models, the disaggregation view, the ledger and the
scheduler all run in the browser.

```
index.html   the whole thing, one file
```

## Data

Illustrative. Machine profiles are modelled on the **HIPE** open industrial dataset
(KIT Karlsruhe, 10 machines, per-machine ground truth). Not live plant data — the
disaggregation model is validated separately against HIPE.

## Design

Monochrome, with `#F05A24` reserved for the one machine that needs attention.
Six machines read as six steps of grey, so color means *look here* rather than
*this is machine #2*.
