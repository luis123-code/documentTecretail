<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Ejemplo: envíos con estado fallido</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  Este request consulta la tabla <strong><code>OrdenEnvio</code></strong> y filtra únicamente los registros cuyo estado de envío sea <code>fallido</code>.
</p>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1rem; margin-bottom: 1.5rem;">
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M10.29 3.86L1.82 18a2 2 0 0 0 1.71 3h16.94a2 2 0 0 0 1.71-3L13.71 3.86a2 2 0 0 0-3.42 0z"></path><line x1="12" y1="9" x2="12" y2="13"></line><line x1="12" y1="17" x2="12.01" y2="17"></line></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Filtro de estado</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Filtra <code>EstadodelEnvio.NombreSelect = "fallido"</code> a través de la relación LAOT del estado del envío.</p>
  </div>
</div>

<h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Request</h3>

<api>
{
  "url": "tql_module/unified-select-external-laots/OrdenEnvio",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json"
  },
  "body": {
    "where": [
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
    <li><strong>Filtro simple:</strong> un único objeto en <code>where</code> filtra por el estado <code>fallido</code>.</li>
    <li>El token Bearer se ingresa en la pestaña <strong>Auth</strong> del bloque API, no se guarda en el Markdown.</li>
  </ul>
</alert>