# sistemasenviojava
# 🚚 Sistema **EnvíaConecta**

## 🧩 Descripción del proyecto
**EnvíaConecta** es un sistema desarrollado en **Java** bajo la arquitectura **MVC (Modelo–Vista–Controlador)**, diseñado para simular la gestión de envíos de paquetes.  
El proyecto aplica tres patrones de diseño —**Factory Method**, **Bridge** y **State**— con el fin de garantizar **flexibilidad, reutilización y bajo acoplamiento** entre las clases del sistema.

El sistema permite:
- Crear diferentes tipos de envíos (terrestres o aéreos).
- Cambiar el comportamiento de los envíos según su tipo.
- Gestionar los estados del envío (preparando, en tránsito, entregado o cancelado).

---

## 👥 Integrantes
- elmer jesus galvan oquendo
- juan david berrio durango

---

## 💻 Lenguaje y herramientas

| Elemento | Descripción                      |
|-----------|----------------------------------|
| 🧠 **Lenguaje principal** | Java                             |
| 🧱 **Entorno de desarrollo** | IntelliJ IDEA                    |
| 🧰 **Control de versiones** | GitHub                           |
| 🧮 **Modelado UML** | plantext                         |
| 🖼️ **Documentación visual** | Carpeta `docs/` con diagrama UML |

---

## 🏗️ Patrones usados y su rol dentro del MVC

| Patrón | Tipo | Rol en el MVC | Descripción |
|---------|------|---------------|--------------|
| **Factory Method** | Creacional | **Modelo** | Permite crear los distintos tipos de envío (`EnvioAereo`, `EnvioTerrestre`) sin depender de clases concretas. Facilita la extensión del sistema con nuevos tipos de envíos. |
| **Bridge** | Estructural | **Modelo ↔ Vista** | Separa la abstracción del envío (modelo) de su implementación concreta. Esto permite conectar distintos tipos de transporte sin afectar la lógica principal del sistema. |
| **State** | Comportamiento | **Controlador** | Gestiona los diferentes estados del envío (`Preparando`, `En tránsito`, `Entregado`, `Cancelado`), permitiendo que el objeto cambie su comportamiento dinámicamente. |

---

## ⚙️ Estructura del proyecto

---

## 🧩 Diagramas UML

### 🧱 Diagrama de Clases

El siguiente diagrama representa la estructura del sistema **EnvíaConecta**, integrando los patrones de diseño **MVC**, **Factory Method**, **Bridge**, **State** y **Strategy**.

![Diagrama de Clases](.idea/uml/uml-proyecto.jpg)




**Descripción general:**
- El **ControladorPrincipal** gestiona la comunicación entre **ModeloPaquete** y **VistaEnvio**.
- El **Factory Method** se usa para crear envíos (aéreos o terrestres).
- El **ModeloPaquete** aplica:
    - **Strategy** para calcular costos.
    - **Bridge** para separar el tipo de envío.
    - **State** para manejar los estados del paquete.

---

### 🔁 Diagrama de Secuencia: *Registro de Envío*

```text
Usuario -> VistaEnvio : ingresarDatosEnvio()
VistaEnvio -> ControladorPrincipal : registrarPaquete()
ControladorPrincipal -> FabricaEnvio : crearEnvio(destino)
FabricaEnvio -> Envio : new EnvioAereo() / EnvioTerrestre()
ControladorPrincipal -> ModeloPaquete : setEnvio(Envio)
ModeloPaquete -> EstrategiaCosto : calcular(peso)
ModeloPaquete -> EstadoEnvio : setEstado(Preparando)
ModeloPaquete -> VistaEnvio : mostrarPaquete()
``` 

### 💬 Reflexión final

### ✅ **Ventajas**
- Alta **modularidad**: cada componente cumple una función específica.  
- **Extensibilidad:** se pueden agregar nuevos tipos de envío, estrategias o estados sin alterar el código existente.  
- **Mantenibilidad:** los patrones reducen el acoplamiento y facilitan la comprensión del sistema.  
- Aplicación clara del **principio de abierto/cerrado (OCP)**.

### ⚠️ **Limitaciones**
- Aumenta la **complejidad estructural**, ya que hay muchas clases y relaciones.  
- Puede requerir **mayor tiempo de desarrollo** por el uso combinado de múltiples patrones.

### 💡 **Posibles mejoras** 
- Agregar una **interfaz gráfica más interactiva** para simular el flujo de los envíos.  
- Incluir un módulo de **persistencia de datos** (por ejemplo, con archivos o base de datos).

---