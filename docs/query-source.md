# Query Source Controls

## Modifying the Loop Grid Query Source

- **Problem:** The "Source" dropdown in the Loop Grid's Query tab is not easily extensible via a standard filter.
- **Solution:** We globally replace the `related-query` group control with our own custom class, `Acf_Query_Control_Wrapper`.
    - This is done by hooking into `elementor/controls/register` with a late priority (999) and using `$controls_manager->add_group_control()` to overwrite the existing control.
    - Our custom class extends `\ElementorPro\Modules\QueryControl\Controls\Group_Control_Related` to ensure we inherit all the default functionality.

## Adding Custom Controls

- The `Acf_Query_Control_Wrapper` class overrides the `get_fields_array()` method.
- This method is responsible for:
    - **Adding Sources:** Adding "ACF Repeater" and "ACF Relationship" to the `post_type` control's options.
    - **Adding Conditional Dropdowns:**
        - Defines a `SELECT` control named `acf_repeater_name`, conditionally displayed when the source is `acf_repeater`.
        - Defines a `SELECT` control named `acf_relation_name`, conditionally displayed when the source is `acf_relation`.
    - **Hiding Controls:** Modifying the `condition` array of several default controls (like Include/Exclude, Date, and Order) to hide them when the source is `acf_repeater` or `acf_relation`.
