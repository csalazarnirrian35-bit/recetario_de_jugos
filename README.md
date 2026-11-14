# Recetario de Jugos — Aplicación Web Full Stack

Aplicación web desarrollada de extremo a extremo con **Java y Spring Boot** bajo el patrón de arquitectura **Modelo-Vista-Controlador (MVC)**. El sistema permite a usuarios registrados gestionar su propio catálogo de recetas de jugos (nombre, descripción, ingredientes, instrucciones de preparación e imagen de portada), integrando autenticación segura, operaciones CRUD completas y validaciones en tiempo real.

Proyecto desarrollado como parte de mi certificación intensiva **Bootcamp Desarrollador Full Stack Java (180 horas)** impartido por **Skillnest** en convocatoria con **Banco de Chile**.

---

## Funcionalidades Principales

### Módulo de Usuarios y Seguridad (`ControladorUsuarios`)
*   **Registro de Usuarios (`/formulario/registro` y `/procesa/registro`):** Creación de cuentas con validación de formulario (`@Valid`, `BindingResult`) y encriptación segura de contraseñas mediante **BCrypt**.
*   **Inicio de Sesión (`/login`):** Autenticación mediante DTO dedicado (`LoginUsuario`), verificación de credenciales y manejo de sesión activa (`idUsuario`, `nombreCompleto`) con `HttpSession`.
*   **Cierre de Sesión (`/logout`):** Invalidación segura de la sesión mediante `sesion.invalidate()`.

###  Módulo de Gestión de Recetas (`ControladorJugos`)
*   **Control de Acceso:** Protección de todas las vistas y formularios verificando sesión activa antes de renderizar información.
*   **Operaciones CRUD Completas:**
    *   **Lectura (`/jugos` y `/detalle/{id}`):** Visualización del listado general y ficha detallada de preparación.
    *   **Creación (`/formulario/agregar` y `/agregar`):** Formulario vinculado con Spring Form Tags (`<form:form>`, `modelAttribute="jugo"`) para registrar título, descripción, ingredientes, instrucciones y URL de portada.
    *   **Actualización (`/formulario/editar/{id}` y `/editar`):** Edición de recetas existentes mediante peticiones HTTP `PUT`.
    *   **Eliminación (`/eliminar/{id}`):** Borrado de registros mediante peticiones HTTP `DELETE`.
*   **Validaciones de Negocio:** Uso de `<form:errors>` en vista y validación personalizada en `ServicioJugos` para evitar recetas con títulos duplicados.

  ## 🛠️ Tecnologías Utilizadas

*   **Backend:** Java, Spring Boot, Spring Web MVC, Spring Data JPA.
*   **Seguridad y Sesiones:** `HttpSession`, Jakarta Validation (`@Valid`), DTOs de validación y encriptación con BCrypt.
*   **Frontend:** JSP (JavaServer Pages), Spring Form Taglib, JSTL, HTML5, CSS3.
*   **Base de Datos:** MySQL (Persistencia relacional con ORM / Hibernate).
*   **Control de Versiones:** Git y GitHub.

---

## Estructura del Proyecto (Arquitectura MVC)

```text
src/
├── main/
│   ├── java/com/cynthiasalazar/
│   │   ├── controllers/    # ControladorUsuarios y ControladorJugos
│   │   ├── models/         # Entidades JPA y DTOs (Usuario, LoginUsuario, Jugo)
│   │   ├── repositories/   # Interfaces Spring Data JPA
│   │   └── services/       # Lógica de negocio y validaciones personalizadas
│   └── webapp/WEB-INF/     # Vistas dinámicas JSP (login, registro, jugos, agregar, editar, detalle)
```

## Cómo ejecutar este proyecto localmente

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com
   ```
2. **Configurar la base de datos MySQL:**
   * Crea una base de datos vacía en MySQL Workbench o consola.
   * Abre `src/main/resources/application.properties` y configura tu URL de conexión, usuario y contraseña locales.
3. **Ejecutar la aplicación:**
   * Abre el proyecto en Spring Tool Suite (STS), IntelliJ IDEA o VS Code.
   * Ejecuta la clase principal con `@SpringBootApplication`.
   * Ingresa en tu navegador a `http://localhost:8080` para registrarte o iniciar sesión.
---

## Datos de Contacto:

**Cynthia del Carmen Salazar Nirrian**  
Desarrolladora Full Stack Java Junior  
*   **LinkedIn:** [www.linkedin.com/in/cynthia-salazar-nirrian-1b43a7435]
*   **GitHub:** [https://github.com/csalazarnirrian35-bit]
