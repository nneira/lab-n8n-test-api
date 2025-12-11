# 🔗 n8n OAuth 2.0 - Conectar Google APIs

Workflow de prueba para verificar que tus credenciales OAuth 2.0 están correctamente configuradas en n8n.

**Suscríbete en:** https://www.youtube.com/@nicolasneiragarcia?sub_confirmation=1

**Video tutorial completo:** [Cómo conectar n8n con Google Drive, Sheets, Calendar (OAuth 2.0)] https://www.youtube.com/watch?v=mndPg8wGVNQ

---

## 📦 ¿Qué incluye este workflow?

Este workflow prueba la conexión de **5 Google APIs** en paralelo:

- ✅ Gmail (obtiene 1 email)
- ✅ Google Drive (crea carpeta de prueba)
- ✅ Google Calendar (obtiene 5 eventos)
- ✅ Google Sheets (crea spreadsheet de prueba)
- ✅ Google Tasks (obtiene 5 tareas)

---

## 🚀 Setup Rápido

### 1. Prerequisitos

Antes de importar este workflow, necesitas:

- ✅ Proyecto creado en Google Cloud Console
- ✅ APIs habilitadas (Gmail, Drive, Calendar, Sheets, Tasks)
- ✅ Pantalla de consentimiento OAuth configurada
- ✅ Usuario de prueba agregado
- ✅ Credencial OAuth creada (Client ID + Secret)

**Si no tienes esto configurado**, ve el video tutorial primero: [OAuth 2.0 Parte 1 - Setup desde CERO] https://youtu.be/s1HoX4W1hvw?si=4z9rYNW6ZVeb2WjN

---

### 2. Importar Workflow

1. Descarga `api_test.json`
2. En n8n: Click en **"..."** (menú) → **Import from File**
3. Selecciona `api_test.json`
4. Click **Import**

---

### 3. Configurar Credenciales

El workflow viene **sin credenciales** (por seguridad). Debes conectar las tuyas:

#### Opción A: Usar LA MISMA credencial OAuth para todo (Recomendado)

1. En n8n, ve a **Credentials** (menú lateral)
2. Crea UNA credencial OAuth con estos scopes:
   - Gmail API
   - Drive API
   - Calendar API
   - Sheets API
   - Tasks API

3. Asigna esa credencial a los 5 nodos del workflow

#### Opción B: Credenciales separadas

Crea una credencial para cada API:
- `Gmail OAuth2`
- `Google Drive OAuth2`
- `Google Calendar OAuth2`
- `Google Sheets OAuth2`
- `Google Tasks OAuth2`

---

### 4. Ejecutar Prueba

1. Click en **"Execute Workflow"**
2. Todos los nodos deben aparecer en **verde** ✅
3. Si alguno falla en **rojo** ❌, ve [Troubleshooting](#-troubleshooting)

---

## 🐛 Troubleshooting

### Error: "API not enabled"

**Causa:** La API no está habilitada en Google Cloud Console

**Solución:**
1. Ve a: https://console.cloud.google.com
2. **API & Services** → **Library**
3. Busca la API que falla (ej: "Google Sheets API")
4. Click **Enable**
5. Vuelve a ejecutar el workflow

---

### Error: "Forbidden - perhaps check your credentials?"

**Causa:** Credencial mal configurada o sin permisos

**Solución:**
1. Ve a **Credentials** en n8n
2. Click en la credencial OAuth
3. Verifica:
   - ✅ Client ID correcto
   - ✅ Client Secret correcto
   - ✅ Redirect URL agregada en Google Cloud Console
4. Click **Connect** y vuelve a autorizar

---

### Error: "User not authorized"

**Causa:** Tu email no está en la lista de usuarios de prueba

**Solución:**
1. Google Cloud Console → **OAuth consent screen**
2. **Test users** → **Add Users**
3. Agrega tu email de Google
4. Guarda cambios
5. Vuelve a conectar la credencial en n8n

---

### Error en Google Tasks: "Invalid task list"

**Causa:** El ID de lista de tareas no existe en tu cuenta

**Solución:**
1. Abre el nodo **"Test Google Tasks"**
2. En el campo **"Task List"**, selecciona:
   - `@default` (tu lista principal)
   - O cualquier lista que tengas creada
3. Guarda y ejecuta

---

## 📚 Recursos

- **Video tutorial Parte 1:** [Setup OAuth Gmail desde CERO] https://youtu.be/s1HoX4W1hvw?si=4z9rYNW6ZVeb2WjN
- **Video tutorial Parte 2:** [Conectar Drive, Sheets, Calendar] https://www.youtube.com/watch?v=s1HoX4W1hvw
- **Documentación oficial n8n:** https://docs.n8n.io/integrations/builtin/credentials/google/
- **Google Cloud Console:** https://console.cloud.google.com

---

## 🤔 Preguntas Frecuentes

### ¿Puedo usar este workflow en producción?

No, este workflow es **solo para pruebas**. Crea tus propios workflows según tus necesidades.

### ¿Necesito una credencial diferente para cada API?

No. Puedes usar **UNA sola credencial OAuth** para todas las Google APIs. Solo asegúrate de que tenga los scopes necesarios.

### ¿Por qué el workflow crea carpetas/spreadsheets de prueba?

Para verificar que n8n tiene **permisos de escritura**, no solo lectura. Puedes borrarlos después de la prueba.

### ¿Funciona con cuentas gratuitas de Google?

Sí, no necesitas Google Workspace. Funciona con cuentas @gmail.com normales.

### ¿Cuánto cuesta usar Google Cloud Console?

Las APIs de Gmail, Drive, Calendar, Sheets y Tasks son **100% gratuitas** para uso personal/moderado. No pagas nada.

---

## 📧 Contacto

- **Email:** hola@nicolasneira.com
- **YouTube:** [Nicolás Neira García] https://www.youtube.com/@nicolasneiragarcia?sub_confirmation=1
- **GitHub:** nneira

---

## 📄 Licencia

MIT License - Usa este workflow libremente en tus proyectos.

---

**¿Te sirvió este workflow? Dale ⭐ al repo y suscríbete al canal para más tutoriales de n8n. https://www.youtube.com/@nicolasneiragarcia?sub_confirmation=1 **
