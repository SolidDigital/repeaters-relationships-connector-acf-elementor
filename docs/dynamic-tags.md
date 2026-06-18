# Dynamic Tags

The plugin registers two dynamic tags to access field data within the loop. Both are registered for Text, Image, and URL categories.

## ACF Repeater Sub Field Tag (`Acf_Repeater_Sub_Field_Tag`)

**Controls:**
1. **Sub Field:** A dropdown populated with all repeater/sub-field pairs, formatted as `Repeater Label > Sub-field Label`.
2. **Output:** Selects whether to return the raw field value, an ACF File field URL, or an ACF File field name.

**Logic:**
- `get_value()` retrieves the current `post` object within the loop.
- Checks for the custom `acf_repeater_data` property on that object.
- Parses the control's setting to extract the sub-field name and retrieves its value from `acf_repeater_data`.
- Handles ACF File sub-fields saved as an array, attachment ID, or URL when the Output control is set to File URL or File Name.
- Handles image sub-fields by returning the ID/URL array Elementor expects.

## ACF Relationship Sub Field Tag (`Acf_Relation_Sub_Field_Tag`)

**Controls:**
1. **Relationship Field:** Selects the parent ACF Relationship field.
2. **Field:** Selects what data to retrieve from the related post (Post Title, Content, Excerpt, Permalink, Featured Image).

**Logic:**
- In a relationship query, the `global $post` inside the loop is the actual `WP_Post` from the relationship.
- `get_value()` reads the "Field" control's setting and retrieves the corresponding property from `$post` (e.g., `get_the_title($post)`, `get_permalink($post)`).
- Handles requests for the featured image.
