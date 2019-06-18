# Make an HTML table display vertically

### HTML
```HTML
<table class="vertical-table">
    <tbody>
        <tr>
            <th>Monday</th>
            <th>Tuesday</th>
            <th>Wednesday</th>
            <th>Thursday</th>
            <th>Friday</th>
            <th>Saturday</th>
            <th>Sunday</th>
        </tr>
        <tr>
            <td>8h00 to 17h00</td>
            <td>8h00 to 17h00</td>
            <td>8h00 to 17h00</td>
            <td>10h00 to 21h00</td>
            <td>12h00 to 17h00</td>
            <td>Closed</td>
            <td>Closed</td>
        </tr>
    </tbody>
</table>
```

### CSS
```CSS
.vertical-table>tbody>tr{
  display: block;
  float: left;
}

.vertical-table>tbody>tr>th, .vertical-table>tbody>tr>td {
  display: block;
}
```

### Result
<html>
<head>
</head>
<body>
<table style="display:block;float:left;">
        <tbody>
            <tr style="display:block;float:left;">
                <th style="display: block;">Monday</th>
                <th style="display: block;">Tuesday</th>
                <th style="display: block;">Wednesday</th>
                <th style="display: block;">Thursday</th>
                <th style="display: block;">Friday</th>
                <th style="display: block;">Saturday</th>
                <th style="display: block;">Sunday</th>
            </tr>
            <tr style="display:block;float:left;">
                <td style="display: block;">8h00 to 17h00</td>
                <td style="display: block;">8h00 to 17h00</td>
                <td style="display: block;">8h00 to 17h00</td>
                <td style="display: block;">10h00 to 21h00</td>
                <td style="display: block;">12h00 to 17h00</td>
                <td style="display: block;">Closed</td>
                <td style="display: block;">Closed</td>
            </tr>
        </tbody>
    </table>
</body>
