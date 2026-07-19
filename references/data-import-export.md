# Data Import And Export Standards

Use for CSV, Excel, JSON, XML, PDFs, bulk imports, exports, migrations, reports, and user data portability.

- Parse defensively and validate before writing.
- Support partial failure reporting for bulk operations.
- Make imports idempotent or deduplicated when rerun.
- Bound file sizes, row counts, memory use, and processing time.
- Exports must enforce permissions and avoid leaking private data.

Review smells: import writes before validation, no row-level error report, unbounded file load into memory, export missing authz, formula injection in CSV.
