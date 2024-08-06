# BI-Functions

Welcome to BI_Functions, here the Neostella BI-Team can share all languages libraries to be used from all BI-Team!

fell free to create your own function and pull a request so your nice function can be shared and used with all BI-Team members.



This repository contains various utility functions and libraries created by the BI team.

## Contents

- [Database Utilities](#database-utilities)

## Database Utilities

### get_all_views

This function retrieves all views from a PostgreSQL database and creates a file for each view with its definition.

### Usage

```python
from bi_functions.db_utils.get_all_views import get_all_views

get_all_views()