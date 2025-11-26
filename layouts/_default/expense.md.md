## Upcoming Expense

### Details 

|Purpose | Amount | Date | Explanation |
|--------|--------|------|-------------|
{{ range .Site.Data.expenses }}{{if eq .paid false }}| {{ .purpose }} | {{ .amount }} |{{ .date }} | {{ .explanation }} |
{{ end }}{{ end }}

### Amount due
{{ $totalSpent := 0 }}
{{ range .Site.Data.expenses }}{{ if eq .paid false }} {{ .amount }}
{{ $totalSpent = add $totalSpent $totalSpent }}
{{ end }}{{ end }}
Total amount spent: {{ $totalSpent }} GHC

## All Expenses

| Purpose | Amount | Date | Explanation |Paid | 
|---|---|---|---|---|
{{ range .Site.Data.expenses }}| {{ if isset . "purpose" }} {{ .purpose }} {{ else }} {{ errorf "The purpose field is missing, which is required" }} {{ end }} | {{ if isset . "amount" }} {{ .amount }} {{ else }} {{ errorf "The amount field is missing, which is required" }} {{ end }} | {{ if isset . "date" }} {{ .date }} {{ else }} Unspecified {{ end }} | {{ default "NA" .explanation }} | {{ if eq .paid true }} :thumbsup: {{ else if eq .paid false }} :x: {{ else }} {{ errorf "The paid boolean field is neither true nor false! lease ensure to use a boolean value." }} {{ end }} | {{ default "NA" .quantity }}
{{ end }}