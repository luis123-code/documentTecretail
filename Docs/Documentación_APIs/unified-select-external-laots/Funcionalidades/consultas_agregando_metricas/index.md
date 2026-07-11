<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Ejemplo: contar envíos fallidos</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  Este request apunta a la tabla <strong><code>OrdenEnvio</code></strong> y cuenta cuántos registros tienen el estado <code>fallido</code>, devolviendo el resultado bajo el alias <code>num</code>.
</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Métrica COUNT</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">La operación <code>COUNT</code> devuelve el número total de registros que cumplen el filtro, expuesto con el alias <code>num</code>.</p>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem;">Filtro de estado</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Filtra <code>EstadodelEnvio.NombreSelect = "fallido"</code> antes de contar.</p>

<h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; margin-top: 1.5rem; font-family: Inter, system-ui, sans-serif;">Notas del ejemplo</h3>

<div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem; margin-bottom: 1rem;">
  <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
    <li><strong>Endpoint:</strong> <code>POST /tql_module/unified-select-external-laots/OrdenEnvio</code> apunta a la tabla <code>OrdenEnvio</code>.</li>
    <li><strong>COUNT:</strong> devuelve el total de registros que cumplen el filtro bajo el alias <code>num</code>.</li>
    <li><strong>Múltiples métricas:</strong> el array <code>metrics</code> admite más objetos si necesitas agregar otras operaciones.</li>
    <li><strong>AND por defecto:</strong> si agregas más condiciones al <code>where</code>, se combinarán con AND automáticamente.</li>
    <li>El token Bearer se ingresa en la pestaña <strong>Auth</strong> del bloque API, no se guarda en el Markdown.</li>
  </ul>
</div>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Request</h3>

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
  </div>
</div>
<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Ejemplo: contar montos de envíos fallidos</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  Este request apunta a la tabla <strong><code>OrdenEnvio</code></strong> y cuenta los valores del campo <code>Monto</code> cuyo estado de envío sea <code>fallido</code>, devolviendo el resultado bajo el alias <code>num</code>.
</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Métrica COUNT</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">La operación <code>COUNT</code> sobre el campo <code>Monto</code> devuelve el número total de registros que cumplen el filtro, expuesto con el alias <code>num</code>.</p>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem;">Filtro de estado</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Filtra <code>EstadodelEnvio.NombreSelect = "fallido"</code> antes de contar.</p>

<h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; margin-top: 1.5rem; font-family: Inter, system-ui, sans-serif;">Notas del ejemplo</h3>

<div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem; margin-bottom: 1rem;">
  <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
    <li><strong>Endpoint:</strong> <code>POST /tql_module/unified-select-external-laots/OrdenEnvio</code> apunta a la tabla <code>OrdenEnvio</code>.</li>
    <li><strong>COUNT con field:</strong> al incluir <code>"field": "Monto"</code>, la operación cuenta los registros no nulos de ese campo.</li>
    <li><strong>Múltiples métricas:</strong> el array <code>metrics</code> admite más objetos si necesitas agregar otras operaciones.</li>
    <li><strong>AND por defecto:</strong> si agregas más condiciones al <code>where</code>, se combinarán con AND automáticamente.</li>
    <li>El token Bearer se ingresa en la pestaña <strong>Auth</strong> del bloque API, no se guarda en el Markdown.</li>
  </ul>
</div>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Request</h3>

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
  </div>
</div><h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Ejemplo: sumar montos de envíos fallidos</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  Este request apunta a la tabla <strong><code>OrdenEnvio</code></strong> y suma los valores del campo <code>Monto</code> cuyo estado de envío sea <code>fallido</code>, devolviendo el resultado bajo el alias <code>num</code>.
</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Métrica SUM</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">La operación <code>SUM</code> sobre el campo <code>Monto</code> devuelve la suma total de los valores que cumplen el filtro, expuesto con el alias <code>num</code>.</p>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem;">Filtro de estado</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Filtra <code>EstadodelEnvio.NombreSelect = "fallido"</code> antes de sumar.</p>

<h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; margin-top: 1.5rem; font-family: Inter, system-ui, sans-serif;">Notas del ejemplo</h3>

<div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem; margin-bottom: 1rem;">
  <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
    <li><strong>Endpoint:</strong> <code>POST /tql_module/unified-select-external-laots/OrdenEnvio</code> apunta a la tabla <code>OrdenEnvio</code>.</li>
    <li><strong>SUM con field:</strong> al incluir <code>"field": "Monto"</code>, la operación suma todos los valores de ese campo que cumplan el filtro.</li>
    <li><strong>Múltiples métricas:</strong> el array <code>metrics</code> admite más objetos si necesitas agregar otras operaciones.</li>
    <li><strong>AND por defecto:</strong> si agregas más condiciones al <code>where</code>, se combinarán con AND automáticamente.</li>
    <li>El token Bearer se ingresa en la pestaña <strong>Auth</strong> del bloque API, no se guarda en el Markdown.</li>
  </ul>
</div>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Request</h3>

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
  </div>
</div>
<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Ejemplo: ventas agrupadas por canal con métricas múltiples</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  Este request apunta a la tabla <strong><code>OrdenVenta</code></strong>, filtra por rango de fechas y estados de venta, agrupa por <code>Canal_18</code> y calcula tres métricas: suma de ventas, suma de promociones y cantidad de ventas.
</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Rango de fechas</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Filtra <code>fecha</code> desde <code>2024-01-01</code> hasta <code>2026-07-11</code> con <code>&​gt;=</code> y <code>&​lt;=</code>.</p>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem;">Filtro IN de estados</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Restringe <code>StatusVent</code> a: completada, pendiente, enviado, por fabricar, por enviar y ahorro.</p>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem;">GroupBy por canal</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Agrupa los resultados por <code>Canal_18</code> con el alias <code>canal</code>.</p>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem;">Métricas múltiples</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><code>SUM(total)</code> → <code>monto_ventas</code><br><code>SUM(Promocion.valor)</code> → <code>monto_promociones</code><br><code>COUNT(total)</code> → <code>cantidad_ventas</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; margin-top: 0;">Notas del ejemplo</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem; margin-bottom: 1rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>Endpoint:</strong> <code>POST /tql_module/unified-select-external-laots/OrdenVenta</code></li>
        <li><strong>GroupBy:</strong> <code>columna: "Canal_18"</code> agrupa por canal; alias <code>canal</code>.</li>
        <li><strong>SUM con header:</strong> usa <code>"header": "Promocion"</code> para sumar <code>valor</code> del LAOT.</li>
        <li><strong>Múltiples métricas:</strong> SUM y COUNT en una sola consulta.</li>
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



<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Ejemplo: ventas agrupadas por promociones con metricas multiples </h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  Este request apunta a la tabla <strong><code>OrdenVenta</code></strong>, filtra por el año 2024 con <code>IN_YEAR</code> y por estados de venta, calculando suma de ventas, suma de promociones y cantidad de ventas.
</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Filtro IN_YEAR</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">El operador <code>IN_YEAR</code> filtra <code>fecha</code> por el año <code>2024</code> sin necesidad de rangos manuales.</p>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem;">Filtro IN de estados</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Restringe <code>StatusVent</code> a: completada, pendiente, enviado, por fabricar, por enviar y ahorro.</p>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem;">Métricas múltiples</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><code>SUM(total)</code> → <code>monto_ventas</code><br><code>SUM(Promocion.valor)</code> → <code>monto_promociones</code><br><code>COUNT(total)</code> → <code>cantidad_ventas</code></p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; margin-top: 0;">Notas del ejemplo</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>Endpoint:</strong> <code>POST /tql_module/unified-select-external-laots/OrdenVenta</code></li>
        <li><strong>IN_YEAR:</strong> filtra por año completo con un solo valor, sin rangos manuales.</li>
        <li><strong>SUM con header:</strong> usa <code>"header": "Promocion"</code> para sumar <code>valor</code> del LAOT.</li>
        <li><strong>Múltiples métricas:</strong> SUM y COUNT en una sola consulta.</li>
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
        "value": "2026"
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