<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Ejemplo: insertar registro en TablaEjemplo</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  Este request inserta un nuevo registro en la tabla <strong><code>TablaEjemplo</code></strong> con todos los campos vacíos. El endpoint <code>unified-upsert</code> detecta que el registro no existe y ejecuta un <strong>insert</strong>.
</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; margin-bottom: 1.5rem;">
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Modo JSON individual</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 1rem 0;">El payload es un objeto (no un arreglo), por lo que se ejecuta un solo upsert. Como el registro no existe, se crea uno nuevo.</p>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 1.5rem;">Campos de la tabla</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;"><code>Nombre</code>, <code>LOGS</code> — campos de texto general.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;"><code>fechita</code> — campo de fecha.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;"><code>telefon</code>, <code>correin</code>, <code>liiink</code> — contacto y enlace.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;"><code>nmerito</code>, <code>percent</code>, <code>Monedita</code> — numéricos y porcentajes.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0 0 0.5rem 0;"><code>ciudades</code>, <code>paises</code>, <code>unicselect</code> — selects y ubicación.</p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><code>checxboxname</code>, <code>checxboxname_1</code> — checkboxes.</p>
  </div>
  <div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 1rem; margin-top: 0;">Notas del ejemplo</h3>
    <div style="border-left: 4px solid #22C55E; background-color: #F0FDF4; border-radius: 0.5rem; padding: 1rem 1.25rem;">
      <ul style="margin: 0; padding-left: 1.25rem; font-size: 13px; color: #166534; line-height: 1.7;">
        <li><strong>Endpoint:</strong> <code>POST /tql_module/unified-upsert/TablaEjemplo</code> apunta a la tabla <code>TablaEjemplo</code>.</li>
        <li><strong>Insert:</strong> como el registro no existe, <code>doUnifiedUpsert()</code> ejecuta un insert.</li>
        <li><strong>Campos vacíos:</strong> todos los valores son string vacío <code>""</code>. El backend los interpreta según el tipo de cada columna.</li>
        <li><strong>Modo individual:</strong> el payload es un objeto, no un arreglo. Para insertar múltiples registros, enviar un array.</li>
        <li><strong>Sin archivos:</strong> usa <code>application/json</code>. Para adjuntar archivos, usar <code>multipart/form-data</code> con <code>jsonData</code>.</li>
        <li>El token Bearer se ingresa en la pestaña <strong>Auth</strong> del bloque API, no se guarda en el Markdown.</li>
      </ul>
    </div>
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
    "Nombre": "",
    "LOGS": "",
    "a": "",
    "test": "",
    "fasfads": "",
    "NOMCOLUMNA": "",
    "NTRESCOLUM": "",
    "checxboxname": "",
    "fechita": "",
    "telefon": "",
    "correin": "",
    "liiink": "",
    "nmerito": "",
    "percent": "",
    "ciudades": "",
    "paises": "",
    "unicselect": "",
    "Monedita": "",
    "abcx": "",
    "dasdsa": "",
    "checxboxname_1": "",
    "dfd": "",
    "pruevaxd": ""
  }
}
</api>