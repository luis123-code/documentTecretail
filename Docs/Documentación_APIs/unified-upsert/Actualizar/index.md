<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Ejemplo: actualizar registro en TablaEjemplo</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  Este request actualiza un registro existente en la tabla <strong><code>TablaEjemplo</code></strong>. La estructura es <strong>idéntica a la del insert</strong>, con la única diferencia de que incluye el campo <code>ID_UPDATE</code> para identificar el registro a actualizar.
</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Campo ID_UPDATE</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">El campo <code>ID_UPDATE</code> es obligatorio para actualizar. Indica qué registro modificar. Su valor es el ID del registro existente.</p>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem;">Cómo encontrar el ID</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">El ID del registro se encuentra en el <strong>key que termina con <code>_ID</code></strong>. Por ejemplo: <code>ID_UPDATE</code>, <code>ORDEN_ID</code>, <code>CONTACT_ID</code>, etc. Consulta la tabla con <code>unified-select</code> para obtener el valor antes de actualizar.</p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; margin-top: 0;">Notas del ejemplo</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>Endpoint:</strong> <code>POST /tql_module/unified-upsert/TablaEjemplo</code></li>
        <li><strong>Update:</strong> al incluir <code>ID_UPDATE</code>, <code>doUnifiedUpsert()</code> detecta que el registro existe y ejecuta un update.</li>
        <li><strong>Misma estructura:</strong> el payload es igual al insert, solo se agrega <code>ID_UPDATE</code>.</li>
        <li><strong>Camdos parciales:</strong> no es necesario enviar todos los campos. Solo los que se quieren actualizar.</li>
        <li><strong>Key con _ID:</strong> el ID del registro siempre está en el campo que termina con <code>_ID</code>.</li>
        <li>El token Bearer se ingresa en la pestaña <strong>Auth</strong> del bloque API, no se guarda en el Markdown.</li>
      </ul>
    </div>
  </div>
</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div style="border: 1px solid rgb(182, 228, 204); border-radius: 1rem; padding: 1.25rem; background-color: rgb(232, 245, 238);">
    <div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.75rem;">
      <div style="display: inline-flex; align-items: center; justify-content: center; width: 36px; height: 36px; border-radius: 10px; background-color: rgb(182, 228, 204); color: rgb(17, 82, 51);">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="5" x2="12" y2="19"></line><line x1="5" y1="12" x2="19" y2="12"></line></svg>
      </div>
      <h3 style="font-size: 15px; font-weight: 600; color: rgb(17, 82, 51); margin: 0;">Insert (sin ID_UPDATE)</h3>
    </div>
    <p style="font-size: 13px; color: rgb(17, 82, 51); line-height: 1.55; margin: 0;">Payload sin <code>ID_UPDATE</code> → crea un registro nuevo.</p>
  </div>
  <div style="border: 1px solid rgb(255, 224, 178); border-radius: 1rem; padding: 1.25rem; background-color: rgb(255, 243, 224);">
    <div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.75rem;">
      <div style="display: inline-flex; align-items: center; justify-content: center; width: 36px; height: 36px; border-radius: 10px; background-color: rgb(255, 224, 178); color: rgb(230, 81, 0);">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M12 20h9"></path><path d="M16.5 3.5a2.121 2.121 0 0 1 3 3L7 19l-4 1 1-4L16.5 3.5z"></path></svg>
      </div>
      <h3 style="font-size: 15px; font-weight: 600; color: rgb(230, 81, 0); margin: 0;">Update (con ID_UPDATE)</h3>
    </div>
    <p style="font-size: 13px; color: rgb(123, 31, 0); line-height: 1.55; margin: 0;">Payload con <code>ID_UPDATE</code> → actualiza el registro existente.</p>
  </div>
</div>

<api>
{
  "url": "tql_module/unified-upsert/TablaEjemplo",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json"
  },
  "body": {
    "ID_UPDATE": "4600",
    "NOMCOLUMNA": "dasd"
  }
}
</api>