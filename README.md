# 🛡️ PreVe — Sistema Predictivo de Seguridad para Juventudes Urbanas

**Hackathon RedPública (PNUD) — Edición Seguridad Ciudadana**
**Equipo: Minsky Devs** · Universidad Peruana de Ciencias Aplicadas (UPC)

---

## 📋 ¿Qué es PreVe?

PreVe es una plataforma ciudadana inteligente que **anticipa** zonas, rutas y horarios de riesgo para jóvenes (15-29 años) en Lima Centro, transformando reportes ciudadanos en alertas tempranas **antes** de que ocurra el delito.

A diferencia de las apps de seguridad existentes (reactivas, de público general), PreVe combina tres atributos:

- **Predictivo**, no reactivo — usa Machine Learning para anticipar el riesgo.
- **Enfocado en juventudes** — alineado con el mandato del PNUD de protagonismo juvenil.
- **Sin fricción** — funciona por WhatsApp, sin necesidad de descargar una app.

### El problema que atacamos

- Solo **16,1 %** de las víctimas de delito denuncia en el Perú (INEI, 2024), generando un subregistro que impide diseñar prevención efectiva.
- En Lima Metropolitana, **18 de cada 100 personas** fueron víctimas de robo en el semestre sept. 2025 – feb. 2026 (INEI, 2026).
- Los jóvenes universitarios son un blanco recurrente en sus trayectos cotidianos (universidad–paradero–trabajo), con casos documentados en Universidad de Lima, PUCP, UTP y UCH.

### La solución: 3 componentes

| Componente | Tecnología | Función |
|---|---|---|
| **Chatbot IA por WhatsApp** | Twilio API + NLP | Recibe reportes en lenguaje natural, extrae ubicación, hora y tipo de delito |
| **Plataforma web + mapa de calor** | React (PWA) + Google Maps API | Visualiza rutas y zonas críticas para juventudes en tiempo real |
| **Motor predictivo de ML** | Python + scikit-learn | Random Forest + Regresión Logística + K-Means predicen riesgo y disparan alertas |

**Resultados del prototipo de ML:** Random Forest 79,5 % de exactitud · Regresión Logística AUC-ROC 0,68 · K-Means detecta 4 zonas críticas para juventudes.

---

## 📁 Estructura del repositorio

```
preve-repo/
├── README.md                          ← este archivo
├── docs/                              ← documentos de la postulación (Word)
│   ├── Punto_A_Problema.docx          ← identificación del problema (resumen ejecutivo)
│   ├── Punto_B_Solucion.docx          ← solución propuesta + diagrama + sustento
│   ├── Anexo2_Puntos_B_C_E.docx       ← solución, resultados esperados y presupuesto
│   ├── Anexo_Analisis_Detallado.docx  ← marco teórico, causas, análisis por distrito
│   └── Indice_Fuentes_Datos.docx      ← guía de fuentes oficiales descargables
├── notebooks/
│   └── PreVe_Juvenil_ML.ipynb         ← notebook con los 3 modelos de ML (ejecutado)
├── data/
│   ├── incidentes_juvenil.csv         ← dataset sintético (800 incidentes) para el ML
│   ├── Datos_PreVe_Juvenil.xlsx       ← datos citados: distritos, delitos, vulnerabilidad juvenil
│   ├── Datos_Lima_Centro.xlsx         ← datos citados: denuncias, tipos de delito, victimización
│   └── Presupuesto_PreVe.xlsx         ← presupuesto detallado (8 hojas, S/ 10 000, 75 fórmulas)
├── web/
│   └── preve_demo.html                ← demo interactiva (chat WhatsApp + mapa de calor + alertas)
└── assets/
    └── diagrama_preve.png             ← diagrama de arquitectura y flujo del sistema
```

---

## 🚀 Cómo usar cada parte

### Ver la demo interactiva
Abre `web/preve_demo.html` directamente en cualquier navegador (no requiere instalación ni internet). Incluye:
- Chat simulado de WhatsApp donde se puede reportar un incidente en lenguaje natural.
- Mapa de calor de Lima Centro con zonas universitarias marcadas (🎓).
- Botón de "Simulación automática" para ver el flujo completo sin escribir.
- Sistema de alertas que se dispara al acumular 3 reportes en una misma zona.

### Ejecutar el notebook de Machine Learning
1. Sube `notebooks/PreVe_Juvenil_ML.ipynb` y `data/incidentes_juvenil.csv` a [Google Colab](https://colab.research.google.com/) (o Jupyter local).
2. Asegúrate de que el CSV esté en la misma carpeta que el notebook.
3. Ejecuta todas las celdas (`Entorno de ejecución → Ejecutar todas`).
4. Verás los 3 modelos entrenados con sus métricas y gráficos (matriz de confusión, curva ROC, clusters).

**Librerías requeridas:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`.

### Revisar el presupuesto
Abre `data/Presupuesto_PreVe.xlsx` en Excel o Google Sheets. Todas las fórmulas son nativas de Excel (no requiere macros). La Hoja 1 muestra el resumen; las Hojas 2-6 el detalle por rubro; la Hoja 7 el cronograma; la Hoja 8 la contrapartida y sostenibilidad.

---

## 👥 Equipo — Minsky Devs

| Integrante | Rol | Carrera |
|---|---|---|
| Fabrizio Carruitero Osorio | Líder de Proyecto + Data Scientist | Ing. Industrial |
| Ramón Jorge Arévalo | Tech Lead / Arquitecto | Ing. de Software |
| Eduardo Santillán Taboada | Backend Developer + Data Engineer | Ing. de Sistemas de Información |
| Victor Temoche Coronado | Frontend Developer + UX | Ing. de Sistemas de Información |
| Oscar Gamboa More | QA + Encargado de Campo | Ing. de Sistemas de Información |

---

## 📊 Datos y fuentes

Todos los datos citados provienen de fuentes oficiales: INEI (Victimización en el Perú 2024/2025, Estadísticas de Criminalidad), MININTER (Política Nacional Multisectorial de Seguridad Ciudadana al 2030), CEPLAN y el Observatorio del Crimen y la Violencia (Credicorp/CHS, 2025). El dataset de incidentes (`incidentes_juvenil.csv`) es **sintético**, calibrado con tendencias reales, y sirve como prueba de concepto del modelo predictivo mientras se recolectan datos reales durante el piloto.

Ver `docs/Indice_Fuentes_Datos.docx` para el listado completo de fuentes descargables (DATACRIM, SIRTOD, Registro Nacional de Denuncias).

---

## 📄 Licencia

Proyecto desarrollado con fines académicos y de postulación a la Hackathon RedPública (PNUD), 2026. Uso educativo y de innovación social.
