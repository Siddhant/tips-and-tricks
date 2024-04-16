# Foreign keys
## Self-referencing foreign keys
- SQLite allows self-referencing foreign keys.
- SQLite won't allow you to drop a table containing a self-referencing foreign key, especially if you have the `on delete restrict` clause. When trying to drop the table, it throws this error: `Runtime error: FOREIGN KEY constraint failed (19)`. To overcome this error, the trick is to switch off foreign key pgrama (`pragma foreign_keys = on;`), drop the table, and then re-enable it (`pragma foreign_keys = on;`).
