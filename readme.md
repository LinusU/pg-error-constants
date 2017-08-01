# PG Error Constants

PostgresQL error constants for use with Node.js. Use these to avoid code like `if (err.code === '23505')` and instead write `if (err.code === UNIQUE_VIOLATION)`.

## Installation

```sh
npm install --save pg-error-constants
```

## Usage

```js
const { UNIQUE_VIOLATION } = require('pg-error-constants')

// ...
  .catch((err) => {
    if (err.code === UNIQUE_VIOLATION && err.constraint === 'user_name_key') {
      throw new UserError('That name is already taken')
    }

    throw err
  })
```

## Constants

<table>
  <tr><th align="left">Error Code</th> <th align="left">Constant name</th></tr>

  <tr><th align="left" colspan="2">Class 00 — Successful Completion</th></tr>
  <tr><td>00000</td><td>SUCCESSFUL_COMPLETION</td></tr>

  <tr><th align="left" colspan="2">Class 01 — Warning</th></tr>
  <tr><td>01000</td><td>WARNING</td></tr>
  <tr><td>0100C</td><td>DYNAMIC_RESULT_SETS_RETURNED</td></tr>
  <tr><td>01008</td><td>IMPLICIT_ZERO_BIT_PADDING</td></tr>
  <tr><td>01003</td><td>NULL_VALUE_ELIMINATED_IN_SET_FUNCTION</td></tr>
  <tr><td>01007</td><td>PRIVILEGE_NOT_GRANTED</td></tr>
  <tr><td>01006</td><td>PRIVILEGE_NOT_REVOKED</td></tr>
  <tr><td>01004</td><td>STRING_DATA_RIGHT_TRUNCATION</td></tr>
  <tr><td>01P01</td><td>DEPRECATED_FEATURE</td></tr>

  <tr><th align="left" colspan="2">Class 02 — No Data (this is also a warning class per the SQL standard)</th></tr>
  <tr><td>02000</td><td>NO_DATA</td></tr>
  <tr><td>02001</td><td>NO_ADDITIONAL_DYNAMIC_RESULT_SETS_RETURNED</td></tr>

  <tr><th align="left" colspan="2">Class 03 — SQL Statement Not Yet Complete</th></tr>
  <tr><td>03000</td><td>SQL_STATEMENT_NOT_YET_COMPLETE</td></tr>

  <tr><th align="left" colspan="2">Class 08 — Connection Exception</th></tr>
  <tr><td>08000</td><td>CONNECTION_EXCEPTION</td></tr>
  <tr><td>08003</td><td>CONNECTION_DOES_NOT_EXIST</td></tr>
  <tr><td>08006</td><td>CONNECTION_FAILURE</td></tr>
  <tr><td>08001</td><td>SQLCLIENT_UNABLE_TO_ESTABLISH_SQLCONNECTION</td></tr>
  <tr><td>08004</td><td>SQLSERVER_REJECTED_ESTABLISHMENT_OF_SQLCONNECTION</td></tr>
  <tr><td>08007</td><td>TRANSACTION_RESOLUTION_UNKNOWN</td></tr>
  <tr><td>08P01</td><td>PROTOCOL_VIOLATION</td></tr>

  <tr><th align="left" colspan="2">Class 09 — Triggered Action Exception</th></tr>
  <tr><td>09000</td><td>TRIGGERED_ACTION_EXCEPTION</td></tr>

  <tr><th align="left" colspan="2">Class 0A — Feature Not Supported</th></tr>
  <tr><td>0A000</td><td>FEATURE_NOT_SUPPORTED</td></tr>

  <tr><th align="left" colspan="2">Class 0B — Invalid Transaction Initiation</th></tr>
  <tr><td>0B000</td><td>INVALID_TRANSACTION_INITIATION</td></tr>

  <tr><th align="left" colspan="2">Class 0F — Locator Exception</th></tr>
  <tr><td>0F000</td><td>LOCATOR_EXCEPTION</td></tr>
  <tr><td>0F001</td><td>INVALID_LOCATOR_SPECIFICATION</td></tr>

  <tr><th align="left" colspan="2">Class 0L — Invalid Grantor</th></tr>
  <tr><td>0L000</td><td>INVALID_GRANTOR</td></tr>
  <tr><td>0LP01</td><td>INVALID_GRANT_OPERATION</td></tr>

  <tr><th align="left" colspan="2">Class 0P — Invalid Role Specification</th></tr>
  <tr><td>0P000</td><td>INVALID_ROLE_SPECIFICATION</td></tr>

  <tr><th align="left" colspan="2">Class 0Z — Diagnostics Exception</th></tr>
  <tr><td>0Z000</td><td>DIAGNOSTICS_EXCEPTION</td></tr>
  <tr><td>0Z002</td><td>STACKED_DIAGNOSTICS_ACCESSED_WITHOUT_ACTIVE_HANDLER</td></tr>

  <tr><th align="left" colspan="2">Class 20 — Case Not Found</th></tr>
  <tr><td>20000</td><td>CASE_NOT_FOUND</td></tr>

  <tr><th align="left" colspan="2">Class 21 — Cardinality Violation</th></tr>
  <tr><td>21000</td><td>CARDINALITY_VIOLATION</td></tr>

  <tr><th align="left" colspan="2">Class 22 — Data Exception</th></tr>
  <tr><td>22000</td><td>DATA_EXCEPTION</td></tr>
  <tr><td>2202E</td><td>ARRAY_SUBSCRIPT_ERROR</td></tr>
  <tr><td>22021</td><td>CHARACTER_NOT_IN_REPERTOIRE</td></tr>
  <tr><td>22008</td><td>DATETIME_FIELD_OVERFLOW</td></tr>
  <tr><td>22012</td><td>DIVISION_BY_ZERO</td></tr>
  <tr><td>22005</td><td>ERROR_IN_ASSIGNMENT</td></tr>
  <tr><td>2200B</td><td>ESCAPE_CHARACTER_CONFLICT</td></tr>
  <tr><td>22022</td><td>INDICATOR_OVERFLOW</td></tr>
  <tr><td>22015</td><td>INTERVAL_FIELD_OVERFLOW</td></tr>
  <tr><td>2201E</td><td>INVALID_ARGUMENT_FOR_LOGARITHM</td></tr>
  <tr><td>22014</td><td>INVALID_ARGUMENT_FOR_NTILE_FUNCTION</td></tr>
  <tr><td>22016</td><td>INVALID_ARGUMENT_FOR_NTH_VALUE_FUNCTION</td></tr>
  <tr><td>2201F</td><td>INVALID_ARGUMENT_FOR_POWER_FUNCTION</td></tr>
  <tr><td>2201G</td><td>INVALID_ARGUMENT_FOR_WIDTH_BUCKET_FUNCTION</td></tr>
  <tr><td>22018</td><td>INVALID_CHARACTER_VALUE_FOR_CAST</td></tr>
  <tr><td>22007</td><td>INVALID_DATETIME_FORMAT</td></tr>
  <tr><td>22019</td><td>INVALID_ESCAPE_CHARACTER</td></tr>
  <tr><td>2200D</td><td>INVALID_ESCAPE_OCTET</td></tr>
  <tr><td>22025</td><td>INVALID_ESCAPE_SEQUENCE</td></tr>
  <tr><td>22P06</td><td>NONSTANDARD_USE_OF_ESCAPE_CHARACTER</td></tr>
  <tr><td>22010</td><td>INVALID_INDICATOR_PARAMETER_VALUE</td></tr>
  <tr><td>22023</td><td>INVALID_PARAMETER_VALUE</td></tr>
  <tr><td>2201B</td><td>INVALID_REGULAR_EXPRESSION</td></tr>
  <tr><td>2201W</td><td>INVALID_ROW_COUNT_IN_LIMIT_CLAUSE</td></tr>
  <tr><td>2201X</td><td>INVALID_ROW_COUNT_IN_RESULT_OFFSET_CLAUSE</td></tr>
  <tr><td>22009</td><td>INVALID_TIME_ZONE_DISPLACEMENT_VALUE</td></tr>
  <tr><td>2200C</td><td>INVALID_USE_OF_ESCAPE_CHARACTER</td></tr>
  <tr><td>2200G</td><td>MOST_SPECIFIC_TYPE_MISMATCH</td></tr>
  <tr><td>22004</td><td>NULL_VALUE_NOT_ALLOWED</td></tr>
  <tr><td>22002</td><td>NULL_VALUE_NO_INDICATOR_PARAMETER</td></tr>
  <tr><td>22003</td><td>NUMERIC_VALUE_OUT_OF_RANGE</td></tr>
  <tr><td>22026</td><td>STRING_DATA_LENGTH_MISMATCH</td></tr>
  <tr><td>22001</td><td>STRING_DATA_RIGHT_TRUNCATION</td></tr>
  <tr><td>22011</td><td>SUBSTRING_ERROR</td></tr>
  <tr><td>22027</td><td>TRIM_ERROR</td></tr>
  <tr><td>22024</td><td>UNTERMINATED_C_STRING</td></tr>
  <tr><td>2200F</td><td>ZERO_LENGTH_CHARACTER_STRING</td></tr>
  <tr><td>22P01</td><td>FLOATING_POINT_EXCEPTION</td></tr>
  <tr><td>22P02</td><td>INVALID_TEXT_REPRESENTATION</td></tr>
  <tr><td>22P03</td><td>INVALID_BINARY_REPRESENTATION</td></tr>
  <tr><td>22P04</td><td>BAD_COPY_FILE_FORMAT</td></tr>
  <tr><td>22P05</td><td>UNTRANSLATABLE_CHARACTER</td></tr>
  <tr><td>2200L</td><td>NOT_AN_XML_DOCUMENT</td></tr>
  <tr><td>2200M</td><td>INVALID_XML_DOCUMENT</td></tr>
  <tr><td>2200N</td><td>INVALID_XML_CONTENT</td></tr>
  <tr><td>2200S</td><td>INVALID_XML_COMMENT</td></tr>
  <tr><td>2200T</td><td>INVALID_XML_PROCESSING_INSTRUCTION</td></tr>

  <tr><th align="left" colspan="2">Class 23 — Integrity Constraint Violation</th></tr>
  <tr><td>23000</td><td>INTEGRITY_CONSTRAINT_VIOLATION</td></tr>
  <tr><td>23001</td><td>RESTRICT_VIOLATION</td></tr>
  <tr><td>23502</td><td>NOT_NULL_VIOLATION</td></tr>
  <tr><td>23503</td><td>FOREIGN_KEY_VIOLATION</td></tr>
  <tr><td>23505</td><td>UNIQUE_VIOLATION</td></tr>
  <tr><td>23514</td><td>CHECK_VIOLATION</td></tr>
  <tr><td>23P01</td><td>EXCLUSION_VIOLATION</td></tr>

  <tr><th align="left" colspan="2">Class 24 — Invalid Cursor State</th></tr>
  <tr><td>24000</td><td>INVALID_CURSOR_STATE</td></tr>

  <tr><th align="left" colspan="2">Class 25 — Invalid Transaction State</th></tr>
  <tr><td>25000</td><td>INVALID_TRANSACTION_STATE</td></tr>
  <tr><td>25001</td><td>ACTIVE_SQL_TRANSACTION</td></tr>
  <tr><td>25002</td><td>BRANCH_TRANSACTION_ALREADY_ACTIVE</td></tr>
  <tr><td>25008</td><td>HELD_CURSOR_REQUIRES_SAME_ISOLATION_LEVEL</td></tr>
  <tr><td>25003</td><td>INAPPROPRIATE_ACCESS_MODE_FOR_BRANCH_TRANSACTION</td></tr>
  <tr><td>25004</td><td>INAPPROPRIATE_ISOLATION_LEVEL_FOR_BRANCH_TRANSACTION</td></tr>
  <tr><td>25005</td><td>NO_ACTIVE_SQL_TRANSACTION_FOR_BRANCH_TRANSACTION</td></tr>
  <tr><td>25006</td><td>READ_ONLY_SQL_TRANSACTION</td></tr>
  <tr><td>25007</td><td>SCHEMA_AND_DATA_STATEMENT_MIXING_NOT_SUPPORTED</td></tr>
  <tr><td>25P01</td><td>NO_ACTIVE_SQL_TRANSACTION</td></tr>
  <tr><td>25P02</td><td>IN_FAILED_SQL_TRANSACTION</td></tr>

  <tr><th align="left" colspan="2">Class 26 — Invalid SQL Statement Name</th></tr>
  <tr><td>26000</td><td>INVALID_SQL_STATEMENT_NAME</td></tr>

  <tr><th align="left" colspan="2">Class 27 — Triggered Data Change Violation</th></tr>
  <tr><td>27000</td><td>TRIGGERED_DATA_CHANGE_VIOLATION</td></tr>

  <tr><th align="left" colspan="2">Class 28 — Invalid Authorization Specification</th></tr>
  <tr><td>28000</td><td>INVALID_AUTHORIZATION_SPECIFICATION</td></tr>
  <tr><td>28P01</td><td>INVALID_PASSWORD</td></tr>

  <tr><th align="left" colspan="2">Class 2B — Dependent Privilege Descriptors Still Exist</th></tr>
  <tr><td>2B000</td><td>DEPENDENT_PRIVILEGE_DESCRIPTORS_STILL_EXIST</td></tr>
  <tr><td>2BP01</td><td>DEPENDENT_OBJECTS_STILL_EXIST</td></tr>

  <tr><th align="left" colspan="2">Class 2D — Invalid Transaction Termination</th></tr>
  <tr><td>2D000</td><td>INVALID_TRANSACTION_TERMINATION</td></tr>

  <tr><th align="left" colspan="2">Class 2F — SQL Routine Exception</th></tr>
  <tr><td>2F000</td><td>SQL_ROUTINE_EXCEPTION</td></tr>
  <tr><td>2F005</td><td>FUNCTION_EXECUTED_NO_RETURN_STATEMENT</td></tr>
  <tr><td>2F002</td><td>MODIFYING_SQL_DATA_NOT_PERMITTED</td></tr>
  <tr><td>2F003</td><td>PROHIBITED_SQL_STATEMENT_ATTEMPTED</td></tr>
  <tr><td>2F004</td><td>READING_SQL_DATA_NOT_PERMITTED</td></tr>

  <tr><th align="left" colspan="2">Class 34 — Invalid Cursor Name</th></tr>
  <tr><td>34000</td><td>INVALID_CURSOR_NAME</td></tr>

  <tr><th align="left" colspan="2">Class 38 — External Routine Exception</th></tr>
  <tr><td>38000</td><td>EXTERNAL_ROUTINE_EXCEPTION</td></tr>
  <tr><td>38001</td><td>CONTAINING_SQL_NOT_PERMITTED</td></tr>
  <tr><td>38002</td><td>MODIFYING_SQL_DATA_NOT_PERMITTED</td></tr>
  <tr><td>38003</td><td>PROHIBITED_SQL_STATEMENT_ATTEMPTED</td></tr>
  <tr><td>38004</td><td>READING_SQL_DATA_NOT_PERMITTED</td></tr>

  <tr><th align="left" colspan="2">Class 39 — External Routine Invocation Exception</th></tr>
  <tr><td>39000</td><td>EXTERNAL_ROUTINE_INVOCATION_EXCEPTION</td></tr>
  <tr><td>39001</td><td>INVALID_SQLSTATE_RETURNED</td></tr>
  <tr><td>39004</td><td>NULL_VALUE_NOT_ALLOWED</td></tr>
  <tr><td>39P01</td><td>TRIGGER_PROTOCOL_VIOLATED</td></tr>
  <tr><td>39P02</td><td>SRF_PROTOCOL_VIOLATED</td></tr>

  <tr><th align="left" colspan="2">Class 3B — Savepoint Exception</th></tr>
  <tr><td>3B000</td><td>SAVEPOINT_EXCEPTION</td></tr>
  <tr><td>3B001</td><td>INVALID_SAVEPOINT_SPECIFICATION</td></tr>

  <tr><th align="left" colspan="2">Class 3D — Invalid Catalog Name</th></tr>
  <tr><td>3D000</td><td>INVALID_CATALOG_NAME</td></tr>

  <tr><th align="left" colspan="2">Class 3F — Invalid Schema Name</th></tr>
  <tr><td>3F000</td><td>INVALID_SCHEMA_NAME</td></tr>

  <tr><th align="left" colspan="2">Class 40 — Transaction Rollback</th></tr>
  <tr><td>40000</td><td>TRANSACTION_ROLLBACK</td></tr>
  <tr><td>40002</td><td>TRANSACTION_INTEGRITY_CONSTRAINT_VIOLATION</td></tr>
  <tr><td>40001</td><td>SERIALIZATION_FAILURE</td></tr>
  <tr><td>40003</td><td>STATEMENT_COMPLETION_UNKNOWN</td></tr>
  <tr><td>40P01</td><td>DEADLOCK_DETECTED</td></tr>

  <tr><th align="left" colspan="2">Class 42 — Syntax Error or Access Rule Violation</th></tr>
  <tr><td>42000</td><td>SYNTAX_ERROR_OR_ACCESS_RULE_VIOLATION</td></tr>
  <tr><td>42601</td><td>SYNTAX_ERROR</td></tr>
  <tr><td>42501</td><td>INSUFFICIENT_PRIVILEGE</td></tr>
  <tr><td>42846</td><td>CANNOT_COERCE</td></tr>
  <tr><td>42803</td><td>GROUPING_ERROR</td></tr>
  <tr><td>42P20</td><td>WINDOWING_ERROR</td></tr>
  <tr><td>42P19</td><td>INVALID_RECURSION</td></tr>
  <tr><td>42830</td><td>INVALID_FOREIGN_KEY</td></tr>
  <tr><td>42602</td><td>INVALID_NAME</td></tr>
  <tr><td>42622</td><td>NAME_TOO_LONG</td></tr>
  <tr><td>42939</td><td>RESERVED_NAME</td></tr>
  <tr><td>42804</td><td>DATATYPE_MISMATCH</td></tr>
  <tr><td>42P18</td><td>INDETERMINATE_DATATYPE</td></tr>
  <tr><td>42P21</td><td>COLLATION_MISMATCH</td></tr>
  <tr><td>42P22</td><td>INDETERMINATE_COLLATION</td></tr>
  <tr><td>42809</td><td>WRONG_OBJECT_TYPE</td></tr>
  <tr><td>42703</td><td>UNDEFINED_COLUMN</td></tr>
  <tr><td>42883</td><td>UNDEFINED_FUNCTION</td></tr>
  <tr><td>42P01</td><td>UNDEFINED_TABLE</td></tr>
  <tr><td>42P02</td><td>UNDEFINED_PARAMETER</td></tr>
  <tr><td>42704</td><td>UNDEFINED_OBJECT</td></tr>
  <tr><td>42701</td><td>DUPLICATE_COLUMN</td></tr>
  <tr><td>42P03</td><td>DUPLICATE_CURSOR</td></tr>
  <tr><td>42P04</td><td>DUPLICATE_DATABASE</td></tr>
  <tr><td>42723</td><td>DUPLICATE_FUNCTION</td></tr>
  <tr><td>42P05</td><td>DUPLICATE_PREPARED_STATEMENT</td></tr>
  <tr><td>42P06</td><td>DUPLICATE_SCHEMA</td></tr>
  <tr><td>42P07</td><td>DUPLICATE_TABLE</td></tr>
  <tr><td>42712</td><td>DUPLICATE_ALIAS</td></tr>
  <tr><td>42710</td><td>DUPLICATE_OBJECT</td></tr>
  <tr><td>42702</td><td>AMBIGUOUS_COLUMN</td></tr>
  <tr><td>42725</td><td>AMBIGUOUS_FUNCTION</td></tr>
  <tr><td>42P08</td><td>AMBIGUOUS_PARAMETER</td></tr>
  <tr><td>42P09</td><td>AMBIGUOUS_ALIAS</td></tr>
  <tr><td>42P10</td><td>INVALID_COLUMN_REFERENCE</td></tr>
  <tr><td>42611</td><td>INVALID_COLUMN_DEFINITION</td></tr>
  <tr><td>42P11</td><td>INVALID_CURSOR_DEFINITION</td></tr>
  <tr><td>42P12</td><td>INVALID_DATABASE_DEFINITION</td></tr>
  <tr><td>42P13</td><td>INVALID_FUNCTION_DEFINITION</td></tr>
  <tr><td>42P14</td><td>INVALID_PREPARED_STATEMENT_DEFINITION</td></tr>
  <tr><td>42P15</td><td>INVALID_SCHEMA_DEFINITION</td></tr>
  <tr><td>42P16</td><td>INVALID_TABLE_DEFINITION</td></tr>
  <tr><td>42P17</td><td>INVALID_OBJECT_DEFINITION</td></tr>

  <tr><th align="left" colspan="2">Class 44 — WITH CHECK OPTION Violation</th></tr>
  <tr><td>44000</td><td>WITH_CHECK_OPTION_VIOLATION</td></tr>

  <tr><th align="left" colspan="2">Class 53 — Insufficient Resources</th></tr>
  <tr><td>53000</td><td>INSUFFICIENT_RESOURCES</td></tr>
  <tr><td>53100</td><td>DISK_FULL</td></tr>
  <tr><td>53200</td><td>OUT_OF_MEMORY</td></tr>
  <tr><td>53300</td><td>TOO_MANY_CONNECTIONS</td></tr>
  <tr><td>53400</td><td>CONFIGURATION_LIMIT_EXCEEDED</td></tr>

  <tr><th align="left" colspan="2">Class 54 — Program Limit Exceeded</th></tr>
  <tr><td>54000</td><td>PROGRAM_LIMIT_EXCEEDED</td></tr>
  <tr><td>54001</td><td>STATEMENT_TOO_COMPLEX</td></tr>
  <tr><td>54011</td><td>TOO_MANY_COLUMNS</td></tr>
  <tr><td>54023</td><td>TOO_MANY_ARGUMENTS</td></tr>

  <tr><th align="left" colspan="2">Class 55 — Object Not In Prerequisite State</th></tr>
  <tr><td>55000</td><td>OBJECT_NOT_IN_PREREQUISITE_STATE</td></tr>
  <tr><td>55006</td><td>OBJECT_IN_USE</td></tr>
  <tr><td>55P02</td><td>CANT_CHANGE_RUNTIME_PARAM</td></tr>
  <tr><td>55P03</td><td>LOCK_NOT_AVAILABLE</td></tr>

  <tr><th align="left" colspan="2">Class 57 — Operator Intervention</th></tr>
  <tr><td>57000</td><td>OPERATOR_INTERVENTION</td></tr>
  <tr><td>57014</td><td>QUERY_CANCELED</td></tr>
  <tr><td>57P01</td><td>ADMIN_SHUTDOWN</td></tr>
  <tr><td>57P02</td><td>CRASH_SHUTDOWN</td></tr>
  <tr><td>57P03</td><td>CANNOT_CONNECT_NOW</td></tr>
  <tr><td>57P04</td><td>DATABASE_DROPPED</td></tr>

  <tr><th align="left" colspan="2">Class 58 — System Error (errors external to PostgreSQL itself)</th></tr>
  <tr><td>58000</td><td>SYSTEM_ERROR</td></tr>
  <tr><td>58030</td><td>IO_ERROR</td></tr>
  <tr><td>58P01</td><td>UNDEFINED_FILE</td></tr>
  <tr><td>58P02</td><td>DUPLICATE_FILE</td></tr>

  <tr><th align="left" colspan="2">Class F0 — Configuration File Error</th></tr>
  <tr><td>F0000</td><td>CONFIG_FILE_ERROR</td></tr>
  <tr><td>F0001</td><td>LOCK_FILE_EXISTS</td></tr>

  <tr><th align="left" colspan="2">Class HV — Foreign Data Wrapper Error (SQL/MED)</th></tr>
  <tr><td>HV000</td><td>FDW_ERROR</td></tr>
  <tr><td>HV005</td><td>FDW_COLUMN_NAME_NOT_FOUND</td></tr>
  <tr><td>HV002</td><td>FDW_DYNAMIC_PARAMETER_VALUE_NEEDED</td></tr>
  <tr><td>HV010</td><td>FDW_FUNCTION_SEQUENCE_ERROR</td></tr>
  <tr><td>HV021</td><td>FDW_INCONSISTENT_DESCRIPTOR_INFORMATION</td></tr>
  <tr><td>HV024</td><td>FDW_INVALID_ATTRIBUTE_VALUE</td></tr>
  <tr><td>HV007</td><td>FDW_INVALID_COLUMN_NAME</td></tr>
  <tr><td>HV008</td><td>FDW_INVALID_COLUMN_NUMBER</td></tr>
  <tr><td>HV004</td><td>FDW_INVALID_DATA_TYPE</td></tr>
  <tr><td>HV006</td><td>FDW_INVALID_DATA_TYPE_DESCRIPTORS</td></tr>
  <tr><td>HV091</td><td>FDW_INVALID_DESCRIPTOR_FIELD_IDENTIFIER</td></tr>
  <tr><td>HV00B</td><td>FDW_INVALID_HANDLE</td></tr>
  <tr><td>HV00C</td><td>FDW_INVALID_OPTION_INDEX</td></tr>
  <tr><td>HV00D</td><td>FDW_INVALID_OPTION_NAME</td></tr>
  <tr><td>HV090</td><td>FDW_INVALID_STRING_LENGTH_OR_BUFFER_LENGTH</td></tr>
  <tr><td>HV00A</td><td>FDW_INVALID_STRING_FORMAT</td></tr>
  <tr><td>HV009</td><td>FDW_INVALID_USE_OF_NULL_POINTER</td></tr>
  <tr><td>HV014</td><td>FDW_TOO_MANY_HANDLES</td></tr>
  <tr><td>HV001</td><td>FDW_OUT_OF_MEMORY</td></tr>
  <tr><td>HV00P</td><td>FDW_NO_SCHEMAS</td></tr>
  <tr><td>HV00J</td><td>FDW_OPTION_NAME_NOT_FOUND</td></tr>
  <tr><td>HV00K</td><td>FDW_REPLY_HANDLE</td></tr>
  <tr><td>HV00Q</td><td>FDW_SCHEMA_NOT_FOUND</td></tr>
  <tr><td>HV00R</td><td>FDW_TABLE_NOT_FOUND</td></tr>
  <tr><td>HV00L</td><td>FDW_UNABLE_TO_CREATE_EXECUTION</td></tr>
  <tr><td>HV00M</td><td>FDW_UNABLE_TO_CREATE_REPLY</td></tr>
  <tr><td>HV00N</td><td>FDW_UNABLE_TO_ESTABLISH_CONNECTION</td></tr>

  <tr><th align="left" colspan="2">Class P0 — PL/pgSQL Error</th></tr>
  <tr><td>P0000</td><td>PLPGSQL_ERROR</td></tr>
  <tr><td>P0001</td><td>RAISE_EXCEPTION</td></tr>
  <tr><td>P0002</td><td>NO_DATA_FOUND</td></tr>
  <tr><td>P0003</td><td>TOO_MANY_ROWS</td></tr>

  <tr><th align="left" colspan="2">Class XX — Internal Error</th></tr>
  <tr><td>XX000</td><td>INTERNAL_ERROR</td></tr>
  <tr><td>XX001</td><td>DATA_CORRUPTED</td></tr>
  <tr><td>XX002</td><td>INDEX_CORRUPTED</td></tr>
</table>
