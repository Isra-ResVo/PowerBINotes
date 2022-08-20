## Replacing multiple characters

Para modificar/borrar múltiples caracteres se tiene que primero crear una lista de ellos. Esto se hace con el siguiente comando:
```
= Text.ToList("',[]") # donde los elementos entre comillas son los elementos a reemplazar
```
Luego utilizamos esta lista creada, esto por meido del nombre que se assigna la ventana de la derecha de Power BI, para eliminar los caracteres en la tabla de nuestra elección, la sintaxis es la siguiente:
```
= List.Accumulate(Vals2Lisst, #"Removed Other Columns", (table, old)=>Table.ReplaceValue(table,old,"",Replacer.ReplaceText,{"Job Skills"}))
```

Donde:
`Vals2Lisst` es el nombre de lista creada previamente
`#"Removed` other columns" es tabla que se va a modificar, como se puede ver esta puede ser el resultado de una transformación de la talba source,
`table,  old`, son variables de nuetra funcion lambda y,
`{"Job Skills"}` es/son la/s columnas donde este procedimiento se llevará acabo, los demás son valores son parte de la función.

This informatin was take from [here](https://www.youtube.com/watch?v=N-0JrYQB0Ag)