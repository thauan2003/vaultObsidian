Formas de utilizar códigos CSS no meu arquivo html:
1. <span style="color:rgb(112, 48, 160)">Inline: </span>
```
<p style="color:green; font-size:24px;">aaaa</p>
```

2. <span style="color:rgb(112, 48, 160)">InHead</span>
```
<head>

<style>
p{ color:green; 
   font-size:24px;
}
</style>

</head>
```

3. <span style="color:rgb(112, 48, 160)">Externo</span>
```
-No HTML
<head>
<link rel="stylesheet" href="style.css">
</head>

-no arquivo .css
.destaque{
	color: green;
	font-size:24px;
}

#titulo-principal{
..
}
```

