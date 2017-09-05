

# API

## `/match`

Returns the CJ identifier that the dedupe service believes matches a HMIS identifier (if any).

### Parameters
- `hmis`: a valid hmis id

### Response

- `404` Empty json object, If the value of `hmis` is not a id known to this service
- `204` Empty json object, The service can not find a CJ identifier that is a possible match
- `200` `{"cj": "best matching cj id", "score": score_of_that_match_(float)"}`

### Example

```bash
curl http:/service.url/match?hmis=10
{"cj": "ad8aa", "score": .89}
```

## `/crosswalk`

Returns the current crosswalk table as CSV

# Updating
The crosswalk will be updated daily, after the HMIS updates
