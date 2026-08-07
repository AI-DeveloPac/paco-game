# paco-game
App de gamification personal

## Check-in de Voz

Página en `checkin.html` — registro de energía/hábitos por voz, 2 veces al día. Guarda texto crudo en la tabla `Checkin-Voz` de la base Airtable `Personal`; la estructuración de campos se hace después, a demanda, en una sesión de Claude.

**Setup en el iPhone:**
1. Crear un PAT dedicado en [airtable.com/create/tokens](https://airtable.com/create/tokens): scopes `data.records:read` + `data.records:write`, acceso a la base `Personal`, expira a 90 días.
2. Abrir `https://ai-developac.github.io/paco-game/checkin.html`, pegar el PAT.
3. **Agregar a pantalla de inicio** (obligatorio — Safari borra `localStorage` en ~7 días si no está instalada).

**Recordatorios (iOS Shortcuts, sin código):**
1. App Shortcuts → pestaña Automatización → "+" → Crear Automatización Personal → Hora del día → 12:00 PM, se repite diario.
2. Añadir acción "Hablar texto" con el texto: `Hora de tu check-in de energía`.
3. Añadir acción "Abrir URLs" con `https://ai-developac.github.io/paco-game/checkin.html`.
4. Desactivar "Preguntar antes de ejecutar" para que corra sola.
5. Repetir todo para las 9:00 PM con el texto `Hora de tu check-in de la noche`.
