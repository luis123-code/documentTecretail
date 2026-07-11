<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Ejemplo: filtro LIKE en provDist</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  Este request consulta la tabla <strong><code>OrdenEnvio</code></strong> y filtra los registros cuyo campo <code>provDist</code> contenga el texto <code>Abancay - Curahuasi</code> usando el operador <code>like</code>.
</p>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1rem; margin-bottom: 1.5rem;">
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Filtro LIKE</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Busca <code>OrdenEnvio.provDist</code> que contenga <code>Abancay - Curahuasi</code> en cualquier posición gracias a los comodines <code>%</code>.</p>
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
        "header": "OrdenEnvio",
        "field": "provDist",
        "operator": "like",
        "value": "%Abancay - Curahuasi%"
      }
    ]
  }
}
</api>

<h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; margin-top: 1.5rem; font-family: Inter, system-ui, sans-serif;">Notas del ejemplo</h3>

<alert type="info">
  <ul>
    <li><strong>Endpoint:</strong> <code>POST /tql_module/unified-select-external-laots/OrdenEnvio</code> apunta a la tabla <code>OrdenEnvio</code>.</li>
    <li><strong>LIKE:</strong> el valor <code>"%Abancay - Curahuasi%"</code> busca el texto en cualquier posición del campo.</li>
    <li><strong>Case sensitivity:</strong> el comportamiento de mayúsculas/minúsculas depende de la configuración del motor de base de datos.</li>
    <li><strong>AND por defecto:</strong> si agregas más condiciones al <code>where</code>, se combinarán con AND automáticamente.</li>
    <li>El token Bearer se ingresa en la pestaña <strong>Auth</strong> del bloque API, no se guarda en el Markdown.</li>
  </ul>
</alert>