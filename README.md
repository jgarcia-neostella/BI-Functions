# BI-Functions

Welcome to BI_Functions, here the Neostella BI-Team can share all languages libraries to be used from all BI-Team!

Feel free to create your own function and pull a request so your nice function can be shared and used with all BI-Team members.

This repository contains various utility functions and libraries created by the BI team.

## Contents

- [Database Utilities](#database-utilities)
- [concat-yaml.py](#concat-yamlpy)

## Database Utilities

### get_all_views

This function retrieves all views from a PostgreSQL database and creates a file for each view with its definition.

#### Usage

```python
from bi_functions.db_utils.get_all_views import get_all_views

get_all_views()
```

#### concat-yaml.py
concat-yaml.py is a utility script designed to generate SQL queries dynamically based on a YAML template and a CSV schema. The script reads variables, objects, and query parameters from a YAML file and processes them to replace variables, construct SQL queries, and handle multiple data types efficiently.

#### Usage
To use concat-yaml.py, follow these steps:

#### Prepare a YAML Template:
Create a YAML file that defines the variables, objects, and query parameters required for your SQL query. For example:

```yaml
Variables:
  section_name:
    default: "Your Section Name"
  query_output_name:
    default: "output_query.sql"
  construct_query:
    default: true
  original_table_name:
    default: "YourTable"
  contacts_legacy_table:
    default: "LegacyContacts"

Objects:
  - field1: "{{your_field1}}"
  - field2: "{{your_field2}}"

QueryVariables:
  additional_columns_to_show: {}

```

#### Run the Script: 
Execute the script by passing the YAML template file path as an argument. Use the following command:

```bash
python concat-yaml.py <full_template_file_path>
```

Review Output: The script will generate a SQL query based on the provided YAML template and save it to the specified output file (output_query.sql in the example).

#### Functions Overview
read_template: Reads the YAML template and extracts variables, objects, and query parameters.
replace_variables: Replaces placeholders in the objects with actual values from the variables.
read_schema: Reads the schema data from a CSV file and filters it based on the provided section name.
generate_sorted_df: Sorts the schema fields based on the provided order.
SQLScriptGenerator: Generates different SQL components (like columns and joins) based on the data type of each field.
create_query_items: Constructs the final SQL query by aggregating all SQL components.
generate_query: Combines the replaced objects and the constructed SQL query and saves the final result to an output file.
#### Example
If your YAML template is located at path/to/template.yaml, you would run:

```bash
Copiar código
python concat-yaml.py path/to/template.yaml
```