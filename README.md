# Semáforo

Panel independiente de control de inventario, caja y comprobantes para la reventa temporal de Súper 8 y gomitas de eucalipto.

**Proyecto completamente separado** de Breto’s Services, BHG, ZivaLatam y Panel Capa 2.  
No aplica la reserva del 10 % ni ninguna regla financiera de otros proyectos.

## Uso inmediato (hoy / mañana)

1. Abre el archivo `index.html` en el navegador del teléfono (Chrome o Safari).
2. O súbelo a cualquier hosting estático (GitHub Pages del propio repo, Netlify Drop, etc.).
3. El panel funciona offline con los datos guardados en el navegador (localStorage).
4. Puedes exportar un CSV compatible con Google Sheets en cualquier momento desde la pantalla Resumen.

### Datos precargados
- Súper 8: 48 unidades · $248/u · total $11.904
- Gomitas: 60 unidades · $155/u · total $9.300
- Costo total inventario: $21.204
- Precio de venta: $400/u o 3 × $1.000

## Las 5 pantallas

1. **Dashboard** — Caja estimada, stock actual, margen aproximado, botón de nuevo cierre.
2. **Cierre** — Caja inicial/final, ingresos, gastos, stock físico restante, notas. Las unidades vendidas se calculan por diferencia y se marcan como aproximadas.
3. **Inventario** — Inventario inicial + comparación teórico vs real.
4. **Comprobantes** — Guarda enlace de Drive + datos del documento. OCR solo como sugerencia editable (tú confirmas).
5. **Resumen** — Totales del período + exportación CSV y texto.

## Cómo conectar Google Sheets + Drive (siguiente paso)

Cuando quieras pasar de localStorage a Sheets:

1. Crea una carpeta en Google Drive llamada `Semáforo-Reventa`.
2. Dentro crea una hoja de cálculo con pestañas: `Cierres`, `Comprobantes`, `Inventario`.
3. Crea un proyecto de Google Apps Script vinculado a esa hoja.
4. Pega un backend simple que reciba JSON de cierres/comprobantes y los escriba en las pestañas.
5. Despliega el Apps Script como Web App (solo tú o “Cualquiera con el enlace”).
6. Sustituye en el `index.html` la función `saveState` / `loadState` por llamadas `fetch` a la URL del Apps Script.

Hasta que eso esté listo, el panel ya es usable y exporta CSV listo para pegar en Sheets.

## Reglas de operación

- Solo Luis registra los cierres (consolida la información del compañero).
- No se registran ventas individuales.
- Toda estimación de unidades vendidas se muestra como **aprox**.
- No se amplía el alcance hasta completar 10–14 cierres reales.
- Las fotos de comprobantes se guardan en Drive; el panel solo guarda el enlace + datos confirmados.

## Pruebas básicas recomendadas

1. Abrir el panel y verificar stock inicial 48 / 60.
2. Hacer un cierre de prueba con stock restante distinto.
3. Verificar que el Dashboard y el Resumen actualizan unidades vendidas (aprox) y margen.
4. Guardar un comprobante con enlace ficticio.
5. Exportar CSV y abrirlo en Sheets o Excel.

---

Repositorio creado el 24-09-2026 para la iniciativa temporal de reventa.  
Identidad y datos completamente independientes.
