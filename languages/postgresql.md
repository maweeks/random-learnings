# Postgresql

Check if key exists in a json field for each record.

```sql
SELECT jsonField FROM tableName WHERE jsonField->>'jsonKey' IS NOT NULL
```
