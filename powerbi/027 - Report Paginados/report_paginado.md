# 📄 Ejercicio Sencillo: Crear un Report Paginado en Power BI

[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Report Builder](https://img.shields.io/badge/Report%20Builder-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)](https://www.microsoft.com/download)

## 📋 Objetivo
Crear un informe paginado profesional con los datos de ventas diarias que pueda exportarse a PDF, Excel o imprimirse con formato perfecto.

## 🎯 ¿Qué son los Reports Paginados?
Los informes paginados son ideales para:
- 📊 **Informes impresos** con formato perfecto
- 📑 **Facturas, recibos** y documentos oficiales
- 📧 **Reportes automáticos** por correo electrónico
- 📝 **Listados detallados** con múltiples páginas
- 💾 **Exportación** a PDF, Excel, Word, CSV

## 📚 Tabla de Contenidos
- [Requisitos previos](#requisitos-previos)
- [Paso 1: Instalar Power BI Report Builder](#paso-1-instalar-power-bi-report-builder)
- [Paso 2: Preparar los datos](#paso-2-preparar-los-datos)
- [Paso 3: Crear el informe paginado](#paso-3-crear-el-informe-paginado)
- [Paso 4: Diseñar el informe](#paso-4-diseñar-el-informe)
- [Paso 5: Publicar y compartir](#paso-5-publicar-y-compartir)

---

## ✅ Requisitos previos

- ✔️ Power BI Report Builder (gratis)
- ✔️ Archivo `ventas_diarias.xlsx` (del ejercicio anterior)
- ✔️ Licencia de Power BI Pro o Premium (para publicar)
- ✔️ Windows (Report Builder solo funciona en Windows)

---

## 🔧 PASO 1: Instalar Power BI Report Builder

### 1.1 Descargar la herramienta
1. Ve a [Report Builder](https://www.microsoft.com/en-us/download/details.aspx?id=105942)
2. O desde Power BI Service:
   - Abre [app.powerbi.com](https://app.powerbi.com)
   - Haz clic en **Nuevo** > **Informe paginado**
   - Clic en **Descargar Power BI Report Builder**

### 1.2 Instalar
1. Ejecuta el instalador `PBIDesktopPaginatedReports.msi`
2. Sigue los pasos de instalación
3. Abre **Power BI Report Builder** desde el menú de inicio

---

## 📂 PASO 2: Preparar los datos

### 2.1 Usar el mismo archivo Excel
Utilizaremos el archivo `ventas_diarias.xlsx` del ejercicio anterior:

| Fecha | Ventas | Meta_Diaria |
|------------|--------|-------------|
| 01/11/2024 | 4500 | 5000 |
| 02/11/2024 | 5200 | 5000 |
| 03/11/2024 | 4800 | 5000 |
| 04/11/2024 | 5500 | 5000 |
| 05/11/2024 | 4200 | 5000 |
| 06/11/2024 | 5800 | 5000 |
| 07/11/2024 | 4600 | 5000 |

### 2.2 Opcional: Añadir más columnas para un informe más completo

Puedes añadir estas columnas adicionales para hacer el informe más interesante:

| Fecha | Vendedor | Producto | Ventas | Meta_Diaria |
|------------|----------|----------|--------|-------------|
| 01/11/2024 | Ana García | Laptop | 4500 | 5000 |
| 02/11/2024 | Luis Pérez | Monitor | 5200 | 5000 |
| 03/11/2024 | Ana García | Teclado | 4800 | 5000 |
| 04/11/2024 | María López | Mouse | 5500 | 5000 |
| 05/11/2024 | Luis Pérez | Laptop | 4200 | 5000 |
| 06/11/2024 | María López | Monitor | 5800 | 5000 |
| 07/11/2024 | Ana García | Teclado | 4600 | 5000 |

---

## 📊 PASO 3: Crear el informe paginado

### 3.1 Iniciar Report Builder
1. Abre **Power BI Report Builder**
2. Verás la pantalla de inicio con plantillas
3. Selecciona **Informe en blanco** o **Asistente para tablas**
4. Para este ejercicio, usaremos el **Asistente para tablas**

### 3.2 Conectar con el origen de datos

#### A través de Power BI Service (Recomendado)
1. En el asistente, haz clic en **Nuevo**
2. Selecciona **Power BI Dataset**
3. Inicia sesión en Power BI
4. Selecciona el conjunto de datos que publicaste anteriormente
5. Haz clic en **Siguiente**

### 3.3 Diseñar la consulta
1. En la ventana del diseñador de consultas:
   - Selecciona todos los campos: `Fecha`, `Ventas`, `Meta_Diaria`
   - (Si añadiste más columnas: `Vendedor`, `Producto`)
2. Haz clic en **Siguiente**

### 3.4 Organizar los campos
1. **Grupos de filas:** Arrastra `Fecha` aquí
2. **Valores:** Arrastra `Ventas` y `Meta_Diaria`
3. Haz clic en **Siguiente**

### 3.5 Elegir el diseño
1. Selecciona **Mostrar subtotales y totales generales**
2. Elige el estilo: **Corporativo** o **Océano**
3. Haz clic en **Siguiente** y luego **Finalizar**

---

## 🎨 PASO 4: Diseñar el informe

### 4.1 Añadir encabezado del informe
1. En la parte superior, haz clic derecho > **Insertar** > **Encabezado**
2. Arrastra un **Cuadro de texto** desde el panel de herramientas
3. Escribe: **"Informe de Ventas Diarias"**
4. Formato:
   - Fuente: **Arial, 18pt, Negrita**
   - Color: **Azul oscuro** (#003366)
   - Alineación: **Centrada**

### 4.2 Añadir fecha de generación
1. Añade otro cuadro de texto debajo del título
2. Haz clic derecho > **Expresión**
3. Escribe esta fórmula:
   ```vb
   ="Generado el: " & Format(Today(), "dd/MM/yyyy")
   ```
4. Formato:
   - Fuente: **Arial, 10pt**
   - Alineación: **Centrada**

### 4.3 Mejorar la tabla

#### Formato de columnas
1. **Columna Fecha:**
   - Selecciona la celda de datos (no el encabezado)
   - Formato: **dd/MM/yyyy**
   
2. **Columna Ventas:**
   - Formato de número: **Moneda**
   - Símbolo: **€** o **$**
   - Decimales: **2**

3. **Columna Meta_Diaria:**
   - Formato de número: **Moneda**
   - Símbolo: **€** o **$**
   - Decimales: **2**

#### Añadir formato condicional
1. Selecciona la celda de **Ventas** (fila de datos)
2. Haz clic derecho > **Propiedades del cuadro de texto**
3. Ve a **Relleno**
4. Haz clic en el botón **fx** junto a "Color de relleno"
5. Escribe esta expresión:
   ```vb
   =IIF(Fields!Ventas.Value < Fields!Meta_Diaria.Value, "LightCoral", "LightGreen")
   ```
6. Esto coloreará en **rojo claro** si no alcanza la meta y en **verde claro** si la supera

### 4.4 Añadir una columna calculada (Diferencia vs Meta)
1. Haz clic derecho en el encabezado de la última columna
2. **Insertar columna** > **A la derecha**
3. En el encabezado escribe: **"Diferencia"**
4. En la celda de datos, haz clic derecho > **Expresión**
5. Escribe:
   ```vb
   =Fields!Ventas.Value - Fields!Meta_Diaria.Value
   ```
6. Formato: **Moneda**, **2 decimales**

### 4.5 Añadir totales
1. Selecciona la última fila de la tabla (Total)
2. Verifica que muestre:
   - **Total de Ventas:** `=Sum(Fields!Ventas.Value)`
   - **Total de Metas:** `=Sum(Fields!Meta_Diaria.Value)`
3. Aplica formato **negrita** y color de fondo **gris claro**

### 4.6 Añadir pie de página
1. Haz clic derecho en la parte inferior > **Insertar** > **Pie de página**
2. Arrastra un cuadro de texto
3. Escribe esta expresión para número de página:
   ```vb
   ="Página " & Globals!PageNumber & " de " & Globals!TotalPages
   ```
4. Alineación: **Derecha**

---

## ☁️ PASO 5: Publicar y compartir

### 5.1 Vista previa del informe
1. Haz clic en la pestaña **Vista previa** (o presiona **F5**)
2. Verifica que todo se vea correctamente
3. Prueba la navegación entre páginas si hay múltiples

### 5.2 Guardar el archivo
1. **Archivo** > **Guardar como**
2. Guarda como: `Informe_Ventas_Paginado.rdl`
3. Ubicación: Tu carpeta local

### 5.3 Publicar en Power BI Service
1. En Report Builder: **Archivo** > **Publicar**
2. O haz clic en el icono de **Power BI** en la barra de herramientas
3. Selecciona **Mi área de trabajo** (o tu workspace)
4. Haz clic en **Seleccionar**
5. Espera la confirmación: "Publicación correcta"

### 5.4 Ver en Power BI Service
1. Ve a [app.powerbi.com](https://app.powerbi.com)
2. Navega a **Mi área de trabajo**
3. Busca tu informe: **Informe_Ventas_Paginado**
4. Haz clic para abrirlo

### 5.5 Exportar el informe

#### Desde Report Builder:
1. **Archivo** > **Exportar**
2. Elige el formato:
   - 📄 **PDF** - Para impresión o distribución
   - 📊 **Excel** - Para análisis adicional
   - 📝 **Word** - Para documentos editables
   - 📋 **CSV** - Para datos puros

#### Desde Power BI Service:
1. Abre el informe publicado
2. Haz clic en **Exportar**
3. Selecciona el formato deseado
4. Descarga el archivo

---

## 🚀 PASO 6: Funcionalidades avanzadas (Opcional)

### 6.1 Añadir parámetros
Los parámetros permiten filtrar el informe al ejecutarlo.

1. En Report Builder, ve al panel **Datos del informe**
2. Haz clic derecho en **Parámetros** > **Agregar parámetro**
3. Nombre: `FechaInicio`
4. Tipo de datos: **Fecha/hora**
5. Repite para crear `FechaFin`

6. Modifica el conjunto de datos:
   - Haz clic derecho en el dataset > **Propiedades del conjunto de datos**
   - Ve a **Filtros** > **Agregar**
   - Expresión: `[Fecha]`
   - Operador: `>=`
   - Valor: `[@FechaInicio]`
   - Añade otro filtro para `<=` `[@FechaFin]`

### 6.2 Añadir un gráfico
1. Desde el **Cuadro de herramientas**, arrastra un **Gráfico**
2. Selecciona tipo: **Gráfico de columnas**
3. Configura:
   - **Eje X:** Fecha
   - **Valores:** Ventas y Meta_Diaria
4. Personaliza colores y etiquetas

### 6.3 Programar suscripciones
En Power BI Service (requiere Premium):
1. Abre el informe paginado
2. Haz clic en **Suscribirse**
3. Configura:
   - **Frecuencia:** Diaria, semanal, mensual
   - **Destinatarios:** Correos electrónicos
   - **Formato:** PDF, Excel, etc.
   - **Parámetros:** Si los tienes configurados
4. Guarda la suscripción

---

## 💡 Comparación: Informe Regular vs Paginado

| Característica | Informe Regular | Informe Paginado |
|----------------|-----------------|------------------|
| **Interactividad** | ✅ Alta (filtros, drill-through) | ❌ Limitada |
| **Impresión** | ⚠️ Problemas de formato | ✅ Perfecto para imprimir |
| **Exportación PDF** | ⚠️ Básica | ✅ Profesional |
| **Múltiples páginas** | ❌ Una página larga | ✅ Paginación perfecta |
| **Tablas largas** | ⚠️ Scroll infinito | ✅ Divide en páginas |
| **Facturas/Recibos** | ❌ No ideal | ✅ Perfecto |
| **Suscripciones email** | ✅ Sí | ✅ Sí (más formatos) |
| **Diseño pixel-perfect** | ❌ No | ✅ Sí |

---

## 🔧 Solución de Problemas

**❌ No puedo instalar Report Builder:**
- Verifica que tienes Windows (no funciona en Mac/Linux)
- Asegúrate de tener permisos de administrador

**❌ No puedo publicar:**
- Verifica que tienes licencia Power BI Pro o Premium
- Comprueba tu conexión a internet
- Asegúrate de estar autenticado en Power BI

**❌ Los datos no se actualizan:**
- Los informes paginados usan conexión en vivo
- Si usas Excel, publica el archivo en SharePoint o OneDrive
- Considera usar un conjunto de datos de Power BI

**❌ El formato se rompe al exportar:**
- Verifica los márgenes de página
- Ajusta el ancho de las columnas
- Usa la vista previa antes de exportar

**❌ Las fórmulas no funcionan:**
- Report Builder usa **VB.NET**, no DAX
- Las expresiones deben empezar con `=`
- Los nombres de campo van entre `Fields!NombreCampo.Value`

---

## 📝 Ejercicios Adicionales

Una vez completes el ejercicio básico, intenta estos retos:

1. **🎯 Básico:** Añade un logotipo de tu empresa en el encabezado
2. **🎯 Intermedio:** Crea un parámetro para filtrar por vendedor
3. **🎯 Avanzado:** Añade un gráfico de tendencia de ventas
4. **🎯 Experto:** Diseña una factura completa con logo, datos del cliente y cálculos de IVA

---

## 🎉 ¡Ejercicio Completado!

Ahora tienes un informe paginado profesional que puedes:
- 📄 Exportar a PDF con formato perfecto
- 📊 Enviar automáticamente por correo
- 🖨️ Imprimir sin problemas de formato
- 📧 Programar como suscripción

### 📚 Recursos Adicionales

- [Documentación oficial de informes paginados](https://learn.microsoft.com/es-es/power-bi/paginated-reports/)
- [Expresiones en Report Builder](https://learn.microsoft.com/es-es/sql/reporting-services/report-design/expressions-report-builder-and-ssrs)
- [Tutorial de Microsoft sobre informes paginados](https://learn.microsoft.com/es-es/power-bi/paginated-reports/paginated-reports-quickstart-aw)

### 🤝 Contribuciones

Si encuentras algún error o tienes sugerencias, ¡contribuye al repositorio!

### 📄 Licencia

Este tutorial es de dominio público. Úsalo libremente.

---


**⭐ Si este tutorial te fue útil, dale una estrella en GitHub!**
