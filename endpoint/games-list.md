# Description

This document provides reference documentation for the GET /games endpoint of the RAWG.IO public API. It includes a parameter reference describing each supported query parameter, along with implementation notes documenting verified endpoint behavior, observed inconsistencies, and integration considerations identified through independent testing.

# Parameters

|Parameter|Type|Description|
|---|---|---|
|search|string|Matches the keyword against the `name` field in RAWG's database.|
|genres|integer, string|Accepts `id`, comma separated `id` list, for example `1,20`, and slugs to pull all games belonging to the requested genre. Some games can be associated with more than one genre. Refer to `GET /genres` to find dedicated `id`s and slugs for each genre. Refer to [Genres Notes](#genres) for more information and edge cases.| 
|ordering|string|Accepts following fields: `name`,`released`,`added`,`created`,`updated`,`rating`,`metacritic`. To sort in descending order, pass the value with `-` prefix, eg: `-rating`. Refer to [Ordering Notes](#ordering) for parameter inconsistencies.|
|tags|integer, string|Accepts integer values as `id` and strings as slug to return a list of games that belong to requested tag. Also accepts comma separated `ids` and slugs to return OR matched results. Refer to `GET /tags` to find dedicated tag `id`s and slugs. Refer to [Tags Notes](#tags) for more information.|
|platforms|integer|Accepts `id` or comma separated `id`s to return a list of games available on specified platform(s). Refer to `GET /platforms` to learn about corresponding `id`s and platforms. Also, refer to [Platform Notes](#platforms) for more.|
|developers|integer, string| Accepts `id`, comma separated `id`s, and slugs to filter and return developers matching the query parameter. Refer to [Developers Notes](#developers) for workflows on finding developers `id`.|

# Parameter Notes

### Genres

- `GET /games` doesn't include a parameter to exclude `genres`. This can result in responses to include games that have more `genres` in addition to the specified genre.
- May not include all intuitive genres. Refer to `GET /tags` if specific genre is missing. For instance: horror is a `tag` not a `genre`.

### Ordering

- `name` and `-name` sort entries based on unicode values. It can cause non-English names to appear at the top or bottom of sorting order.
- `added` and `-added` revert to `/games` response body.
- `created` reverts to `/games` response body. `-created` returns a paginated list of games that appear sorted. However, the criteria of sorting is unverifiable since `created` is missing from response body.
- `-updated` reverts to `/games` response body.

### Tags

- Passing wrong type and wrong value returns the HTTP 200 success code, even though `count` remains 0.

### Platforms

- Does not accept slugs to filter platforms. Returns the HTTP 200 success code instead, with a `count` of 0.

### Developers

- Developers can follow either of the two listed workflows to find developers `id` and slugs:

    a. Search a game from a developer in the `/games` endpoint.  For example: `GET /games?search=portal`. Make a note of `id` in `/games` response body. Next, pass `id` in `GET /games/{id}`. For example: `GET /games/13536`.  Investigate the response body to find developer `id` and slug.

    b. Search the developer name in `GET /developers` endpoint, using the search parameter. For example: `GET /developers?search=valve`. Investigate the response body to find the matching developer name and `id`. Be mindful of naming conventions as developers can have different registered names. For example: 

    ``` JSON

    "name": "Valve Software",
            "exact_name": "valve software",
            "search_name": "valve software",
            "slug": "valve-software",

    ```
    Optionally, test the developer `id` in `GET /developers/{id}` to pull developer details for confirmation.

