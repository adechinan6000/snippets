## Remove parent row jquery


* HTML

```bash
<table>
  <tr>
    <td>row 1, cell 1</td>
    <td><img class="delete" src="del.gif" /></td>
  </tr>
  <tr>
    <td>row 2, cell 1</td>
    <td><img class="delete" src="del.gif" /></td>
  </tr>
</table>
```

* JQUERY

```bash
$('table td img.delete').click(function(){
    $(this).parent().parent().remove();
});
```