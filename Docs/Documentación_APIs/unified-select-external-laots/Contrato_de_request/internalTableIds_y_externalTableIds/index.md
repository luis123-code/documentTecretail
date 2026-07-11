<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">internalTableIds y externalTableIds: expansión de relaciones</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  Ambos parámetros permiten expandir relaciones de tablas en una sola consulta, evitando múltiples requests. Pueden usarse en cualquier funcionalidad del endpoint (<code>where</code>, <code>metrics</code>, <code>groupBy</code>), pero <strong>la lógica interna de cada uno trae una respuesta con estructura diferente</strong>.
</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">internalTableIds</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;">Array de nombres de tablas <strong>LAOT internas</strong> de la tabla consultada.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;">La respuesta <strong>anida</strong> los registros relacionados dentro de cada resultado de la tabla principal.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Ejemplo: <code>"internalTableIds": ["OrdenVenta"]</code> trae las relaciones internas de <code>OrdenVenta</code> dentro de cada registro.</p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">externalTableIds</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;">Array de nombres de tablas <strong>externas</strong> del mismo <code>Enterprise_id</code>.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;">La respuesta trae datos de <strong>múltiples tablas</strong> en una sola consulta, con una estructura diferente a <code>internalTableIds</code>.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Ejemplo: <code>"externalTableIds": ["Boletas", "Facturas", "OrdenEnvio"]</code> trae datos de esas tablas en una sola respuesta.</p>
  </div>
</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.25rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 40px; height: 40px; border-radius: 10px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1rem;">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z"></path><polyline points="3.27 6.96 12 12.01 20.73 6.96"></polyline><line x1="12" y1="22.08" x2="12" y2="12"></line></svg>
    </div>
    <h3 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.5rem; margin-top: 0;">Respuesta internalTableIds</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Cada registro de la tabla principal incluye un objeto anidado por cada tabla interna solicitada. Los datos relacionados quedan <strong>embebidos</strong> dentro del registro padre.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.25rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 40px; height: 40px; border-radius: 10px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1rem;">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle><line x1="2" y1="12" x2="22" y2="12"></line><path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"></path></svg>
    </div>
    <h3 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.5rem; margin-top: 0;">Respuesta externalTableIds</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">La respuesta incluye datos de las tablas externas solicitadas con una <strong>estructura plana o separada</strong>, diferente a la anidación de <code>internalTableIds</code>.</p>
  </div>
</div>

<div style="border-left: 4px solid #F59E0B; background-color: #FFFBEB; border-radius: 0.5rem; padding: 1rem 1.25rem; margin-bottom: 1.5rem;">
  <p style="margin: 0; font-size: 13px; color: #92400E; line-height: 1.7;">
    <strong>Importante:</strong> ambos parámetros pueden combinarse en el mismo request, pero la <strong>estructura de la respuesta cambia</strong> según se use <code>internalTableIds</code>, <code>externalTableIds</code> o ambos. El programador debe revisar la estructura devuelta antes de consumirla.
  </p>
</div>

<h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; margin-top: 1.5rem; font-family: Inter, system-ui, sans-serif;">Ejemplos</h3>

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem; font-family: Inter, system-ui, sans-serif;">Expansión interna con filtro where</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Consulta <code>DetOrdVent</code> filtrando por rango de fechas de <code>OrdenVen</code> y expande las relaciones internas de <code>OrdenVenta</code> y <code>Contact</code>. La respuesta anida los datos de ambas tablas dentro de cada registro.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>internalTableIds:</strong> <code>["OrdenVenta", "Contact"]</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>header en where:</strong> <code>"header": "OrdenVen"</code> indica que <code>fecha</code> pertenece a la tabla LAOT <code>OrdenVen</code>.</li>
        <li><strong>Anidación:</strong> cada registro incluye los datos de <code>OrdenVenta</code> y <code>Contact</code> anidados.</li>
        <li><strong>AND por defecto:</strong> ambas condiciones de fecha se combinan con AND.</li>
        <li>Token Bearer en pestaña <strong>Auth</strong>, no se guarda en Markdown.</li>
      </ul>
    </div>
  </div>
</div>

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
        "operator": "&​gt;=",
        "value": "2026-01-01T00:00:00.000Z"
      },
      {
        "header": "OrdenVen",
        "field": "fecha",
        "operator": "&​lt;=",
        "value": "2027-01-01T00:00:00.000Z"
      }
    ],
    "internalTableIds": [
      "OrdenVenta",
      "Contact"
    ]
  }
}
</api>

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 2rem; font-family: Inter, system-ui, sans-serif;">Expansión externa con paginación</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Consulta paginada de <code>Facturas</code> con <code>?limit=200&​amp;offset=0</code> y expande 8 tablas externas: Boletas, Facturas, OrdenEnvio, CuentasPorCobrar, Movimientos, Contactx, OrdenVenta y DetOrdVent. La respuesta trae datos de todas esas tablas en una sola consulta.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>externalTableIds:</strong> 8 tablas externas</p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>Paginación:</strong> <code>?limit=200</code> trae 200 registros, <code>&offset=0</code> empieza desde el primero.</li>
        <li><strong>Múltiples tablas:</strong> una sola consulta trae datos de 8 tablas externas.</li>
        <li><strong>Estructura diferente:</strong> la respuesta no anida como <code>internalTableIds</code>.</li>
        <li>Token Bearer en pestaña <strong>Auth</strong>, no se guarda en Markdown.</li>
      </ul>
    </div>
  </div>
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

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 2rem; font-family: Inter, system-ui, sans-serif;">Expansión interna con filtro IN de estados</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Consulta <code>DetOrdVent</code> filtrando por rango de fechas y por estados de venta con <code>IN</code>, expandiendo la tabla interna <code>OrdenVenta</code>. La respuesta anida los datos de <code>OrdenVenta</code> dentro de cada registro de detalle.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>internalTableIds:</strong> <code>["OrdenVenta"]</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>IN con header:</strong> <code>"header": "OrdenVen"</code> filtra estados de la tabla LAOT <code>OrdenVen</code>.</li>
        <li><strong>Una sola tabla interna:</strong> <code>OrdenVenta</code> se anida en cada resultado.</li>
        <li><strong>AND por defecto:</strong> las 3 condiciones del <code>where</code> se combinan con AND.</li>
        <li>Token Bearer en pestaña <strong>Auth</strong>, no se guarda en Markdown.</li>
      </ul>
    </div>
  </div>
</div>

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
        "operator": "&​gt;=",
        "value": "2026-01-01T00:00:00.000Z"
      },
      {
        "header": "OrdenVen",
        "field": "fecha",
        "operator": "&​lt;=",
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

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 2rem; font-family: Inter, system-ui, sans-serif;">Combinación de internalTableIds y externalTableIds</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Consulta <code>OrdenVenta</code> expandiendo tanto la tabla interna <code>DetOrdVent</code> como tablas externas <code>Facturas</code> y <code>Contactx</code>. La respuesta combina ambas estructuras: anidación interna + datos externos planos.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>Ambos:</strong> <code>internalTableIds</code> + <code>externalTableIds</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>Combinación:</strong> ambos parámetros pueden usarse en el mismo request.</li>
        <li><strong>Estructura mixta:</strong> la respuesta tiene anidación interna + datos externos.</li>
        <li><strong>Revisar respuesta:</strong> el programador debe inspeccionar la estructura devuelta.</li>
        <li>Token Bearer en pestaña <strong>Auth</strong>, no se guarda en Markdown.</li>
      </ul>
    </div>
  </div>
</div>

<api>
{
  "url": "tql_module/unified-select-external-laots/OrdenVenta",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json"
  },
  "body": {
    "internalTableIds": [
      "DetOrdVent"
    ],
    "externalTableIds": [
      "Facturas",
      "Contactx"
    ]
  }
}
</api>