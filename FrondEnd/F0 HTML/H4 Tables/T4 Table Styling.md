## HTML Table - Zebra Stripes
- If you add a background color on every other table row, you will get a nice zebra stripes effect.
![[Screenshot 2024-12-25 115115.png]]
- To style every other table row element, use the `:nth-child(even)` selector like this:
``` css
tr:nth-child(even) {  background-color: #D6EEEE;}
```


## HTML Table - Vertical Zebra Stripes
- To make vertical zebra stripes, style every other _column_, instead of every other _row_.
![[Screenshot 2024-12-25 115115 1.png]]
- Set the `:nth-child(even)` for table data elements like this:
``` css
td:nth-child(even), th:nth-child(even) {  background-color: #D6EEEE;}
```

## Combine Vertical and Horizontal Zebra Stripes
- You can combine the styling from the two examples above and you will have stripes on every other row and every other column.
- If you use a transparent color you will get an overlapping effect.
![[Pasted image 20241225115441.png]]

Use an `rgba()` color to specify the transparency of the color:
``` css

tr:nth-child(even) {  background-color: rgba(150, 212, 212, 0.4);}  
th:nth-child(even),td:nth-child(even) {  background-color: rgba(150, 212, 212, 0.4);}
```

