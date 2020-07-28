# Excel

Check if cells in `B5:B14` are sorted in reverse order (have to all be full or use next example for ascending)

```xlsx
=AND(B5:B13>=B6:B14)
```

Check if full non-empty cells in `G5:G14` are sorted in order

```xlsx
=IF(COUNT(G5:G14)>1,AND(INDIRECT(CONCAT("G5:G",(COUNT(G5:G14)+3)))<=INDIRECT(CONCAT("G6:G",(COUNT(G5:G14)+4)))),TRUE)
```

Check how many rows in `I5:I14` it takes to total more than `H23`, `I4` is the column heading.

```xlsx
=MATCH(TRUE,INDEX(SUMIF(OFFSET($I$4,1,,ROW(I4:I14)-ROW(I4)+1,1),"<>0")>=H23,0),0)
```
