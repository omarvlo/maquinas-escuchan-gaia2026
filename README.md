# ¿Pueden escuchar las máquinas?

Material de la conferencia **"¿Las máquinas escuchan? IA, señales y música"**,
impartida en el Día GAIA del Club de Inteligencia Artificial, ESCOM-IPN,
el 11 de septiembre de 2026.

Dr. Omar Velázquez López — IIMAS, UNAM

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/omarvlo/maquinas-escuchan-gaia2026/blob/main/demos_las_maquinas_escuchan.ipynb)

---

## De qué va

Un recorrido por tres generaciones del análisis computacional de audio musical:

1. **Ingeniería de características** — un humano diseña a mano cómo el sonido
   se convierte en algo que la máquina pueda mirar.
2. **Aprendizaje profundo** — la máquina aprende el clasificador, pero la
   representación se le sigue dando hecha.
3. **Modelos fundacionales** — la máquina aprende sin etiquetas, y la
   representación se le sigue dando hecha.

La columna de la representación nunca se movió. El **front-end** —el banco de
filtros que convierte la señal en la entrada del modelo— es la única pieza que
no se automatizó, y sigue usando una escala derivada de experimentos
psicoacústicos de 1937.

Esa es la pregunta con la que trabajo en el IIMAS: ¿el front-end es
preprocesamiento neutro, o decide qué evidencia acústica queda disponible
para el modelo?

## Cómo correrlo

Abre el notebook en Colab con el botón de arriba y activa la GPU en
`Entorno de ejecución → Cambiar tipo de entorno → T4 GPU`.

- **Partes 1 y 2** (señal, espectrogramas, bancos de filtros): solo `numpy`
  y `scipy`. Corren sin GPU en segundos.
- **Partes 3 y 4** (red entrenada desde cero, modelo preentrenado): necesitan
  GPU. La primera ejecución descarga GTZAN (~1.2 GB) y un modelo preentrenado;
  después queda en caché.

## Los audios

| Archivo | Qué es |
|---|---|
| `00_original.wav` | El fragmento que sonó al inicio |
| `canal_6_mel.wav` | El canal 6 del banco de filtros, escala Mel (294–359 Hz) |
| `canal_6_greenwood.wav` | El mismo canal 6, escala Greenwood (155–185 Hz) |

Mismo número de canal, misma señal, contenido distinto. Ese es el punto.

## Créditos

La arquitectura de la Parte 3 está **inspirada en** (no es una réplica de) la
del tutorial *Deep Learning 101 for Audio-based MIR* de Geoffroy Peeters,
ISMIR 2024.

GTZAN: G. Tzanetakis y P. Cook, *Musical genre classification of audio
signals*, IEEE TSAP, 2002.

## Contacto

IIMAS, UNAM — [omarvlo@comunidad.unam.mx]
