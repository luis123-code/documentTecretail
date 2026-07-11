<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Metrics: agregaciones</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  El bloque <code>metrics</code> es un array de operaciones de agregación. Cada métrica especifica <code>operation</code> (tipo de cálculo), <code>field</code> (campo a calcular), <code>alias</code> (nombre del resultado en la respuesta) y opcionalmente <code>header</code> (tabla LAOT donde está el campo). Se puede combinar con <code>where</code> para filtrar antes de agregar y con <code>groupBy</code> para agrupar los resultados.
</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Estructura de una métrica</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;"><code>operation</code> — Tipo de agregación: <code>SUM</code>, <code>COUNT</code>, <code>AVG</code>, <code>MIN</code>, <code>MAX</code>.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;"><code>field</code> — Campo sobre el que se aplica la operación. En <code>COUNT</code> puede omitirse para contar todos los registros.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;"><code>alias</code> — Nombre con el que aparece el resultado en la respuesta JSON.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><code>header</code> — Opcional. Tabla LAOT donde está el campo. Permite agregar campos de relaciones externas.</p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Operaciones soportadas</h3>
    <table style="width: 100%; border-collapse: collapse; font-size: 12px;">
      <thead>
        <tr style="border-bottom: 2px solid #e5e7eb;">
          <th style="padding: 6px 10px; text-align: left; font-weight: 600; background-color: #f9fafb; color: #121212;">Operación</th>
          <th style="padding: 6px 10px; text-align: left; font-weight: 600; background-color: #f9fafb; color: #121212;">Descripción</th>
        </tr>
      </thead>
      <tbody>
        <tr style="border-bottom: 1px solid #e5e7eb;">
          <td style="padding: 6px 10px; color: #121212; font-weight: 500;"><code>SUM</code></td>
          <td style="padding: 6px 10px; color: #6B6B6B;">Suma todos los valores del campo.</td>
        </tr>
        <tr style="border-bottom: 1px solid #e5e7eb;">
          <td style="padding: 6px 10px; color: #121212; font-weight: 500;"><code>COUNT</code></td>
          <td style="padding: 6px 10px; color: #6B6B6B;">Cuenta los registros (o los no nulos del campo).</td>
        </tr>
        <tr style="border-bottom: 1px solid #e5e7eb;">
          <td style="padding: 6px 10px; color: #121212; font-weight: 500;"><code>AVG</code></td>
          <td style="padding: 6px 10px; color: #6B6B6B;">Promedio de los valores del campo.</td>
        </tr>
        <tr style="border-bottom: 1px solid #e5e7eb;">
          <td style="padding: 6px 10px; color: #121212; font-weight: 500;"><code>MIN</code></td>
          <td style="padding: 6px 10px; color: #6B6B6B;">Valor mínimo del campo.</td>
        </tr>
        <tr>
          <td style="padding: 6px 10px; color: #121212; font-weight: 500;"><code>MAX</code></td>
          <td style="padding: 6px 10px; color: #6B6B6B;">Valor máximo del campo.</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>

<div style="border-left: 4px solid #F59E0B; background-color: #FFFBEB; border-radius: 0.5rem; padding: 1rem 1.25rem; margin-bottom: 1.5rem;">
  <p style="margin: 0; font-size: 13px; color: #92400E; line-height: 1.7;">
    <strong>Importante:</strong> el array <code>metrics</code> admite múltiples operaciones en una sola consulta. Cada una se calcula de forma independiente sobre los mismos registros filtrados por <code>where</code>. Si se usa junto a <code>groupBy</code>, las métricas se calculan por cada grupo.
  </p>
</div>

<h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; margin-top: 1.5rem; font-family: Inter, system-ui, sans-serif;">Ejemplos</h3>

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem; font-family: Inter, system-ui, sans-serif;">COUNT simple con filtro</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Cuenta los registros de <code>OrdenEnvio</code> con estado <code>fallido</code>. El resultado se devuelve bajo el alias <code>num</code>.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>Operación:</strong> <code>COUNT</code> sin <code>field</code> → cuenta todos los registros.</p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>COUNT sin field:</strong> cuenta todos los registros que cumplen el filtro.</li>
        <li><strong>alias:</strong> el resultado aparece como <code>num</code> en la respuesta.</li>
        <li>Token Bearer en pestaña <strong>Auth</strong>, no se guarda en Markdown.</li>
      </ul>
    </div>
  </div>
</div>

<api>
{
  "url": "tql_module/unified-select-external-laots/OrdenEnvio",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json"
  },
  "body": {
    "metrics": [
      {
        "operation": "COUNT",
        "alias": "num"
      }
    ],
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

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 2rem; font-family: Inter, system-ui, sans-serif;">COUNT con field específico</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Cuenta los registros no nulos del campo <code>Monto</code> en <code>OrdenEnvio</code> con estado <code>fallido</code>. Incluir <code>field</code> hace que <code>COUNT</code> solo cuente registros donde ese campo no sea null.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>Operación:</strong> <code>COUNT</code> con <code>field: "Monto"</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>COUNT con field:</strong> cuenta registros donde <code>Monto</code> no es null.</li>
        <li><strong>Diferencia:</strong> sin <code>field</code> cuenta todos; con <code>field</code> solo no nulos.</li>
        <li>Token Bearer en pestaña <strong>Auth</strong>, no se guarda en Markdown.</li>
      </ul>
    </div>
  </div>
</div>

<api>
{
  "url": "tql_module/unified-select-external-laots/OrdenEnvio",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json"
  },
  "body": {
    "metrics": [
      {
        "operation": "COUNT",
        "field": "Monto",
        "alias": "num"
      }
    ],
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

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 2rem; font-family: Inter, system-ui, sans-serif;">SUM con filtro</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Suma los valores del campo <code>Monto</code> en <code>OrdenEnvio</code> donde el estado sea <code>fallido</code>. El resultado se devuelve bajo el alias <code>num</code>.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>Operación:</strong> <code>SUM</code> con <code>field: "Monto"</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>SUM:</strong> suma todos los valores numéricos del campo.</li>
        <li><strong>alias:</strong> el resultado aparece como <code>num</code> en la respuesta.</li>
        <li>Token Bearer en pestaña <strong>Auth</strong>, no se guarda en Markdown.</li>
      </ul>
    </div>
  </div>
</div>

<api>
{
  "url": "tql_module/unified-select-external-laots/OrdenEnvio",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json"
  },
  "body": {
    "metrics": [
      {
        "operation": "SUM",
        "field": "Monto",
        "alias": "num"
      }
    ],
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

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 2rem; font-family: Inter, system-ui, sans-serif;">Múltiples métricas con groupBy</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Consulta <code>OrdenVenta</code> filtrando por año <code>2024</code> y estados, agrupando por <code>Canal_18</code>. Calcula 3 métricas en una sola consulta: SUM de ventas, SUM de promociones (con <code>header</code> LAOT) y COUNT de ventas.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>Operaciones:</strong> <code>SUM</code>, <code>SUM</code> con <code>header</code>, <code>COUNT</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>groupBy:</strong> <code>columna: "Canal_18"</code> agrupa por canal; alias <code>canal</code>.</li>
        <li><strong>SUM con header:</strong> <code>"header": "Promocion"</code> suma <code>valor</code> del LAOT externo.</li>
        <li><strong>3 métricas:</strong> cada una se calcula por grupo de canal.</li>
        <li><strong>AND por defecto:</strong> las condiciones del <code>where</code> se combinan con AND.</li>
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
    "metrics": [
      {
        "operation": "SUM",
        "field": "total",
        "alias": "monto_ventas"
      },
      {
        "operation": "SUM",
        "field": "valor",
        "header": "Promocion",
        "alias": "monto_promociones"
      },
      {
        "operation": "COUNT",
        "field": "total",
        "alias": "cantidad_ventas"
      }
    ],
    "where": [
      {
        "field": "fecha",
        "operator": "IN_YEAR",
        "value": "2024"
      },
      {
        "header": "StatusVent",
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
    "groupBy": {
      "columna": "Canal_18",
      "alias": "canal"
    }
  }
}
</api>