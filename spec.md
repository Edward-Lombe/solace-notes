# Spec notes / questions

- How are we going to get their data into our system?
- Sequelize supports migration from MySQL, SQLite, and MSSQL
- The scope of our datastore (should we only use cache's database, how much should postgres for)
    - The respsibilty for the splitting of the datastore
    - Use postrgres to mirror parts of the cache database
