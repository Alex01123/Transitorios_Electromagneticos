# Marco Teórico: Corriente de Arranque de Transformadores

La **corriente de arranque** o **corriente de irrupción** (*inrush current*) en transformadores es un fenómeno transitorio que se presenta al energizar el equipo desde vacío. Se caracteriza por la circulación de corrientes de gran magnitud, típicamente entre **5 y 15 veces la corriente nominal**, y de corta duración, aunque con formas de onda altamente distorsionadas [1]–[3].

---

## 1. Origen del fenómeno

El origen de la corriente de arranque está asociado a la **saturación del núcleo magnético**. Al cerrar el interruptor, el flujo magnético instantáneo impuesto por la tensión aplicada puede no coincidir con el flujo remanente en el núcleo. Si el valor requerido supera la zona lineal de la característica de magnetización, el núcleo entra en saturación y la inductancia magnetizante disminuye drásticamente, lo que permite el paso de corrientes elevadas [2], [4].

La relación entre el flujo $\phi$ y la tensión aplicada se expresa como:

$$
\phi(t) = \frac{1}{N} \int v(t)\, dt
$$

donde:

- $N$ es el número de espiras,
- $v(t)$ es la tensión aplicada.  

La asimetría entre el flujo inicial y el flujo impuesto genera un **desplazamiento del punto de operación en la curva de magnetización**, aumentando la probabilidad de saturación.

📌 **Curva de magnetización** (ejemplo):  
![Curva de magnetización](https://upload.wikimedia.org/wikipedia/commons/a/a7/Magnetization_curves.svg)

---

## 2. Factores que influyen en la magnitud de la corriente de irrupción

La intensidad y duración de este transitorio dependen de varios factores [3], [5]:

- **Instante de cierre del interruptor**: el cierre cerca del cruce por cero de la tensión es la condición más desfavorable.  
- **Flujo residual en el núcleo**: incrementa la probabilidad de alcanzar saturación extrema.  
- **Impedancia de la red de alimentación**: una fuente rígida permite corrientes de mayor magnitud.  
- **Diseño del transformador**: reactancia de magnetización, pérdidas y características del núcleo.  
- **Grupo de conexión**: afecta la circulación de corrientes homopolares y el reparto entre fases.  

---

## 3. Características de la corriente de arranque

- **Amplitud elevada**: en transformadores de potencia puede superar 10 veces la corriente nominal.  
- **Forma de onda no sinusoidal**: con fuerte componente de continua y armónicos de bajo orden, principalmente el segundo armónico.  
- **Duración limitada**: su decaimiento se debe a las pérdidas en el núcleo y en los devanados, así como a la amortiguación por la impedancia de la red.  

📌 **Forma de onda de inrush** (ejemplo animado):  
![Inrush de transformador](https://upload.wikimedia.org/wikipedia/commons/e/ed/Power_Transformer_Inrush_Current.gif)

---

## 4. Análisis espectral y protección

El análisis mediante **transformada rápida de Fourier (FFT)** muestra que la corriente de arranque presenta un contenido armónico característico, con predominio del **segundo armónico** [4], [6].  

Esta propiedad es utilizada en las **protecciones diferenciales** de transformadores para discriminar entre una falla interna y un fenómeno de *inrush*, evitando disparos intempestivos.

📌 **Espectro armónico (ejemplo ilustrativo)**:  
![Espectro armónico](https://upload.wikimedia.org/wikipedia/commons/b/b7/Harmonic_spectra_theoretical_x_y.png?20121231110728)

---

## 5. Representación en simulaciones EMT

Para estudios en programas como **EMTP, PSCAD o PowerFactory**, el transformador debe modelarse con su **característica de saturación no lineal** [4], [6].  

Existen dos enfoques principales:

- **Curva lineal por tramos**: simplificación que aproxima la pendiente en la zona lineal y en saturación.  
- **Modelo polinomial de saturación**: más preciso, permite ajustar el comportamiento real mediante un factor de saturación $k_{sat}$.  

📌 **Curvas de histéresis (ejemplo ilustrativo del núcleo)**:  
![Curvas de histéresis](https://upload.wikimedia.org/wikipedia/commons/4/4b/Hysteresis-comparison.svg)

---

## 6. Normativa aplicable

El estudio de la corriente de arranque se enmarca en las siguientes normas:

- **IEC 60076-1**: requisitos generales de transformadores, incluyendo consideraciones sobre corrientes de irrupción.  
- **IEEE Std C57.109**: guía para límites de corriente de *inrush* y criterios de protección diferencial.  
- **IEEE Std C37.111 (COMTRADE)**: formato estándar para el análisis y registro de transitorios.  

---

## Referencias

[1] F. Lattarulo (ed.), *Electromagnetic Compatibility in Power Systems*, Elsevier, 2007.  
[2] A. Shenkman, *Transient Analysis of Electric Power Circuits Handbook*, Springer, 2005.  
[3] J. C. Das, *Transients in Electrical Systems: Analysis, Recognition, and Mitigation*, McGraw-Hill, 2010.  
[4] A. Ametani (ed.), *Numerical Analysis of Power System Transients and Dynamics*, IET, 2015.  
[5] D. Peelo, *Current Interruption Transients Calculation (2nd Edition)*, Wiley, 2020.  
[6] J. A. Martinez-Velasco (ed.), *Transient Analysis of Power Systems: A Practical Approach*, Wiley-IEEE, 2020.  
[7] Q. Huang, A. Khawaja, Y. Chen, J. Li, *Magnetic Field Measurement with Applications to Modern Power Grids*, Wiley, 2020.  
[8] P. J. Nahin, *Transients for Electrical Engineers*, Springer, 2019.  

---
