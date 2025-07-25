# 🚀 Flujo de Trabajo Completo - procalculoFactory

## 📋 Tabla de Contenido

- [👥 Estructura del Equipo](#-estructura-del-equipo)
- [📋 FASE 1: Llegada y Triaje de Issues](#-fase-1-llegada-y-triaje-de-issues)
- [💻 FASE 2: Desarrollo](#-fase-2-desarrollo)
- [📋 Flujo para atender un Issues](#-flujo-para-atender-un-issues)
- [🎨 Mejores Prácticas para Pull Requests](#-mejores-prácticas-para-pull-requests)
- [🔥 Flujo para HotFix](#-flujo-para-hotfix-urgente---producción)
- [🏷️ Convenciones de Naming](#️-convenciones-de-naming)
- [⚠️ Notas Importantes](#️-notas-importantes)

---

## 👥 Estructura del Equipo

- **👑 LÍDER TÉCNICO**: Sebastián Díaz (@procalculoFactoryLeader)
  - Backend senior, Desktop, ArcGIS, Arquitectura, Supervisión general

- **🎯 FULLSTACK 1**: Andrés Carlos (@andres-c94)
  - Frontend, Backend de soporte, Supervisión de Brayan

- **⚙️ FULLSTACK 2**: Brian Bohórquez (@bbohorquezs)
  - Backend, Frontend de soporte

- **🎨 ARQUITECTURA CLOUD, INFRAESTRUCTURA, DEVELOPER JR**: Brayan Gerez (@bgerez)
  - Cloud, AWS Scripts

---

## 📋 FASE 1: Llegada y Triaje de Issues

### 1.1 Creación del Issue

**🎯 Quién puede crear issues:**
- Clientes/usuarios (bugs, feature requests)
- Product Owner/Manager
- Cualquier miembro del equipo
- QA/Testing team

**📝 Proceso:**
1. Ir al repositorio correspondiente
2. Click en **"New Issue"**
3. Seleccionar template apropiado:
   - 🐛 Bug Report (Frontend/Backend/Desktop)
   - ✨ Feature Request (Frontend/Backend/Desktop)
   - 👑 Technical Review (solo Sebastián)
   - 🔗 Cross-Project Issue (Sebastián)
   - 🔄 Backend Support (Fullstack)
   - 🔧 Jr Tasks

### 1.2 Auto-asignación según Template

**⚡ Asignación automática:**
```
Frontend Issues → andres-c94
Backend Issues → procalculoFactoryLeader  
Desktop/ArcGIS → procalculoFactoryLeader
Backend Fullstack → andres-c94
Jr Frontend Tasks → bgerez
Jr Backend Tasks → bbohorquezs
Technical Review → procalculoFactoryLeader
Cross-Project → procalculoFactoryLeader
```

### 1.3 Triaje Semanal (Lunes 9:00 AM)

**👑 Sebastián lidera el triaje:**

1. **Revisar issues `needs-triage`**

2. **Asignar prioridades:**
   - 🔴 **Crítica**: Bloquea producción/usuarios
   - 🟡 **Alta**: Afecta funcionalidad importante
   - 🟢 **Media**: Mejora significativa
   - 🔵 **Baja**: Nice to have

3. **Estimar effort:**
   - 🟢 **1-2 días**
   - 🟡 **3-5 días**
   - 🔴 **1+ semana**
   - 🟣 **Épica** (dividir en subtasks)

4. **Asignar a Sprint actual o Backlog**

---

## 💻 FASE 2: Desarrollo

### 2.1 Tomar Ownership del Issue

**📋 El desarrollador asignado debe:**

1. **Leer completamente el issue**
2. **Comentar en el issue:**
   ```
   🎯 Tomando ownership de este issue
   📅 ETA: [fecha estimada]
   ❓ Preguntas: [si las hay]
   ```
3. **Cambiar label** de `needs-triage` a `in-progress`
4. **Mover en GitHub Project** a columna "In Progress"

### 2.2 Branching Strategy

**🌿 Convención de nombres:**
```bash
# Para features
feature/ISS-123-nueva-funcionalidad

# Para bugs  
bugfix/ISS-456-corregir-login

# Para hotfixes
hotfix/ISS-789-error-critico-produccion

# Para tareas junior
task/ISS-321-actualizar-componente-jr

# Para refactor/arquitectura
refactor/ISS-654-optimizar-queries
```

**📝 Crear branch:**
```bash
# Desde main/master actualizado
git checkout main
git pull origin main
```

---

## 📋 Flujo para atender un Issues

### 🌟 Flujo Principal (Feature/BugFix)

#### 1️⃣ Asegurarse que development está actualizado
```bash
git checkout development
git pull origin development
```
#### 🔍 Métodos para verificar sincronización
## 1️⃣ Método rápido - Comparar commits
```bash# Actualizar referencias remotas primero
git fetch origin
```
## Verificar si development está detrás de main
```bash
git log development..origin/main --oneline
```
📊 Interpretación:

Sin output = development está actualizado ✅
Muestra commits = development está desactualizado ❌

#### 2️⃣ Verificar que main también está sync (buena práctica)
```bash
git checkout main 
git pull origin main
```

#### 3️⃣ Volver a development como base
```bash
git checkout development
```

#### 4️⃣ Crear branch desde development (NO desde main)

**🆕 Para Features:**
```bash
git checkout -b feature/ISS-123-user-login-validation
```

**🐛 Para Bug Fixes:**
```bash
git checkout -b bugfix/ISS-456-fix-password-reset-email
```

#### 5️⃣ Verificar que estás en la rama correcta
```bash
git branch
# * feature/ISS-123-user-login-validation
#   development  
#   main
```

#### 6️⃣ Push inicial
```bash
git push -u origin feature/ISS-123-user-login-validation
```

#### 7️⃣ Desarrollo con commits frecuentes

**🆕 Ejemplo para Feature:**
```bash
git add .
git commit -m "feat(auth): add email validation logic

- Implement email format validation
- Add error messaging
- Update tests

Related to #123"
```

**🐛 Ejemplo para BugFix:**
```bash
git add .
git commit -m "fix(auth): resolve password reset email issue

- Fix email template loading error
- Update SMTP configuration
- Add error handling for failed sends

Fixes #456"
```

#### 8️⃣ Push diario para backup
```bash
git push origin feature/ISS-123-user-login-validation
```

#### 9️⃣ Crear Pull Request a development

##### 🎯 Paso a paso en GitHub:

**1. 🌐 Ir a GitHub y navegar al repositorio**
```
https://github.com/tu-usuario/tu-repositorio
```

**2. 🔍 GitHub detectará automáticamente tu nueva rama**
- Verás un banner amarillo: "feature/ISS-123-user-login-validation had recent pushes"
- Click en **"Compare & pull request"**

**3. 🔄 Si no aparece el banner automático:**
- Click en **"Pull requests"** tab
- Click en **"New pull request"**
- Seleccionar:
  - **Base:** `development` ← **Compare:** `feature/ISS-123-user-login-validation`

**4. 📝 Completar el formulario del PR:**

**🏷️ Título del PR:**
```
feat(auth): Add user login validation - ISS-123
```

**📄 Descripción del PR (Template):**
```markdown
## 📋 Descripción
Brief description of what this PR does.

## 🎯 Issue relacionado
- Related to #123
- [Link to issue](https://github.com/user/repo/issues/123)

## 🔄 Tipo de cambio
- [ ] Bug fix (non-breaking change which fixes an issue)
- [x] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] Documentation update

## ✅ Cambios realizados
- [x] Implement email validation logic
- [x] Add error messaging for invalid emails
- [x] Update unit tests
- [x] Update documentation

## 🧪 Testing
- [x] Unit tests pass
- [x] Integration tests pass
- [x] Manual testing completed

## 📸 Screenshots (si aplica)
[Add screenshots of UI changes]

## 📝 Checklist
- [x] Code follows project style guidelines
- [x] Self-review completed
- [x] Tests added/updated
- [x] Documentation updated
- [x] No breaking changes
```

**5. ⚙️ Configurar opciones del PR:**

**👥 Reviewers:**
- Click en ⚙️ junto a "Reviewers"
- Seleccionar team members o usuarios específicos
- Ejemplo: `@tech-lead`, `@senior-dev`

**👤 Assignees:**
- Asignarte a ti mismo como responsable

**🏷️ Labels:**
- `feature` para nuevas funcionalidades
- `bugfix` para corrección de bugs
- `priority: high/medium/low`
- `size: small/medium/large`

**📊 Projects:**
- Asociar con el proyecto correspondiente si usas GitHub Projects

**🎯 Milestone:**
- Asociar con el sprint o milestone actual

**6. ✨ Crear el Pull Request:**
- Click en **"Create pull request"**

**7. 📢 Después de crear el PR:**

**🔔 Notificar al equipo:**
- En Slack/Teams: "PR ready for review: [link]"
- Tag a los reviewers si es necesario

**📈 Seguimiento:**
- Responder a comentarios de reviewers
- Hacer cambios solicitados
- Push cambios adicionales a la misma rama

---

## 🎨 Mejores Prácticas para Pull Requests

### 📝 Template automático para PRs

**📁 Crear archivo `.github/pull_request_template.md`:**
```markdown
## 📋 Descripción
<!-- Brief description of what this PR does -->

## 🎯 Issue relacionado
<!-- Link to issue: Fixes #123, Related to #456 -->

## 🔄 Tipo de cambio
- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] Documentation update

## ✅ Cambios realizados
<!-- List of changes made -->

## 🧪 Testing
- [ ] Unit tests pass
- [ ] Integration tests pass
- [ ] Manual testing completed

## 📝 Checklist
- [ ] Code follows project style guidelines
- [ ] Self-review completed
- [ ] Tests added/updated
- [ ] Documentation updated
- [ ] No breaking changes
```

### 🔍 Review Process

**👨‍💻 Para Reviewers:**
1. **🎯 Code Quality Check:**
   - Lógica correcta
   - Estilo de código consistente
   - Manejo de errores adecuado
   - Performance considerations

2. **🧪 Testing Verification:**
   - Tests cubren casos edge
   - Tests pasan localmente
   - No hay regression

3. **🔒 Security Review:**
   - No hay vulnerabilidades
   - Input validation adecuada
   - Credentials no hardcodeadas

**✍️ Para Author (después de feedback):**
1. **💬 Responder a comentarios:**
   - Hacer cambios solicitados
   - Explicar decisiones si no se cambia algo
   - Resolver todas las conversaciones

2. **🔄 Push cambios adicionales:**
   ```bash
   git add .
   git commit -m "fix: address review feedback
   
   - Update error handling logic
   - Add missing test cases
   - Fix code style issues"
   
   git push origin feature/ISS-123-user-login-validation
   ```

3. **🔁 Re-request review:**
   - En GitHub, click "Re-request review" 
   - Notificar que cambios están listos

### 🚨 Troubleshooting común

**⚠️ Problema: Conflicts en el PR**
```bash
# 1. Actualizar tu rama local
git checkout feature/ISS-123-user-login-validation
git fetch origin
git merge origin/development

# 2. Resolver conflicts manualmente
# 3. Commit la resolución
git add .
git commit -m "resolve merge conflicts with development"

# 4. Push la resolución
git push origin feature/ISS-123-user-login-validation
```

**📦 Problema: PR muy grande**
- Dividir en múltiples PRs más pequeños
- Usar draft PRs para trabajo en progreso
- Crear PRs incrementales

**🔧 Problema: CI/CD falla**
```bash
# Ver logs en GitHub Actions/CI
# Fix issues localmente
git add .
git commit -m "fix: resolve CI issues"
git push origin feature/ISS-123-user-login-validation
```

**📅 Problema: Branch desactualizada**
```bash
# Rebase para limpiar historial
git checkout feature/ISS-123-user-login-validation
git rebase origin/development
git push --force-with-lease origin feature/ISS-123-user-login-validation
```

### 📊 GitHub Features útiles

**✏️ Draft PRs:**
- Para trabajo en progreso
- No asignar reviewers hasta que esté listo
- Convertir a ready cuando esté completo

**🤖 Auto-merge:**
- Configurar auto-merge después de aprobaciones
- Solo para PRs no críticos

**🛡️ Branch protection rules:**
- Require review before merge
- Require status checks
- Restrict pushes to main/development

**⌨️ GitHub CLI (opcional):**
```bash
# Instalar GitHub CLI
# Crear PR desde terminal
gh pr create --title "feat(auth): Add login validation" --body "Related to #123"

# Ver status de PRs
gh pr status

# Merge PR desde terminal
gh pr merge 123 --squash
```

---

## 🔥 Flujo para HotFix (Urgente - Producción)

### 🚨 Proceso de Emergencia

#### 1️⃣ Asegurarse que main está actualizado
```bash
git checkout main
git pull origin main
```

#### 2️⃣ Crear branch desde main (NO desde development)
```bash
git checkout -b hotfix/ISS-789-critical-security-patch
```

#### 3️⃣ Verificar que estás en la rama correcta
```bash
git branch
# * hotfix/ISS-789-critical-security-patch
#   development  
#   main
```

#### 4️⃣ Push inicial
```bash
git push -u origin hotfix/ISS-789-critical-security-patch
```

#### 5️⃣ Implementar el fix urgente
```bash
git add .
git commit -m "hotfix(security): patch critical vulnerability

- Fix SQL injection in user query
- Update input sanitization
- Add security tests

URGENT: Fixes #789"
```

#### 6️⃣ Push del hotfix
```bash
git push origin hotfix/ISS-789-critical-security-patch
```

#### 7️⃣ Crear Pull Request a main (URGENTE)

##### 🆘 Paso a paso para HotFix:

**1. 🚨 Crear PR en GitHub:**
- Base: `main` ← Compare: `hotfix/ISS-789-critical-security-patch`

**2. 🔥 Título del PR:**
```
🚨 HOTFIX(security): Critical security patch - ISS-789
```

**3. 📋 Descripción del PR (Template para HotFix):**
```markdown
## 🚨 HOTFIX CRÍTICO

### 🔥 Problema
Brief description of the critical issue being fixed.

### 🎯 Issue relacionado
- Fixes #789 (CRITICAL)
- [Link to issue](https://github.com/user/repo/issues/789)

### ⚡ Solución implementada
- [x] Fix SQL injection vulnerability
- [x] Update input sanitization
- [x] Add security tests
- [x] Verify fix in staging

### 🧪 Testing de emergencia
- [x] Security tests pass
- [x] Critical path tested
- [x] No regression detected

### 📋 Impact Assessment
- **Sistemas afectados:** Production API
- **Usuarios impactados:** All users
- **Downtime esperado:** 0 minutes
- **Rollback plan:** Available

### ✅ Checklist HOTFIX
- [x] Issue is critical/blocking production
- [x] Fix is minimal and targeted
- [x] Testing completed
- [x] Staging deployment successful
- [x] Rollback plan ready
```

**4. ⚡ Configurar PR urgente:**
- **👥 Reviewers:** Solo reviewers senior/tech leads
- **🏷️ Labels:** `hotfix`, `critical`, `security`
- **🔴 Priority:** URGENT

**5. 🏃‍♂️ Proceso acelerado:**
- Notificar inmediatamente en canales de emergencia
- Review express (max 30 minutos)
- Merge directo después de aprobación

**6. 🚀 Post-merge inmediato:**
- Deploy a producción
- Monitoreo intensivo
- Notificar resolución del incidente

#### 8️⃣ Sincronizar development con el hotfix
```bash
# Después del merge a main
git checkout development
git pull origin development
git merge main  # Traer el hotfix a development
git push origin development
```

---

## 🏷️ Convenciones de Naming

### 🌿 Branches
- **🆕 Features:** `feature/ISS-{número}-{descripción-corta}`
- **🐛 Bug Fixes:** `bugfix/ISS-{número}-{descripción-corta}`
- **🔥 Hot Fixes:** `hotfix/ISS-{número}-{descripción-corta}`

### 📝 Commits
- **🆕 Features:** `feat(scope): descripción`
- **🐛 Bug Fixes:** `fix(scope): descripción`
- **🔥 Hot Fixes:** `hotfix(scope): descripción`

### 🎯 Ejemplos de Scopes
- `auth` 🔐 - Autenticación
- `ui` 🎨 - Interfaz de usuario
- `api` 🌐 - API/Backend
- `db` 🗄️ - Base de datos
- `security` 🔒 - Seguridad
- `performance` ⚡ - Rendimiento

---

## ⚠️ Notas Importantes

### 🚫 **NUNCA crear features/bugfix desde main**
- ✅ Siempre usar `development` como base para features y bugfix
- ⚠️ Solo usar `main` para hotfix críticos

### 📋 **Issues deben estar vinculados**
- 🆕 Usar `Related to #123` para features
- 🐛 Usar `Fixes #456` para bugfix y hotfix

### 🔄 **Pull Requests**
- 🆕🐛 Features/BugFix → `development`
- 🔥 HotFix → `main` (luego sincronizar con development)
