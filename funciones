### Funciones del Código

**A) obtener_precios(inicio: str, fin: str, tickers: pd.DataFrame, with_benchmark: bool) -> pd.DataFrame:**

Esta función obtienen los precios de una lista de instrumentos financieros  

Insumos:
1) inicio. fecha del primer día en que se obtendra la informacion. Debe ser un dato tipo string en formato YYYY-MM=DD.
Nota: Dado que el primer dia se pierde al sacar rendimientos, se sugiere comenzar con un día previo
        
2) fin. fecha del ultimo dia en que se obtendra la informacion. Debe ser un dato tipo string en formato YYYY-MM=DD,
o en su defecto, puede ser texto que diga "hoy" o "today"
    
3) tickers. de los instrumentos de los que se quiere obtener los precios de cierre. Debe ser una columna de
un pd.Dataframe. La función lo pasa a lista
    
4) with_benchmark. declarar si queremos agregar el benchmark del mercado. Es una variable booleana. 
El benchmark que se agrega es el valor del índice S&P 500 (^GSPC)
    
Resultado:
Un pd.DataFrame con los precios de los instrumentos financieros seleccionados y en la fecha indicada

<br>


---

**B) rendimiento_acumulado(tabla: pd.DataFrame) -> pd.DataFrame:**

Esta función realiza las operaciones necesarias para calcular el rendimiento diario de 
los instrumentos financieros y los suma para conocer el rendimiento acumulado 
    
Insumos:
1) tabla con los precios de los instrumentos. Debe ser un pd.DataFrame
    
Resultado:
Un pd.DataFrame con los precios en porcentaje

<br>


---
    
**C) grafica_barras_h(tabla: pd.DataFrame, ordenar_rendimientos: bool, descargar_img: bool, titulo: str, subtitulo: str):**

Esta función abarca los procedimientos necesarios para mostrar una gráfica de barras horizontales.
En este caso, la grafica va a mostrar el desempeño de los sectores del S&P 500 
    
Insumos:
1) tabla con el rendimiento de los sectores del S&P 500. Debe ser un pd.DataFrame

2) ordenar_rendimientos. declarar si queremos la gráfica ordenada de mayor a menor rendimiento. 
Es una variable booleana.

3) descargar_img. declarar si queremos descargar la gráfica. Los parámetros están al final de la función. 
Es una variable booleana.

4) titulo. texto que se muestra como título de la gráfica. En este espacio se puede poner la fecha 
en que se trae los datos, como YTD, trimestral o mensual. Debe ser un dato tipo string

5) subtitulo. texto que se muestra como el subtítulo de la gráfica. Debe ser un dato tipo string
        
Resultado:
Gráfica de barras horizontales que muestra el desempeño de los sectores  del S&P 500

<br>


---
    
**D) lista_colores(tabla: pd.DataFrame) -> list:**

Esta función complementa al proceso de creación de la gráfica de barras horizontal.
Esta función determina si los rendimientos son positivos o negativos, y crea una lista de colores para mostrar en la gráfica 
    
Insumos:
1) tabla con el rendimiento de los sectores del S&P 500. Debe ser un pd.DataFrame
        
Resultado:
Lista con el color que le corresponde a cada rendimiento

<br>


---
    
**E) grafica_lineas(tabla: pd.DataFrame, descargar_img: bool, titulo: str, subtitulo: str):**

Esta función realiza los procedimientos necesarios para mostrar una gráfica de líneas
    
Insumos:
1) tabla con el rendimiento de los activos financieros. Debe ser un pd.DataFrame

2) descargar_img. declarar si queremos descargar la gráfica. Los parámetros están al final de la función. 
Es una variable booleana.

3) titulo. texto que se muestra como título de la gráfica. En este espacio se puede poner la fecha 
en que se trae los datos, como YTD, trimestral o mensual. Debe ser un dato tipo string

4) subtitulo. texto que se muestra como el subtítulo de la gráfica. Debe ser un dato tipo string
        
Resultado:
Grafica de líneas que muestra el desempeño de los instrumentos financieros seleccionados

<br>


---
    
**F) mapa_termico_correlaciones(tabla: pd.DataFrame, tipo: str):**

Esta función realiza los procedimientos necesarios para mostrar una gráfica con los coeficientes de correlación de Pearson
    
Insumos:
1) tabla con el rendimiento de los instrumentos financieros. Debe ser un pd.DataFrame

2) tipo. Definimos el formato del rango de colores que muestra el mapa térmico. Algunas opciones son: seismic, RdBu, bwr.
Es un dato tipo str.
        
Resultado:
Gráfica con el coeficiente de correlación de Pearson de los instrumentos financieros

<br>


---

**G) sharpe_ratio(tabla: pd.DataFrame) -> pd.DataFrame:**

Esta función realiza los procedimientos correspondientes para calcular el Sharpe Ratio, lo cual incluye:
    a) rendimiento promedio diario de la muestra
    b) desviación estándar muestral
    c) Sharpe Ratio al periodo y anualizado     
    
Insumos:
1) tabla con el precio de los instrumentos financieros seleccionados. Debe ser un pd.DataFrame.
        
Resultado:
Tabla con el resumen de los valores para cada instrumento financiero 

<br>


---

**H) risk_free_rate(tabla: pd.DataFrame) -> pd.Series:**

Con esta función se obtiene el valor de los bonos del tesoro de EEUU a 10 años.
(en yahoo el símbolo es: ^TNX) (como referencia, ver la pág de la CNBC: "U.S. 10 Year Treasury")  

Para mantener el sentido de las fechas, el primer dia en que se obtiene el valor va a ser el mismo al declarado
al usar la función de la tabla de precios

Insumos:
1) tabla con índice de fechas
    
Resultado:
Valor de la tasa libre de riesgo promedio a la fecha indicada

<br>


---

**I) sortino_ratio(tabla: pd.DataFrame) -> pd.DataFrame:**

Esta función realiza los procedimientos correspondientes para calcular el Sortino Ratio, lo cual incluye:
    a) tasa libre de riesgo diaria
    b) rendimiento promedio diario
    c) rendimiento mínimamente aceptable o MAR (minimum acceptable return)
    d) rendimiento negativo
    e) desviación estandar ajustado
    f) Sharpe Ratio al periodo y anualizado     
    
Insumos:
1) tabla con el precio de los instrumentos financieros seleccionados. Debe ser un pd.DataFrame.
        
Resultado:
Tabla con el resumen de los valores para cada instrumento financiero 

<br>


---
    
**J) moving_average(tabla, sma: list, ema: list):**

Esta función realiza los cálculos correspondientes para graficar tanto el  
SMA (Simple Moving Average) como el EMA (Exponential Moving Average)
    
Insumos:
1) tabla con el precio de los instrumentos financieros seleccionados. Debe ser un pd.DataFrame
        
2) sma. Es una lista con la cantidad de días en que calcula el SMA (ventana temporal). 
Es una estructura de datos tipo lista
        
3) ema. Es una lista con la cantidad de días en que calcula el EMA (ventana temporal)
Es una estructura de datos tipo lista
        
Resultado:
Tabla original junto con los datos de las medias móviles para graficar

<br>


---
