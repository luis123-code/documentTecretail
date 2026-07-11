<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Ejemplo: órdenes de envío courier fallidas</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  Este request apunta a la tabla <strong><code>OrdenEnvio</code></strong> y filtra las órdenes de tipo <code>courier</code> programadas durante el año 2026 cuyo estado de envío es <code>fallido</code>.
</p>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1rem; margin-bottom: 1.5rem;">
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="7" width="20" height="14" rx="2" ry="2"></rect><path d="M16 21V5a2 2 0 0 0-2-2h-4a2 2 0 0 0-2 2v16"></path></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Tipo de orden</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Filtra <code>tipoOrden.NombreSelect = "courier"</code> usando el campo anidado de la relación LAOT.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"></rect><line x1="16" y1="2" x2="16" y2="6"></line><line x1="8" y1="2" x2="8" y2="6"></line><line x1="3" y1="10" x2="21" y2="10"></line></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Rango de fechas</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Filtra <code>OrdenEnvio.fechaProgramada</code> desde <code>2026-01-01</code> inclusive hasta antes de <code>2027-01-01</code> usando <code>&​gt;=</code> y <code>&​lt;</code>.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M10.29 3.86L1.82 18a2 2 0 0 0 1.71 3h16.94a2 2 0 0 0 1.71-3L13.71 3.86a2 2 0 0 0-3.42 0z"></path><line x1="12" y1="9" x2="12" y2="13"></line><line x1="12" y1="17" x2="12.01" y2="17"></line></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Estado fallido</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Filtra <code>EstadodelEnvio.NombreSelect = "fallido"</code> a través del LAOT de estado del envío.</p>
  </div>
</div>

<h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Request</h3>

<api>
{
  "url": "https://bks.tecretail.org/tql_module/unified-select-external-laots/OrdenEnvio",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json"
  },
  "body": {
    "where": [
      {
        "header": "tipoOrden",
        "field": "NombreSelect",
        "operator": "=",
        "value": "courier"
      },
      {
        "header": "OrdenEnvio",
        "field": "fechaProgramada",
        "operator": ">=",
        "value": "2026-01-01"
      },
      {
        "header": "OrdenEnvio",
        "field": "fechaProgramada",
        "operator": "<",
        "value": "2027-01-01"
      },
      {
        "header": "EstadodelEnvio",
        "field": "NombreSelect",
        "operator": "=",
        "value": "fallido"
      }
    ]
  }
}
</api>

<h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; margin-top: 1.5rem; font-family: Inter, system-ui, sans-serif;">Notas del ejemplo</h3>

<alert type="info">
  <ul>
    <li><strong>Endpoint:</strong> <code>POST /tql_module/unified-select-external-laots/OrdenEnvio</code> apunta a la tabla <code>OrdenEnvio</code>.</li>
    <li><strong><code>tipoOrden.NombreSelect</code>:</strong> relación LAOT que indica el tipo de orden; en este caso <code>courier</code>.</li>
    <li><strong><code>OrdenEnvio.fechaProgramada</code>:</strong> campo directo de la tabla; usa <code>&​gt;=</code> y <code>&​lt;</code> para definir el rango anual.</li>
    <li><strong><code>EstadodelEnvio.NombreSelect</code>:</strong> relación LAOT que indica el estado del envío; en este caso <code>fallido</code>.</li>
    <li>El token Bearer se ingresa en la pestaña <strong>Auth</strong> del bloque API, no se guarda en el Markdown.</li>
  </ul>
</alert>