## Upcoming Expense

### Details 


|Purpose | Amount | Quantity |Date | Explanation | Pals |
|--------|--------|----------|-----|-------------|------
{{ $total := 0 }}{{ range .Site.Data.expenses }}{{if eq .paid false }}|{{ .purpose }}|{{ .amount }}|{{ default "NA" .quantity }}|{{ .date }}|{{ .explanation }}|{{ $total = add $total (mul (default 1 .quantity) .amount) }}{{ default "NA" .pal }}
{{ end }}{{ end }}

### Summary

total unpaid : {{ $total }}ghc

## All Expenses

| Purpose | Amount | Date |Explanation | Paid | quantity | Pal |
|---------|--------|------|------------|------|----------|-----|
{{ range .Site.Data.expenses }}| {{ if isset . "purpose" }} {{ .purpose }} {{ else }} {{ errorf "The purpose field is missing, which is required" }} {{ end }} | {{ if isset . "amount" }} {{ .amount }} {{ else }} {{ errorf "The amount field is missing, which is required" }} {{ end }} | {{ if isset . "date" }} {{ .date }} {{ else }} Unspecified {{ end }} | {{ default "NA" .explanation }} | {{ if eq .paid true }} :thumbsup: {{ else if eq .paid false }} :x: {{ else }} {{ errorf "The paid boolean field is neither true nor false! please ensure to use a boolean value." }} | {{ default "NA" .quantity}} | {{ default "None" .pal }} 
{{ end }}
{{ end }}