
## Expenses


| Purpose | Amount | Date | Explanation |Paid |
|---|---|---|---|---|
{{ range .Site.Data.expenses }}| {{ .purpose }} | {{ .amount }} | {{ .date }} | {{ .explanation }} | {{ if eq .paid true }} :thumbsup: {{ else if eq .paid false }} :x: {{ else }} ERROR {{ end }}
{{ end }}