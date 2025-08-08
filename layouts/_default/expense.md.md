
## Tabular representation

| Purpose | Amount | Date | Explanation |Paid       |
|---|---|---|---|---|
| {{ .Site.Data.expense.purpose }} | {{ .Site.Data.expense.amount }} | {{ .Site.Data.expense.date }} | {{ .Site.Data.expense.explaination }}


## Another tabular representation

| Field | Value |
|-------|-------|
| {{ .Site.Data.expense.purpose }} |
| {{ .Site.Data.expense.amount }} |
| {{ .Site.Data.expense.date }} |
| {{ .Site.Data.expense.explaination }} |

## Bullet-point representation

**Expense**:
- _{{ .Site.Data.expense.purpose }}_
- _{{ .Site.Data.expense.amount }}_
- _{{ .Site.Data.expense.date }}_
- _{{ .Site.Data.expense.explaination }}_