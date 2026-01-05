|Purpose | Amount | Quantity |Date | Explanation | Pal |
|--------|--------|----------|-----|-------------|------
{{ $total := 0 }}{{ $total_uncle := 0 }}{{ range .Site.Data.expenses }}{{if eq .paid false }}|{{ .purpose }}|{{ .amount }}|{{ default "NA" .quantity }}|{{ .date }}|{{ .explanation }}|{{ $total = add $total (mul (default 1 .quantity) .amount) }}{{ default "None" .pal }}{{ if eq .paid Uncle}}{{ $total_Uncle = add .amount}}
{{ end }}{{ end }}




## Upcoming Expense

### Details 


|Purpose | Amount | Quantity |Date | Explanation | Pal |
|--------|--------|----------|-----|-------------|------
{{ $total := 0 }}{{ $total_uncle := 0 }}{{ range .Site.Data.expenses }}{{if eq .paid false }}|{{ .purpose }}|{{ .amount }}|{{ default "NA" .quantity }}|{{ .date }}|{{ .explanation }}|{{ $total = add $total (mul (default 1 .quantity) .amount) }}{{ default "None" .pal }}
{{ end }}{{ end }}

### Summary

Total unpaid: {{ $total }}ghc

#### Payments committed to by Uncle

Total unpaid: {{ $total_uncle }}ghc

## All Expenses

| Purpose | Amount | Date |Explanation | Paid | Quantity | Pal |
|---------|--------|------|------------|------|----------|-----|
{{ range .Site.Data.expenses }}| {{ if isset . "purpose" }} {{ .purpose }} {{ else }} {{ errorf "The purpose field is missing, which is required" }} {{ end }} | {{ if isset . "amount" }} {{ .amount }} {{ else }} {{ errorf "The amount field is missing, which is required" }} {{ end }} | {{ if isset . "date" }} {{ .date }} {{ else }} Unspecified {{ end }} | {{ default "NA" .explanation }} | {{ if eq .paid true }} :thumbsup: {{ else if eq .paid false }} :x: {{ else }} {{ errorf "The paid boolean field is neither true nor false! please ensure to use a boolean value." }} {{end}} | {{ default "NA" .quantity }} | {{ default "None" .pal }}
{{ end }}