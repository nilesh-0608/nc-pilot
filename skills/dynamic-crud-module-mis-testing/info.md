# Dynamic CRUD Module MIS Testing — settings

Inputs the agent uses to test a CRUD module. Fill what you know; blank fields are discovered
at runtime or asked about. Use a **test/staging** environment.

> The agent marks created records with a `QA_` prefix and only deletes records it created.
> It never touches real/pre-existing data without asking. Keep Ask Permission mode on so the
> Delete confirm is gated.

## Target module

- `moduleName`:             <!-- e.g. Products, Users, Vendors -->
- `moduleUrl`:              <!-- path/URL of the module list, e.g. /admin/products -->
- `uniqueField`:            <!-- label/column used to find the row later, e.g. Name / Code / Email -->

## Test data (Create)

<!-- Field label → value. Leave blank to auto-generate marked test values per field type. -->

- `create`:
  - Name: QA_Test Item
  - Code:
  - Email:
  - <field>:

## Update data

<!-- Field label → new value for the Update step. Blank = append "_edited" to a text field. -->

- `update`:
  - Name: QA_Test Item (edited)
  - <field>:

## Run options

- `cleanup`:                <!-- yes = delete the test record at the end; no = leave it -->
- `environment`:            <!-- staging / test / production (production warns first) -->
- `stopOnFirstFail`:        <!-- yes / no; default no (run all CRUD steps, report each) -->

## Notes for the agent

<!-- Fields to skip, special formats, how to open Add/Edit/Delete if non-standard,
     search/filter usage, what NOT to delete. -->
