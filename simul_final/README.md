# Simulación de Interacción de Fotones

Este script en Python simula la interacción de fotones con un material, considerando tanto interacciones fotoeléctricas como Compton. Incluye funciones para simular interacciones sin y con resolución de energía.

## Resumen del Código

### Parámetros y Constantes

- `pho`: Densidad del material (NaI).
- `mu_f`, `mu_c`, `mu`: Parámetros relacionados con las propiedades del material.
- `t`: Grosor del material.
- `E`: Energía inicial de los fotones.
- `eps`: Factor de conversión de energía.
- `E_c`: Energía del pico de Compton.
- `deltaE`: Paso de discretización de energía.

### Probabilidades y Funciones de Distribución Acumulativa (CDFs)

- `P_int`, `P_no_int`: Probabilidades de interacción y no interacción.
- `pdf1`, `cdf1`: Función de densidad de probabilidad y función de distribución acumulativa para la interacción.
- `Pf`, `Pc`: Probabilidades relativas de interacciones fotoeléctricas y de Compton.
- `pdf2`, `cdf2`: Función de densidad de probabilidad y función de distribución acumulativa para el tipo de interacción.

### Funciones de Distribución de Energía

- `dist_E_c`: Función de distribución para las energías de Compton.
- `Es_c`: Discretización de las energías de Compton.
- `pdf_Ec`, `cdf_Ec`: Función de densidad de probabilidad y función de distribución acumulativa para las energías de Compton.

### Funciones de Simulación Monte Carlo

- `Energia_compton()`: Simula la energía de las interacciones de Compton.
- `interacción()`: Simula si hay una interacción.
- `fotoelectrico()`: Simula si la interacción es fotoeléctrica o de Compton.
- `simul_sin_FWHM(N_fotones)`: Simulación Monte Carlo sin considerar la resolución de energía.
- `FWHM(E)`: Función para calcular el ancho completo a la mitad del máximo (FWHM).
- `añadir_Fwhm(E)`: Función para agregar resolución de energía (FWHM) a una energía dada.
- `simul_con_FWHM(N_fotones)`: Simulación Monte Carlo considerando la resolución de energía.

## Uso

1. Ajusta los parámetros y constantes según tus necesidades.
2. Llama a las funciones de simulación según tu escenario específico.

```python
# Ejemplo de uso para simulación sin FWHM
Energias_sin_FWHM, cuentas_sin_FWHM = simul_sin_FWHM(N_fotones=10000)

# Ejemplo de uso para simulación con FWHM
Energias_con_FWHM, cuentas_con_FWHM = simul_con_FWHM(N_fotones=10000)
