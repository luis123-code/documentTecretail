
<div style="line-height: 1.7; color: #121212; font-family: Inter, system-ui, -apple-system, sans-serif; font-size: 14px;">
  <p style="margin-bottom: 1em; margin-top: 1em;">
    <span style="font-size: 12px; font-weight: 500; color: #249f65; text-transform: uppercase; letter-spacing: 0.08em;">Módulo TQL</span>
  </p>
  <p style="margin-bottom: 1em; margin-top: 1em;">
    <span style="font-family: 'Cormorant Garamond', Georgia, serif; font-style: italic; font-size: 18px; color: #6b6b6b; line-height: 1.6; display: block; margin-bottom: 1.25rem;">
      APIs de lectura y escritura unificada para tablas empresariales con relaciones LAOT.
    </span>
  </p>
  <p style="margin-bottom: 1em; margin-top: 1em; font-size: 14px; color: #6b6b6b; line-height: 1.7; max-width: 680px;">
    El módulo <span style="font-weight: 500; color: #121212;">TQL</span> expone dos endpoints REST principales para consultar y modificar datos del ERP. Permite leer tablas con expansiones de relaciones internas y externas, e insertar o actualizar registros resolviendo automáticamente relaciones, opciones select y archivos.
  </p>
  <div style="display: flex; gap: 0.5rem; flex-wrap: wrap; margin: 1.25rem 0;">
    <span style="display: inline-flex; align-items: center; padding: 0.125rem 0.5rem; border-radius: 9999px; border: 1px solid #e5e5e5; background: #ffffff; font-size: 11px; color: #6b6b6b;">REST</span>
    <span style="display: inline-flex; align-items: center; padding: 0.125rem 0.5rem; border-radius: 9999px; border: 1px solid #e5e5e5; background: #ffffff; font-size: 11px; color: #6b6b6b;">Enterprise</span>
    <span style="display: inline-flex; align-items: center; padding: 0.125rem 0.5rem; border-radius: 9999px; border: 1px solid #e5e5e5; background: #ffffff; font-size: 11px; color: #6b6b6b;">Bearer Auth</span>
    <span style="display: inline-flex; align-items: center; padding: 0.125rem 0.5rem; border-radius: 9999px; border: 1px solid #249f65; background: #e8f5ee; font-size: 11px; color: #115233;">● Activo</span>
  </div>
  <hr style="border-width: 1px medium medium; border-style: solid none none; border-color: #e5e7eb currentcolor currentcolor; border-image: none; margin: 1em 0;">
  <h2 style="font-size: 1.5em; font-weight: 600; letter-spacing: -0.02em; margin-bottom: 0.5em; margin-top: 1.25em; color: #121212; font-family: Inter, system-ui, sans-serif;">Endpoints disponibles</h2>
  <table class="tiptap-table" style="width: 100%; border-collapse: collapse; margin-bottom: 1em; margin-top: 1em; border: 1px solid #e5e7eb; min-width: 75px;">
    <colgroup>
      <col style="min-width: 25px;">
      <col style="min-width: 25px;">
      <col style="min-width: 25px;">
    </colgroup>
    <tbody>
      <tr style="border-bottom: 1px solid #e5e7eb;">
        <th class="tiptap-table-header" colspan="1" rowspan="1" style="padding: 0; font-weight: 600; background-color: #f9fafb; border-bottom: 2px solid #e5e7eb; border-right: 1px solid #e5e7eb; height: 35px;">
          <div style="height: 35px; display: flex; align-items: center; padding: 0 12px; overflow: hidden;"><p style="margin-bottom: 1em; margin-top: 1em;">#</p></div>
        </th>
        <th class="tiptap-table-header" colspan="1" rowspan="1" style="padding: 0; font-weight: 600; background-color: #f9fafb; border-bottom: 2px solid #e5e7eb; border-right: 1px solid #e5e7eb; height: 35px;">
          <div style="height: 35px; display: flex; align-items: center; padding: 0 12px; overflow: hidden;"><p style="margin-bottom: 1em; margin-top: 1em;">Endpoint</p></div>
        </th>
        <th class="tiptap-table-header" colspan="1" rowspan="1" style="padding: 0; font-weight: 600; background-color: #f9fafb; border-bottom: 2px solid #e5e7eb; border-right: 1px solid #e5e7eb; height: 35px;">
          <div style="height: 35px; display: flex; align-items: center; padding: 0 12px; overflow: hidden;"><p style="margin-bottom: 1em; margin-top: 1em;">Descripción</p></div>
        </th>
      </tr>
      <tr style="border-bottom: 1px solid #e5e7eb;">
        <td class="tiptap-table-cell" colspan="1" rowspan="1" style="padding: 0; border-bottom: 1px solid #e5e7eb; border-right: 1px solid #e5e7eb; height: 35px;">
          <div style="height: 35px; display: flex; align-items: center; padding: 0 12px; overflow: hidden;"><p style="margin-bottom: 1em; margin-top: 1em;"><span style="font-size: 11px; color: #6b6b6b;">01</span></p></div>
        </td>
        <td class="tiptap-table-cell" colspan="1" rowspan="1" style="padding: 0; border-bottom: 1px solid #e5e7eb; border-right: 1px solid #e5e7eb; height: 35px;">
          <div style="height: 35px; display: flex; align-items: center; padding: 0 12px; overflow: hidden;"><p style="margin-bottom: 1em; margin-top: 1em;">
            <span style="display: inline-flex; align-items: center; font-weight: 500; color: #121212;">
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" style="margin-right: 0.4rem; flex-shrink: 0;">
                <circle cx="11" cy="11" r="8" stroke="#121212" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></circle>
                <path d="m21 21-4.3-4.3" stroke="#121212" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path>
              </svg>
              unified-select-external-laots
            </span>
          </p></div>
        </td>
        <td class="tiptap-table-cell" colspan="1" rowspan="1" style="padding: 0; border-bottom: 1px solid #e5e7eb; border-right: 1px solid #e5e7eb; height: 35px;">
          <div style="height: 35px; display: flex; align-items: center; padding: 0 12px; overflow: hidden;"><p style="margin-bottom: 1em; margin-top: 1em;"><span style="font-size: 13px; color: #6b6b6b;">Lectura avanzada con relaciones LAOT internas y externas.</span></p></div>
        </td>
      </tr>
      <tr style="border-bottom: 1px solid #e5e7eb;">
        <td class="tiptap-table-cell" colspan="1" rowspan="1" style="padding: 0; border-bottom: 1px solid #e5e7eb; border-right: 1px solid #e5e7eb; height: 35px;">
          <div style="height: 35px; display: flex; align-items: center; padding: 0 12px; overflow: hidden;"><p style="margin-bottom: 1em; margin-top: 1em;"><span style="font-size: 11px; color: #6b6b6b;">02</span></p></div>
        </td>
        <td class="tiptap-table-cell" colspan="1" rowspan="1" style="padding: 0; border-bottom: 1px solid #e5e7eb; border-right: 1px solid #e5e7eb; height: 35px;">
          <div style="height: 35px; display: flex; align-items: center; padding: 0 12px; overflow: hidden;"><p style="margin-bottom: 1em; margin-top: 1em;">
            <span style="display: inline-flex; align-items: center; font-weight: 500; color: #121212;">
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" style="margin-right: 0.4rem; flex-shrink: 0;">
                <path d="M12 20h9" stroke="#121212" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path>
                <path d="M16.5 3.5a2.12 2.12 0 0 1 3 3L7 19l-4 1 1-4Z" stroke="#121212" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path>
              </svg>
              unified-upsert
            </span>
          </p></div>
        </td>
        <td class="tiptap-table-cell" colspan="1" rowspan="1" style="padding: 0; border-bottom: 1px solid #e5e7eb; border-right: 1px solid #e5e7eb; height: 35px;">
          <div style="height: 35px; display: flex; align-items: center; padding: 0 12px; overflow: hidden;"><p style="margin-bottom: 1em; margin-top: 1em;"><span style="font-size: 13px; color: #6b6b6b;">Inserción o actualización con resolución de relaciones.</span></p></div>
        </td>
      </tr>
    </tbody>
  </table>
  <hr style="border-width: 1px medium medium; border-style: solid none none; border-color: #e5e7eb currentcolor currentcolor; border-image: none; margin: 1em 0;">
  <p style="margin-bottom: 1em; margin-top: 1em;">
    <span style="font-size: 12px; font-weight: 500; color: #249f65; text-transform: uppercase; letter-spacing: 0.08em;">¿Qué puedo hacer con estas APIs?</span>
  </p>
  <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1rem; margin-bottom: 1.5em; margin-top: 1.5em; font-family: Inter, system-ui, -apple-system, sans-serif;">
    <a href="#" style="position: relative; display: block; text-decoration: none; border-radius: 1rem; border: 1px solid #e5e5e5; background-color: #ffffff; padding: 1.5rem; transition: border-color 0.2s, box-shadow 0.2s; box-shadow: none; font-family: Inter, system-ui, -apple-system, sans-serif; cursor: pointer;">
      <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="position: absolute; top: 1.25rem; right: 1.25rem; color: rgba(107, 107, 107, 0.4); transform: translate(0, 0); transition: 0.2s;">
        <path d="M7 7h10v10"></path>
        <path d="M7 17 17 7"></path>
      </svg>
      <div style="margin-bottom: 2rem; transition: color 0.2s; color: rgba(18, 18, 18, 0.6);">
        <div style="width: 28px; height: 28px;">
          <svg width="28" height="28" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <circle cx="11" cy="11" r="8" stroke="#121212" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></circle>
            <path d="m21 21-4.3-4.3" stroke="#121212" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path>
          </svg>
        </div>
      </div>
      <h3 style="font-size: 16px; font-weight: 500; letter-spacing: -0.01em; color: #121212; margin-bottom: 0.75rem; margin-top: 0; display: flex; align-items: center; gap: 0.35rem; flex-wrap: wrap;">Lectura unificada</h3>
      <p style="font-size: 13px; color: #6b6b6b; line-height: 1.55; margin-bottom: 1rem; margin-top: 0;">
        Lee una tabla principal junto con relaciones LAOT/Select, LAOTs externos e internos en un solo request.
      </p>
      <div style="display: flex; flex-wrap: wrap; gap: 0.375rem;">
        <span style="display: inline-flex; align-items: center; padding: 0.125rem 0.5rem; border-radius: 9999px; border: 1px solid #e5e5e5; background-color: #ffffff; font-size: 11px; color: #6b6b6b;">select</span>
        <span style="display: inline-flex; align-items: center; padding: 0.125rem 0.5rem; border-radius: 9999px; border: 1px solid #e5e5e5; background-color: #ffffff; font-size: 11px; color: #6b6b6b;">relations</span>
        <span style="display: inline-flex; align-items: center; padding: 0.125rem 0.5rem; border-radius: 9999px; border: 1px solid #e5e5e5; background-color: #ffffff; font-size: 11px; color: #6b6b6b;">filters</span>
      </div>
    </a>
    <a href="#" style="position: relative; display: block; text-decoration: none; border-radius: 1rem; border: 1px solid #e5e5e5; background-color: #ffffff; padding: 1.5rem; transition: border-color 0.2s, box-shadow 0.2s; box-shadow: none; font-family: Inter, system-ui, -apple-system, sans-serif; cursor: pointer;">
      <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="position: absolute; top: 1.25rem; right: 1.25rem; color: rgba(107, 107, 107, 0.4); transform: translate(0, 0); transition: 0.2s;">
        <path d="M7 7h10v10"></path>
        <path d="M7 17 17 7"></path>
      </svg>
      <div style="margin-bottom: 2rem; transition: color 0.2s; color: rgba(18, 18, 18, 0.6);">
        <div style="width: 28px; height: 28px;">
          <svg width="28" height="28" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M12 20h9" stroke="#121212" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path>
            <path d="M16.5 3.5a2.12 2.12 0 0 1 3 3L7 19l-4 1 1-4Z" stroke="#121212" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path>
          </svg>
        </div>
      </div>
      <h3 style="font-size: 16px; font-weight: 500; letter-spacing: -0.01em; color: #121212; margin-bottom: 0.75rem; margin-top: 0; display: flex; align-items: center; gap: 0.35rem; flex-wrap: wrap;">Escritura segura</h3>
      <p style="font-size: 13px; color: #6b6b6b; line-height: 1.55; margin-bottom: 1rem; margin-top: 0;">
        Inserta o actualiza registros resolviendo relaciones, opciones select y soportando carga de archivos.
      </p>
      <div style="display: flex; flex-wrap: wrap; gap: 0.375rem;">
        <span style="display: inline-flex; align-items: center; padding: 0.125rem 0.5rem; border-radius: 9999px; border: 1px solid #e5e5e5; background-color: #ffffff; font-size: 11px; color: #6b6b6b;">upsert</span>
        <span style="display: inline-flex; align-items: center; padding: 0.125rem 0.5rem; border-radius: 9999px; border: 1px solid #e5e5e5; background-color: #ffffff; font-size: 11px; color: #6b6b6b;">files</span>
        <span style="display: inline-flex; align-items: center; padding: 0.125rem 0.5rem; border-radius: 9999px; border: 1px solid #e5e5e5; background-color: #ffffff; font-size: 11px; color: #6b6b6b;">batch</span>
      </div>
    </a>
    <a href="#" style="position: relative; display: block; text-decoration: none; border-radius: 1rem; border: 1px solid #e5e5e5; background-color: #ffffff; padding: 1.5rem; transition: border-color 0.2s, box-shadow 0.2s; box-shadow: none; font-family: Inter, system-ui, -apple-system, sans-serif; cursor: pointer;">
      <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="position: absolute; top: 1.25rem; right: 1.25rem; color: rgba(107, 107, 107, 0.4); transform: translate(0, 0); transition: 0.2s;">
        <path d="M7 7h10v10"></path>
        <path d="M7 17 17 7"></path>
      </svg>
      <div style="margin-bottom: 2rem; transition: color 0.2s; color: rgba(18, 18, 18, 0.6);">
        <div style="width: 28px; height: 28px;">
          <svg width="28" height="28" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M12.22 2h-.44a2 2 0 0 0-2 2v.18a2 2 0 0 1-1 1.73l-.43.25a2 2 0 0 1-2 0l-.15-.08a2 2 0 0 0-2.73.73l-.22.38a2 2 0 0 0 .73 2.73l.15.1a2 2 0 0 1 1 1.72v.51a2 2 0 0 1-1 1.74l-.15.09a2 2 0 0 0-.73 2.73l.22.38a2 2 0 0 0 2.73.73l.15-.08a2 2 0 0 1 2 0l.43.25a2 2 0 0 1 1 1.73V20a2 2 0 0 0 2 2h.44a2 2 0 0 0 2-2v-.18a2 2 0 0 1 1-1.73l.43-.25a2 2 0 0 1 2 0l.15.08a2 2 0 0 0 2.73-.73l.22-.39a2 2 0 0 0-.73-2.73l-.15-.08a2 2 0 0 1-1-1.74v-.5a2 2 0 0 1 1-1.74l.15-.09a2 2 0 0 0 .73-2.73l-.22-.38a2 2 0 0 0-2.73-.73l-.15.08a2 2 0 0 1-2 0l-.43-.25a2 2 0 0 1-1-1.73V4a2 2 0 0 0-2-2z" stroke="#121212" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path>
            <circle cx="12" cy="12" r="3" stroke="#121212" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></circle>
          </svg>
        </div>
      </div>
      <h3 style="font-size: 16px; font-weight: 500; letter-spacing: -0.01em; color: #121212; margin-bottom: 0.75rem; margin-top: 0; display: flex; align-items: center; gap: 0.35rem; flex-wrap: wrap;">Post-procesos</h3>
      <p style="font-size: 13px; color: #6b6b6b; line-height: 1.55; margin-bottom: 1rem; margin-top: 0;">
        Después de responder se ejecutan sincronizaciones MeiliSearch, bridges como Salmec y automatizaciones.
      </p>
      <div style="display: flex; flex-wrap: wrap; gap: 0.375rem;">
        <span style="display: inline-flex; align-items: center; padding: 0.125rem 0.5rem; border-radius: 9999px; border: 1px solid #e5e5e5; background-color: #ffffff; font-size: 11px; color: #6b6b6b;">async</span>
        <span style="display: inline-flex; align-items: center; padding: 0.125rem 0.5rem; border-radius: 9999px; border: 1px solid #e5e5e5; background-color: #ffffff; font-size: 11px; color: #6b6b6b;">meili</span>
        <span style="display: inline-flex; align-items: center; padding: 0.125rem 0.5rem; border-radius: 9999px; border: 1px solid #e5e5e5; background-color: #ffffff; font-size: 11px; color: #6b6b6b;">integrations</span>
      </div>
    </a>
  </div>
  <div style="background-color: #dbeafe; border-left: 4px solid #3b82f6; padding: 1em 1.25em; margin-bottom: 1.5em; margin-top: 1.5em; border-radius: 0.375em; color: #1e40af; display: flex; align-items: flex-start; gap: 0.75em; font-family: Inter, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif; font-size: 0.875em; line-height: 1.5; box-shadow: rgba(0, 0, 0, 0.05) 0px 1px 2px;">
    <span style="color: #3b82f6; flex-shrink: 0; margin-top: 0.125em;">
      <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-info w-4 h-4">
        <circle cx="12" cy="12" r="10"></circle>
        <path d="M12 16v-4"></path>
        <path d="M12 8h.01"></path>
      </svg>
    </span>
    <div style="flex: 1 1 0%;">
      Ambos endpoints requieren autenticación <strong>Bearer</strong> y operan dentro del <strong>Enterprise_id</strong> del token. El parámetro <code>:Table_id</code> acepta un ID numérico o el nombre de la tabla.
    </div>
  </div>
</div>