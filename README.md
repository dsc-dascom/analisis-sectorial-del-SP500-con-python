#  **Análisis sectorial del S&P 500** 📊

  **El [índice Standard & Poor's 500 (S&P 500)](https://es.wikipedia.org/wiki/S%26P_500)**, junto con el Nasdaq y el Dow Jones, es uno de los índices bursátiles más importantes y representativos de la situación del mercado accionario de Estados Unidos. Este índice está compuesto por 500 empresas de gran capitalización que están clasificadas en [11 sectores](https://en.wikipedia.org/wiki/Global_Industry_Classification_Standard) de acuerdo a la principal operación comercial de las empresas.

Uno puede consultar el valor del S&P 500 como [índice](https://www.santander.com/es/stories/que-son-los-indices-bursatiles-y-para-que-sirven) o su precio como [ETF](https://economipedia.com/definiciones/etf-fondos-cotizados.html), con la diferencia de que sólo se puede comprar/invertir en el ETF del S&P 500, el cual replica el comportamiento del índice. Algunos ETF que siguen el comportamiento del *benchmark* son [$SPY de SSGA](https://www.investopedia.com/articles/investing/122215/spy-spdr-sp-500-trust-etf.asp) o [$VOO de Vanguard](https://investor.vanguard.com/investment-products/etfs/profile/voo).

De igual forma, existen ETFs que siguen el comportamiento de los sectores dentro del S&P 500. Para este trabajo, solo voy a nombrar a los [SPDR ETFs](https://www.sectorspdrs.com/).

El nombre de los sectores y su [Ticker](https://economipedia.com/definiciones/simbolo-ticker.html) son los siguientes:

1. Communication Services (Servicios de comunicación) — XLC
2. Consumer Discretionary (Consumo discrecional) — XLY
3. Consumer Staples (Consumo básico) — XLP
4. Energy (Energía) — XLE
5. Financials (Finanzas) — XLF
6. Health Care (Salud) — XLV
7. Industrials (Industria) — XLI
8. Materials (Materiales) — XLB
9. Real Estate (Bienes raíces) — XLRE
10. Technology (Tecnología de la información) — XLK
11. Utilities (Servicios públicos) — XLU

Dentro de estos sectores podemos encontrar algunas de las empresas más grandes y reconocidas del mundo, como lo es Alphabet Inc. (GOOGL) y Meta Platforms Inc. (META), los cuales están dentro de Servicios de comunicación — XLC; Amazon.com Inc. (AMZN) y Tesla Inc. (TSLA), que se encuentran en Consumo discrecional — XLY: Apple Inc. (AAPL), Microsoft Corp. (MSFT), y NVIDIA Corp. (NVDA), que se encuentran en el sector de Tecnología — XLK, entre otros muchos ejemplos.

<br>

Aunque una estrategia de inversión consiste en mantener una inversión diversificada, en algunas ocasiones los sectores del mercado presentan mejores oportunidades de inversión que el mercado en general, o incluso algunas acciones individuales dentro de un sector pueden llegar a representar una mejor inversión que todo el conjunto. Pero la tarea de encontrar acciones cuyos precios llegan a tener rendimientos tanto por encima o por debajo del rendimiento del mercado, se vuelve complicada al tener 500 empresas. Es por esto que comenzar con el análisis sectorial del S&P 500, puede permitir reconocer tendencias a un nivel intermedio; no general como el índice, ni particular como una acción individual. Entonces, al analizar un sector, se puede tener una mejor visión del movimiento del mercado accionario estadounidense, para posteriormente analizar el sector y ver qué acciones presentan comportamientos atípicos (*outliers*). 

De esta forma, el presente código tiene como objetivo servir como una herramienta de análisis de los sectores del mercado, con la posibilidad de calcular tanto el rendimiento en un periodo dado de los ETF y acciones, así como calcular el Sharpe Ratio y el Sortino Ratio, indicadores financieros que brindan más información de la relación riesgo-beneficio de un instrumento financiero. Además, entre las funciones del código se puede calcular las medias móviles (SMA y EMA), indicadores técnicos básicos que se utilizan para identificar tendencias y posibles señales de compra/venta. Finalmente, como complemento para el análisis sectorial, se puede graficar un mapa térmico de correlaciones.

En conclusión, esta herramienta tiene la intención de servir como un radar o monitor del mercado accionario, que junto con algunas funciones, proporciona información sobre el comportamiento de un instrumento financiero y proporcionar información para mejorar la toma de decisiones al momento de invertir.

<br>

*Nota: El ambiente de programación utilizado para este trabajo fue Jupyter Notebook.*

---

Ejemplo de una gráfica generada con el código: Rendimiento en lo que val del año del S&P 500 $SPY y del Nasdaq-100 $QQQ

<p align="center">
  <img width="4200" height="2600" alt="grafica_lineas" src="https://github.com/user-attachments/assets/69b46dbd-fa79-4a8b-a105-5c5fd9ef4db0" />

</p>


---

# **Funciones del Código**   :open_file_folder:
Este  código está compuesto por tres secciones. En la primera sección se muestra el rendimiento de los ETFs del S&P 500 con una gráfica de barras horizontales. En la sección dos se carga una lista con información de las empresas que conforman el benchmark, para posteriormente seleccionar un sector y visualizar las acciones dentro del mismo de forma dinámica (con la ayuda de una gráfica en plotly). En la tercera sección se encuentran las funciones que permiten el desarrollo del código de manera ordenada, parametrizada y ajustable.  

Para un buen funcionamiento del código, primero se deben importar las librerías y posteriormente correr la tercera sección del código que corresponde a las funciones. 

<br>

A) obtener_precios()

B) rendimiento_acumulado()
    
C) grafica_barras_h()
    
D) lista_colores()
    
E) grafica_lineas()
    
F) mapa_termico_correlaciones()
    
G) sharpe_ratio()
    
H) risk_free_rate()
    
I) sortino_ratio()
    
J) moving_average()

Dado que las funciones son 
<br>

---

# **Video de apoyo** 

De forma complementaria, en youtube he subido un video en el que muestro y explico algunos ejemplos del uso que se le puede dar a este cóodigo.
El video lo pueden consultar [aquí]()

<br>

---

# **Redes Sociales** 🌐
A continuación dejo los enlaces a mi página de LinkedIn y a mi canal de Youtube donde tengo otros proyectos con Python y VBA:

<br>

<p align="center">
  <a href="https://www.linkedin.com/in/daniel-salmoran">
    <img src="https://github.com/user-attachments/assets/b944e977-6ca1-44e5-b7b5-631e19a4f4ba" alt="linkedin_page" width="450">
  </a>
</p>

<br>

<p align="center">
  <a href="https://www.youtube.com/@dsc-econ">
    <img src="https://github.com/user-attachments/assets/ea03e075-5617-4d87-a1a1-09d49854da74" alt="canal_youtube" width="450">
  </a>
</p>

<br>

---

