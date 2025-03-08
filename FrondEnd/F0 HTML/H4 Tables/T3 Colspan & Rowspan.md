## HTML Table - Colspan
- To make a cell span over multiple columns, use the `colspan` attribute:
``` html

<table>  
  <tr>  
    <th colspan="2">Name</th>   <!-- Name take two colums to span-->
    <th>Age</th>  
  </tr>  
  <tr>  
    <td>Jill</td>  
    <td>Smith</td>  
    <td>43</td>  
  </tr>  
  <tr>  
    <td>Eve</td>  
    <td>Jackson</td>  
    <td>57</td>  
  </tr>  
</table>

```

## HTML Table - Rowspan
- To make a cell span over multiple rows, use the `rowspan` attribute:
``` html
<table>  
  <tr>  
    <th>Name</th>  
    <td>Jill</td>  
  </tr>  
  <tr>  
    <th rowspan="2">Phone</th>  <!-- Phone take 2 row to span -->
    <td>555-1234</td>  
  </tr>  
  <tr>  
    <td>555-8745</td>  
</tr>  
</table>
```

