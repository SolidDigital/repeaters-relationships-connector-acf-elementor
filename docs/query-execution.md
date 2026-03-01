# Custom Query Execution

We use the `elementor/query/query_results` filter to intercept the query after it runs.

## ACF Repeater Source

The Loop Grid expects an array of `WP_Post` objects, but our source is an ACF Repeater (an array of arrays).

1. Get the repeater data from the current post using `get_field()`.
2. Loop through each repeater row and create a `stdClass` object cast to `WP_Post`.
3. Map common sub-field names (`title`, `content`) to post properties (`post_title`, `post_content`) for basic dynamic tag compatibility.
4. Attach the original, unmodified repeater row array to the new post object under the custom property `acf_repeater_data`.
5. Replace the original query results with the new array of generated objects.

## ACF Relationship Source

1. Get the array of `WP_Post` objects directly from the ACF Relationship field using `get_field()`.
2. Replace the original query results with this array. No special object creation is needed.
