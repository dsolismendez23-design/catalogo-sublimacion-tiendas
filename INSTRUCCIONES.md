# Catálogo Sublimación Tiendas — Guía rápida

Es una copia del **Catálogo Sublimación** hecha para que las tiendas pidan diseños. Usa el mismo Google Drive (CATALOGO MODATELAS) y funciona igual. La diferencia es que **cada pedido pide la tienda** que lo hace:

**SAN RAMÓN · HEREDIA · CARTAGO · GUAPILES · DESAMPARADOS · TIBAS · BODEGA**

Las dos apps son independientes: cada una tiene sus propios pedidos, su propia numeración y su propia configuración.

## Instalar en la computadora (Windows)
Ejecute `dist\CatalogoSublimacionTiendas-Instalador-1.1.0.exe` (crea el ícono "Catálogo Sublimación Tiendas" en el Escritorio).
También está `dist\CatalogoSublimacionTiendas-Portable-1.1.0.exe`, que se abre sin instalar.

## Hacer un pedido
1. Busque los diseños por código o por tema y presione **+ Agregar**.
2. Escriba el nombre del cliente (puede agregar varios clientes con **+ Agregar otro cliente**).
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

## Archivo para celular Android
En **Configuración → Generar archivo para celular** se crea `Documentos\Catalogo Sublimacion Tiendas celular\CatalogoSublimacionTiendas.html`. Páselo al celular y ábralo con Chrome. En el celular también pide la tienda.

Esta app todavía **no tiene enlace publicado** en internet (el del catálogo original sigue siendo solo del original). Para iPhone haría falta publicarla aparte.

## Para programar
- `npm start`: abre la app.
- `npm run dist`: arma el instalador y el portable en `dist\`.
- `npm run movil`: arma el archivo para celular en `celular\`.
- La lista de tiendas está en `src/app.js` (constante `TIENDAS`).
- Datos en `%APPDATA%\Catalogo Sublimacion Tiendas`.

## Control de pedidos (pestaña "Control de pedidos")
Muestra todos los pedidos realizados con su tienda, cuántos ítems llegaron y su estado. Los botones de arriba filtran: **Todos · Sin cerrar · Pendientes · Completados**. El buscador busca por tienda, cliente, número de pedido o código.

1. Presione **Abrir** en un pedido.
2. Marque con ✔ cada ítem **recibido**. Cada marca se guarda al momento con su fecha y hora. **Marcar todo como recibido** marca todo de una vez.
3. Presione **Cerrar pedido**:
   - si **todos** los ítems están recibidos, el pedido queda **Completado** (verde);
   - si falta **alguno**, queda **Pendiente** (amarillo).
4. Un pedido Pendiente se puede volver a abrir para marcar lo que llegue y cerrarlo otra vez. Si a un pedido Completado se le quita una marca, vuelve a quedar Pendiente.

"Salir sin cerrar" guarda las marcas pero no cambia el estado. Los pedidos que nunca se han cerrado salen como **Sin cerrar**.
