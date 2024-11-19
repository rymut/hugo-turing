# Hugo Turing Core

Core functionallity for hugo

# Functionality 

## 'turing/parmas.tmpl'

Retrives turing site configuration and fill any missing elements with default values

## 'turing/partial.tmpl'

Calling partial from site configuration
it does not require to be set in turing path 

```
{{ partial 'turing/partial.go.tmpl' (slice "reflect/is_map" ... ) }}
```

## 'turing/fmt/warnidf' and 'turing/warnidf'

Fill for 'warnidf' in hugo before version 0.123.0

## 'turing/fmt/printf'

Wrapper for printing using slice insted of direct print call

## Common errors

`warning-turing-partial-not-found` 
`error-turing-partial-not-found`


# Configuration

```yaml
params:
    turing:
        lookup:
            prefix: ['turing']
            suffix: ['tmpl', '', 'html']
        types: ['json', 'array'] # stores information about additional types
```