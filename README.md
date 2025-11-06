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

<p align="center">
  <img alt="imag_mag7" src="https://github.com/user-attachments/assets/45a57fab-f9a4-46f1-a5dc-2e35fd23fd1d" />

</p>

---

<br>

#  **Objetivo de este proyecto** 🎯
Aunque una estrategia de inversión consiste en mantener una inversión diversificada, en algunas ocasiones los sectores del mercado representan mejores oportunidades de inversión que el mercado en general, o incluso algunas acciones individuales dentro de un sector pueden llegar a ser una mejor inversión que todo el conjunto. Pero la tarea de encontrar acciones cuyos precios llegan a tener comportamientos distintos al del mercado, se vuelve complicada al tener 500 empresas. Es por esto que comenzar con el análisis sectorial del S&P 500, se puede reconocer tendencias a un nivel intermedio; no general como el índice, ni particular como una acción individual.

De esta forma, el presente código tiene como objetivo servir como una herramienta de análisis de los sectores del mercado, con la posibilidad de calcular tanto el rendimiento en un periodo dado de los ETF y acciones, así como calcular el [Sharpe Ratio](https://www.investopedia.com/terms/s/sharperatio.asp) y el [Sortino Ratio](https://www.investopedia.com/terms/s/sortinoratio.asp), indicadores que brindan más información de la relación riesgo-beneficio de un instrumento financiero. Además, entre las funciones del código se puede calcular las medias móviles ([SMA](https://www.investopedia.com/terms/s/sma.asp) y [EMA](https://www.investopedia.com/terms/e/ema.asp)), indicadores técnicos básicos que se utilizan para identificar tendencias y posibles señales de compra/venta. Finalmente, como complemento para el análisis sectorial, se puede graficar un [mapa térmico de correlaciones](https://www.probabilidadyestadistica.net/matriz-de-correlacion/).

En conclusión, esta herramienta tiene la intención de servir como un radar o monitor del mercado accionario, que junto con algunas funciones, proporciona información sobre el comportamiento de un instrumento financiero y da información para mejorar la toma de decisiones al momento de invertir.

<br>

Ejemplo de una gráfica generada con el código.

Rendimiento en lo que val del año del S&P 500 $SPY y del Nasdaq-100 $QQQ

<p align="center">
  <img width="4200" height="2600" alt="grafica_linea_mercado" src="https://github.com/user-attachments/assets/69b46dbd-fa79-4a8b-a105-5c5fd9ef4db0" />

</p>

---

<br>

# **Estrucutra del Código**   :open_file_folder:
Este  código está compuesto por tres secciones. 

Sección 1. En esta parte se puede visualizar, en una gráfica de barras horizontales, el rendimiento del mercado ([S&P 500](https://finance.yahoo.com/quote/%5EGSPC/)) junto con el comportamiento de los [11 sectores del SPDR ETFs](https://www.sectorspdrs.com/) en que se clasifican a las empresas. Sin embargo, también se puede visualizar el comportamiento de los sectores con una gráfica de líneas haciendo uso de la función correspondiente. Otra característica de esta sección es que se puede crear un mapa térmico de correlaciones de Pearson, el cual permite conocer la relación que guardan cada sector con el *benchmark*. Ejemplo de la gráfica generada:

<p align="center">
  <img width="450" alt="picture1" src="https://github.com/user-attachments/assets/079102f7-8d8d-4a25-b219-f9b4e953e014" />

</p>
<br>

Sección 2. Aquí se empieza cargando una [tabla de información](https://en.wikipedia.org/wiki/List_of_S%26P_500_companies) de las empresas que componen al índice, para posteriormente seleccionar y filtrar las empresas de un sector y visualizar las acciones en un gráfica de líneas. La visualización de esta gráfica es dinámica ya que se utiliza la librería de plotly. Una vez se tiene identificado el sector y sus componentes, se puede calcular el Sharpe ratio y el Sortino Ratio para conocer cuánto rendimiento obtenemos por cada unidad de riesgo que asumimos, en el caso del Sharpe Ratio. Después de identificar las acciones con mayor rendimiento o con el Sharpe/Sortino Ratio más alto, podemos volver a grafica las empresas que nos interesan para hacer más un análisis más refinado. 
Ejemplo de la gráfica generada sobre el sector de Energía:

<p align="center">
  <img width="4200" height="2600" alt="picture2" src="https://github.com/user-attachments/assets/217f58ce-2ffc-4142-84b7-8ef1afe60d18" />

</p>

<br>

Gráfica de las empresas con mejor desempeño dentro del sector Energía:

<p align="center">
  <img width="4200" height="2600" alt="picture3" src="https://github.com/user-attachments/assets/69a724ab-a91a-4b1b-808c-f69ed500c062" />

</p>

<br>

Dentro del código agregué dos apartados extras con los que pretendía dar más ejemplos del uso que se le puede dar a las funciones. El primer exrtra es un portafolio compuesto por las empresas que conforman al grupo de las [MAG7](https://www.investing.com/academy/stocks/magnificent-seven-stocks/): Apple Inc. (AAPL), Microsoft Corp. (MSFT), Amazon.com Inc. (AMZN), Alphabet Inc. (GOOGL), NVIDIA Corp. (NVDA), Tesla Inc. (TSLA), Meta Platforms Inc. (META). Se puede ejecutar las mismas funciones anteriormente mencionadas sobre este grupo o si es cualquier otra combinación de instrumentos financieros. Ejemplo de la gráfica generada:

<p align="center">
  <img width="4200" height="2600" alt="picture4" src="https://github.com/user-attachments/assets/3e2c9dc6-c76d-4176-9ec3-2fc02db6feab" />

</p>

<br>

En el segundo procedimiento extra del código, utilizo la acción de Reddit $RDDT para ejemplificar el uso de la función que permite calcular las medias móviles: SMA y EMA. Estos indicadores técnicos son básicos para identificar las tendencias en los precios de una acción (o acciones) a lo largo del tiempo. Según sea el dato de los días en que se calculan estos valores, se agregan a la gráfica y se puede interactuar con ellos gracias a la gráfica de líneas en PLOTLY. Ejemplo de la gráfica generada:

<p align="center">
  <img width="4200" height="2600" alt="picture5" src="https://github.com/user-attachments/assets/9799d91f-d4d2-49d5-b816-77b3a85a4355" />

</p>

<br>

Sección 3. En la tercera sección se encuentran las funciones que permiten el desarrollo del código de manera ordenada, parametrizada y ajustable. En orden de aparición en el código, las funciones utilizadas son las siguientes: 

Se puede revisar las fucniones de este trabajo con mejor detalle [aquí](https://github.com/dsc-dascom/analisis-sectorial-del-SP500/blob/main/funciones.md)

**Para un buen funcionamiento del código, primero se deben importar las librerías y posteriormente correr la tercera sección del código que corresponde a las funciones. **


*Nota: El ambiente de programación utilizado para este trabajo fue Jupyter Notebook.*

---

<br>

# **Video de Ejemplo** 💻

De forma complementaria, en youtube he subido un video en el que muestro y explico algunos ejemplos del uso que se le puede dar a este código.
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

