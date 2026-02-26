# Architecture

The plugin is namespaced under `RepRelCon`. The main plugin file, `repeaters-relationships-connector-acf-elementor.php`, loads all includes.

## Key Files

- **`includes/register_controls.php`**: Modifies the Elementor Query control to add ACF Repeater and Relationship as query sources.
- **`includes/register_dynamic_tag.php`**: Implements the two dynamic tags: `Acf_Repeater_Sub_Field_Tag` and `Acf_Relation_Sub_Field_Tag`.
- **`includes/modify_query_results.php`**: Filters Elementor's query results to inject ACF repeater or relationship data.
