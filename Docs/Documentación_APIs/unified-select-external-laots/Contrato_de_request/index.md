<h2 style="font-size: 20px; font-weight: 600; letter-spacing: -0.02em; color: rgb(18, 18, 18); margin-bottom: 1rem; font-family: Inter, system-ui, sans-serif;">Contrato de request</h2>

<p style="font-family: Georgia, serif; font-size: 16px; font-style: italic; color: rgb(107, 107, 107); line-height: 1.6; margin-bottom: 1.5rem;">
  El body del request acepta un JSON con cinco bloques opcionales: <code>where</code> para filtros, <code>metrics</code> para agregados, <code>groupBy</code> para agrupaciones, <code>internalTableIds</code> y <code>externalTableIds</code> para expansión de relaciones. Todos pueden combinarse en una sola petición.
</p>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 1rem; margin-bottom: 1.5rem;">
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.25rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 40px; height: 40px; border-radius: 10px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1rem;">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M22 3H2l8 9.46V19l4 2v-8.54L22 3z"></path></svg>
    </div>
    <h3 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.5rem; margin-top: 0;">where</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Array de condiciones. Cada condición indica <code>header</code> (tabla LAOT), <code>field</code>, <code>operator</code> y <code>value</code>. Se combinan con <strong>AND</strong> por defecto.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.25rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 40px; height: 40px; border-radius: 10px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1rem;">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="20" x2="18" y2="10"></line><line x1="12" y1="20" x2="12" y2="4"></line><line x1="6" y1="20" x2="6" y2="14"></line></svg>
    </div>
    <h3 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.5rem; margin-top: 0;">metrics</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Array de operaciones de agregación: <code>SUM</code>, <code>COUNT</code>, <code>AVG</code>, <code>MIN</code>, <code>MAX</code>. Cada métrica indica <code>operation</code>, <code>field</code>, <code>alias</code> y opcionalmente <code>header</code>.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.25rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 40px; height: 40px; border-radius: 10px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1rem;">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="7" height="7"></rect><rect x="14" y="3" width="7" height="7"></rect><rect x="14" y="14" width="7" height="7"></rect><rect x="3" y="14" width="7" height="7"></rect></svg>
    </div>
    <h3 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.5rem; margin-top: 0;">groupBy</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Objeto con <code>columna</code> y <code>alias</code>. Agrupa los resultados por el campo indicado. Se usa junto a <code>metrics</code> para obtener totales por grupo.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.25rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 40px; height: 40px; border-radius: 10px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1rem;">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z"></path><polyline points="3.27 6.96 12 12.01 20.73 6.96"></polyline><line x1="12" y1="22.08" x2="12" y2="12"></line></svg>
    </div>
    <h3 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.5rem; margin-top: 0;">internalTableIds</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Array de nombres de tablas LAOT internas a expandir. La respuesta anida los registros relacionados dentro de cada resultado.</p>
  </div>
  <div style="border: 1px solid #E5E5E5; border-radius: 1rem; padding: 1.25rem; background-color: #ffffff;">
    <div style="display: inline-flex; align-items: center; justify-content: center; width: 40px; height: 40px; border-radius: 10px; background-color: rgb(245, 245, 245); color: rgb(18, 18, 18); margin-bottom: 1rem;">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle><line x1="2" y1="12" x2="22" y2="12"></line><path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"></path></svg>
    </div>
    <h3 style="font-size: 15px; font-weight: 600; color: #121212; margin-bottom: 0.5rem; margin-top: 0;">externalTableIds</h3>
    <p style="font-size: 13px; color: #6B6B6B; line-height: 1.55; margin: 0;">Array de nombres de tablas externas del mismo <code>Enterprise_id</code> a expandir. La respuesta trae datos de múltiples tablas en una sola consulta, con una estructura diferente a <code>internalTableIds</code>.</p>
  </div>
</div>

<div style="border-left: 4px solid #F59E0B; background-color: #FFFBEB; border-radius: 0.5rem; padding: 1rem 1.25rem; margin-bottom: 1.5rem;">
  <p style="margin: 0; font-size: 13px; color: #92400E; line-height: 1.7;">
    <strong>Importante:</strong> todos los bloques son opcionales. Un request con body vacío <code>{}</code> devuelve todos los registros de la tabla sin filtros ni expansión. La combinación de <code>internalTableIds</code> y <code>externalTableIds</code> en el mismo request es posible, pero la <strong>estructura de la respuesta cambia</strong> según cuál se utilice.
  </p>
</div>