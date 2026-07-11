<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Consulta paginada de Facturas con expansión externa</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  Este request consulta la tabla <strong><code>Facturas</code></strong> con paginación mediante <code>limit</code> y <code>offset</code> en la URL, y expande relaciones externas de múltiples tablas usando <code>externalTableIds</code> en el body.
</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Paginación con limit y offset</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;"><code>?limit=200</code> indica cuántos registros traer por página. <code>&offset=0</code> indica desde qué posición empezar. Para la siguiente página, usar <code>offset=200</code>, luego <code>offset=400</code>, etc.</p>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem;">Expansión externa</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;"><code>externalTableIds</code> expande relaciones de tablas externas en una sola consulta: Boletas, Facturas, OrdenEnvio, CuentasPorCobrar, Movimientos, Contactx, OrdenVenta y DetOrdVent.</p>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem;">Diferencia con internalTableIds</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><code>internalTableIds</code> expande LAOTs internas de la tabla. <code>externalTableIds</code> trae datos relacionados de otras tablas del mismo Enterprise.</p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; margin-top: 0;">Patrones de endpoints</h3>
    <table style="width: 100%; border-collapse: collapse; font-size: 12px;">
      <thead>
        <tr style="border-bottom: 2px solid #e5e7eb;">
          <th style="padding: 6px 10px; text-align: left; font-weight: 600; background-color: #f9fafb; color: #121212;">Tipo de endpoint</th>
          <th style="padding: 6px 10px; text-align: left; font-weight: 600; background-color: #f9fafb; color: #121212;">Patrón</th>
        </tr>
      </thead>
      <tbody>
        <tr style="border-bottom: 1px solid #e5e7eb;">
          <td style="padding: 6px 10px; color: #6B6B6B;">Filtro por campo con like</td>
          <td style="padding: 6px 10px; color: #121212;"><code>Búsqueda de [entidad] por [campo]</code></td>
        </tr>
        <tr style="border-bottom: 1px solid #e5e7eb;">
          <td style="padding: 6px 10px; color: #6B6B6B;">Filtro por tabla dinámica</td>
          <td style="padding: 6px 10px; color: #121212;"><code>Consulta dinámica por tabla</code></td>
        </tr>
        <tr style="border-bottom: 1px solid #e5e7eb;">
          <td style="padding: 6px 10px; color: #6B6B6B;">Con limit/offset</td>
          <td style="padding: 6px 10px; color: #121212;"><code>Consulta paginada de [entidad]</code></td>
        </tr>
        <tr style="border-bottom: 1px solid #e5e7eb;">
          <td style="padding: 6px 10px; color: #6B6B6B;">Métricas agregadas</td>
          <td style="padding: 6px 10px; color: #121212;"><code>Métricas de [entidad]</code></td>
        </tr>
        <tr>
          <td style="padding: 6px 10px; color: #6B6B6B;">Agrupación + métricas</td>
          <td style="padding: 6px 10px; color: #121212;"><code>Resumen agrupado de [entidad]</code></td>
        </tr>
      </tbody>
    </table>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem;">Ejemplos del patrón paginado</h3>
    <ul style="font-size: 13px; color: #6B6B6B; line-height: 1.7; padding-left: 1.25rem; margin: 0;">
      <li>Consulta paginada de detalle de orden de venta</li>
      <li>Consulta paginada de comprobantes</li>
      <li>Consulta paginada de motorizados</li>
      <li>Consulta paginada de órdenes de envío</li>
    </ul>
  </div>
</div>

<h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Notas del ejemplo</h3>

<div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem; margin-bottom: 1.5rem;">
  <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
    <li><strong>Endpoint:</strong> <code>POST /tql_module/unified-select-external-laots/Facturas?limit=200&​amp;offset=0</code> apunta a la tabla <code>Facturas</code> con paginación.</li>
    <li><strong>limit:</strong> número máximo de registros por página. Se recomienda no exceder 500.</li>
    <li><strong>offset:</strong> posición inicial. Para página 2 usar <code>offset=200</code>, página 3 <code>offset=400</code>, etc.</li>
    <li><strong>externalTableIds:</strong> expande datos de tablas externas en una sola consulta, evitando múltiples requests.</li>
    <li><strong>AND por defecto:</strong> si agregas condiciones al <code>where</code>, se combinan con AND automáticamente.</li>
    <li>El token Bearer se ingresa en la pestaña <strong>Auth</strong> del bloque API, no se guarda en el Markdown.</li>
  </ul>
</div>

<api>
{
  "url": "tql_module/unified-select-external-laots/Facturas?limit=200&offset=0",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json"
  },
  "body": {
    "externalTableIds": [
      "Boletas",
      "Facturas",
      "OrdenEnvio",
      "CuentasPorCobrar",
      "Movimientos",
      "Contactx",
      "OrdenVenta",
      "DetOrdVent"
    ]
  }
}
</api>