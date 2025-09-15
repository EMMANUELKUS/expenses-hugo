
## Expenses


| Purpose | Amount | Date | Explanation |Paid |
|---|---|---|---|---|
{{ range .Site.Data.expenses }}| {{ default "ERROR" .purpose }} | {{ default "ERROR" .amount }} | {{ default "ERROR" .date }} | {{ default "ERROR" .explanation }} | {{ if eq .paid true }} :thumbsup: {{ else if eq .paid false }} :x: {{ else }} ERROR {{ end }}
{{ end }}