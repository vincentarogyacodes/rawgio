# Description

This is a reference document for RAWG.IO's API. It allows developers to request data from RAWG.IO's video game database.

# Parameters

|Parameter|Type|Description|
|---|---|---|
|search|string|Matches the keyword against the `name` field in RAWG's database|
|genres|integer, string|Accepts `id`, comma separated `id` list, for example `1,20`, and slugs to pull all games belonging to the requested genre. Some games can be associated with more than one genre. Refer to `GET/genres` to find dedicated `id`s and slugs for each genre. Refer to [`Genres` Notes] #Genres for more information and edge cases.| 
|ordering|string|Accepts following fields: `name`,`released`,`added`,`created`,`updated`,`rating`,`metacritic`. To sort in descending order, pass the value with `-` prefix, eg: `-rating`. Refer to [`Ordering` Notes] #ordering for parameter inconsistencies|

# Parameter Notes

### Genres

- `GET /Games doesn't include a parameter to exclude genres. When requesting games of specific genres, the response may include games that have more genres in addition to the specified genre. 

### Ordering

- `name` and `-name` sort entries based on unicode values. It can cause non-English names to appear at the top or bottom of sorting order.
- `added` and `-added` revert to `/games` response body.
- `created` reverts to `/games` response body. `-created` returns a paginated list of games that appear sorted. However, the criteria of sorting is unverifiable since `created` is missing from response body.
- `-updated` reverts to `/games` response body.
