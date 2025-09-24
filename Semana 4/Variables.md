**Depositos**: lista con los nombres de los 4 depósitos candidatos.

**Centros**: lista con los CACs (centros de acopio).

**Depositos_x_Centros**: lista de tuplas (i, j) Depósitos × CACs.

**mejor_costo**: valor de referencia del costo mínimo histórico (24,881) para acotar el nuevo costo (110%).

**q**: tarifa de transporte convertida a millones de pormiltoneladas − km(300/ton·km → 0.3 M$/mil ton·km).

**dataDepositos**: diccionario depósito → [latitud, longitud, capacidad triplicada, costo fijo].

**dataCentros**: diccionario CAC → [latitud, longitud, producción proyectada].

**lat_d**, **lon_d**: diccionarios depósito → latitud/longitud (grados).

**capacidad**: diccionario depósito → capacidad (miles de ton/año).

**costo_fijo**: diccionario depósito → costo fijo anual (no usado en el modelo).

**lat_c**, **lon_c**: diccionarios CAC → latitud/longitud (grados).

**produccion**: diccionario CAC → producción (miles de ton/año).

**distancia**[(i, j)]: distancia geográfica en km entre depósito i y CAC j (geopy).

**costo_transporte**[(i, j)]: costo anualizado de transportar la producción de j desde i: q · produccion[j] · distancia[i, j].

**problema**: modelo de optimización PuLP (minimización) para el esquema min–max.

**x**[i, j]: variable binaria; 1 si el depósito i atiende al CAC j, 0 en otro caso.

**z**: variable continua ≥ 0; máxima demanda atendida por un depósito (variable auxiliar del min–max).

**solver**: configurador del solucionador CBC en PuLP con gapRel=0.001 y salida silenciosa.

**inicio**: marca de tiempo para medir duración de la optimización.

**estado**: estado del optimizador en texto (Optimal, Infeasible, etc.).

**obj**: valor óptimo de la función objetivo (z óptima).

**costo_total**: suma de costos de transporte de la solución: Σ c_ij · x_ij.

**matriz**: matriz de marcas “X”/“-” para visualizar la asignación de CACs a depósitos.

**df**: DataFrame (pandas) construido desde matriz para presentar la asignación.

**utilizado**: lista con la demanda total asignada a cada depósito en la solución (para graficar).

