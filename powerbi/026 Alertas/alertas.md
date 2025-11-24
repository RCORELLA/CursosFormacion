# Ejercicio Completo: Crear Alertas en Power BI Service

## Objetivo
Crear un informe con datos de ventas desde Excel, publicarlo en Power BI Service, añadirlo a un dashboard y configurar una alerta que se dispare automáticamente.

---

## PASO 1: Preparar el archivo Excel

### 1.1 Crea un archivo llamado `ventas_diarias.xlsx` con estos datos:

| Fecha | Ventas | Meta_Diaria |
|------------|--------|-------------|
| 01/11/2024 | 4500 | 5000 |
| 02/11/2024 | 5200 | 5000 |
| 03/11/2024 | 4800 | 5000 |
| 04/11/2024 | 5500 | 5000 |
| 05/11/2024 | 4200 | 5000 |
| 06/11/2024 | 5800 | 5000 |
| 07/11/2024 | 4600 | 5000 |

### 1.2 Guarda el archivo en tu ordenador
- Recuerda la ubicación del archivo

---

## PASO 2: Crear el informe en Power BI Desktop

### 2.1 Importar los datos
1. Abre **Power BI Desktop**
2. Haz clic en **Obtener datos** > **Excel**
3. Selecciona tu archivo `ventas_diarias.xlsx`
4. Marca la tabla y haz clic en **Cargar**

### 2.2 Crear una medida para las ventas de hoy
1. En el panel de **Campos**, haz clic derecho en tu tabla
2. Selecciona **Nueva medida**
3. Escribe esta fórmula DAX:

```dax
Ventas Hoy = 
VAR UltimaFecha = MAX('ventas_diarias'[Fecha])
RETURN
CALCULATE(
    SUM('ventas_diarias'[Ventas]),
    'ventas_diarias'[Fecha] = UltimaFecha
)
```

### 2.3 Crear una tarjeta (Card) visual
1. En el panel de **Visualizaciones**, selecciona el visual **Tarjeta**
2. Arrastra la medida **Ventas Hoy** al campo **Campos** de la tarjeta
3. Dale formato:
   - Haz clic en el pincel (Formato visual)
   - Activa **Etiqueta de categoría**
   - Escribe como título: "Ventas de Hoy"
   - Formato de número: Moneda (€ o $)

### 2.4 Opcional: Crear visuales adicionales
- Añade un gráfico de líneas con la evolución de ventas
- Añade otra tarjeta con la Meta Diaria
- Esto hará tu informe más completo

### 2.5 Guardar el informe
1. **Archivo** > **Guardar como**
2. Nómbralo: `Informe_Ventas_Alertas`

---

## PASO 3: Publicar en Power BI Service

### 3.1 Publicar el informe
1. En Power BI Desktop, haz clic en **Publicar** (botón en la cinta superior)
2. Si te pide iniciar sesión, usa tus credenciales de Power BI
3. Selecciona **Mi área de trabajo** (o un área de trabajo específica)
4. Haz clic en **Seleccionar**
5. Espera el mensaje: "Publicación en Power BI correcta"
6. Haz clic en **Abrir 'Informe_Ventas_Alertas' en Power BI**

### 3.2 Configurar la actualización de datos (importante para alertas)
1. En Power BI Service, ve a **Mi área de trabajo**
2. Busca el **conjunto de datos** (aparece con un icono de tabla)
3. Haz clic en los **tres puntos (...)** junto al conjunto de datos
4. Selecciona **Configuración**
5. En **Credenciales del origen de datos**, haz clic en **Editar credenciales**
6. Selecciona **Cuenta de Microsoft** o las credenciales apropiadas
7. Haz clic en **Iniciar sesión**

---

## PASO 4: Crear el Dashboard

### 4.1 Anclar la tarjeta al dashboard
1. En el informe abierto en Power BI Service, pasa el cursor sobre la **tarjeta de Ventas Hoy**
2. Haz clic en el icono de **chincheta** (📌) que aparece en la esquina superior derecha
3. Selecciona **Nuevo dashboard**
4. Nómbralo: `Dashboard Ventas con Alertas`
5. Haz clic en **Anclar**

### 4.2 Verificar el dashboard
1. Haz clic en el enlace que aparece para ir al dashboard
2. Deberías ver tu tarjeta con las ventas del día

---

## PASO 5: Configurar la Alerta

### 5.1 Crear la regla de alerta
1. En el dashboard, localiza la tarjeta **Ventas Hoy**
2. Haz clic en los **tres puntos (...)** en la esquina superior derecha de la tarjeta
3. Selecciona **Administrar alertas**
4. Haz clic en **+ Agregar regla de alerta**

### 5.2 Configurar los parámetros
- **Título:** Ventas por debajo de la meta
- **Condición:** Por debajo de
- **Umbral:** 5000
- **Frecuencia de notificaciones:** Como máximo una vez al día
- Activa **Enviarme también un correo electrónico**
- Haz clic en **Guardar y cerrar**

---

## PASO 6: Probar la Alerta

### Opción A: Actualizar datos en Excel (Recomendado)

1. Abre tu archivo `ventas_diarias.xlsx`
2. Añade una nueva fila con la fecha de hoy y ventas bajas:
   ```
   24/11/2024 | 4000 | 5000
   ```
3. Guarda el archivo
4. En Power BI Service, ve a **Mi área de trabajo**
5. Busca tu conjunto de datos
6. Haz clic en los **tres puntos (...)** y selecciona **Actualizar ahora**
7. Espera 1-2 minutos
8. Ve a tu dashboard y verifica que el valor ha cambiado
9. Revisa tu correo electrónico y el **Centro de notificaciones** de Power BI (icono de campana 🔔)

### Opción B: Ajustar el umbral para prueba rápida

1. Ve a **Administrar alertas** en la tarjeta
2. Edita la alerta existente
3. Cambia el umbral a un valor por **encima** de tus ventas actuales
   - Por ejemplo, si tienes 4600, ponlo en 4700
4. Guarda
5. La alerta debería dispararse inmediatamente
6. Verifica tu correo y el centro de notificaciones

---

## PASO 7: Verificar las Notificaciones

### 7.1 Centro de notificaciones de Power BI
1. En Power BI Service, haz clic en el icono de **campana** (🔔) en la barra superior
2. Deberías ver la notificación de tu alerta

### 7.2 Correo electrónico
1. Revisa tu bandeja de entrada
2. Busca un correo de `no-reply@microsoft.com` o `alerts-noreply@microsoft.com`
3. El asunto será algo como: "Alerta de datos: Ventas por debajo de la meta"

---

## PASO 8: Administrar Alertas (Opcional)

### Ver todas tus alertas
1. En Power BI Service, haz clic en el **icono de engranaje** ⚙️ (esquina superior derecha)
2. Selecciona **Configuración**
3. Ve a la pestaña **Alertas**
4. Aquí puedes ver, editar o eliminar todas tus alertas

---

## Consejos Adicionales

### ✅ Mejores prácticas
- Usa umbrales realistas basados en tus datos históricos
- No configures demasiadas alertas (puedes saturarte de notificaciones)
- Ajusta la frecuencia según la criticidad del KPI

### ⚠️ Limitaciones importantes
- Las alertas solo funcionan en: **Tarjetas, KPIs y Medidores**
- Los datos deben actualizarse para que se evalúen las alertas
- Hay límites en el número de alertas según tu licencia:
  - **Power BI Pro:** Hasta 500 alertas
  - **Power BI Premium:** Ilimitadas

### 🔄 Actualización automática
Para que las alertas funcionen sin intervención manual:
1. Configura una **actualización programada** del conjunto de datos
2. Ve a **Configuración del conjunto de datos** > **Actualización programada**
3. Activa la actualización automática (requiere Power BI Gateway si el Excel está local)

---

## Solución de Problemas

**❌ La alerta no se dispara:**
- Verifica que los datos se hayan actualizado
- Comprueba que el umbral sea correcto
- Asegúrate de que el visual es una tarjeta, KPI o medidor

**❌ No recibo correos:**
- Revisa la carpeta de spam
- Verifica que activaste "Enviarme también un correo electrónico"
- Comprueba la configuración de tu cuenta en Power BI

**❌ No puedo publicar:**
- Asegúrate de tener una licencia de Power BI (Pro o Premium)
- Verifica tu conexión a internet
- Intenta iniciar sesión nuevamente

---

## ¡Ejercicio Completado! 🎉

Ahora tienes un sistema funcional de alertas en Power BI que te notificará automáticamente cuando tus ventas caigan por debajo del umbral establecido.