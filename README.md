# 📌 Trabajo Final – Sistema de Kiosco (C# + Windows Forms + SQL Server)

## 📝 Descripción General

Este proyecto fue desarrollado como trabajo final de segundo año para la materia de Programación Orientada a Objetos.
Consiste en un **sistema de gestión para un kiosco**, implementado en **C# (Windows Forms)** con una arquitectura basada en entidades, repositorios y una base de datos en **SQL Server** integrada desde Visual Studio.

El objetivo del trabajo era aplicar:

* Programación orientada a objetos (POO)
* Herencia, encapsulamiento y polimorfismo
* Manejo de formularios y eventos
* CRUD con SQL Server mediante repositorios
* Separación en capas (modelo + UI)

---

## 🧱 Arquitectura del Proyecto

La solución está dividida en **dos proyectos principales**:

### 🔹 1. `Modelo/`

Contiene toda la lógica del dominio:

#### **🧩 Entidades**

* `Cliente.cs`
* `Empleado.cs`
* `Producto.cs`
* `ProductoPerecedero.cs`
* `ProductoNoPerecedero.cs`
* `ItemVenta.cs`
* `Venta.cs`
* `Descuento.cs`

Incluye **herencia** en la jerarquía de productos (perecederos / no perecederos) y composición en ventas (lista de ítems).

#### **📦 Repositorios**

* `RepositorioCliente.cs`
* `RepositorioEmpleado.cs`
* `RepositorioProducto.cs`
* `RepositorioVenta.cs`
* `RepositorioItemVenta.cs`
* `RepositorioDescuento.cs`

Los repositorios encapsulan operaciones CRUD hacia SQL Server, permitiendo desacoplar la lógica del formulario.

---

### 🔹 2. `TrabajoFinal_v3/`

Proyecto de Windows Forms que implementa la interfaz gráfica.

#### **📄 Formularios Principales**

* `FormCliente` → alta/baja/modificación de clientes
* `FormEmpleado` → gestión de empleados
* `FormDescuentos` → administración de descuentos
* `FormVenta` → proceso completo de venta
* `FormHistorial` → listado de ventas registradas
* `FormAddStockGondola` / `FormAddStockHeladera` → carga y actualización de stock
* `FormPrincipal` → menú o pantalla principal

Cada formulario tiene su `.Designer.cs` y `.resx` correspondientes.

---

## 🛒 Funcionalidades del Sistema

### ✔ Gestión de Productos

* Clasificación en **perecederos y no perecederos**
* Control de stock
* Actualización por góndola o heladera
* Búsqueda y listado

### ✔ Gestión de Clientes

* Alta, baja y modificación
* Datos básicos y validación

### ✔ Gestión de Empleados

* Registro y mantenimiento de empleados

### ✔ Ventas

* Selección de productos
* Agregado de items a la venta
* Aplicación de descuentos
* Cálculo de subtotal, total y actualización de stock
* Registro automático en historial

### ✔ Historial de Ventas

* Consulta de ventas anteriores
* Detalle completo de la transacción

---

## 🗄 Base de Datos (SQL Server)

El sistema se conecta a una base de datos creada desde Visual Studio.

Tablas típicas utilizadas por los repositorios:

* **Productos**
* **Clientes**
* **Empleados**
* **Ventas**
* **DetalleVentas / ItemVenta**
* **Descuentos**

> La base se manejó con consultas SQL simples a través de ADO.NET.

---

## 📂 Estructura del Proyecto (resumen)

```
/Modelo
 ├── Entidades
 │    ├── Cliente.cs
 │    ├── Empleado.cs
 │    ├── Producto.cs
 │    ├── ProductoPerecedero.cs
 │    ├── ProductoNoPerecedero.cs
 │    ├── Venta.cs
 │    ├── ItemVenta.cs
 │    └── Descuento.cs
 ├── Repositorios
 │    ├── RepositorioCliente.cs
 │    ├── RepositorioEmpleado.cs
 │    ├── RepositorioProducto.cs
 │    ├── RepositorioVenta.cs
 │    ├── RepositorioItemVenta.cs
 │    └── RepositorioDescuento.cs
 └── Modelo.csproj

/TrabajoFinal_v3
 ├── FormPrincipal.cs
 ├── FormCliente.cs
 ├── FormEmpleado.cs
 ├── FormVenta.cs
 ├── FormHistorial.cs
 ├── FormDescuentos.cs
 ├── FormAddStockGondola.cs
 ├── FormAddStockHeladera.cs
 ├── Program.cs
 └── TrabajoFinal_v3.csproj
```

---

## ▶️ Cómo Ejecutarlo

1. Clonar el repositorio:

   ```bash
   git clone https://github.com/tuusuario/TrabajoFinalKiosco.git
   ```

2. Abrir la solución en Visual Studio.

3. Configurar la base de datos SQL Server:

   * Crear la base
   * Ejecutar el script SQL (si está incluido)
   * Ajustar la cadena de conexión en `app.config`

4. Ejecutar con **F5**.

---

## 🎓 Aprendizajes y Objetivos Cumplidos

* Aplicación real de **herencia** y **polimorfismo**
* Implementación del **patrón Repository**
* Separación en capas (Modelo / UI)
* CRUD con SQL Server
* Diseño y programación de formularios complejos
* Simulación completa de un sistema de kiosco

---

## 👤 Autor

**Kepa Gogenola**
Segundo año – Ingeniería en Sistemas Informáticos (UAI)
