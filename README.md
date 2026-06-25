# DLC-Anolis-mariarum

Entrenamiento de modelo de seguimiento de pose con **DeepLabCut** para *Anolis mariarum*.  
Proyecto colaborativo entre Joshua y Xaira.

---

## Equipo

| Integrante | GitHub |
|------------|--------|
| Joshua | [@JTQM](https://github.com/JTQM) |
| Xaira | *(agregar usuario)* |

---

## Estado del proyecto

- [x] Configuración inicial del repositorio
- [x] Estructura de carpetas definida
- [ ] Etiquetado de frames — iteración 1
- [ ] Primer entrenamiento
- [ ] Evaluación iteración 1
- [ ] Iteración 2 (si es necesaria)

---

## ⚠️ Regla fundamental

**Este repositorio NO contiene imágenes ni videos.**  
Todos los archivos pesados se comparten exclusivamente por **Google Drive**.

| Tipo de archivo | Dónde va |
|-----------------|----------|
| Videos `.mp4`, `.avi` | Solo Google Drive |
| Imágenes `.png`, `.jpg` | Solo Google Drive |
| Modelos entrenados `.pb` | Solo Google Drive |
| `config.yaml` | ✅ GitHub |
| `CollectedData_*.csv` | ✅ GitHub |
| `CollectedData_*.h5` | ✅ GitHub |
| `README.md`, `.gitignore` | ✅ GitHub |

---

## Estructura de carpetas

```
DLC-Anolis-mariarum/
│
├── config.yaml                        ← configuración principal de DLC
├── README.md                          ← este archivo
├── .gitignore                         ← archivos excluidos de Git
│
└── labeled-data/
    ├── GX010336-editado_labeled/
    │   ├── CollectedData_Joshua.csv   ← etiquetas (sí en Git)
    │   └── CollectedData_Joshua.h5    ← etiquetas (sí en Git)
    ├── GX010385-editado_labeled/
    │   ├── CollectedData_Xaira.csv
    │   └── CollectedData_Xaira.h5
    └── GX010389-editado_labeled/
        ├── CollectedData_Joshua.csv
        └── CollectedData_Xaira.csv
```

**En Google Drive** (misma estructura de carpetas):
```
Drive - DLC-Anolis-mariarum/
│
├── videos/
│   ├── GX010336-editado.mp4
│   ├── GX010385-editado.mp4
│   └── GX010389-editado.mp4
│
└── labeled-data/
    ├── GX010336-editado_labeled/
    │   └── img0001.png, img0002.png ...
    ├── GX010385-editado_labeled/
    │   └── img0001.png, img0002.png ...
    └── GX010389-editado_labeled/
        └── img0001.png, img0002.png ...
```

---

## Flujo de trabajo

### Al comenzar cada sesión
```bash
git pull origin main
```
Siempre lo primero. Descarga los cambios de la compañera.

### Durante el trabajo
```bash
git add labeled-data/nombre_video/CollectedData_tunombre.csv
git add labeled-data/nombre_video/CollectedData_tunombre.h5
git commit -m "Etiquetado: 50 frames de GX010336 - Joshua"
```

### Al terminar cada sesión
```bash
git push origin main
```

### Cuando se agrega un video nuevo
1. Subir el video a la carpeta `videos/` en Google Drive.
2. Avisarle a la compañera por mensaje.
3. Cada una descarga el video a su computador local.
4. Extraer frames con DeepLabCut normalmente.
5. Subir las imágenes extraídas a `labeled-data/nombre_video/` en Google Drive.
6. Cada una etiqueta sus frames asignados localmente.
7. Hacer `git add` + `git commit` + `git push` solo de los archivos `.csv` y `.h5`.

---

## Convención para mensajes de commit

```
Etiquetado: [cantidad] frames de [video] - [nombre]
Config: [descripción del cambio]
Evaluación: [resultado] - iteración [número]
Corrección: [descripción]
```

**Ejemplos:**
```
Etiquetado: 80 frames de GX010389 - Xaira
Config: ajustado numshuffles a 5
Evaluación: error promedio 3.2px - iteración 1
```

---

## Registro de iteraciones

| Iteración | Frames totales | Videos | Error (px) | Fecha | Notas |
|-----------|---------------|--------|------------|-------|-------|
| 1 | — | — | — | — | En progreso |

*(Actualizar esta tabla después de cada evaluación)*

---

## Contacto y coordinación

Ante cualquier duda sobre el repositorio, abrir un **Issue** en GitHub:  
`https://github.com/JTQM/DLC-Anolis-mariarum/issues`
