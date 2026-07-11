

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  Este request apunta a la tabla <strong><code>DetOrdVent</code></strong>, filtra por un rango de fechas, por un conjunto de estados de venta y expande las relaciones LAOT internas de <code>OrdenVenta</code>.
</p>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1rem; margin-bottom: 1.5rem;">
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"></rect><line x1="16" y1="2" x2="16" y2="6"></line><line x1="8" y1="2" x2="8" y2="6"></line><line x1="3" y1="10" x2="21" y2="10"></line></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Rango de fechas</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Filtra <code>OrdenVen.fecha</code> entre <code>2026-01-01</code> y <code>2027-01-01</code> usando los operadores <code>&​gt;=</code> y <code>&​lt;=</code>.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><polygon points="22 3 2 3 10 12.46 10 19 14 21 14 12.46 22 3"></polygon></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Filtro IN de estados</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Restringe por <code>StatusVent.NombreSelect</code> a los valores: completada, pendiente, enviado, por fabricar, por enviar y ahorro.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="5" r="3"></circle><line x1="12" y1="8" x2="12" y2="12"></line><line x1="12" y1="12" x2="8" y2="16"></line><line x1="12" y1="12" x2="16" y2="16"></line><path d="M8 16a3 3 0 1 0 0 6 3 3 0 0 0 0-6z"></path><path d="M16 16a3 3 0 1 0 0 6 3 3 0 0 0 0-6z"></path></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Expansión interna</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><code>internalTableIds: ["OrdenVenta"]</code> fuerza la expansión completa de las relaciones LAOT internas de <code>OrdenVenta</code>.</p>
  </div>
</div>

<h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Request</h3>

<api>
{
  "url": "tql_module/unified-select-external-laots/DetOrdVent",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json"
  },
  "body": {
    "where": [
      {
        "header": "OrdenVen",
        "field": "fecha",
        "operator": ">=",
        "value": "2026-01-01T00:00:00.000Z"
      },
      {
        "header": "OrdenVen",
        "field": "fecha",
        "operator": "<=",
        "value": "2027-01-01T00:00:00.000Z"
      },
      {
        "header": "OrdenVen",
        "field": "StatusVent.NombreSelect",
        "operator": "IN",
        "value": [
          "completada",
          "pendiente",
          "enviado",
          "por fabricar",
          "por enviar",
          "ahorro"
        ]
      }
    ],
    "internalTableIds": [
      "OrdenVenta"
    ]
  }
}
</api>

<h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; margin-top: 1.5rem; font-family: Inter, system-ui, sans-serif;">Notas del ejemplo</h3>

<alert type="info">
  <ul>
    <li><strong>Endpoint:</strong> <code>POST /tql_module/unified-select-external-laots/DetOrdVent</code> apunta a la tabla <code>DetOrdVent</code>.</li>
    <li><strong>Header <code>OrdenVen</code>:</strong> indica que los campos de filtro pertenecen a la tabla principal del request.</li>
    <li><strong><code>StatusVent.NombreSelect</code>:</strong> campo anidado de una relación LAOT; el operador <code>IN</code> requiere un array de strings.</li>
    <li><strong><code>internalTableIds</code>:</strong> expande relaciones internas de <code>OrdenVenta</code>.</li>
    <li>El token Bearer se ingresa en la pestaña <strong>Auth</strong> del bloque API, no se guarda en el Markdown.</li>
  </ul>
</alert>