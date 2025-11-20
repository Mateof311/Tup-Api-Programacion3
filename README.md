# Tup-Api-Programacion3

API desarrollada en C# (.NET) como práctica final de la materia **Programación 3 (TUP)**.  
Implementa un sistema de **E-Commerce mayorista y minorista**, incluyendo gestión de productos, carrito, usuarios, compras y administración.

## 🚀 Tecnologías utilizadas
- .NET (C#)
- Entity Framework Core
- SQL Server / LocalDB
- Swagger

## 🛒 Descripción del sistema
El sistema permite compras minoristas y mayoristas, con 3 roles:

### 👤 Client
- Registrarse / iniciar sesión  
- Ver productos  
- Agregar/quitar del carrito  
- Confirmar compra  
- Elegir tipo de entrega

### 🛠️ Admin
- Crear productos  
- Editar productos  
- Eliminar productos  
- Consultar clientes (limitado)

### 🧩 SysAdmin
- Crear usuarios (Client / Admin / SysAdmin)  
- Editar usuarios  
- Eliminar usuarios  
- Consultar todos los usuarios  
- Gestionar administradores  
- Gestionar clientes  
*(Todas estas acciones verificadas en los controladores AdminController y ClientController.)*

## 🏗️ Modelo de dominio
### User (abstract)
- Id, Name, Email, Password, Location, Dni, UserRol

Herencia:
- Client
- Admin
- SysAdmin

### Cart
- Id, ClientId, Delivery, Products, TotalAmount

### Item
- Id, ProductId, ProductName, UnitPrice, Quantity, Total, CartId

### Product
- Id, Name, Price, Stock, Brand

## 📌 Endpoints principales
### Auth
- POST /auth/register  
- POST /auth/login  

### Products (Admin)
- GET /products  
- POST /products  
- PUT /products/{id}  
- DELETE /products/{id}

### Clients
- GET /client/getall (SysAdmin/Admin)
- POST /client/addclient (público)
- PUT /client/updateclient/{id} (SysAdmin)
- DELETE /client/deleteclient/{id} (SysAdmin)

### Admins (SysAdmin)
- GET /admin/getall  
- POST /admin/addadmin  
- PUT /admin/updateadmin/{id}  
- DELETE /admin/deleteadmin/{id}

## 🛠️ Cómo ejecutar localmente
```
git clone https://github.com/Mateof311/Tup-Api-Programacion3.git
cd Tup-Api-Programacion3
dotnet restore
dotnet run
```

Swagger:  
`https://localhost:xxxx/swagger/index.html`

## 📦 Base de datos
Si usás EF Migrations:
```
dotnet ef database update
```

## 📚 Qué aprendí
- Herencia en entidades  
- Relaciones 1-1 y 1-N  
- Endpoints REST  
- Validaciones  
- Manejo de roles  
- Swagger y documentación  
