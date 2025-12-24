# Interpretaciones Estadísticas

## 1. Conceptos básicos

### Población
- Conjunto total de datos u objetos de estudio.
- En un archivo XLSX: población = todos los registros cargados en la base.

### Muestra
- Subconjunto de la población.
- "El número con que se pobló una tabla" cuando solo se toma una parte.

### Variable
- Característica que se analiza.
- Ejemplo: edad, sueldo, horas trabajadas, nota.

---

## 2. Tipos de variables

### Cualitativas
- **Nominal**: sin orden (marcas, nombres de autos, colores).
- **Ordinal**: tienen orden (nivel educativo, nivel de satisfacción).

### Cuantitativas
- **Discretas**: números contables (número de hermanos).
- **Continuas**: valores en rango continuo (dinero, altura, peso).

---

## 3. Tablas de frecuencia

| Tipo | Cómo se calcula | Ejemplo |
|------|----------------|---------|
| Frecuencia absoluta (f) | Conteo total. | Jazz = 3 |
| Frecuencia relativa (h) | f / total. | 3 / 30 = 0,10 |
| Frecuencia relativa % (h%) | h × 100. | 10% |
| Frecuencia absoluta acumulada (F) | Suma progresiva por fila. | 4 → 4+8=12 → 12+3=15 |

**Ejemplo simple:**

| Género | f | h | h% | F |
|--------|---|---|----|---|
| Pop | 4 | 0.13 | 13 | 4 |
| Rock | 8 | 0.26 | 26 | 12 |
| Jazz | 3 | 0.10 | 10 | 15 |

---

## 4. Gráficos según tipo de variable

| Gráfico | Se usa para | Observación |
|---------|-------------|-------------|
| Barras / Columnas | Cualitativas o cuantitativas discretas | Eje Y = frecuencia absoluta |
| Histograma | Cuantitativa continua | Se trabaja por intervalos (ej: 200–400) |
| Circular / Torta | Cualitativas | No usar muchas categorías |

---

## 5. Medidas de tendencia central

### Media (promedio)
- Suma de todos los valores / cantidad.
- Es la medida más usada junto con la desviación estándar.

### Mediana (percentil 50 / cuartil 2)
- El valor central.
- 50% de los datos están por debajo.

### Moda
- El valor que más se repite.
- "Lo que está de moda".

---

## 6. Medidas de dispersión

### Desviación estándar (σ o std)
- Mide cuánto se alejan los datos del promedio.
- Se calcula con std() en pandas.

### Coeficiente de variación (CV)
- **Fórmula**: CV = (Desviación estándar / Media) × 100

| CV | Interpretación |
|----|----------------|
| Bajo (cercano a 10%) | Homogéneo: datos parecidos |
| Alto (cercano a 90%) | Heterogéneo: datos muy distintos |

---

## 7. Distribuciones, asimetría y curtosis

### Asimetría
- **Asimetría positiva**: media > mediana → cola a la derecha.
- **Asimetría negativa**: media < mediana → cola a la izquierda.
- **Asimetría = 0**: distribución simétrica.

### Curtosis
- Describe qué tan "picuda" o "plana" es la distribución.

| Tipo | Característica |
|------|----------------|
| Leptocúrtica | Más delgada y alta (pico fuerte) |
| Mesocúrtica | Normal o media |
| Platicúrtica | Más plana |

**Ejemplos referenciales:**
- Leptocúrtica: > 0.5
- Mesocúrtica: entre -5 y 0.5
- Platicúrtica: < -0.5

---

## 8. Histogramas y frecuencias

**Interpretación correcta:**
- **Intervalos**: "entre 199 y 399".
- **f**: cuántos están dentro de ese rango.
- **h**: porcentaje que representa ese rango.
- **F**: cuántos ganan "a lo más" hasta el límite superior (ej: hasta 299 mil).
- **H acumulada**: porcentaje acumulado total.

**Ejemplo típico de interpretación:**
"359 trabajadores reciben un sueldo de hasta 620 mil pesos". (Nunca se escribe con % en el texto final, se agrega coma.)

---

## 9. Correlación, covarianza y relación lineal

### Coeficiente de relación lineal (r)
- Va desde -1 a 1.
- Cerca de 0 → correlación débil o nula.
- Cerca de 1 → correlación positiva fuerte.
- Cerca de -1 → correlación negativa fuerte.

### Covarianza
- Indica dirección de la relación.
- No mide fuerza.
- Positiva: relación directa.
- Negativa: relación inversa.

*(Nombres comunes: covarianza, varianza cruzada. NO es lo mismo que R².)*

### Relación directa o inversa
- **Directa**: si una sube, la otra sube (pendiente positiva).
- **Inversa**: si una sube, la otra baja (pendiente negativa).

---

## 10. Modelo lineal

**Ecuación general:**
```
Y = mX + n
```

- **m**: pendiente.
- **n**: intercepto.
- **X**: variable independiente.
- **Y**: variable dependiente.

**Ejemplo:**
```
Y = 2.000X + 222
```

---

## 11. Interpretaciones típicas
- El 35% recibe un sueldo "desde… hasta…" (sin % en texto).
- El más frecuente es la moda.
- Media es el promedio.
- Mediana es el percentil 50.
- `df.describe()`: entrega media, std, y percentiles.
- `df.quantile(0.9)`: valor del percentil 90.
- Percentil 90 → límite inferior del 10% más alto.

---

## 12. Ejemplos de criterios
- Homogéneo: CV bajo.
- Heterogéneo: CV alto.
- Dinero: cuantitativa continua.
- N° de hermanos: cuantitativa discreta.
- Nombres de marcas: cualitativa nominal.
- Nivel de educación: cualitativa ordinal.
