# Folio — finanzas privadas, local-first

Panel web para importar movimientos bancarios desde CSV, clasificarlos y analizar gastos sin enviar datos a ningún servidor.

## Características

- Importación CSV con detección y asignación manual de columnas.
- Parser compatible con coma, punto y coma, tabulaciones y campos entre comillas.
- Clasificación automática mediante reglas locales.
- Edición manual de categorías, búsqueda y filtros.
- Dashboard mensual con balance, ingresos, gastos, ahorro y gráficos.
- Respaldo/exportación CSV y borrado completo de datos.
- Persistencia exclusiva en `localStorage`; sin cookies, cuentas, analytics ni APIs.
- Interfaz responsive y accesible, optimizada para desktop y móvil.

## Ejecutar localmente

No requiere instalación ni compilación:

```bash
python -m http.server 4173
```

Abrí `http://localhost:4173`. También podés abrir `index.html` directamente.

## Formato CSV recomendado

```csv
fecha,descripcion,importe,cuenta
2026-11-01,Sueldo mensual,2850000,Cuenta sueldo
2026-11-02,Supermercado,-86450,Visa débito
```

Los nombres de columnas pueden variar: Folio permite mapearlos antes de importar. Los gastos deben usar importes negativos y los ingresos, positivos.

## Privacidad

Todos los cálculos y transformaciones ocurren en el navegador. El archivo seleccionado no se sube. Los movimientos, categorías, reglas y preferencias se guardan únicamente en el almacenamiento local del navegador actual.

> Importante: limpiar los datos del navegador elimina la información. Usá **Ajustes → Descargar respaldo** periódicamente.

## Estructura

```text
index.html   Interfaz y estructura semántica
styles.css   Sistema visual responsive
app.js       Estado local, CSV, reglas, filtros y gráficos
```

## Seguridad

- Sin dependencias de terceros ni recursos remotos.
- Sin ejecución dinámica (`eval`) ni HTML proveniente del CSV sin escapar.
- CSP-friendly y desplegable como sitio estático.

## Licencia

MIT

