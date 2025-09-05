
## Expenses


| Purpose | Amount | Date | Explanation |Paid |
|---|---|---|---|---|
{{ range .Site.Data.expenses }}| {{ .purpose }} | {{ .amount }} | {{ .date }} | {{ .explanation }} | {{ if .paid }} :thumbsup: {{ else }} :x: {{ end }}
{{ end }}