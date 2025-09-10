
- **cacs**: DataFrame de pandas con la información de los CACs (Centros de Acopio Consolidados).

- **depositos**: DataFrame de pandas con la información de los depósitos candidatos.

- **I**: Lista con los nombres de los depósitos (índices del conjunto I).

- **J**: Lista con los nombres de los CACs (índices del conjunto J).

- **capacidad**: Diccionario: clave = depósito, valor = capacidad máxima de ese depósito.

- **costo_fijo**: Diccionario: clave = depósito, valor = costo fijo de operación anual de ese depósito.

- **depositos_lat_lon**: Diccionario: clave = depósito, valor = tupla (latitud, longitud) del depósito.

- **produccion**: Diccionario: clave = CAC, valor = producción proyectada de ese CAC.

- **cacs_lat_lon**: Diccionario: clave = CAC, valor = tupla (latitud, longitud) del CAC.

- **q**: Costo anualizado por cada mil toneladas por kilómetro (constante).

- **r**: Distancia máxima (en km) para considerar que un CAC está bien atendido (constante).

- **distancia**: Diccionario: clave = (depósito, CAC), valor = distancia geodésica en km entre ambos.

- **costo_transporte**: Diccionario: clave = (depósito, CAC), valor = costo de transportar la producción del CAC al depósito.

- **capacidad**: Diccionario: clave = depósito, valor = capacidad máxima de ese depósito.

- **costo_fijo**: Diccionario: clave = depósito, valor = costo fijo de operación anual de ese depósito.

- **depositos_lat_lon**: Diccionario: clave = depósito, valor = tupla (latitud, longitud) del depósito.

- **produccion**: Diccionario: clave = CAC, valor = producción proyectada de ese CAC.

- **cacs_lat_lon**: Diccionario: clave = CAC, valor = tupla (latitud, longitud) del CAC.

- **q**: Costo anualizado por cada mil toneladas por kilómetro (constante).

- **r**: Distancia máxima (en km) para considerar que un CAC está bien atendido (constante).

- **distancia**: Diccionario: clave = (depósito, CAC), valor = distancia geodésica en km entre ambos.

- **costo_transporte**: Diccionario: clave = (depósito, CAC), valor = costo de transportar la producción del CAC al depósito.

---


- **x**: Diccionario de variables binarias de PuLP:
x[i, j] = 1 si el CAC j es atendido por el depósito i, 0 en caso contrario.

- **y**: Diccionario de variables binarias de PuLP:
y[i] = 1 si el depósito i es operado, 0 en caso contrario.

- **problema**: Objeto de modelo de optimización de PuLP (LpProblem).