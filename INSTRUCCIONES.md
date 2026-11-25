# Catálogo Sublimación Tiendas — Guía rápida

Es una copia del **Catálogo Sublimación** hecha para que las tiendas pidan diseños. Usa el mismo Google Drive (CATALOGO MODATELAS) y funciona igual. La diferencia es que **cada pedido pide la tienda** que lo hace:

**SAN RAMÓN · HEREDIA · CARTAGO · GUAPILES · DESAMPARADOS · TIBAS · BODEGA**

Las dos apps son independientes: cada una tiene sus propios pedidos, su propia numeración y su propia configuración.

## Instalar en la computadora (Windows)
Ejecute `dist\CatalogoSublimacionTiendas-Instalador-1.2.0.exe` (crea el ícono "Catálogo Sublimación Tiendas" en el Escritorio).
También está `dist\CatalogoSublimacionTiendas-Portable-1.2.0.exe`, que se abre sin instalar.

## Hacer un pedido
1. Busque los diseños por código o por tema y presione **+ Agregar**.
2. Escriba el nombre del cliente (puede agregar varios clientes con **+ Agregar otro cliente**).
   Las **cantidades pueden llevar decimales** (por ejemplo 1.25 o 1,25), hasta 2 decimales. Los botones − y + suman o restan 1.
3. Presione **Enviar pedido**.
4. **Elija la tienda** que hace el pedido. Es obligatorio. La última tienda usada queda marcada.
5. Elija **PDF** o **Excel**. Se abre WhatsApp con el resumen y el archivo queda copiado: péguelo con **Ctrl + V**.

La tienda sale en:
- el **PDF**: franja morada "TIENDA …" debajo del encabezado;
- el **Excel**: fila "TIENDA: …" arriba, y la columna **Tienda** en la hoja *Detalle*;
- el **mensaje de WhatsApp**: línea *TIENDA: …*;
- el **nombre del archivo**: `Pedido 0001 - HEREDIA - Cliente - fecha.pdf`;
- **Pedidos hechos**: columna Tienda. El buscador también busca por tienda (por ejemplo, escriba "cartago").

Los archivos quedan en `Documentos\Pedidos Sublimacion Tiendas`.

## Celulares Android y iPhone: enlace publicado (recomendado)
**https://dsolismendez23-design.github.io/catalogo-sublimacion-tiendas/**

- En la app de Windows: Configuración → **Copiar enlace**, y envíelo por WhatsApp a cada tienda.
- **Android:** abrir el enlace en **Chrome** → menú ⋮ → **Agregar a pantalla principal** (o **Instalar app**). Queda el ícono "Pedidos tiendas".
- **iPhone:** abrir en **Safari** → Compartir → **Agregar a pantalla de inicio**.
- **Se actualiza solo** cada 4 horas (6:20 y 10:20 a. m., 2:20 y 6:20 p. m., etc.) con los diseños nuevos del Google Drive. GitHub a veces atrasa estas corridas un par de horas. Para actualizar al momento: https://github.com/dsolismendez23-design/catalogo-sublimacion-tiendas/actions → *Publicar catálogo tiendas* → **Run workflow**.
- Es público: cualquiera con el enlace ve el catálogo. Los pedidos y el control se guardan solo en cada celular; no quedan en GitHub.

## Archivo para celular Android (sin internet de por medio)
En **Configuración → Generar archivo para celular** se crea `Documentos\Catalogo Sublimacion Tiendas celular\CatalogoSublimacionTiendas.html`. Páselo al celular y ábralo con Chrome. No se actualiza solo y no queda con ícono.

## Para programar
- `npm start`: abre la app.
- `npm run dist`: arma el instalador y el portable en `dist\`.
- `npm run movil`: arma el archivo para celular en `celular\`.
- La lista de tiendas está en `src/app.js` (constante `TIENDAS`).
- Datos en `%APPDATA%\Catalogo Sublimacion Tiendas`.

## Control de pedidos (pestaña "Control de pedidos")
Muestra **una fila por cliente**: si un pedido trae 3 clientes, salen 3 filas (0001 · cliente 1 de 3, etc.), y cada cliente se controla y se cierra por separado. Cada fila trae la tienda, cuántos ítems de ese cliente llegaron y su estado. Los botones de arriba filtran: **Todos · Sin cerrar · Pendientes · Completados**. El buscador busca por tienda, cliente, número de pedido o código.

1. Presione **Abrir** en el cliente.
2. Marque con ✔ cada ítem **recibido**. Cada marca se guarda al momento con su fecha y hora. **Marcar todo como recibido** marca todo de una vez.
3. Presione **Cerrar pedido**:
   - si **todos** los ítems de ese cliente están recibidos, queda **Completado** (verde);
   - si falta **alguno**, queda **Pendiente** (amarillo).
4. Un cliente Pendiente se puede volver a abrir para marcar lo que llegue y cerrarlo otra vez. Si a uno Completado se le quita una marca, vuelve a quedar Pendiente. Cerrar un cliente no cambia a los demás clientes del mismo pedido.

"Salir sin cerrar" guarda las marcas pero no cambia el estado. Los clientes que nunca se han cerrado salen como **Sin cerrar**.
