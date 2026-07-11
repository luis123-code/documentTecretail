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
  <span style="display: inline-flex; align-items: center; padding: 0.25rem 0.75rem; border-radius: 999px; border: 1px solid rgb(229, 229, 229); background-color: rgb(255, 255, 255); color: rgb(107, 107, 107); font-size: 12px; font-weight: 500; font-family: Inter, system-ui, sans-serif;">Escritura</span>
  <span style="display: inline-flex; align-items: center; padding: 0.25rem 0.75rem; border-radius: 999px; border: 1px solid rgb(229, 229, 229); background-color: rgb(255, 255, 255); color: rgb(107, 107, 107); font-size: 12px; font-weight: 500; font-family: Inter, system-ui, sans-serif;">JSON / multipart</span>
</div>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  Endpoint para <strong>crear o actualizar registros</strong> en una tabla. A diferencia de <code>unified-select-external-laots</code> (que solo lee), este endpoint <strong>escribe datos</strong>: inserta registros nuevos o actualiza existentes. Internamente delega la lógica a la función <code>doUnifiedUpsert()</code>.
</p>

<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Ruta registrada</h2>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1rem; margin-bottom: 1.5rem;">
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Ruta principal</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><code>POST /unified-upsert/<strong>:Table_id</strong></code> donde <strong><code>:Table_id</code> es el nombre de la tabla</strong>.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 20h9"></path><path d="M16.5 3.5a2.121 2.121 0 0 1 3 3L7 19l-4 1 1-4L16.5 3.5z"></path></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Función interna</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Delega la lógica a <code>doUnifiedUpsert()</code> que determina si inserta o actualiza según si el registro ya existe.</p>
  </div>
</div>

<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Formatos de request</h2>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">application/json</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Para operaciones <strong>sin archivos</strong>. El payload se envía directamente en <code>req.body</code> como JSON.</p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">multipart/form-data</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Para operaciones <strong>con archivos</strong> (imágenes, PDFs). Exige el campo <code>jsonData</code> (string parseado a JSON) + archivos en memoria.</p>
  </div>
</div>

<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Autenticación y control de acceso</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1rem;">
  El endpoint pasa por la siguiente cadena de middlewares antes de ejecutar el handler.
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
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #121212; font-weight: 500;"><code>upload.any()</code></td>
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #6B6B6B;">Captura archivos adjuntos si el request es multipart.</td>
    </tr>
    <tr style="background-color: #FAFAFA;">
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #6B6B6B;">2</td>
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #121212; font-weight: 500;"><code>apiLimiter</code></td>
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #6B6B6B;">Limita la tasa de peticiones por cliente.</td>
    </tr>
    <tr style="background-color: #ffffff;">
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #6B6B6B;">3</td>
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #121212; font-weight: 500;"><code>ensureToken</code></td>
      <td style="padding: 0.3rem 0.75rem; border-bottom: 1px solid #E5E5E5; color: #6B6B6B;">Valida la presencia y forma del token Bearer.</td>
    </tr>
    <tr style="background-color: #FAFAFA;">
      <td style="padding: 0.3rem 0.75rem; color: #6B6B6B;">4</td>
      <td style="padding: 0.3rem 0.75rem; color: #121212; font-weight: 500;"><code>ValidityToken</code></td>
      <td style="padding: 0.3rem 0.75rem; color: #6B6B6B;">Verifica firma, expiración y validez del token.</td>
    </tr>
  </tbody>
</table>

<div style="border-left: 4px solid #F59E0B; background-color: #FFFBEB; border-radius: 0.5rem; padding: 1rem 1.25rem; margin-bottom: 1.5rem;">
  <p style="margin: 0; font-size: 13px; color: #92400E; line-height: 1.7;">
    <strong>Importante:</strong> este endpoint <strong>no pasa</strong> por <code>MiddlewareRolDBCreate</code> ni <code>MiddlewareRolDBUpdate</code> (están comentados en la ruta). La validación de acceso se basa únicamente en que la tabla resuelta pertenezca al <code>Enterprise_id</code> del token.
  </p>
</div>

<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Detección de modo</h2>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Modo JSON</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Si el request es <code>application/json</code>, toma <code>req.body</code> directamente como payload. No hay archivos involucrados.</p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Modo multipart</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Si el request es <code>multipart/form-data</code>, exige el campo <code>jsonData</code> (string que se parsea a JSON) más los archivos en memoria.</p>
  </div>
</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Modo batch</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Si el payload final es un <strong>arreglo</strong>, entra en modo batch: ejecuta un upsert por cada item del array. Cada elemento se procesa de forma independiente.</p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Modo individual</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Si el payload es un <strong>objeto</strong>, ejecuta un solo upsert con ese registro.</p>
  </div>
</div>

<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Operaciones</h2>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div style="border: 1px solid rgb(182, 228, 204); border-radius: 1rem; padding: 1.25rem; background-color: rgb(232, 245, 238);">
    <div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.75rem;">
      <div style="display: inline-flex; align-items: center; justify-content: center; width: 36px; height: 36px; border-radius: 10px; background-color: rgb(182, 228, 204); color: rgb(17, 82, 51);">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg>
      </div>
      <h3 style="font-size: 15px; font-weight: 600; color: rgb(17, 82, 51); margin: 0;">Insert</h3>
    </div>
    <p style="font-size: 13px; color: rgb(17, 82, 51); line-height: 1.55; margin: 0;">Si el registro no existe, se crea uno nuevo con los datos del payload.</p>
  </div>
  <div style="border: 1px solid rgb(255, 224, 178); border-radius: 1rem; padding: 1.25rem; background-color: rgb(255, 243, 224);">
    <div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.75rem;">
      <div style="display: inline-flex; align-items: center; justify-content: center; width: 36px; height: 36px; border-radius: 10px; background-color: rgb(255, 224, 178); color: rgb(230, 81, 0);">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 20h9"></path><path d="M16.5 3.5a2.121 2.121 0 0 1 3 3L7 19l-4 1 1-4L16.5 3.5z"></path></svg>
      </div>
      <h3 style="font-size: 15px; font-weight: 600; color: rgb(230, 81, 0); margin: 0;">Update</h3>
    </div>
    <p style="font-size: 13px; color: rgb(123, 31, 0); line-height: 1.55; margin: 0;">Si el registro ya existe, se actualizan los campos con los datos del payload.</p>
  </div>
</div>

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

<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Checklist de seguridad</h2>

<div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem; margin-bottom: 1.5rem;">
  <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
    <li>Token Bearer válido y no expirado.</li>
    <li><strong><code>Table_id</code> es el nombre de la tabla</strong> y se resuelve dentro del <code>Enterprise_id</code> del token.</li>
    <li>El sistema valida que la tabla pertenezca al <code>Enterprise_id</code> del token.</li>
    <li><strong>No requiere</strong> <code>MiddlewareRolDBCreate</code> ni <code>MiddlewareRolDBUpdate</code> (están comentados).</li>
    <li>El token Bearer se ingresa en la pestaña <strong>Auth</strong> del bloque API, no se guarda en el Markdown.</li>
  </ul>
</div>