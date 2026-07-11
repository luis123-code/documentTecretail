<p style="font-size: 12px; font-weight: 600; color: rgb(17, 82, 51); text-transform: uppercase; letter-spacing: 0.06em; margin-bottom: 0.75rem; font-family: Inter, system-ui, sans-serif;">
  Módulo TQL · API
</p>

<p style="font-family: Georgia, serif; font-size: 18px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.25rem;">
  Lectura enriquecida de tablas principales con expansión automática de relaciones LAOT internas y externas. No realiza escrituras.
</p>

<div style="display: flex; flex-wrap: wrap; gap: 0.5rem; margin-bottom: 1.5rem;">
  <span style="display: inline-flex; align-items: center; padding: 0.25rem 0.75rem; border-radius: 999px; border: 1px solid rgb(229, 229, 229); background-color: rgb(255, 255, 255); color: rgb(107, 107, 107); font-size: 12px; font-weight: 500; font-family: Inter, system-ui, sans-serif;">POST</span>
  <span style="display: inline-flex; align-items: center; padding: 0.25rem 0.75rem; border-radius: 999px; border: 1px solid rgb(229, 229, 229); background-color: rgb(255, 255, 255); color: rgb(107, 107, 107); font-size: 12px; font-weight: 500; font-family: Inter, system-ui, sans-serif;">LAOT externo</span>
  <span style="display: inline-flex; align-items: center; padding: 0.25rem 0.75rem; border-radius: 999px; border: 1px solid rgb(229, 229, 229); background-color: rgb(255, 255, 255); color: rgb(107, 107, 107); font-size: 12px; font-weight: 500; font-family: Inter, system-ui, sans-serif;">LAOT interno</span>
  <span style="display: inline-flex; align-items: center; padding: 0.25rem 0.75rem; border-radius: 999px; border: 1px solid rgb(229, 229, 229); background-color: rgb(255, 255, 255); color: rgb(107, 107, 107); font-size: 12px; font-weight: 500; font-family: Inter, system-ui, sans-serif;">Metrics</span>
  <span style="display: inline-flex; align-items: center; gap: 0.35rem; padding: 0.25rem 0.75rem; border-radius: 999px; border: 1px solid rgb(182, 228, 204); background-color: rgb(232, 245, 238); color: rgb(17, 82, 51); font-size: 12px; font-weight: 500; font-family: Inter, system-ui, sans-serif;">
    <span style="width: 6px; height: 6px; border-radius: 50%; background-color: rgb(36, 159, 101); display: inline-block;"></span>
    Activo
  </span>
</div>

<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Resumen del contrato</h2>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1rem; margin-bottom: 1.5rem;">
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Endpoint</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><code>/tql_module/unified-select-external-laots/:Table_id</code> con <code>limit</code> y <code>offset</code> opcionales.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path><polyline points="15 3 21 3 21 9"></polyline><line x1="10" y1="14" x2="21" y2="3"></line></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Alias funcional</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><code>POST /ADR/:Table_id</code> resuelve al mismo handler exacto.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="11" width="18" height="11" rx="2" ry="2"></rect><path d="M7 11V7a5 5 0 0 1 10 0v4"></path></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Autenticación</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Requiere <code>apiLimiter → ensureToken → ValidityToken → MiddlewareRolDBRead</code>.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"></path><polyline points="14 2 14 8 20 8"></polyline><line x1="16" y1="13" x2="8" y2="13"></line><line x1="16" y1="17" x2="8" y2="17"></line><polyline points="10 9 9 9 8 9"></polyline></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Respuesta</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Filas enriquecidas, agrupaciones o métricas según el modo.</p>
  </div>
</div>

<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Funcionalidades</h2>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1rem; margin-bottom: 1.5rem;">
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="5" r="3"></circle><line x1="12" y1="8" x2="12" y2="12"></line><line x1="12" y1="12" x2="8" y2="16"></line><line x1="12" y1="12" x2="16" y2="16"></line><path d="M8 16a3 3 0 1 0 0 6 3 3 0 0 0 0-6z"></path><path d="M16 16a3 3 0 1 0 0 6 3 3 0 0 0 0-6z"></path></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Expansión de relaciones</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Expande headers LAOT/Select (tipos 15, 17, 18). Habilita LAOTs inversos con <code>externalTableIds</code> y expansión completa con <code>internalTableIds</code>.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Búsqueda inteligente</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><code>searchKey</code> con <code>header/field</code> arma LIKE relacional. Sin ellos delega a MeiliSearch sobre el índice de la tabla.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M18 20V10"></path><path d="M12 20V4"></path><path d="M6 20v-6"></path></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Agregados y métricas</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;"><code>metrics</code> activa modo estadístico. Compatible con <code>groupBy</code> para agregados COUNT, SUM, AVG, MIN, MAX por grupo.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.5rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 48px; height: 48px; border-radius: 12px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1.25rem;">
      <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><polygon points="22 3 2 3 10 12.46 10 19 14 21 14 12.46 22 3"></polygon></svg>
    </div>
    <h3 style="font-size: 16px; font-weight: 600; color: #121212; margin-bottom: 0.75rem; margin-top: 0;">Filtros avanzados</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Operadores relacionales, rangos de fecha, rangos horarios y mezclas AND/OR con paréntesis automáticos.</p>
  </div>
</div>

<alert type="warning">
  <strong>Seguridad:</strong> <code>Table_id</code> se resuelve dentro del <code>Enterprise_id</code> del token. Tabla no encontrada → 404. Tabla de otro enterprise → 403.
</alert>

<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Contrato de request</h2>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 1rem; margin-bottom: 1.5rem;">
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.25rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.75rem;">
      <div style="display: inline-flex; align-items: center; justify-content: center; width: 36px; height: 36px; border-radius: 10px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18);">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M13 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V9z"></path><polyline points="13 2 13 9 20 9"></polyline></svg>
      </div>
      <div style="font-size: 14px; font-weight: 600; color: #121212; font-family: Inter, system-ui, sans-serif;"><code>Table_id</code></div>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0 0 0.25rem 0;"><strong>Path param</strong></p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Nombre de tabla. Se resuelve dentro del enterprise del token.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.25rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.75rem;">
      <div style="display: inline-flex; align-items: center; justify-content: center; width: 36px; height: 36px; border-radius: 10px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18);">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><line x1="4" y1="9" x2="20" y2="9"></line><line x1="4" y1="15" x2="20" y2="15"></line><line x1="10" y1="3" x2="8" y2="21"></line><line x1="16" y1="3" x2="14" y2="21"></line></svg>
      </div>
      <div style="font-size: 14px; font-weight: 600; color: #121212; font-family: Inter, system-ui, sans-serif;"><code>limit / offset</code></div>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0 0 0.25rem 0;"><strong>Query string</strong></p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Paginación. Defaults: <code>limit=50</code>, <code>offset=0</code>.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.25rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.75rem;">
      <div style="display: inline-flex; align-items: center; justify-content: center; width: 36px; height: 36px; border-radius: 10px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18);">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"></path><polyline points="14 2 14 8 20 8"></polyline><line x1="16" y1="13" x2="8" y2="13"></line><line x1="16" y1="17" x2="8" y2="17"></line><polyline points="10 9 9 9 8 9"></polyline></svg>
      </div>
      <div style="font-size: 14px; font-weight: 600; color: #121212; font-family: Inter, system-ui, sans-serif;"><code>where</code></div>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0 0 0.25rem 0;"><strong>Body</strong></p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Array de condiciones <code>{ field, operator, value, conector? }</code>.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.25rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.75rem;">
      <div style="display: inline-flex; align-items: center; justify-content: center; width: 36px; height: 36px; border-radius: 10px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18);">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path><circle cx="9" cy="7" r="4"></circle><path d="M23 21v-2a4 4 0 0 0-3-3.87"></path><path d="M16 3.13a4 4 0 0 1 0 7.75"></path></svg>
      </div>
      <div style="font-size: 14px; font-weight: 600; color: #121212; font-family: Inter, system-ui, sans-serif;"><code>externalTableIds</code></div>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0 0 0.25rem 0;"><strong>Body</strong></p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Obligatorio para LAOTs externos. Acepta IDs o nombres de tabla.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.25rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.75rem;">
      <div style="display: inline-flex; align-items: center; justify-content: center; width: 36px; height: 36px; border-radius: 10px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18);">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="3" width="20" height="14" rx="2" ry="2"></rect><line x1="8" y1="21" x2="16" y2="21"></line><line x1="12" y1="17" x2="12" y2="21"></line></svg>
      </div>
      <div style="font-size: 14px; font-weight: 600; color: #121212; font-family: Inter, system-ui, sans-serif;"><code>internalTableIds</code></div>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0 0 0.25rem 0;"><strong>Body</strong></p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Opcional. Fuerza expansión completa de tablas LAOT internas.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.25rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.75rem;">
      <div style="display: inline-flex; align-items: center; justify-content: center; width: 36px; height: 36px; border-radius: 10px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18);">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>
      </div>
      <div style="font-size: 14px; font-weight: 600; color: #121212; font-family: Inter, system-ui, sans-serif;"><code>searchKey</code></div>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0 0 0.25rem 0;"><strong>Body</strong></p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Con header+field arma LIKE; sin ellos usa MeiliSearch.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.25rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.75rem;">
      <div style="display: inline-flex; align-items: center; justify-content: center; width: 36px; height: 36px; border-radius: 10px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18);">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"></path><path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"></path></svg>
      </div>
      <div style="font-size: 14px; font-weight: 600; color: #121212; font-family: Inter, system-ui, sans-serif;"><code>header / field</code></div>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0 0 0.25rem 0;"><strong>Body</strong></p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Contexto de filtro relacional y campo directo o anidado.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.25rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.75rem;">
      <div style="display: inline-flex; align-items: center; justify-content: center; width: 36px; height: 36px; border-radius: 10px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18);">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M16 3h3v3h-3z"></path><path d="M8 3h3v3H8z"></path><path d="M5 8h14v12a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V8z"></path><path d="M8 12h8"></path><path d="M8 16h8"></path></svg>
      </div>
      <div style="font-size: 14px; font-weight: 600; color: #121212; font-family: Inter, system-ui, sans-serif;"><code>groupBy / metrics</code></div>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0 0 0.25rem 0;"><strong>Body</strong></p>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Agrupación y agregados COUNT, SUM, AVG, MIN, MAX.</p>
  </div>
</div>

<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Operadores soportados</h2>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 0.75rem; margin-bottom: 1.5rem;">
  <div style="border: 1px solid #E5E5E5; border-radius: 0.75rem; padding: 1rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.5rem;">
      <span style="font-family: 'JetBrains Mono', monospace; font-size: 13px; font-weight: 600; color: #121212; background-color: #F5F5F5; padding: 0.15rem 0.4rem; border-radius: 0.375rem;">=</span>
      <span style="font-size: 13px; font-weight: 500; color: #121212;">Igualdad</span>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0;">Comparación directa de igualdad.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 0.75rem; padding: 1rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.5rem;">
      <span style="font-family: 'JetBrains Mono', monospace; font-size: 13px; font-weight: 600; color: #121212; background-color: #F5F5F5; padding: 0.15rem 0.4rem; border-radius: 0.375rem;">!=</span>
      <span style="font-size: 13px; font-weight: 500; color: #121212;">Desigualdad</span>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0;">Negación de la igualdad.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 0.75rem; padding: 1rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.5rem;">
      <span style="font-family: 'JetBrains Mono', monospace; font-size: 13px; font-weight: 600; color: #121212; background-color: #F5F5F5; padding: 0.15rem 0.4rem; border-radius: 0.375rem;"> > , >= , <=, < , =  </span>
      <span style="font-size: 13px; font-weight: 500; color: #121212;">Comparación</span>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0;">Mayor, menor e inclusivos. Numéricos.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 0.75rem; padding: 1rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.5rem;">
      <span style="font-family: 'JetBrains Mono', monospace; font-size: 13px; font-weight: 600; color: #121212; background-color: #F5F5F5; padding: 0.15rem 0.4rem; border-radius: 0.375rem;">LIKE</span>
      <span style="font-size: 13px; font-weight: 500; color: #121212;">Búsqueda parcial</span>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0;">Envuelve automáticamente con % si no se indica.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 0.75rem; padding: 1rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.5rem;">
      <span style="font-family: 'JetBrains Mono', monospace; font-size: 13px; font-weight: 600; color: #121212; background-color: #F5F5F5; padding: 0.15rem 0.4rem; border-radius: 0.375rem;">IN</span>
      <span style="font-size: 13px; font-weight: 500; color: #121212;">Pertenencia</span>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0;">Requiere array de valores.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 0.75rem; padding: 1rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.5rem;">
      <span style="font-family: 'JetBrains Mono', monospace; font-size: 12px; font-weight: 600; color: #121212; background-color: #F5F5F5; padding: 0.15rem 0.4rem; border-radius: 0.375rem;">THIS_MONTH</span>
      <span style="font-size: 13px; font-weight: 500; color: #121212;">Mes actual</span>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0;">Filtra registros del mes actual.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 0.75rem; padding: 1rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.5rem;">
      <span style="font-family: 'JetBrains Mono', monospace; font-size: 12px; font-weight: 600; color: #121212; background-color: #F5F5F5; padding: 0.15rem 0.4rem; border-radius: 0.375rem;">LAST_MONTH</span>
      <span style="font-size: 13px; font-weight: 500; color: #121212;">Mes anterior</span>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0;">Filtra registros del mes anterior.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 0.75rem; padding: 1rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.5rem;">
      <span style="font-family: 'JetBrains Mono', monospace; font-size: 12px; font-weight: 600; color: #121212; background-color: #F5F5F5; padding: 0.15rem 0.4rem; border-radius: 0.375rem;">IN_MONTH</span>
      <span style="font-size: 13px; font-weight: 500; color: #121212;">Mes específico</span>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0;">Acepta <code>YYYY-MM</code> o <code>{ year, month }</code>.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 0.75rem; padding: 1rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.5rem;">
      <span style="font-family: 'JetBrains Mono', monospace; font-size: 12px; font-weight: 600; color: #121212; background-color: #F5F5F5; padding: 0.15rem 0.4rem; border-radius: 0.375rem;">IN_YEAR</span>
      <span style="font-size: 13px; font-weight: 500; color: #121212;">Año específico</span>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0;">Acepta <code>YYYY</code> o <code>{ year }</code>.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 0.75rem; padding: 1rem; background-color: #ffffff;">
    <div style="display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.5rem;">
      <span style="font-family: 'JetBrains Mono', monospace; font-size: 11px; font-weight: 600; color: #121212; background-color: #F5F5F5; padding: 0.15rem 0.4rem; border-radius: 0.375rem;">HORA_ENTRE</span>
      <span style="font-size: 13px; font-weight: 500; color: #121212;">Rango horario</span>
    </div>
    <p style="font-size: 12px; color: #6B6B6B; margin: 0;">Acepta <code>[min, max]</code> o <code>{ min, max }</code>.</p>
  </div>
</div>

<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Notas prácticas</h2>

<alert type="success">
  <ul>
    <li>Usa siempre <code>{ field, operator, value }</code> en <code>where</code>.</li>
    <li>Incluye nombres de tablas externas en <code>externalTableIds</code> o <code>internalTableIds</code>.</li>
    <li>Para full-text sin columna exacta → <code>searchKey</code> solo, sin <code>header/field</code>.</li>
    <li>Condiciones inválidas se omiten y el handler continúa.</li>
    <li>AND/OR se reagrupan con paréntesis automáticamente.</li>
  </ul>
</alert>