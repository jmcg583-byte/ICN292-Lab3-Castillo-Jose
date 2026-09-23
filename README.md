# ICN292 - Laboratorio 3

Nombre:José Castillo
**RUT (sin dígito verificador): 21356378
Fecha: 23-09-2026
Parámetros: S = 378 · U = $58.000 · D = 21 días

Workflows de n8n

Para abrirlos: en n8n, menú Workflows, Import from File y seleccionar el .json.

- `ICN292-Lab3-Castillo-Jose-triage.json` — Parte A. Recibe las solicitudes por webhook (POST), las clasifica con un nodo Switch, consulta la UF en mindicador.cl, registra en una Data Table y responde.
- `ICN292-Lab3-Castillo-Jose-emisor.json` — Envía las 15 solicitudes al webhook del triage. Se ejecuta con el Trigger manual.
- `ICN292-Lab3-Castillo-Jose-resumen.json` — Parte B. Schedule Trigger diario que consolida el registro con Summarize y emite un solo mensaje.

Nota: el triage escribe en una Data Table llamada `registro_devoluciones`, que debe existir en la instancia de n8n antes de ejecutarlo.

 Informe

- `ICN292-Lab3-Castillo-Jose.pdf`
- `ICN292-Lab3-Castillo-Jose.docx`

Capturas de ejecución

- `A-01-exito-flujo-completo.png` — ejecución exitosa del triage
- `A-02-exito-switch-aprobacion.png` — el Switch derivando a la salida APROBACION
- `A-03-ejecucion-fallida.png` — ejecución fallida
- `B-01-mensaje-resumen.png` — mensaje único del resumen diario
- `C-INV-01-sin-id.png` — entrada inválida: id_solicitud vacío
- `C-INV-02-monto-cero.png` — entrada inválida: monto igual a cero
- `C-INV-03-veinte-mil-falla-nodo.png` — entrada inválida que hace fallar un nodo
- `C3-01-limite-monto-igual-U.png` — caso límite: monto exactamente igual a U
- `C3-02-limite-dias-igual-D.png` — caso límite: días exactamente igual a D
- `C4-01-error-de-tipo.png` — error de tipo provocado en la condición del monto
- `C5-01-veinte-mil-falla.png` — solicitud con monto "veinte mil"
- `C5-02-sku-inexistente-pasa.png` — solicitud con SKU inexistente que pasa la validación
