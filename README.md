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
- **elmer jesus galvan oquendo**
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

