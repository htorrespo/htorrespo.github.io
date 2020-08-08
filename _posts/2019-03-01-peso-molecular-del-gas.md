---
title: Peso molecular de una mezcla de gases
description: Determina las concentraciones de CO2, O2 y peso molecular seco de gases de emisión de un proceso de combustión de combustibles fósiles u otro proceso de oxidación.
categories: 
  - Blog
  - Emisiones
comments: true
---

<img src="/images/post/molecular_weight.png" alt="Imagen del peso molecular de gases" style="width">
<!--
![Imagen del peso molecular de gases]("/images/post/molecular_weight.png")
-->

Determina las concentraciones de $CO_2$, $O_2$ y peso molecular seco de gases de emisión
de un proceso de combustión de combustibles fósiles u otro proceso de oxidación.

<!--
### Introducción

* El peso molecular de los gases que se emiten por chimenea es empleado en
cálculos para determinar el flujo de gases.
* Los gases que se emiten por chimenea están compuestos casi siempre una mezcla de gases.
* El peso molecular aparente de la mezcla de gases es función de la composición
de la mezcla.
* Los gases poseen cantidades significativas de diversos compuestos como el
oxígeno, nitrógeno, dióxido de carbono y vapor de agua, que deben analizarse
para determinar el peso molecular aparente
-->

<!--
Fundamentos de termodinámica técnica
Por Michael J. Moran, Howard N. Shapiro
https://books.google.com.co/books?id=lJJcF1oqP5wC&pg=PA631&lpg=PA631&dq=peso+molecular+aparente&source=bl&ots=rbnjPcS93J&sig=ACfU3U3Vq3WbvpTb-13-5CfAkOGp84V3-w&hl=es-419&sa=X&ved=2ahUKEwjGv9nImd3gAhWGct8KHVfWC6AQ6AEwEHoECAMQAQ#v=onepage&q=peso%20molecular%20aparente&f=false
-->

#### Peso (masa) molecular aparente de una mezcla de gases

Se asume que los componentes principales de la combustión de cualquier
combustible (sólido, líquido o gaseoso) son oxígeno, nitrógeno, dióxido de
carbono, vapor de agua y monóxido de carbono.

Ya que una mezcla de gases está compuesta de moléculas de diferentes tamaños,
podríamos decir que esta mezcla tiene un peso molecular, afirmación que es incorrecta.
Sin embargo, a pesar de todo una mezcla de gases se comporta como si tuviera un peso
molecular definido.  Si queremos utilizar esta propiedad se debe emplear un
artilugio, para hacer uso de la ley de gases en cálculos de ingeniería. La
solución es introducir el concepto _peso molecular aparente_ para designar la masa
que posee una mezcla de gases inertes que tienen masas atómicas diferentes y que
se encuentra presente en cantidades particulares.

#### La ley de gases ideales

1. La ley de Boyle establece que a temperatura constante, el volumen de la masa
de un gas perfecto con una composición dada varía inversamente con la presión
absoluta.
2. De otra parte, la ley de Charles establece que a volumen constante, la presión
absoluta de la masa de un gas perfecto con una composición dada varía directamente
con la temperatura absoluta.
3. Como resultado de la combinación de estas relaciones se cuenta con una ecuación,
de la siguiente forma -- conocida también como ecuación de estado --
\\[ \large{
PV = \frac{mRT}{M}} \tag{Ec-1}
\\]
Donde:<br>
$P$ = presión absoluta<br>
$T$ = temperatura absoluta<br>
$V$ = volumen de gas<br>
$M$ = peso molecular del gas (masa / mol)<br>
$m$ = masa del gas<br>

La ecuación anterior satisface la ley de Dalton de presiones parciales cuando
\\[\large{
P_xV_{mix} = \frac{m_xRT_{mix}}{M_x}} \tag{Ec-2}
\\]
Donde:<br>
$P_x$ = presión parcial de un gas en una mezcla de gases inertes<br>
R = constante universal de los gases<br>
$T_{mix}$ = temperatura absoluta de las mezcla de gases<br>
$V_{mix}$ = volumen de la mezcla de gases<br>
$M_x$ = peso molecular de un gas componente (masa / mol)<br>
$m_x$ = masa de un gas componente<br>

Tener en cuenta que $\large{\frac{P_xV_{mix}}{T_{mix}}}$ es constante sólo si
$\large{\frac{m_x}{M_x}}$ permanece constante.

La ecuación de estado de una mezcla de gases es la siguiente
\\[\large{
P_{mix}V_{mix} = \frac{m_{mix}RT_{mix}}{M_{mix}}}  \tag{Ec-3}
\\]
Si reordenamos la ecuación de Dalton de presiones parciales y la
ecuación de estado de una mezcla de gases, en un término común, tendremos

\\[\large{
\frac{P_{mix}M_{mix}}{m_{mix}} = \underbrace{\frac{RT_{mix}}{V_{mix}}}_\text{termino común}
}
\\]

y

\\[\large{
\frac{P_{x}M_{x}}{m_{x}} = \underbrace{\frac{RT_{mix}}{V_{mix}}}_\text{termino común}
}
\\]

Tenemos que ambas ecuaciones se igualan. Ahora podemos expresar cada una de ellas
en presiones y construir un cociente entre ambos términos
\\[\large{
\frac{P_x}{P_{mix}} = \LARGE{\frac{\frac{m_x}{M_{x}}} {\frac{m_{mix}}{M_{mixx}}}} \tag{Ec-4}
}
\\]
La ecuación de estado general a temperatura y presión constante, esto es condiciones
ambientales del sitio de muestreo de gases promedio, es

\\[\large{
\frac{m}{M} = \frac{PV}{RT} \tag{Ec-5}
}
\\]
Reordenando las ecuaciones 2, 3 y 5, tenemos
\\[\large{
\frac{P_x}{P_{mix}} = \frac{V_x}{V_{mix}}  \tag{Ec-6}
}
\\]

La última parte de la ecuación hace referencia a un número adimensional. que es
fracción de un volumen o proporción de volumen. De esta manera esta ecuación se
puede representar,
\\[\large{
B_x = \frac{P_x}{P_{mix}}  \tag{Ec-7}
}
\\]
Entonces la proporción en volumen o porcentaje en volumen es función de la
presión parcial de un soluto, o mejor un gas componente de la mezcla, que está
directamente relacionado con la fracción molar --Por la ley de Dalton--. Ahora
se puede determinar el peso molecular aparente de una mezcla gaseosas,
empleado la presión parcial a cambio de la fracción molar. Reordenando la
segunda ecuación, que representa la ecuación de estado para un gas
o soluto en la mezcla gaseosa,
\\[\large{
{M_x}P_xV_{mix} = m_xRT_{mix} \tag{Ec-8}
}
\\]
Si utilizamos la anterior expresión para determinar la composición de la mezcla,
debemos aplicar sumatoria a todos los solutos o gases presentes en la mezcla,
\\[\large{
V_{mix} \sum{M_x P_x} = RT_{mix} \sum{m_x} \tag{Ec-9}
}
\\]
Sabemos que $\sum{m_{x}} = m_{mix}$, entonces de le ecuación 5, se resuelve para
$m_{mix}$

\\[\large{
m_{mix} = \frac{M_{mix}P_{mix}V_{mix}}{RT_{mix}} \tag{Ec-10}
}
\\]
Resolviendo la ecuación 9 para $\sum{m_x}$ y reemplazando en la ecuación 10 como
$m_{mix}$ se obtiene,
\\[\large{
M_{mix} = \frac{\sum{P_x M_x}}{P_{mix}} \tag{Ec-11}
}
\\]
Puesto que $\large{\frac{P_x}{P_{mix}}} = B_x$, la ecuación 11 también se puede
expresar de esta manera,
\\[\large{
M_{mix} = \sum{B_x M_x} \tag{Ec-11}
}
\\]

#### Conclusiones

Se pueden utilizar otros métodos, o modificaciones al procedimiento estándar.
Incluyen: (1) muestreo en muchos puntos para analizar una muestra integrada;
(2) medir $CO_2$, $O_2$ y emplear cálculos estequiométricos para determinar el
peso molecular seco; y (3) asignando un valor de 30.0 al peso molecular seco,
a cambio de mediciones reales, para los procesos de combustión de gas natural,
carbón mineral o petróleo crudo. Si bien estos métodos y modificaciones son
sugeridos por el procedimiento estándar están sujetos a la aprobación de la
autoridad ambiental. Este procedimiento se puede emplear en procesos en los
cuales se ha determinado que los compuestos diferentes a la combustión -- CO2, O2,
monóxido de carbono (CO) y nitrógeno (N2) -- están presentes en concentraciones
insuficientes para afectar los resultados.


#### Contacto

- Envienos un correo a `henrytorrespo@yahoo.com`
