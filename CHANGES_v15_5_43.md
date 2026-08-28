# PhysioSentinel AI v15.5.43 · Diana V/S + Manómetros

## Cambio exclusivo de visualización · Pestaña 10

Se añade un panel dual Plotly sin modificar los algoritmos fisiológicos de v15.5.42.

### Diana de Control Autonómico
Eje X:
`S · Alerta / Barorreflejo`

Eje Y:
`V · Vagal`

No se denomina S como "simpático puro", para mantener la precisión fisiológica.

### Zonas
- V alto / S bajo: Reciprocidad con predominio vagal.
- V alto / S alto: Coactivación.
- V bajo / S alto: Reciprocidad con predominio Alerta/Barorreflejo.
- V bajo / S bajo: Coinhibición.
- Centro: zona preservada/intermedia.

La frontera central NO está fijada en ±0.20:
usa `Umbral_gris_actual` de la lógica fuzzy v15.5.42.

### Desacoplamiento fisiológico
Se representan bandas discontinuas junto a los ejes:
- V desplazado con S casi neutro.
- S desplazado con V casi neutro.

La incoherencia metodológica/señal NO se fuerza a una zona geométrica y se mantiene como aviso independiente.

### Manómetros
Dos indicadores:
- V · Rama vagal.
- S · Alerta / Barorreflejo.

Utilizan la misma zona fuzzy/adaptativa del registro actual.

### Trayectoria temporal
Selector:
- Misma fase del paciente.
- Todos los registros/fases visibles.
- Sólo estado actual.

Si existen al menos 2 puntos, la diana incorpora reproducción/pausa de la trayectoria temporal.

### Rendimiento
El gráfico usa exclusivamente la tabla autonómica ya calculada/cacheada.
No recalcula HRV, V/S/L/C/R ni longitudinal.

### Sin cambios
Se conserva íntegramente v15.5.42:
- S refinado con corrección de contaminación vagal.
- lógica fuzzy adaptativa;
- desacoplamiento fisiológico unilateral;
- patrón complejo/incoherente separado;
- Poincaré/SD1-SD2 y soporte de asimetría cuando exista;
- edad/sexo;
- longitudinal 100%;
- integrado 70/30;
- Modo ultraligero/cache;
- PostgreSQL.
