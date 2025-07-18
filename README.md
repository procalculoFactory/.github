<html><head></head><body><h1>🚀 Flujo de Trabajo Completo - procalculoFactory</h1>
<h2>👥 Estructura del Equipo</h2>
<ul>
<li><strong>👑 LÍDER TÉCNICO</strong>: Sebastián Díaz (@procalculoFactoryLeader)
<ul>
<li>Backend senior, Desktop, ArcGIS, Arquitectura, Supervisión general</li>
</ul>
</li>
<li><strong>🎯 FULLSTACK SENIOR</strong>: Andrés Carlos (@andres-c94)
<ul>
<li>Frontend lead, Backend de soporte, Supervisión de Brayan</li>
</ul>
</li>
<li><strong>⚙️ BACKEND JR</strong>: Brian Bohórquez (@bbohorquezs)
<ul>
<li>Backend junior, supervisión de Sebastián</li>
</ul>
</li>
<li><strong>🎨 FRONTEND JR</strong>: Brayan Gerez (@bgerez)
<ul>
<li>Frontend junior, supervisión de Andrés</li>
</ul>
</li>
</ul>
<hr>
<h2>📋 FASE 1: Llegada y Triaje de Issues</h2>
<h3>1.1 Creación del Issue</h3>
<p><strong>🎯 Quién puede crear issues:</strong></p>
<ul>
<li>Clientes/usuarios (bugs, feature requests)</li>
<li>Product Owner/Manager</li>
<li>Cualquier miembro del equipo</li>
<li>QA/Testing team</li>
</ul>
<p><strong>📝 Proceso:</strong></p>
<ol>
<li>Ir al repositorio correspondiente</li>
<li>Click en <strong>"New Issue"</strong></li>
<li>Seleccionar template apropiado:
<ul>
<li>🐛 Bug Report (Frontend/Backend/Desktop)</li>
<li>✨ Feature Request (Frontend/Backend/Desktop)</li>
<li>👑 Technical Review (solo Sebastián)</li>
<li>🔗 Cross-Project Issue (Sebastián)</li>
<li>🔄 Backend Support (Fullstack)</li>
<li>🔧 Jr Tasks</li>
</ul>
</li>
</ol>
<h3>1.2 Auto-asignación según Template</h3>
<p><strong>⚡ Asignación automática:</strong></p>
<pre><code>Frontend Issues → andres-c94
Backend Issues → procalculoFactoryLeader  
Desktop/ArcGIS → procalculoFactoryLeader
Backend Fullstack → andres-c94
Jr Frontend Tasks → bgerez
Jr Backend Tasks → bbohorquezs
Technical Review → procalculoFactoryLeader
Cross-Project → procalculoFactoryLeader
</code></pre>
<h3>1.3 Triaje Semanal (Lunes 9:00 AM)</h3>
<p><strong>👑 Sebastián lidera el triaje:</strong></p>
<ol>
<li>
<p><strong>Revisar issues <code>needs-triage</code></strong></p>
</li>
<li>
<p><strong>Asignar prioridades:</strong></p>
<ul>
<li>🔴 <strong>Crítica</strong>: Bloquea producción/usuarios</li>
<li>🟡 <strong>Alta</strong>: Afecta funcionalidad importante</li>
<li>🟢 <strong>Media</strong>: Mejora significativa</li>
<li>🔵 <strong>Baja</strong>: Nice to have</li>
</ul>
</li>
<li>
<p><strong>Estimar effort:</strong></p>
<ul>
<li>🟢 <strong>1-2 días</strong></li>
<li>🟡 <strong>3-5 días</strong></li>
<li>🔴 <strong>1+ semana</strong></li>
<li>🟣 <strong>Épica</strong> (dividir en subtasks)</li>
</ul>
</li>
<li>
<p><strong>Asignar a Sprint actual o Backlog</strong></p>
</li>
</ol>
<hr>
<h2>💻 FASE 2: Desarrollo</h2>
<h3>2.1 Tomar Ownership del Issue</h3>
<p><strong>📋 El desarrollador asignado debe:</strong></p>
<ol>
<li><strong>Leer completamente el issue</strong></li>
<li><strong>Comentar en el issue:</strong>
<pre><code>🎯 Tomando ownership de este issue📅 ETA: [fecha estimada]❓ Preguntas: [si las hay]
</code></pre></li>
<li><strong>Cambiar label</strong> de <code>needs-triage</code> a <code>in-progress</code></li>
<li><strong>Mover en GitHub Project</strong> a columna "In Progress"</li>
</ol>
<h3>2.2 Branching Strategy</h3>
<p><strong>🌿 Convención de nombres:</strong></p>
<pre><code class="language-bash"># Para features
feature/ISS-123-nueva-funcionalidad

# Para bugs  
bugfix/ISS-456-corregir-login

# Para hotfixes
hotfix/ISS-789-error-critico-produccion

# Para tareas junior
task/ISS-321-actualizar-componente-jr

# Para refactor/arquitectura
refactor/ISS-654-optimizar-queries
</code></pre>
<p><strong>📝 Crear branch:</strong></p>
<pre><code class="language-bash"># Desde main/master actualizado
git checkout main
git pull origin main

# Crear nueva branch
git checkout -b feature/ISS-123-nueva-funcionalidad

# Push inicial
git push -u origin feature/ISS-123-nueva-funcionalidad
</code></pre>
<h3>2.3 Desarrollo con Mejores Prácticas</h3>
<h4>🔄 Commits Convencionales</h4>
<pre><code class="language-bash"># Tipos permitidos:
feat: nueva funcionalidad
fix: correción de bug
docs: documentación
style: formateo (no afecta lógica)
refactor: refactorización de código
test: agregar/modificar tests
chore: tareas de mantenimiento

# Formato:
git commit -m "feat(frontend): add user login validation

- Add email format validation
- Add password strength requirements  
- Improve error messaging
- Update tests

Closes #123"
</code></pre>
<h4>🧪 Testing Requirements</h4>
<p><strong>Antes de crear PR:</strong></p>
<p><strong>Frontend:</strong></p>
<ul>
<li>✅ Componentes renderizan correctamente</li>
<li>✅ Funcionalidad básica probada</li>
<li>✅ Responsive design verificado</li>
<li>✅ No errores en consola</li>
</ul>
<p><strong>Backend:</strong></p>
<ul>
<li>✅ Unit tests para nueva funcionalidad</li>
<li>✅ Integration tests para endpoints</li>
<li>✅ Postman/API tests documentados</li>
<li>✅ Performance acceptable</li>
</ul>
<p><strong>Desktop:</strong></p>
<ul>
<li>✅ Funcionalidad en Windows 10/11</li>
<li>✅ Compatibilidad con .NET target</li>
<li>✅ No memory leaks</li>
<li>✅ Instalador actualizado (si necesario)</li>
</ul>
<h3>2.4 Comunicación Durante Desarrollo</h3>
<h4>🆘 Escalación por Complejidad</h4>
<p><strong>Si encuentras blocker:</strong></p>
<ol>
<li><strong>Intentar resolver por 2-4 horas</strong></li>
<li><strong>Documentar el problema:</strong>
<pre><code>🚨 BLOCKER en #123Problema: [descripción técnica]Intentado: [lo que ya probaste]Contexto: [información relevante]Ayuda necesaria: [específica]
</code></pre></li>
<li><strong>Escalación según jerarquía:</strong>
<ul>
<li><strong>Brayan (Frontend Jr)</strong> → Andrés → Sebastián</li>
<li><strong>Brian (Backend Jr)</strong> → Sebastián</li>
<li><strong>Andrés (Fullstack)</strong> → Sebastián (solo arquitectura crítica)</li>
</ul>
</li>
</ol>
<h4>📅 Updates Regulares</h4>
<p><strong>Daily progress (Slack/Teams):</strong></p>
<pre><code>📍 Update ISS-123
✅ Completado: [tareas del día]
🚧 En progreso: [tarea actual]  
📅 Próximo: [plan para mañana]
❓ Blockers: [si los hay]
</code></pre>
<hr>
<h2>🔍 FASE 3: Code Review</h2>
<h3>3.1 Crear Pull Request</h3>
<p><strong>📋 PR Template obligatorio:</strong></p>
<pre><code class="language-markdown">## Issue
Closes #123

## Descripción
Descripción clara de los cambios realizados.

## Tipo de cambio
- [ ] Bug fix (non-breaking change)
- [ ] New feature (non-breaking change)  
- [ ] Breaking change (fix o feature que causa que funcionalidad existente no funcione)
- [ ] Documentación

## Checklist
- [ ] Mi código sigue las convenciones del proyecto
- [ ] He hecho self-review de mi código
- [ ] He comentado mi código en áreas complejas
- [ ] He actualizado la documentación  
- [ ] Mis cambios no generan warnings
- [ ] He agregado tests que prueban mi fix/feature
- [ ] Tests nuevos y existentes pasan localmente

## Testing realizado
- [ ] Frontend: Probado en Chrome, Firefox, Safari
- [ ] Backend: Unit tests, integration tests, Postman
- [ ] Desktop: Probado en Windows 10/11

## Screenshots/GIFs
[Si aplica para cambios visuales]
</code></pre>
<h3>3.2 Jerarquía de Review</h3>
<h4>🎯 Matriz de Revisión</h4>

Desarrollador | Primer Review | Segundo Review | Deployment Approval
-- | -- | -- | --
Brayan (FE Jr) | Andrés | Sebastián (si crítico) | Andrés
Brian (BE Jr) | Sebastián | - | Sebastián
Andrés (Fullstack) | Sebastián | - | Sebastián
Sebastián (Leader) | Auto-approve* | - | Auto-approve


<p>*Solo para cambios menores. Arquitectura debe revisarse con el equipo.</p>
<h4>📋 Review Checklist</h4>
<p><strong>🎨 Frontend Review (Andrés revisa a Brayan):</strong></p>
<ul>
<li>✅ <strong>Funcionalidad</strong>: ¿Cumple requirements?</li>
<li>✅ <strong>UI/UX</strong>: ¿Sigue design system?</li>
<li>✅ <strong>Performance</strong>: ¿No degrada rendimiento?</li>
<li>✅ <strong>Responsive</strong>: ¿Funciona en mobile/tablet?</li>
<li>✅ <strong>Accessibility</strong>: ¿Es accesible?</li>
<li>✅ <strong>Code Quality</strong>: ¿Está bien estructurado?</li>
<li>✅ <strong>Testing</strong>: ¿Está bien probado?</li>
</ul>
<p><strong>⚙️ Backend Review (Sebastián revisa a Brian):</strong></p>
<ul>
<li>✅ <strong>Arquitectura</strong>: ¿Sigue patrones establecidos?</li>
<li>✅ <strong>Security</strong>: ¿No introduce vulnerabilidades?</li>
<li>✅ <strong>Performance</strong>: ¿Queries optimizadas?</li>
<li>✅ <strong>API Design</strong>: ¿RESTful/consistente?</li>
<li>✅ <strong>Error Handling</strong>: ¿Maneja errores apropiadamente?</li>
<li>✅ <strong>Documentation</strong>: ¿APIs documentadas?</li>
<li>✅ <strong>Testing</strong>: ¿Unit + integration tests?</li>
</ul>
<h3>3.3 Proceso de Review</h3>
<pre><code>1. PR creado → Notification automática a reviewer
2. Reviewer tiene 24h para initial review
3. Feedback → Developer corrige → Re-review
4. Approval → Merge autorizado
5. Si no response en 24h → Escalate en Slack
</code></pre>
<h3>3.4 Review Comments Guidelines</h3>
<p><strong>🟢 Aprobación:</strong></p>
<pre><code>✅ LGTM! Excelente trabajo con [aspecto específico]
Sugerencia menor: [opcional improvement]
</code></pre>
<p><strong>🟡 Cambios menores:</strong></p>
<pre><code>🔄 Request Changes
- Fix: [issue específico con línea de código]
- Improve: [sugerencia de mejora]
- Consider: [alternativa a considerar]
</code></pre>
<p><strong>🔴 Cambios mayores:</strong></p>
<pre><code>❌ Major Issues Found
- BLOCKER: [issue que debe corregirse]
- SECURITY: [problema de seguridad]
- ARCHITECTURE: [problema de diseño]

Suggested approach: [sugerencia de solución]
Let's discuss offline.
</code></pre>
<hr>
<h2>🚀 FASE 4: Testing y QA</h2>
<h3>4.1 Merge a Development</h3>
<p><strong>Una vez aprobado el PR:</strong></p>
<pre><code class="language-bash"># Merge strategy: Squash and merge (para historia limpia)
git checkout main
git pull origin main
git merge --squash feature/ISS-123-nueva-funcionalidad
git commit -m "feat: implement user login validation (#123)"
git push origin main
</code></pre>
<h3>4.2 Deployment Automático a Staging</h3>
<p><strong>🔄 CI/CD Pipeline se dispara:</strong></p>
<ol>
<li><strong>Linting + Tests</strong> (debe pasar 100%)</li>
<li><strong>Build</strong> (debe ser exitoso)</li>
<li><strong>Deploy to Staging</strong> (automático)</li>
<li><strong>Integration Tests</strong> (automáticos)</li>
<li><strong>Notify en Slack</strong> con staging URL</li>
</ol>
<h3>4.3 QA Testing en Staging</h3>
<p><strong>📋 QA Checklist:</strong></p>
<p><strong>Frontend:</strong></p>
<ul>
<li>✅ <strong>Functionality</strong>: Feature funciona como expected</li>
<li>✅ <strong>Cross-browser</strong>: Chrome, Firefox, Safari, Edge</li>
<li>✅ <strong>Responsive</strong>: Mobile, tablet, desktop</li>
<li>✅ <strong>Performance</strong>: Load times acceptable</li>
<li>✅ <strong>Accessibility</strong>: Screen readers, keyboard navigation</li>
</ul>
<p><strong>Backend:</strong></p>
<ul>
<li>✅ <strong>API Testing</strong>: Postman collection pasa</li>
<li>✅ <strong>Load Testing</strong>: Performance bajo carga</li>
<li>✅ <strong>Security Testing</strong>: Vulnerability scan</li>
<li>✅ <strong>Integration</strong>: Con otros servicios</li>
</ul>
<p><strong>Desktop:</strong></p>
<ul>
<li>✅ <strong>Installation</strong>: Clean install en fresh Windows</li>
<li>✅ <strong>Functionality</strong>: Core features funcionan</li>
<li>✅ <strong>Performance</strong>: No memory leaks, responsive UI</li>
<li>✅ <strong>Compatibility</strong>: Diferentes versiones Windows</li>
</ul>
<h3>4.4 Issue Closure</h3>
<p><strong>✅ Criteria para cerrar issue:</strong></p>
<ol>
<li><strong>Functionality verified</strong> en staging</li>
<li><strong>QA sign-off</strong> completo</li>
<li><strong>Performance acceptable</strong></li>
<li><strong>No regressions</strong> detectadas</li>
<li><strong>Documentation updated</strong> (si necesario)</li>
</ol>
<hr>
<h2>🌟 FASE 5: Producción</h2>
<h3>5.1 Release Planning</h3>
<p><strong>📅 Release Schedule:</strong></p>
<ul>
<li><strong>Hotfixes</strong>: Inmediato (solo bugs críticos)</li>
<li><strong>Minor releases</strong>: Semanal (viernes 5pm)</li>
<li><strong>Major releases</strong>: Quincenal/mensual (coordinado)</li>
</ul>
<h3>5.2 Pre-Production Checklist</h3>
<p><strong>🔍 Sebastián debe verificar:</strong></p>
<ul>
<li>✅ <strong>All tests passing</strong> en staging</li>
<li>✅ <strong>Performance metrics</strong> dentro de SLA</li>
<li>✅ <strong>Security scan</strong> limpio</li>
<li>✅ <strong>Database migrations</strong> preparadas (si aplica)</li>
<li>✅ <strong>Rollback plan</strong> documentado</li>
<li>✅ <strong>Monitoring</strong> configurado para nuevas features</li>
</ul>
<h3>5.3 Deployment Process</h3>
<h4>🔄 Deployment Strategy por Proyecto</h4>
<p><strong>Frontend (prisma-web, abaco-web, observatorio-web):</strong></p>
<pre><code class="language-bash"># Blue-Green deployment
1. Build production bundle
2. Deploy to green environment  
3. Run smoke tests
4. Switch traffic (blue → green)
5. Monitor for 30 min
6. Keep blue as rollback
</code></pre>
<p><strong>Backend (prisma-api, abaco-api):</strong></p>
<pre><code class="language-bash"># Rolling deployment
1. Deploy to staging servers
2. Run database migrations
3. Deploy to 50% production servers
4. Monitor metrics and logs
5. Deploy to remaining 50%
6. Full traffic to new version
</code></pre>
<p><strong>Desktop (prisma-desktop, abaco-desktop):</strong></p>
<pre><code class="language-bash"># Staged rollout
1. Build and sign installer
2. Deploy to beta channel (10% users)
3. Monitor crash reports
4. Deploy to stable channel (90% users)
5. Auto-update notification
</code></pre>
<h3>5.4 Post-Deployment Monitoring</h3>
<p><strong>📊 Sebastián supervisa por 2 horas:</strong></p>
<ul>
<li><strong>Error rates</strong> (must be &lt; baseline)</li>
<li><strong>Response times</strong> (must be &lt; SLA)</li>
<li><strong>User feedback</strong> (support tickets, reviews)</li>
<li><strong>System metrics</strong> (CPU, memory, disk)</li>
</ul>
<h3>5.5 Rollback Procedures</h3>
<p><strong>🚨 Rollback criteria:</strong></p>
<ul>
<li>Error rate &gt; 5% increase</li>
<li>Response time &gt; 2x baseline</li>
<li>Critical functionality broken</li>
<li>Security vulnerability detected</li>
</ul>
<p><strong>⚡ Rollback process (&lt; 15 min):</strong></p>
<pre><code class="language-bash"># Frontend: Switch traffic back
# Backend: Deploy previous version
# Desktop: Revert auto-update, notify users
# Database: Run rollback migrations (if needed)
</code></pre>
<hr>
<h2>📊 FASE 6: Post-Production</h2>
<h3>6.1 Issue Closure y Documentation</h3>
<p><strong>✅ Final steps:</strong></p>
<ol>
<li><strong>Update issue</strong> con staging/production URLs</li>
<li><strong>Close issue</strong> con comment:
<pre><code>✅ RESOLVED IN PRODUCTION📅 Deployed: [date]🔗 URLs: [production links]📊 Metrics: [performance data]
</code></pre></li>
<li><strong>Update documentation</strong> (if needed)</li>
<li><strong>Notify stakeholders</strong></li>
</ol>
<h3>6.2 Retrospective Data</h3>
<p><strong>📈 Track metrics:</strong></p>
<ul>
<li><strong>Lead time</strong>: Issue creation → Production</li>
<li><strong>Cycle time</strong>: Development start → Production</li>
<li><strong>Defect rate</strong>: Bugs found post-production</li>
<li><strong>Team velocity</strong>: Story points per sprint</li>
</ul>
<h3>6.3 Knowledge Sharing</h3>
<p><strong>📚 Weekly team meeting (viernes 4pm):</strong></p>
<ul>
<li><strong>What went well</strong> this week</li>
<li><strong>Challenges faced</strong> and solutions</li>
<li><strong>Lessons learned</strong> for next sprint</li>
<li><strong>Architectural decisions</strong> made</li>
<li><strong>New tools/techniques</strong> discovered</li>
</ul>
<hr>
<h2>⚡ Escalación y Comunicación</h2>
<h3>🆘 Emergency Escalation</h3>
<p><strong>Production down or critical bug:</strong></p>
<pre><code>1. Create CRITICAL issue immediately
2. Notify in #emergencies Slack channel
3. Page Sebastián (if after hours)
4. Assemble war room if needed
5. Fix, test, deploy ASAP
6. Post-mortem within 48h
</code></pre>
<h3>📱 Communication Channels</h3>
<ul>
<li><strong>#daily-updates</strong>: Progress reports</li>
<li><strong>#code-reviews</strong>: PR notifications</li>
<li><strong>#deployments</strong>: Release notifications</li>
<li><strong>#emergencies</strong>: Critical issues only</li>
<li><strong>#random</strong>: Team building, non-work</li>
</ul>
<h3>📋 Regular Ceremonies</h3>
<ul>
<li><strong>Daily standup</strong>: Lunes/Miércoles/Viernes 9:00 AM (15 min)</li>
<li><strong>Sprint planning</strong>: Cada 2 semanas, lunes 10:00 AM (60 min)</li>
<li><strong>Sprint review</strong>: Viernes antes de planning (30 min)</li>
<li><strong>Retrospective</strong>: Viernes después de review (30 min)</li>
<li><strong>Technical review</strong>: Según necesidad (Sebastián convoca)</li>
</ul>
<hr>
<h2>🎯 KPIs y Métricas de Éxito</h2>
<h3>📊 Team Metrics</h3>
<ul>
<li><strong>Lead Time</strong>: &lt; 7 días promedio</li>
<li><strong>Cycle Time</strong>: &lt; 3 días promedio</li>
<li><strong>Defect Rate</strong>: &lt; 5% bugs post-production</li>
<li><strong>Test Coverage</strong>: &gt; 80% backend, &gt; 70% frontend</li>
<li><strong>Code Review Time</strong>: &lt; 24 horas promedio</li>
</ul>
<h3>🎖️ Individual Metrics</h3>
<ul>
<li><strong>Sebastián</strong>: Architecture decisions, team mentoring, critical issues</li>
<li><strong>Andrés</strong>: Feature delivery, frontend quality, Brayan's growth</li>
<li><strong>Brian</strong>: Code quality improvement, learning velocity</li>
<li><strong>Brayan</strong>: Feature delivery, code quality improvement</li>
</ul>
<h3>🏆 Quality Metrics</h3>
<ul>
<li><strong>Production Stability</strong>: &gt; 99.5% uptime</li>
<li><strong>Performance</strong>: &lt; 2s load times</li>
<li><strong>Security</strong>: Zero critical vulnerabilities</li>
<li><strong>User Satisfaction</strong>: &gt; 4.5/5 app store ratings</li>
</ul></body></html>
