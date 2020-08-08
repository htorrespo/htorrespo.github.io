---
title: Determinacion de ecuacion isocinetica
description: Derivacion de ecuacion isocinetica.
categories: 
  - Blog
  - emisiones
comments: true
---

A continuacion se muestra el origen de la constante $\Delta H@ $ del orificio del sistema medicion del tren de muestreo manual de la Agencia de Proteccion Ambiental  de los Estados Unidos (EPA-USA). Esta es una constante de diseño del instrumento de muestreo, que hace referencia a las condiciones estandarizadas para succionar una muestra de aire a 0.75 dcfm (dry standard cubic feet minute), 68°F y 29.92 in.Hg.

El valor del $\Delta H@$ se determina durante la calibración del orificio del tren de muestreo del Método 5 EPA-USA.

Esta es la ecuación:

\\[
{\large\Delta H @ = \cfrac{0.0319\ \Delta H}{P_b(t_0 + 460)} \Bigg[ \cfrac{(t_w + 460)}{V_w} \Bigg]^2}
\\]

### Derivacion

De mecanica de fluidos de Cengel, definamos la ecuacion para determinar el flujo a traves de tuberias.

La tasa de flujo que pasa a traves de un medidor de orificio se determina mediante la siguiente ecuacion:

\\[
{\large Q_m = k_m \sqrt{\cfrac{T_m\ \Delta H}{P_m\ M_m}} }
\\]

Donde:<br>
\\(Q_m\\) = Flujo volumetrico (caudal) a traves del medidor de orificio, cfm (cubic feet minute).<br>
$K_m$ = Constante de calibracion del orificio $${[(in. Hg)(lb-mol)]/[(R)(in. H_2O)]}$$<br>
$T_m$ = Temperatura absoluta en el orificio, °R<br>
$\Delta H$ = Presion diferencial en el orificio, in.$$H_2O$$<br>
$P_m$ = Presion absoluta en el orificio, in.Hg<br>
$M_m$ = Peso molcular del gas que circula por el orificio, lb/lm-mole<br>

En lugar de utilizar el coeficiente de calibracion del orificio \\(K_m\\), se deriva el termino \\(\Delta H@\\) para reflejar las condiciones generales del diseño del tren de muestreo y del orificio de medicion con una constante de calibracion que puede ser relacionada a la tasa de flujo deseada. Por ejemplo el \\(\Delta H@\\) con 1.84 significa que la presion diferencial en el orificio \\(\Delta H\\) debería ser 1.84 cuando el gas circula a traves del orificio de medicion. Las condiciones de referencia definidas para el \\(\Delta H\\) fueron 0.75 dcfm a 68°F y 29.92 in.Hg. Utilizando la segunda ecuacion tenemos:

$$
{\large \Delta H @ = \cfrac{Q^2_@\ P_@\ M_@}{K^2_m\ T_@} }
$$

El subindice \\(@\\) representa condiciones de referencia que estan dadas en 0.75 dcfm a 68°F y 29.92 in.Hg.

Sustituyendo los valores de las condiciones de referencia (exceptuando por $$M_@$$) en la ecuacion anterior se obtiene:

$$
{\large \Delta H @ = \cfrac{(0.75^2)\ (29.92)\ M_@}{K^2_m\ 528)} = 0.0319\ \cfrac{M_@}{K^2_m} }
$$

Ahora la relacion entre $$Q_m$$ y la tasa de flujo volumetrico que pasa a traves de un medidor humedo $$Q_w$$ que se utiliza para calibracion es la siguiente (el subindice "w" se refiere a las condiciones del medidor humedo):

\\[
{\large \cfrac{P_m Q_m}{T_m}=\cfrac{P_w Q_w}{T_w}  }
\\]

Sustituyendo la segunda ecuacion en la anterior y resolviendo para $$K^2_m$$:

\\[
{\large \cfrac{P_m K_m}{T_m} \sqrt{\cfrac{T_m \Delta H}{P_m M_m} } =\cfrac{P_w Q_w}{T_w}  }
\\]

\\[
{\large K^2_m = \cfrac{M_m T_m P^2_w Q^2_w}{\Delta H T^2_w P_m} }
\\]

En la calibracion del Metodo 5, la presion diferencial en el orificio y el medidor humedo son iguales a la presion barometrica. De esta manera $$P_w = P_m = P_b$$. La ecuacion 6 se simplifica a:

\\[
{\large K^2_m = \cfrac{M_m T_m P_b Q^2_w}{\Delta H T^2_w} }
\\]

Sustituyendo la ecuacion 7 en la ecuacion 4, tenemos:

\\[
{\large \Delta H@ = \cfrac{0.0319 M_@ \Delta H\ T^2_w}{M_m T_m P_b Q^2_w} }
\\]

Por cuanto es fluido que se utiliza para calibrar el orificio, $$M_@ = M_m$$ es aire. Adicionalmente, $$Q_w = V_w/ \theta$$, que es volumen registrado por el medidor humedo divido sobre el tiempo, y $$T_m$$ es la temperatura medida a la salida del medidor de gas seco, $$T_m = T_o$$.  Ademas, $$T_w = t_w + 460$$, y $$T_o = t_o + 460$$.  Sustituyendo en la ultima ecuacion,


\\[
{\large\Delta H @ = \cfrac{0.0319\ \Delta H}{P_b(t_0 + 460)} \Bigg[ \cfrac{(t_w + 460)}{V_w} \Bigg]^2}
\\]

Donde:<br>
$$\Delta H@$$ = $$\Delta H$$ que entrega 0.75 dcfm de aire a 67°F y 29.92 in.Hg, en in $$H_2O$$<br>
$$0.0319$$ = constante $$(0.75^2)(29.92)/(68 + 460)$$<br>
$$\Delta H$$ = Presion diferencial en el orificio, in. $$H_2O$$<br>
$$t_w$$ = temperatura del medidor humedo, °F<br>
$$\theta$$ = tiempo, min<br>
$$P_b$$ = Presion barometrica, in.Hg<br>
$$t_o$$ = Temperatura a la salida del medidor de gas seco, °F<br>
$$V_m$$ = Volumen medido por el medidor humedo, cf (cubic feet).<br>

<hr>

### Contacto

Envienos un correo a `henrytorrespo@yahoo.com`
