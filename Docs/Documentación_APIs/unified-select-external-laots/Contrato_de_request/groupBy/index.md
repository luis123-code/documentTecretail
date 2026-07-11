<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">groupBy: agrupación de resultados</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  El bloque <code>groupBy</code> es un objeto que agrupa los resultados por un campo específico. Se compone de <code>columna</code> (nombre del campo por el cual agrupar) y <code>alias</code> (nombre con el que aparece el grupo en la respuesta). Se usa junto a <code>metrics</code> para calcular agregaciones por cada grupo.
</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Estructura de groupBy</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;"><code>columna</code> — Nombre del campo de la tabla por el cual agrupar los resultados.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;"><code>alias</code> — Nombre con el que se identifica el grupo en la respuesta JSON.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Ambos campos son obligatorios cuando se usa <code>groupBy</code>.</p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Combinación con metrics</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Cuando se usa <code>groupBy</code> junto a <code>metrics</code>, cada métrica se calcula de forma independiente para cada grupo. El resultado es un array donde cada elemento tiene el <code>alias</code> del grupo y los <code>alias</code> de cada métrica.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Sin <code>metrics</code>, <code>groupBy</code> devuelve los registros agrupados sin agregación.</p>
  </div>
</div>

<div style="border-left: 4px solid #F59E0B; background-color: #FFFBEB; border-radius: 0.5rem; padding: 1rem 1.25rem; margin-bottom: 1.5rem;">
  <p style="margin: 0; font-size: 13px; color: #92400E; line-height: 1.7;">
    <strong>Importante:</strong> <code>groupBy</code> solo acepta una columna por consulta. Si necesitas agrupar por múltiples dimensiones, debes hacer consultas separadas o usar <code>externalTableIds</code> para expandir tablas relacionadas y agrupar por sus campos.
  </p>
</div>

<h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; margin-top: 1.5rem; font-family: Inter, system-ui, sans-serif;">Ejemplos</h3>

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem; font-family: Inter, system-ui, sans-serif;">Agrupación por canal con múltiples métricas</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Consulta <code>OrdenVenta</code> filtrando por año <code>2024</code> y estados, agrupando por <code>Canal_18</code> con alias <code>canal</code>. Calcula SUM de ventas, SUM de promociones (con <code>header</code> LAOT) y COUNT de ventas, todo por cada canal.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>groupBy:</strong> <code>columna: "Canal_18"</code>, <code>alias: "canal"</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>columna:</strong> <code>Canal_18</code> es el campo de la tabla por el que se agrupa.</li>
        <li><strong>alias:</strong> el grupo aparece como <code>canal</code> en cada elemento de la respuesta.</li>
        <li><strong>3 métricas por grupo:</strong> SUM, SUM con header y COUNT se calculan por canal.</li>
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

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 2rem; font-family: Inter, system-ui, sans-serif;">Agrupación por canal con rango de fechas manual</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Misma agrupación por <code>Canal_18</code> pero con rango de fechas manual usando <code>&​gt;=</code> y <code>&​lt;=</code> en lugar de <code>IN_YEAR</code>. Calcula las mismas 3 métricas por canal.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>groupBy:</strong> <code>columna: "Canal_18"</code>, <code>alias: "canal"</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>Rango manual:</strong> <code>&​gt;=</code> y <code>&​lt;=</code> como alternativa a <code>IN_YEAR</code>.</li>
        <li><strong>Respuesta:</strong> cada elemento tiene <code>canal</code>, <code>monto_ventas</code>, <code>monto_promociones</code> y <code>cantidad_ventas</code>.</li>
        <li><strong>AND por defecto:</strong> las 3 condiciones del <code>where</code> se combinan con AND.</li>
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
    "where": [
      {
        "field": "fecha",
        "operator": "&​gt;=",
        "value": "2024-01-01T05:00:00.000Z"
      },
      {
        "field": "fecha",
        "operator": "&​lt;=",
        "value": "2026-07-11T04:59:59.999Z"
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
    },
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
    ]
  }
}
</api>

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 2rem; font-family: Inter, system-ui, sans-serif;">Agrupación con COUNT simple</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Agrupa <code>OrdenEnvio</code> por <code>provDist</code> con alias <code>provincia</code> y cuenta cuántos envíos hay por cada provincia. Sin filtro <code>where</code>, cuenta todos los registros agrupados.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>groupBy:</strong> <code>columna: "provDist"</code>, <code>alias: "provincia"</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>Sin where:</strong> agrupa todos los registros sin filtro previo.</li>
        <li><strong>COUNT sin field:</strong> cuenta todos los registros de cada grupo.</li>
        <li><strong>Respuesta:</strong> cada elemento tiene <code>provincia</code> y <code>total</code>.</li>
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
        "alias": "total"
      }
    ],
    "groupBy": {
      "columna": "provDist",
      "alias": "provincia"
    }
  }
}
</api>

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 2rem; font-family: Inter, system-ui, sans-serif;">Agrupación con SUM y filtro multiple</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Agrupa <code>OrdenEnvio</code> por <code>tipoOrden.NombreSelect</code> con alias <code>tipo</code>, filtra por estado <code>fallido</code> y suma el campo <code>Monto</code> por cada tipo de orden.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>groupBy:</strong> <code>columna: "provDist"</code>, <code>alias: "provincia"</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>groupBy con campo LAOT:</strong> <code>columna</code> puede referenciar un campo de la tabla principal.</li>
        <li><strong>SUM por grupo:</strong> cada tipo de orden tiene su propio total de <code>Monto</code>.</li>
        <li><strong>AND por defecto:</strong> el filtro del <code>where</code> se aplica antes de agrupar.</li>
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
        "alias": "total_monto"
      }
    ],
    "where": [
      {
        "header": "EstadodelEnvio",
        "field": "NombreSelect",
        "operator": "=",
        "value": "fallido"
      }
    ],
    "groupBy": {
      "columna": "provDist",
      "alias": "provincia"
    }
  }
}
</api>