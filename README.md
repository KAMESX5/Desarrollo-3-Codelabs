### Codelab  1: 
Passphrase: a1b2c3d4

---

### Codelab  2:

### 1. ¿Qué es Attribute-Driven Design (ADD) y cuál es su propósito en el diseño de software?

**Attribute-Driven Design (ADD)** es un método de diseño arquitectónico **basado en los atributos de calidad del sistema**, como rendimiento, seguridad, mantenibilidad, escalabilidad, etc.
Su **propósito** es guiar el diseño arquitectónico priorizando estos atributos (requisitos no funcionales) junto con los requerimientos funcionales, para construir una arquitectura alineada con los objetivos del negocio y las restricciones del entorno.

---

### 2. ¿Cómo se relaciona ADD con Clean Architecture en el proceso de diseño de sistemas?

**ADD** proporciona el *"qué"* y *"por qué"*, mientras que **Clean Architecture** proporciona el *"cómo"*.

* ADD identifica los **atributos de calidad** y los **requisitos arquitectónicos clave**.
* Clean Architecture **implementa una estructura de capas** que facilita el cumplimiento de estos atributos (ej. independencia de frameworks, testabilidad, separación de responsabilidades).

En conjunto, ADD da la **visión estratégica**, y Clean Architecture la **ejecución táctica**.

---

### 3. ¿Cuáles son los pasos principales del método ADD para definir una arquitectura de software?

1. **Identificar los drivers del diseño** (requisitos funcionales, atributos de calidad, restricciones).
2. **Elegir un módulo o funcionalidad a diseñar** (por iteración).
3. **Seleccionar tácticas arquitectónicas** para satisfacer atributos de calidad (ej. usar caché para rendimiento).
4. **Asignar responsabilidades a los módulos** y definir interfaces.
5. **Definir interacciones entre módulos**.
6. **Validar las decisiones arquitectónicas** (verificar contra atributos de calidad y restricciones).
7. **Iterar** con los siguientes módulos o decisiones.

---

### 4. ¿Cómo se identifican los atributos de calidad en ADD y por qué son importantes?

Se identifican a partir de:

* Reuniones con stakeholders.
* Análisis de requerimientos.
* Escenarios de uso y restricciones del negocio.

Son importantes porque:

* Definen el **comportamiento esperado del sistema bajo ciertas condiciones**.
* Permiten tomar **decisiones informadas** sobre estructuras, patrones y tecnologías.
* Ayudan a **priorizar entre alternativas arquitectónicas**.

---

### 5. ¿Por qué Clean Architecture complementa ADD en la implementación de una solución?

Clean Architecture:

* **Encapsula decisiones arquitectónicas clave**, como separación de lógica de negocio, controladores y frameworks.
* **Facilita el cumplimiento de atributos de calidad**, como mantenibilidad, testabilidad y portabilidad.
* Permite una **implementación ordenada** de las decisiones tomadas con ADD.

Es decir, Clean Architecture proporciona una estructura organizacional concreta para **traducir atributos de calidad en código real**.

---

### 6. ¿Qué criterios se deben considerar al definir las capas en Clean Architecture dentro de un proceso ADD?

* **Independencia de tecnologías externas** (frameworks, bases de datos).
* **Dependencias dirigidas hacia el dominio** (la regla de dependencia).
* **Modularidad para satisfacer atributos de calidad**, como escalabilidad o mantenibilidad.
* **Claridad en los límites** entre casos de uso, entidades de negocio y adaptadores.
* **Soporte para pruebas automatizadas** (facilitado por separación de capas).

---

### 7. ¿Cómo ADD ayuda a tomar decisiones arquitectónicas basadas en necesidades del negocio?

ADD se basa en los **"design drivers"**, que incluyen:

* Objetivos estratégicos del negocio.
* Atributos de calidad prioritarios.
* Escenarios de operación.
  Esto permite:
* Priorizar decisiones que impacten el negocio directamente (ej. alta disponibilidad en un sistema financiero).
* Elegir tácticas que **maximicen valor y reduzcan riesgo**.

---

### 8. ¿Cuáles son los beneficios de combinar ADD con Clean Architecture en un sistema basado en microservicios?

* **ADD garantiza que los microservicios estén alineados con los atributos de calidad** (como escalabilidad o resiliencia).
* **Clean Architecture impone una estructura clara a cada microservicio**, haciendo que:

  * Sean independientes y fácilmente desplegables.
  * Sean mantenibles y testeables.
  * Se pueda aplicar seguridad y monitoreo de forma centralizada.
* El sistema resultante es **cohesionado pero flexible**, ideal para entornos distribuidos.

---

### 9. ¿Cómo se asegura que la arquitectura resultante cumpla con los atributos de calidad definidos en ADD?

Mediante:

* **Escenarios de evaluación** para cada atributo (por ejemplo, "¿el sistema responde en menos de 1s bajo carga X?").
* **Tácticas arquitectónicas explícitas** (como balanceadores de carga, capas de caché, colas de eventos).
* **Validaciones continuas** (prototipos, revisiones arquitectónicas, pruebas de carga).
* **Documentación con escenarios de calidad y decisiones justificadas**.

---

### 10. ¿Qué herramientas o metodologías pueden ayudar a validar una arquitectura diseñada con ADD y Clean Architecture?

**Herramientas y enfoques útiles:**

* **ATAM (Architecture Tradeoff Analysis Method)**: para evaluar escenarios de calidad.
* **C4 Model**: para visualizar las decisiones arquitectónicas a diferentes niveles.
* **ADR (Architecture Decision Records)**: para documentar las decisiones tomadas y su justificación.
* **SonarQube**: para análisis de calidad del código.
* **Arquitectura de referencia y prototipos**: para validar hipótesis técnicas.
* **Pruebas de rendimiento y resiliencia**: con JMeter, k6, Chaos Monkey, etc.

---
### Codelab 3

### **1. ¿Cuál es el propósito principal de Clean Architecture en el desarrollo de software?**  
El propósito de **Clean Architecture** es:  
- **Separar responsabilidades** en capas bien definidas para evitar acoplamiento.  
- **Independizar la lógica de negocio** de frameworks, bases de datos y APIs externas.  
- **Facilitar el mantenimiento**, pruebas y escalabilidad al seguir el principio de **Dependencia Invertida** (las capas externas dependen de las internas, no al revés).  

---

### **2. ¿Qué beneficios aporta Clean Architecture a un microservicio en Spring Boot?**  
- **Mayor testabilidad**: La lógica de negocio no depende de Spring, permitiendo tests unitarios sin contexto de Spring.  
- **Flexibilidad para cambiar tecnologías**: Ej: Migrar de JPA a MongoDB sin modificar el dominio.  
- **Mejor organización del código**: Evita el "código espagueti" típico en proyectos sin arquitectura definida.  
- **Resiliencia ante cambios**: Actualizar Spring Boot o librerías afecta mínimamente al core del negocio.  

---

### **3. ¿Cuáles son las principales capas de Clean Architecture y qué responsabilidad tiene cada una?**  
| **Capa**               | **Responsabilidad**                                                                 | **Ejemplo en Spring Boot**                          |  
|-------------------------|-------------------------------------------------------------------------------------|----------------------------------------------------|  
| **Dominio (Entities)**  | Modelos puros del negocio (sin dependencias técnicas).                              | Clases como `User`, `Order` (sin anotaciones JPA). |  
| **Casos de Uso**        | Lógica de aplicación (orquestación de flujos de negocio).                           | Clases `CreateUserUseCase`, `ProcessPaymentUseCase`. |  
| **Interfaces/Adaptadores** | Conexión con el mundo externo (APIs, DB, mensajería).                            | `UserController` (REST), `UserRepositoryImpl` (JPA). |  
| **Frameworks/Infra**    | Herramientas externas (Spring, Hibernate, Kafka).                                   | Configuraciones de Spring, scripts de DB.          |  

---

### **4. ¿Por qué se recomienda desacoplar la lógica de negocio de la infraestructura en un microservicio?**  
- **Evita "vendor lock-in"**: No quedas atado a una tecnología específica (ej: cambiar de JPA a MongoDB es más fácil).  
- **Pruebas más rápidas**: La lógica de negocio se testea sin necesidad de bases de datos o APIs reales.  
- **Mayor claridad**: El equipo entiende mejor las reglas del negocio al no estar mezcladas con código técnico.  

---

### **5. ¿Cuál es el rol de la capa de aplicación y qué tipo de lógica debería contener?**  
- **Rol**: Coordinar flujos de negocio (casos de uso), pero **sin contener reglas del dominio**.  
- **Lógica que incluye**:  
  - Validaciones de entrada.  
  - Llamadas a repositorios (inyectados como interfaces).  
  - Manejo de transacciones (`@Transactional`).  
- **Lógica que NO incluye**:  
  - Reglas complejas del negocio (van en el dominio).  
  - Detalles técnicos (ej: SQL, llamadas HTTP).  

---

### **6. ¿Qué diferencia hay entre un UseCase y un Service en Clean Architecture?**  
| **UseCase**                          | **Service** (tradicional)                |  
|---------------------------------------|------------------------------------------|  
| Representa un flujo específico (ej: "Crear usuario"). | Agrupa operaciones genéricas (ej: `UserService` con múltiples métodos). |  
| Más alineado con DDD (Domain-Driven Design). | Tiende a ser un "God Class" con alta cohesión. |  
| Promueve el principio de Single Responsibility. | Suele violar SRP al crecer. |  

**Ejemplo**:  
- `RegisterUserUseCase` (Clean Architecture) vs. `UserService.register()` (Spring MVC clásico).  

---

### **7. ¿Por qué se recomienda definir Repositories como interfaces en la capa de dominio?**  
- **Principio de Inversión de Dependencias**: El dominio no debe depender de infraestructura (ej: JPA).  
- **Flexibilidad**: Puedes implementar el repositorio con JPA, MongoDB, o incluso en memoria.  
- **Testeo**: Mockeas fácilmente la interfaz en pruebas unitarias.  

**Ejemplo**:  
```java
// En el dominio:
interface UserRepository {  
    User save(User user);  
}  

// En infraestructura (adaptador):
@Repository  
class UserJpaRepository implements UserRepository { ... }  
```

---

### **8. ¿Cómo se implementa un UseCase en Spring Boot y qué ventajas tiene?**  
**Implementación**:  
```java
// 1. Definir interfaz en dominio (opcional):
public interface CreateUserUseCase {  
    User execute(User user);  
}  

// 2. Implementar en capa de aplicación:
@Service  
public class CreateUserUseCaseImpl implements CreateUserUseCase {  
    private final UserRepository repository; // Inyectado  

    @Override  
    @Transactional  
    public User execute(User user) {  
        // Lógica de validación/negocio aquí  
        return repository.save(user);  
    }  
}  
```  
**Ventajas**:  
- **Claro propósito**: Cada UseCase hace una sola cosa.  
- **Fácil de testear**: Mockeas `UserRepository` y pruebas la lógica aislada.  

---

### **9. ¿Qué problemas podrían surgir sin Clean Architecture en microservicios?**  
- **Acoplamiento alto**: Cambiar una DB requiere modificar el dominio.  
- **Tests lentos**: Dependencia de Spring/DB en todas las pruebas.  
- **Dificultad para escalar**: El código se vuelve un "monolito distribuido".  
- **Legibilidad pobre**: Reglas de negocio mezcladas con SQL/APIs.  

---

### **10. ¿Cómo Clean Architecture facilita escalabilidad y mantenibilidad en microservicios?**  
- **Escalabilidad**:  
  - Los microservicios son **autónomos** (cada uno con su dominio claro).  
  - Puedes escalar componentes críticos (ej: UseCases de pagos) sin tocar otros.  
- **Mantenibilidad**:  
  - Cambios en infraestructura (ej: de REST a GraphQL) no afectan al dominio.  
  - Onboarding más rápido: El código está organizado por responsabilidades.  


