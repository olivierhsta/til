# Naming Convention Oracle APEX

## APEX

#### Items

 | Database Page Items        | Static Page Item | Application Items | Substitution String
 | -------------------------- | ---------------- | ----------------- | -------------------
 | `PXX_DATABASE_COLUMN_NAME` | `PXX_NAME`       | `G_NAME`          | `G_NAME`            |

## SQL

#### Database columns

- ALL CAPS
- snake_case
- Abbreviation of 3-6 letters

 | Primary Key                | Lookup Code | Boolean      | Date          | Number       | Language
 | -------------------------- | ----------- | ------------ | ------------- | ------------ | ------------------------
 | `ID_<TABLE_NAME_SINGULAR>` | `RC_<NAME>` | `IND_<NAME>` | `DATE_<NAME>` | `NBR_<NAME>` | `<name>_&lt;FR\</name> | EN\ | AN>`

#### Constraints

 | Primary Key       | Foreign Key                | Unique Key                  | Check Constraint
 | ----------------- | -------------------------- | --------------------------- | ---------------------------
 | `<TABLE_NAME>_PK` | `<TABLE_NAME>_FK<Counter>` | `<COLUMN_NAME>_UK<Counter>` | `<COLUMN_NAME>_CK<Counter>`

#### Indexes

 | Primary Key       | Foreign Key                | Unique Key                  | Other
 | ----------------- | -------------------------- | --------------------------- | ---------------------------
 | `<TABLE_NAME>_PK` | `<TABLE_NAME>_FK<Counter>` | `<COLUMN_NAME>_UK<Counter>` | `<TABLE_NAME>_IDX<Counter>` |

#### Triggers

`<PROJECT_ABBREVIATION>_<TABLE_NAME>_<ACTIONS>_TRG`

Actions are a two, three, or fourletter abbreviationcomposed of the following letters:

1. "B" for Before or "A" for After.
2. "I" for Insert, "U" for Update, "D" for Delete
3. "I" for Insert, "U" for Update, "D" for Delete (Optional)
4. "I" for Insert, "U" for Update, "D" for Delete (Optional)

#### Sequence

`<PROJECT_ABBREVIATION>_<TABLE_NAME>_SEQ`

#### Types

`<PROJECT_ABBREVIATION>_<NAME>_T`

#### Materialized Views

`<PROJECT_ABBREVIATION>_<NAME>_MV`

#### Packages

`<PROJECT_ABBREVIATION>_<NAME>_PKG`

## PL/SQL

#### Variables

|                        | Local | Parameters | Global
| ---------------------- | ----- | ---------- | ------
| Contains Column Value  | `l_<column_name>` | `p_<column_name>` | `g_<column_name>`
| Other                  | `l_<name>` | `p_<name>` | `g_<name>`

| | Constants | Cursors
--- | --------- | -------
Local | `lc_<name>`  | `c_<table_name>`
Global | `gc_<name>` | `c_<name>`


## JavaScript

#### Variables
- camelCase
- jQuery $variables start with `$`
- GLOBALVARIABLES are in uppercase
- CONSTANTS are in uppercase

#### Functions
- camelCase
- pParameters start with `p`
