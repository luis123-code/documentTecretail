<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Where: filtros de consulta</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  El bloque <code>where</code> es un array de condiciones. Cada condición especifica <code>header</code> (tabla LAOT relacionada), <code>field</code> (campo a filtrar), <code>operator</code> (tipo de comparación) y <code>value</code> (valor a comparar). Todas las condiciones se combinan con <strong>AND</strong> por defecto.
</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Estructura de una condición</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;"><code>header</code> — Nombre de la tabla LAOT donde está el campo. Opcional si el campo pertenece a la tabla principal.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;"><code>field</code> — Nombre del campo a filtrar dentro de la tabla.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;"><code>operator</code> — Operador de comparación: <code>=</code>, <code>!=</code>, <code>&​gt;=</code>, <code>&​lt;=</code>, <code>&​gt;</code>, <code>&​lt;</code>, <code>IN</code>, <code>like</code>, <code>IN_YEAR</code>, etc.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><code>value</code> — Valor a comparar. Puede ser string, número, fecha o array (para <code>IN</code>).</p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Combinación AND por defecto</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Cuando se incluyen múltiples condiciones en el array <code>where</code>, se combinan automáticamente con <strong>AND</strong>. No es necesario especificar el operador lógico explícitamente.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Ejemplo: dos condiciones de fecha <code>&​gt;= 2024-01-01</code> y <code>&​lt;= 2026-07-11</code> se interpretan como <code>fecha &​gt;= 2024-01-01 AND fecha &​lt;= 2026-07-11</code>.</p>
  </div>
</div>

<h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; margin-top: 1.5rem; font-family: Inter, system-ui, sans-serif;">Ejemplos</h3>

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem; font-family: Inter, system-ui, sans-serif;">Filtro por rango de fechas y estados con IN</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Filtra <code>OrdenVenta</code> por rango de fechas con <code>&​gt;=</code> y <code>&​lt;=</code>, y restringe <code>StatusVent</code> a múltiples valores con <code>IN</code>. Ambas condiciones se combinan con AND automáticamente.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>Operadores usados:</strong> <code>&​gt;=</code>, <code>&​lt;=</code>, <code>IN</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>IN:</strong> acepta un array de valores. El registro coincide si el campo es igual a cualquiera.</li>
        <li><strong>AND por defecto:</strong> las 3 condiciones se combinan con AND.</li>
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
    ]
  }
}
</api>

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 2rem; font-family: Inter, system-ui, sans-serif;">Filtro por rango de fechas con expansión interna</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Filtra <code>OrdenVenta</code> por rango de fechas y expande relaciones internas de <code>OrdenVenta</code> y <code>Contact</code> usando <code>internalTableIds</code>.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>Operadores usados:</strong> <code>&​gt;=</code>, <code>&​lt;=</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>internalTableIds:</strong> expande LAOTs internas, la respuesta anida los registros relacionados.</li>
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

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 2rem; font-family: Inter, system-ui, sans-serif;">Filtro por estado con igualdad simple</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Filtra <code>OrdenEnvio</code> donde el estado sea <code>fallido</code> usando el operador <code>=</code> con <code>header</code> para referenciar la tabla LAOT <code>EstadodelEnvio</code>.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>Operadores usados:</strong> <code>=</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>header:</strong> indica que <code>NombreSelect</code> pertenece a la tabla LAOT <code>EstadodelEnvio</code>.</li>
        <li><strong>=:</strong> comparación exacta de un solo valor.</li>
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

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 2rem; font-family: Inter, system-ui, sans-serif;">Filtro con operador like</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Busca en <code>OrdenEnvio</code> los registros donde <code>provDist</code> contenga <code>%Abancay - Curahuasi%</code> usando el operador <code>like</code> con comodines <code>%</code>.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>Operadores usados:</strong> <code>like</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>like:</strong> usa <code>%</code> como comodín. <code>%texto%</code> busca coincidencias parciales.</li>
        <li><strong>Case sensitivity:</strong> depende de la configuración del backend.</li>
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

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 2rem; font-family: Inter, system-ui, sans-serif;">Filtro con IN_YEAR y métricas agregadas</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Filtra <code>OrdenVenta</code> por el año <code>2024</code> con <code>IN_YEAR</code> (sin rangos manuales) y por estados con <code>IN</code>. Calcula SUM de ventas, SUM de promociones y COUNT de ventas.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>Operadores usados:</strong> <code>IN_YEAR</code>, <code>IN</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>IN_YEAR:</strong> filtra por año completo con un solo valor string.</li>
        <li><strong>SUM con header:</strong> usa <code>"header": "Promocion"</code> para sumar <code>valor</code> del LAOT.</li>
        <li><strong>AND por defecto:</strong> IN_YEAR e IN se combinan con AND.</li>
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
    ]
  }
}
</api>

<h4 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 2rem; font-family: Inter, system-ui, sans-serif;">Filtro múltiple con where y groupBy</h4>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Filtra <code>OrdenEnvio</code> por tipo de orden <code>courier</code>, rango de fecha programada y estado <code>fallido</code>. Agrupa y calcula métricas en una sola consulta.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><strong>Operadores usados:</strong> <code>=</code>, <code>&​gt;=</code>, <code>&​lt;</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Notas</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>4 condiciones:</strong> tipo, fecha desde, fecha hasta y estado, todas con AND.</li>
        <li><strong>header:</strong> cada condición puede referenciar una tabla LAOT distinta.</li>
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
        "operator": "&​gt;=",
        "value": "2026-01-01"
      },
      {
        "header": "OrdenEnvio",
        "field": "fechaProgramada",
        "operator": "&​lt;",
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