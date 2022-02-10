# Postgresql

Check if key exists in a json field for each record.

```sql
SELECT jsonField FROM tableName WHERE jsonField->>'jsonKey' IS NOT NULL
```

Check index stats

```sql
SELECT * FROM pg_stat_all_indexes;
SELECT * FROM pg_statio_all_indexes;
```
