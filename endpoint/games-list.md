# Description

This is a reference document for RAWG.IO's API. It allows developers to request data from RAWG.IO's video game database.

# Parameters

|Parameter|Type|Description|
|---|---|---|
|search|string|Matches the keyword against the `name` field in RAWG's database|
|ordering|string|Accepts following fields: `name`,`released`,`added`,`created`,`updated`,`rating`,`metacritic`. To sort in descending order, pass the value with `-` prefix, eg: `-rating`. Refer **Ordering Parameter Inconsistencies** to learn more.|

## Ordering Parameter Inconsistencies

- `name` and `-name` sort entries based on unicode values. It can cause non-English names to appear at the top or bottom of sorting order.
- `added` and `-added` revert to `/games` response body.
- `created` reverts to `/games` response body. `-created` returns a paginated list of games that appear sorted. However, the criteria of sorting is unverifiable since `created` is missing from response body.
- `-updated` reverts to `/games` response body.
