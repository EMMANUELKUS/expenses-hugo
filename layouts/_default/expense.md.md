
## Expenses


| Purpose | Amount | Date | Explanation |Paid |
|---|---|---|---|---|
{{ range .Site.Data.expenses }}| {{ .purpose }} | {{ .amount }} | {{ .date }} | {{ .explanation }} |
{{ end }}