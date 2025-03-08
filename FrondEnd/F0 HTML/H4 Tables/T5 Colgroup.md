## HTML Table Colgroup
- If you want to style the two first columns of a table, use the `<colgroup>` and `<col>` elements.
![[Pasted image 20241225115920.png]]
The `<colgroup>` element should be used as a container for the column specifications.
Each group is specified with a `<col>` element.
The `span` attribute specifies how many columns that get the style.
The `style` attribute specifies the style to give the columns.
===> **Note:** There is a very limited selection of [legal CSS properties for colgroups](https://www.w3schools.com/html/html_table_colgroup.asp#legalcss).

### Example
``` html
<table>  
  <colgroup>  
    <col span="2" style="background-color: #D6EEEE">  
  </colgroup>  
  <tr>  
    <th>MON</th>  
    <th>TUE</th>  
    <th>WED</th>  
    <th>THU</th>  
...
```
