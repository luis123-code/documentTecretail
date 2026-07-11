<p style="font-size: 12px; font-weight: 600; color: rgb(17, 82, 51); text-transform: uppercase; letter-spacing: 0.06em; margin-bottom: 0.75rem; font-family: Inter, system-ui, sans-serif;">
  Módulo TQL · API
</p>

<div style="display: inline-flex; align-items: center; gap: 0.4rem; padding: 0.35rem 0.9rem; border-radius: 999px; border: 1px solid rgb(182, 228, 204); background-color: rgb(232, 245, 238); color: rgb(17, 82, 51); font-size: 12px; font-weight: 600; font-family: Inter, system-ui, sans-serif; margin-bottom: 1rem;">
  <span style="width: 6px; height: 6px; border-radius: 50%; background-color: rgb(36, 159, 101); display: inline-block;"></span>
  Table_id = nombre de la tabla
</div>

<div style="display: flex; flex-wrap: wrap; gap: 0.5rem; margin: 0 0 1rem 0;">
  <span style="display: inline-flex; align-items: center; padding: 0.25rem 0.75rem; border-radius: 999px; border: 1px solid rgb(229, 229, 229); background-color: rgb(255, 255, 255); color: rgb(107, 107, 107); font-size: 12px; font-weight: 500; font-family: Inter, system-ui, sans-serif;">POST</span>
  <span style="display: inline-flex; align-items: center; padding: 0.25rem 0.75rem; border-radius: 999px; border: 1px solid rgb(229, 229, 229); background-color: rgb(255, 255, 255); color: rgb(107, 107, 107); font-size: 12px; font-weight: 500; font-family: Inter, system-ui, sans-serif;">Path param</span>
  <span style="display: inline-flex; align-items: center; padding: 0.25rem 0.75rem; border-radius: 999px; border: 1px solid rgb(229, 229, 229); background-color: rgb(255, 255, 255); color: rgb(107, 107, 107); font-size: 12px; font-weight: 500; font-family: Inter, system-ui, sans-serif;">Alias ADR</span>
</div>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  Endpoint de solo lectura para tablas principales. El path recibe <strong><code>:Table_id</code>, que representa el nombre de la tabla</strong>, y lo resuelve dentro del <code>Enterprise_id</code> del token. Expande relaciones LAOT externas e internas, acepta búsquedas, filtros, agregados y agrupaciones.
</p>

<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Ruta registrada y alias</h2>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1rem; margin-bottom: 1.5rem;">
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Ruta principal</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><code>POST /unified-select-external-laots/<strong>:Table_id</strong></code> donde <strong><code>:Table_id</code> es el nombre de la tabla</strong>.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path><polyline points="15 3 21 3 21 9"></polyline><line x1="10" y1="14" x2="21" y2="3"></line></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Alias funcional</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><code>POST /ADR/<strong>:Table_id</strong></code> donde <strong><code>:Table_id</code> es el nombre de la tabla</strong>. Reutiliza el mismo handler.</p>
  </div>
</div>

<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Autenticación</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1rem;">
  El endpoint requiere que la petición pase por la siguiente cadena de middlewares antes de ejecutar el handler.
</p>

<table style="width: 100%; border-collapse: collapse; border: 1px solid #E5E5E5; border-radius: 0.75rem; overflow: hidden; margin-bottom: 1.5rem; font-family: Inter, system-ui, sans-serif; font-size: 11px;">
  <thead>
    <tr style="background-color: #F5F5F5;">
      <th style="padding: 0.35rem 0.75rem; text-align: left; font-weight: 600; color: #121212; border-bottom: 1px solid #E5E5E5;">Orden</th>
      <th style="padding: 0.35rem 0.75rem; text-align: left; font-weight: 600; color: #121212; border-bottom: 1px solid #E5E5E5;">Middleware</th>
      <th style="padding: 0.35rem 0.75rem; text-align: left; font-weight: 600; color: #121212; border-bottom: 1px solid #E5E5E5;">Responsabilidad</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color: #ffffff;">
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #6B6B6B;">1</td>
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #121212; font-weight: 500;"><code>apiLimiter</code></td>
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #6B6B6B;">Limita la tasa de peticiones por cliente.</td>
    </tr>
    <tr style="background-color: #FAFAFA;">
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #6B6B6B;">2</td>
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #121212; font-weight: 500;"><code>ensureToken</code></td>
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #6B6B6B;">Valida la presencia y forma del token Bearer.</td>
    </tr>
    <tr style="background-color: #ffffff;">
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #6B6B6B;">3</td>
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #121212; font-weight: 500;"><code>ValidityToken</code></td>
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #6B6B6B;">Verifica firma, expiración y validez del token.</td>
    </tr>
    <tr style="background-color: #FAFAFA;">
      <td style="padding: 0.3rem 0.75rem; color: #6B6B6B;">4</td>
      <td style="padding: 0.3rem 0.75rem; color: #121212; font-weight: 500;"><code>MiddlewareRolDBRead</code></td>
      <td style="padding: 0.3rem 0.75rem; color: #6B6B6B;">Comprueba permisos de lectura sobre la base de datos.</td>
    </tr>
  </tbody>
</table>

<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Resolución de tabla</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1rem;">
  El parámetro <strong><code>Table_id</code> representa el nombre de la tabla</strong>. El sistema lo resuelve dentro del contexto del <code>Enterprise_id</code> extraído del token.
</p>

<table style="width: 100%; border-collapse: collapse; border: 1px solid #E5E5E5; border-radius: 0.75rem; overflow: hidden; margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif; font-size: 11px;">
  <thead>
    <tr style="background-color: #F5F5F5;">
      <th style="padding: 0.35rem 0.75rem; text-align: left; font-weight: 600; color: #121212; border-bottom: 1px solid #E5E5E5;">Nombre de la tabla</th>
      <th style="padding: 0.35rem 0.75rem; text-align: left; font-weight: 600; color: #121212; border-bottom: 1px solid #E5E5E5;">Comportamiento</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color: #ffffff;">
      <td style="padding: 0.3rem 0.75rem; color: #121212; font-weight: 500;"><code>Table_id</code></td>
      <td style="padding: 0.3rem 0.75rem; color: #6B6B6B;">Nombre de la tabla resuelto dentro del <code>Enterprise_id</code> del token.</td>
    </tr>
  </tbody>
</table>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1rem; margin-bottom: 1.5rem;">
  <div style="border: 1px solid rgb(255, 205, 210); border-radius: 1rem; padding: 1.25rem; background-color: rgb(255, 235, 238);">
    <div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.75rem;">
      <div style="display: inline-flex; align-items: center; justify-content: center; width: 36px; height: 36px; border-radius: 10px; background-color: rgb(255, 205, 210); color: rgb(198, 40, 40);">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle><line x1="12" y1="8" x2="12" y2="12"></line><line x1="12" y1="16" x2="12.01" y2="16"></line></svg>
      </div>
      <h3 style="font-size: 15px; font-weight: 600; color: rgb(198, 40, 40); margin: 0;">404 Not Found</h3>
    </div>
    <p style="font-size: 13px; color: rgb(99, 39, 39); line-height: 1.55; margin: 0;">Se responde cuando la tabla no existe dentro del <code>Enterprise_id</code> del token.</p>
  </div>
  <div style="border: 1px solid rgb(255, 224, 178); border-radius: 1rem; padding: 1.25rem; background-color: rgb(255, 243, 224);">
    <div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.75rem;">
      <div style="display: inline-flex; align-items: center; justify-content: center; width: 36px; height: 36px; border-radius: 10px; background-color: rgb(255, 224, 178); color: rgb(230, 81, 0);">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path><line x1="12" y1="8" x2="12" y2="12"></line><line x1="12" y1="16" x2="12.01" y2="16"></line></svg>
      </div>
      <h3 style="font-size: 15px; font-weight: 600; color: rgb(230, 81, 0); margin: 0;">403 Forbidden</h3>
    </div>
    <p style="font-size: 13px; color: rgb(123, 31, 0); line-height: 1.55; margin: 0;">Se responde cuando la tabla existe pero pertenece a otro <code>Enterprise_id</code>.</p>
  </div>
</div>

<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Expansión LAOT: internal vs external</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1rem;">
  Ambos parámetros pueden usarse en cualquier funcionalidad del endpoint, pero <strong>la lógica interna trae respuestas diferentes</strong> según cuál se utilice.
</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">internalTableIds</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Expande las relaciones <strong>LAOT internas</strong> de la tabla consultada. La respuesta incluye los registros relacionados que pertenecen directamente a la tabla principal, anidados dentro de cada resultado.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Ejemplo: <code>"internalTableIds": ["OrdenVenta"]</code> trae las relaciones internas de <code>OrdenVenta</code> dentro de cada registro de <code>DetOrdVent</code>.</p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">externalTableIds</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">Expande relaciones de <strong>tablas externas</strong> del mismo <code>Enterprise_id</code>. La respuesta trae datos de múltiples tablas en una sola consulta, con una estructura diferente a la de <code>internalTableIds</code>.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Ejemplo: <code>"externalTableIds": ["Boletas", "Facturas", "OrdenEnvio"]</code> trae datos relacionados de esas tablas en una sola respuesta.</p>
  </div>
</div>

<div style="border-left: 4px solid #F59E0B; background-color: #FFFBEB; border-radius: 0.5rem; padding: 1rem 1.25rem; margin-bottom: 1.5rem;">
  <p style="margin: 0; font-size: 13px; color: #92400E; line-height: 1.7;">
    <strong>Importante:</strong> ambos parámetros pueden combinarse en el mismo request, pero la <strong>estructura de la respuesta cambia</strong> según se use <code>internalTableIds</code>, <code>externalTableIds</code> o ambos. El programador debe revisar la estructura devuelta antes de consumirla.
  </p>
</div>

<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Checklist de seguridad</h2>

<div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem; margin-bottom: 1.5rem;">
  <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
    <li>Token Bearer válido y no expirado.</li>
    <li>Rol con permisos de lectura sobre la base de datos.</li>
    <li><strong><code>Table_id</code> es el nombre de la tabla</strong> y se resuelve dentro del <code>Enterprise_id</code> del token.</li>
    <li>El sistema realiza la búsqueda automática por nombre de tabla + enterprise.</li>
    <li><strong><code>internalTableIds</code> y <code>externalTableIds</code></strong> pueden usarse en cualquier funcionalidad, pero la lógica de cada uno trae una respuesta con estructura diferente.</li>
  </ul>
</div>