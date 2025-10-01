
## Expenses


| Purpose | Amount | Date | Explanation |Paid | 
|---|---|---|---|---|
{{ range .Site.Data.expenses }}| {{ if isset . "purpose" }} {{ .purpose }} {{ else }} MISSING {{ end }} | {{ if isset . "amount" }} {{ .amount }} {{ else }} MISSING {{ end }} | {{ if isset . "date" }} {{ .date }} {{ else }} MISSING {{ end }} | {{ .explanation }} | {{ if eq .paid true }} :thumbsup: {{ else if eq .paid false }} :x: {{ else }} ERROR {{ end }}
{{ end }}