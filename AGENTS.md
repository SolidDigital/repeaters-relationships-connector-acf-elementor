# Plugin Context Summary

This plugin allows an Elementor Loop Grid to use an ACF Repeater or ACF Relationship field as its data source. It also provides dynamic tags to pull sub-field data within the loop template.

## Dev Workflow
- Always git commit updates after changes unless instructed otherwise.
- Break large changes into multiple smaller commits grouped by related changes.
- If changes require explanation in the readme.txt, add that
- After changes, make appropriate semantic version updates in repeaters-relationships-connector-acf-elementor.php and readme.txt
- Update the changelog in readme.txt

## Documentation

| Doc | Read if interested in:                                                               |
|-----|--------------------------------------------------------------------------------------|
| [Architecture](docs/architecture.md) | File structure, namespace, and key includes                                          |
| [Query Source Controls](docs/query-source.md) | How the Loop Grid query source is extended with ACF sources and custom dropdowns     |
| [Query Execution](docs/query-execution.md) | How repeater rows and relationship posts are injected into Elementor's query results |
| [Dynamic Tags](docs/dynamic-tags.md) | The two dynamic tags for accessing repeater sub-fields and relationship post data    |
