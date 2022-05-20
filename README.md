# prueba_tecnica
 1.	Generar un dataset que agrupe por item y mes, desde enero 2020 a enero 2022, la cantidad total de ventas en kilos. 

 Para lo solución del punto, se subio el archivo a Google colabority en el archivo de Datos_de_DataUp.ipynb, al leerlo se muestra un archivo que debe ser depurado con fines práctica para poder realizar un manejo mas practico de la información contenida en el documento. Para esto se eliminan algunas columnas y filas, también se renombran las columnas, al finas se cambie el type de dato para las columnas de Venta_Neta_Kilos y Venta_Neta_ME de object a float, esto con fin de poder verificar que ninguna de las ventas sea negativa. 
Por ultimo se utiliza la sentencia de código:
Datosventas_Kilos = Datosventas.groupby(['Mes','Código_Material']).Venta_Neta_Kilos.sum().reset_index(name ='Venta_Neta_Kilos')
Con la cual se agrupa los datos por Mes y Código_Material y se suma la columna Venta_Neta_Kilos


 2.	Generar un dataset con el máximo, mínimo y promedio de venta en dinero por cada item desde enero 2021 a diciembre 2021.    

 Para generar este dataset primero se agrega una columna al dataframe llamada fecha que se extrae de la columna Mes esto con el fin de que esta columna luego se convierta en Index del dataframe, ya que con esta es más fácil extraer los datos correspondientes al año 2021, con esto lidto se generan tres dataset que contienen el mínimo, el máximo y el promedio de las ventas.
 
Luego se hace una unión al para que todos los todos estén en un solo dataframe.


 3.	Generar un pronóstico de ventas en kilos por cada item para el mes en curso: febrero 2022. El modelo o técnica de pronóstico es de libre elección, puede ser tan simple o avanzado como se prefiera.

 Desarrollo:
Para este punto se realizaron varios ensayos, utilizando diferentes técnicas como lo son las redes neuronales y regresiones lineales, con las redes neuronales se intento hacer uso de las redes neuronales recurrentes, pero no se obtuvo un resultado muy satisfactorio, al igual que con algunas redes densas no se logró una buena estimación, aunque siento que por este medio se puede lograr el tiempo no da para realizarlo. Por ende, el modelo que más se ajusto fue una regresión lineal múltiple, que utiliza como valores de entrada el mes y las ventas, esto de cada código de material y de salida la venta neta en kilos, el archivo:

1.	DataUp_modelo_lineal_Multiplescodigos.ipynb halla la predicción para todos lo códigos de material
2.	DataUp_modelo_lineal.ipynb muestra el proceso que realiza DataUp_modelo_lineal_Multiplescodigos.ipynb pero solo para un código de material que este caso seria 1003861


Nota: ambos archivos se ejecutan con el archivo Datosventas_1.xlsx que se guarda al ejecutar el archivo Datos_de_DataUp.ipynb que este a su ves necesita del archivo ventas_nuevas.xlsx proporcionado por la empresa.


Nota 2: El archivo Datos_de_DataUp.ipynb también genera otros archivos como lo son:
Datosventas_kilos.xlsx correspondiente al dataset del punto 1
Datosventas_min_max_mean.xlsx correspondiente al punto 2
Datosventas.xlsx que es un archivo el cual contiene los datos depurados de Datos_nuevas.xlsx

