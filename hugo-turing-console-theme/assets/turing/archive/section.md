---
{{ . | transform.Remarshal "yaml" -}}
---