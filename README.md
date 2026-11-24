# LeetCode Problems — Company Wise

Every LeetCode problem tagged by the company that has actually asked it, split into
**last 30 days / 3 months / 6 months / more than 6 months / all time**, with frequency,
acceptance rate and topic tags.

> Data originated from [liquidslr/leetcode-company-wise-problems](https://github.com/liquidslr/leetcode-company-wise-problems)
> (lists curated as of June 2025). This fork adds a generated index, difficulty
> breakdowns and a searchable JSON export. See [UPSTREAM.md](UPSTREAM.md) for the
> original readme.

---

## Quick start

1. Find your target company in [INDEX.md](INDEX.md) — companies are ranked by list size.
2. Open that folder and read `5. All.csv` for everything, or `1. Thirty Days.csv` for
   what's currently being asked.
3. Sort by **Frequency** descending — that column is how often the question shows up.

| Rank | Company | Total | Easy | Medium | Hard | Last 30 days |
|---:|---|---:|---:|---:|---:|---:|
| 1 | Google | 2324 | 612 | 1215 | 497 | 154 |
| 2 | Amazon | 2015 | 539 | 1086 | 390 | 114 |
| 3 | Meta | 1396 | 439 | 752 | 205 | 27 |
| 4 | Microsoft | 1371 | 393 | 741 | 237 | 47 |
| 5 | Bloomberg | 1239 | 403 | 649 | 187 | 24 |

**470 companies · 16,898 problem entries** across the full dataset.

---

## Repository layout

```
company-wise-problem/
├── INDEX.md                 # ranked summary table (generated)
├── index/
│   └── companies.json       # machine-readable per-company stats + top problems
├── scripts/
│   └── build_index.py       # regenerates INDEX.md and index/companies.json
├── <Company>/               # 470 folders
│   ├── 1. Thirty Days.csv
│   ├── 2. Three Months.csv
│   ├── 3. Six Months.csv
│   ├── 4. More Than Six Months.csv
│   │   └── 5. All.csv
└── UPSTREAM.md              # original upstream readme
```

### CSV columns

| Column | Meaning |
|---|---|
| `Difficulty` | `EASY`, `MEDIUM` or `HARD` |
| `Title` | Problem name |
| `Frequency` | How often the company asks it (higher = more frequent) |
| `Acceptance Rate` | LeetCode acceptance rate |
| `Link` | Direct problem URL |
| `Topics` | Comma-separated tags (e.g. `Array, Hash Table`) |

---

## Using the index

```bash
python scripts/build_index.py     # regenerate INDEX.md + index/companies.json
```

`index/companies.json` exposes, per company: total count, counts per time window,
difficulty breakdown and the five highest-frequency problems with links and topics.
Useful for building your own tracker, spreadsheet import or spaced-repetition plan.

```python
import json
data = json.load(open("index/companies.json"))
google = data["companies"]["Google"]
print(google["total"], google["windows"]["Thirty Days"])
```

---

## Study strategy

1. **Target a company**, not a topic — `Frequency` tells you where the return is.
2. **Start with the last-30-days list**; interview loops recycle recent questions.
3. Do the top 20 by frequency at **Medium** difficulty first — that's the bulk of
   onsite rounds for Google/Amazon/Microsoft.
4. Track solved problems separately; this repository only lists them.

---

## Contributing

Additions are welcome — keep the existing CSV schema and file naming so the index
script keeps working:

```bash
# after editing any <Company>/<window>.csv
python scripts/build_index.py
git add . && git commit -m "data: refresh <Company> lists"
```

---

## Disclaimer

Problem titles and links belong to LeetCode. Frequency figures are community-collected
estimates, not official data. This is a study aid, not affiliated with LeetCode or any
of the listed companies.

No licence was specified upstream; treat the content as shared study material.
