# Numbers

Conditional formatting based on cell value formula.

1. Add a new column (B) next to the column (A) to be highlighted and use the following formula (this highlights weekends)

   ```numbers
   =IF(LEFT(DAYNAME($A2),1)="S",$A2,"")
   ```

2. Add conditional formatting for A2 to highlight if it is =B2
3. Select column (A) and merge conditional formatting rules
4. Hide the extra column (B)
