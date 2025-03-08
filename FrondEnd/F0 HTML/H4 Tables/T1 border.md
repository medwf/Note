HTML tables can have borders of different styles and shapes.
## How To Add a Border
- To add a border, use the CSS `border` property on `table`, `th`, and `td` elements:
![[Screenshot 2024-12-25 112753.png]]
``` css
table, th, td {  border: 1px solid black;}
```

## Collapsed Table Borders
- To avoid having double borders like in the example above, set the CSS `border-collapse` property to `collapse`.
- This will make the borders collapse into a single border:
![[Screenshot 2024-12-25 113056.png]]
``` css
table, th, td {
  border: 1px solid black;  
  border-collapse: collapse;
}
```

==> you can manage border-radius or color by yourself.
