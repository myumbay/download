# Cuestionario de Práctica — Oracle Certified Professional Java EE / Jakarta EE

**100 preguntas de opción múltiple** organizadas por área temática. Las respuestas correctas y sus explicaciones están al final del documento, en la sección **"Respuestas y explicaciones"**.

> Nota sobre el alcance: Oracle transfirió la gobernanza de Java EE a la Eclipse Foundation (ahora **Jakarta EE**) a partir de la versión 8. Las certificaciones históricas de Oracle (ej. 1Z0-899, 1Z0-900) cubren las APIs núcleo que se mantienen prácticamente iguales en Jakarta EE (con el cambio de paquete `javax.*` → `jakarta.*` desde Jakarta EE 9). Este cuestionario cubre esas APIs núcleo: Servlets, JSP, JAX-RS, CDI, JPA, EJB, Bean Validation, JSON-B/JSON-P, WebSocket, Seguridad y Concurrencia.

---

## Índice de secciones
1. Servlets y JSP (preguntas 1–10)
2. JAX-RS — Servicios RESTful (preguntas 11–25)
3. CDI — Contexts and Dependency Injection (preguntas 26–40)
4. JPA — Java Persistence API (preguntas 41–55)
5. EJB — Enterprise JavaBeans (preguntas 56–65)
6. Bean Validation (preguntas 66–73)
7. JSON-B / JSON-P (preguntas 74–81)
8. WebSocket (preguntas 82–86)
9. Seguridad (Jakarta Security) (preguntas 87–94)
10. Concurrency Utilities (preguntas 95–100)

---

## Sección 1: Servlets y JSP

**1.** ¿Qué anotación se utiliza para mapear un Servlet a una URL sin necesidad de declararlo en `web.xml`?

A) `@WebFilter`
B) `@WebServlet`
C) `@ServletMapping`
D) `@Path`

**2.** ¿Cuál es el método del ciclo de vida de un Servlet que se invoca una sola vez, antes de procesar cualquier solicitud?

A) `service()`
B) `doGet()`
C) `init()`
D) `destroy()`

**3.** ¿Qué interfaz debe implementar (directa o indirectamente) una clase para ser un Servlet válido?

A) `jakarta.servlet.ServletContext`
B) `jakarta.servlet.Servlet`
C) `jakarta.servlet.ServletConfig`
D) `jakarta.servlet.ServletRequest`

**4.** En un `HttpServlet`, ¿qué método se sobrescribe típicamente para manejar solicitudes POST?

A) `doPost(HttpServletRequest, HttpServletResponse)`
B) `post(HttpServletRequest, HttpServletResponse)`
C) `handlePost(HttpServletRequest, HttpServletResponse)`
D) `service(HttpServletRequest, HttpServletResponse, "POST")`

**5.** ¿Cuál es el alcance (scope) por defecto de un atributo guardado con `request.setAttribute(...)`?

A) Application
B) Session
C) Request
D) Page

**6.** ¿Qué anotación se usa para declarar un filtro de Servlet?

A) `@WebFilter`
B) `@WebListener`
C) `@FilterChain`
D) `@Intercept`

**7.** En JSP, ¿qué directiva se usa para incluir el contenido de otro archivo en tiempo de traducción (no en tiempo de ejecución)?

A) `<jsp:include>`
B) `<%@ include file="..." %>`
C) `<c:import>`
D) `<jsp:forward>`

**8.** ¿Qué objeto implícito de JSP representa el contexto de la aplicación web completa?

A) `session`
B) `page`
C) `application`
D) `config`

**9.** ¿Cuál de los siguientes NO es un método válido del ciclo de vida de `HttpSessionListener`?

A) `sessionCreated(HttpSessionEvent se)`
B) `sessionDestroyed(HttpSessionEvent se)`
C) `sessionAttributeAdded(HttpSessionEvent se)`
D) Ninguna de las anteriores es incorrecta (ambas existen, pero la tercera pertenece a `HttpSessionAttributeListener`, no a `HttpSessionListener`)

**10.** ¿Qué código de estado HTTP se usa convencionalmente para indicar una redirección temporal desde un Servlet mediante `response.sendRedirect(...)`?

A) 200
B) 301
C) 302
D) 404

---

## Sección 2: JAX-RS — Servicios RESTful

**11.** ¿Qué anotación identifica una clase como un recurso raíz JAX-RS y define su ruta base?

A) `@Resource`
B) `@Path`
C) `@Endpoint`
D) `@RestController`

**12.** Para inyectar el valor de un parámetro de consulta (`?nombre=valor`) en un método de recurso, ¿qué anotación se usa?

A) `@PathParam`
B) `@FormParam`
C) `@QueryParam`
D) `@HeaderParam`

**13.** ¿Qué anotación marca un método para responder a solicitudes HTTP GET?

A) `@HttpGet`
B) `@GET`
C) `@GetMapping`
D) `@Retrieve`

**14.** ¿Cuál es la clase que se usa para construir respuestas HTTP personalizadas en JAX-RS (código de estado, cabeceras, cuerpo)?

A) `jakarta.ws.rs.core.Response`
B) `jakarta.ws.rs.core.HttpResponse`
C) `jakarta.servlet.http.HttpServletResponse`
D) `jakarta.ws.rs.client.ClientResponse`

**15.** ¿Qué anotación se utiliza para extraer un segmento de la URL definido en `@Path("/usuarios/{id}")`?

A) `@QueryParam("id")`
B) `@PathParam("id")`
C) `@MatrixParam("id")`
D) `@BeanParam("id")`

**16.** ¿Qué interfaz se implementa para crear un `ExceptionMapper` personalizado en JAX-RS?

A) `jakarta.ws.rs.ext.ExceptionMapper<E>`
B) `jakarta.ws.rs.core.ExceptionHandler<E>`
C) `jakarta.ws.rs.ErrorHandler<E>`
D) `jakarta.ws.rs.client.ResponseExceptionMapper<E>`

**17.** ¿Cuál es el propósito de la clase `Application` en JAX-RS?

A) Define el punto de entrada `main()` de la aplicación
B) Configura la ruta base de la API y opcionalmente registra clases de recursos y providers
C) Reemplaza al contenedor de Servlets
D) Gestiona las transacciones JTA

**18.** ¿Qué anotación indica los tipos MIME que un método de recurso puede producir como respuesta?

A) `@Consumes`
B) `@Produces`
C) `@MediaType`
D) `@ContentType`

**19.** ¿Qué anotación se usa para inyectar un componente de configuración de parámetros agrupados (varios `@QueryParam`/`@PathParam` en un solo objeto)?

A) `@Context`
B) `@BeanParam`
C) `@Suspended`
D) `@MatrixParam`

**20.** En JAX-RS del lado cliente, ¿qué clase se usa como punto de entrada para construir solicitudes HTTP salientes?

A) `jakarta.ws.rs.client.ClientBuilder`
B) `jakarta.ws.rs.client.RequestFactory`
C) `jakarta.ws.rs.core.UriBuilder`
D) `jakarta.ws.rs.client.HttpClient`

**21.** ¿Qué anotación se usa para inyectar información contextual como `UriInfo` o `HttpHeaders` en un recurso JAX-RS?

A) `@Inject`
B) `@Context`
C) `@Resource`
D) `@Autowired`

**22.** Si un método de recurso lanza una excepción no capturada que no tiene un `ExceptionMapper` registrado, ¿qué código de estado HTTP se devuelve típicamente por defecto?

A) 400 Bad Request
B) 404 Not Found
C) 500 Internal Server Error
D) 503 Service Unavailable

**23.** ¿Qué anotación permite procesar solicitudes de forma asíncrona en JAX-RS, suspendiendo la respuesta hasta que el procesamiento termine?

A) `@Asynchronous`
B) `@Suspended` (usada con `AsyncResponse`)
C) `@Future`
D) `@NonBlocking`

**24.** ¿Cuál de las siguientes anotaciones de método HTTP NO es estándar en JAX-RS?

A) `@GET`
B) `@POST`
C) `@PATCH`
D) `@FETCH`

**25.** ¿Qué mecanismo de JAX-RS permite interceptar solicitudes/respuestas de forma transversal (por ejemplo, para logging o autenticación) sin modificar cada recurso?

A) `ContainerRequestFilter` / `ContainerResponseFilter`
B) `ServletFilter`
C) `@Interceptor` de CDI únicamente
D) `HttpSessionListener`

---

## Sección 3: CDI — Contexts and Dependency Injection

**26.** ¿Qué anotación se usa para solicitar la inyección de una dependencia en CDI?

A) `@Resource`
B) `@Inject`
C) `@Autowired`
D) `@EJB`

**27.** ¿Cuál es el scope (ámbito) por defecto de un bean gestionado por CDI si no se especifica ninguna anotación de scope?

A) `@ApplicationScoped`
B) `@RequestScoped`
C) Dependent pseudo-scope (`@Dependent`)
D) `@SessionScoped`

**28.** ¿Qué anotación se usa para marcar un método de fábrica que produce una instancia gestionada por CDI (útil para tipos que no se pueden anotar directamente, como clases de terceros)?

A) `@Factory`
B) `@Produces`
C) `@Provides`
D) `@Bean`

**29.** ¿Qué anotación permite definir un calificador (qualifier) personalizado para distinguir entre múltiples implementaciones del mismo tipo?

A) Una anotación anotada con `@Qualifier`
B) `@Named` únicamente
C) `@Alternative`
D) `@Specializes`

**30.** ¿Qué scope de CDI mantiene el estado durante toda la duración de una conversación explícita, iniciada y finalizada manualmente?

A) `@RequestScoped`
B) `@ConversationScoped`
C) `@SessionScoped`
D) `@ApplicationScoped`

**31.** ¿Qué elemento se usa para observar eventos disparados con `Event<T>.fire(...)` en CDI?

A) Un método con un parámetro anotado `@Observes`
B) Un método anotado `@Listener`
C) Una clase que implementa `EventListener`
D) Un método anotado `@OnEvent`

**32.** ¿Qué anotación marca un bean como una alternativa que solo se activa si está explícitamente habilitada (en `beans.xml` o vía `@Priority`)?

A) `@Default`
B) `@Alternative`
C) `@Specializes`
D) `@Vetoed`

**33.** ¿Qué archivo (histórico, aunque ya opcional en versiones recientes de CDI) se usaba para activar el descubrimiento de beans en un archivo/módulo?

A) `cdi.xml`
B) `beans.xml`
C) `web.xml`
D) `context.xml`

**34.** ¿Qué anotación se usa junto con `@Interceptor` para definir el tipo de interceptor (por ejemplo, para logging), que luego se activa mediante `@Priority` (o en `beans.xml` en versiones antiguas)?

A) `@InterceptorBinding`
B) `@AroundInvoke`
C) `@Decorator`
D) `@Stereotype`

**35.** Dentro de una clase interceptora, ¿qué anotación marca el método que se ejecuta alrededor de la invocación del método interceptado?

A) `@Around`
B) `@AroundInvoke`
C) `@Intercept`
D) `@Before`

**36.** ¿Qué produce un `Instance<T>` inyectado en CDI (por ejemplo, `@Inject Instance<MiServicio> servicio`)?

A) Acceso programático diferido a una o varias instancias del tipo `T`, resolviendo la inyección en tiempo de uso
B) Una lista fija de todas las implementaciones al momento del despliegue
C) Un proxy que siempre lanza `UnsupportedOperationException`
D) Nada; `Instance<T>` no es válido en CDI

**37.** ¿Qué diferencia principal existe entre un `@Decorator` y un `@Interceptor` en CDI?

A) No hay diferencia, son sinónimos
B) El decorador conoce el tipo de negocio del bean decorado (interfaz), mientras que el interceptor es agnóstico al tipo y se enfoca en aspectos transversales genéricos
C) Los decoradores solo aplican a EJBs
D) Los interceptores solo pueden usarse con `@RequestScoped`

**38.** ¿Qué mecanismo permite inyectar un valor calculado dinámicamente en tiempo de despliegue mediante una clase productora, a diferencia de un valor fijo?

A) Un método o campo anotado `@Produces` dentro de una clase productora
B) `@ConfigProperty` únicamente (MicroProfile Config)
C) `@Value`
D) `@Inject` sin más

**39.** ¿Qué anotación se usa para deshabilitar explícitamente que una clase sea considerada un bean gestionado por CDI, aunque cumpla los requisitos?

A) `@Disabled`
B) `@Vetoed`
C) `@Exclude`
D) `@Ignore`

**40.** ¿Cuál de los siguientes NO es un scope normal (normal scope) de CDI?

A) `@RequestScoped`
B) `@SessionScoped`
C) `@ApplicationScoped`
D) `@Dependent` (es un pseudo-scope, no un normal scope)

---

## Sección 4: JPA — Java Persistence API

**41.** ¿Qué anotación marca una clase como una entidad persistente gestionada por JPA?

A) `@Table`
B) `@Entity`
C) `@Persistable`
D) `@Model`

**42.** ¿Qué anotación es obligatoria en toda entidad JPA para identificar la clave primaria?

A) `@PrimaryKey`
B) `@Id`
C) `@Key`
D) `@Column(primary = true)`

**43.** ¿Qué estrategia de `@GeneratedValue` delega la generación del identificador a una secuencia de base de datos?

A) `GenerationType.IDENTITY`
B) `GenerationType.SEQUENCE`
C) `GenerationType.TABLE`
D) `GenerationType.AUTO` únicamente

**44.** ¿Qué anotación se usa para mapear una relación muchos-a-uno entre entidades?

A) `@OneToMany`
B) `@ManyToOne`
C) `@ManyToMany`
D) `@JoinTable`

**45.** En una relación bidireccional `@OneToMany`/`@ManyToOne`, ¿en qué lado de la relación se coloca normalmente el atributo `mappedBy`?

A) En el lado "dueño" de la relación (el que tiene la columna de clave foránea)
B) En el lado inverso, no propietario, de la relación (normalmente el lado `@OneToMany`)
C) En ambos lados simultáneamente
D) `mappedBy` no se usa en JPA

**46.** ¿Cuál es la diferencia principal entre `FetchType.EAGER` y `FetchType.LAZY`?

A) EAGER carga la asociación inmediatamente junto con la entidad; LAZY la carga solo cuando se accede a ella
B) LAZY es más rápido siempre y EAGER siempre falla
C) No hay diferencia real, ambos cargan de la misma forma
D) EAGER solo aplica a colecciones, LAZY solo a relaciones simples

**47.** ¿Qué lenguaje de consulta orientado a objetos, independiente del motor de base de datos, ofrece JPA?

A) SQL nativo únicamente
B) JPQL (Java Persistence Query Language)
C) HQL (exclusivo de Hibernate, no es parte de la especificación JPA)
D) PL/SQL

**48.** ¿Qué interfaz se usa para construir consultas de forma programática y con seguridad de tipos (type-safe) en JPA (Criteria API)?

A) `jakarta.persistence.criteria.CriteriaBuilder`
B) `jakarta.persistence.Query`
C) `jakarta.persistence.QueryBuilder`
D) `jakarta.persistence.TypedQueryFactory`

**49.** ¿Qué anotación marca una clase como "embebible" para ser incluida como parte del estado de una entidad, sin tener identidad propia?

A) `@Embeddable`
B) `@Embedded`
C) `@Component`
D) `@ValueObject`

**50.** Dentro de una entidad, ¿qué anotación se usa para incluir una instancia de una clase `@Embeddable` como parte de su estado?

A) `@Embeddable`
B) `@Embedded`
C) `@Include`
D) `@Column`

**51.** ¿Qué anotación de callback del ciclo de vida se ejecuta justo antes de que una entidad sea insertada en la base de datos?

A) `@PostPersist`
B) `@PrePersist`
C) `@PreUpdate`
D) `@PostLoad`

**52.** ¿Qué método de `EntityManager` se usa para sincronizar inmediatamente los cambios pendientes con la base de datos sin cerrar la transacción?

A) `flush()`
B) `commit()`
C) `sync()`
D) `persist()`

**53.** ¿Qué tipo de bloqueo optimista se implementa comúnmente en JPA mediante la anotación `@Version`?

A) Bloqueo pesimista exclusivo
B) Control de concurrencia optimista basado en un número de versión o timestamp
C) Bloqueo a nivel de tabla completa
D) `@Version` no está relacionado con bloqueo de concurrencia

**54.** ¿Qué anotación se usa para definir una consulta JPQL con nombre, reutilizable, declarada a nivel de entidad?

A) `@Query`
B) `@NamedQuery`
C) `@StoredQuery`
D) `@PersistentQuery`

**55.** ¿Cuál de las siguientes estrategias de herencia de JPA mapea cada clase concreta de la jerarquía a su propia tabla, incluyendo las columnas heredadas de la superclase?

A) `SINGLE_TABLE`
B) `JOINED`
C) `TABLE_PER_CLASS`
D) `MAPPED_SUPERCLASS` (no es una estrategia de `InheritanceType`, es una anotación distinta: `@MappedSuperclass`)

---

## Sección 5: EJB — Enterprise JavaBeans

**56.** ¿Qué anotación se usa para declarar un EJB de sesión sin estado (stateless)?

A) `@Stateless`
B) `@Stateful`
C) `@Singleton`
D) `@MessageDriven`

**57.** ¿Qué tipo de EJB mantiene una única instancia compartida por toda la aplicación?

A) `@Stateless`
B) `@Stateful`
C) `@Singleton`
D) `@MessageDriven`

**58.** ¿Qué anotación se usa para inyectar la referencia a otro EJB dentro de una clase gestionada por el contenedor?

A) `@Inject` únicamente (CDI no puede inyectar EJBs)
B) `@EJB` (o `@Inject` si el EJB también es un bean CDI válido)
C) `@Resource` exclusivamente
D) `@Autowired`

**59.** ¿Qué tipo de EJB se usa para consumir mensajes de una cola o tópico JMS de forma asíncrona?

A) `@Stateless`
B) `@Stateful`
C) `@Singleton`
D) `@MessageDriven`

**60.** Por defecto, ¿qué tipo de gestión transaccional usan los EJBs si no se especifica lo contrario?

A) Bean-Managed Transactions (BMT)
B) Container-Managed Transactions (CMT)
C) Ninguna gestión transaccional
D) Transacciones manuales JDBC

**61.** ¿Qué anotación se usa en un método de EJB para especificar el atributo de transacción (por ejemplo, `REQUIRES_NEW`)?

A) `@Transactional` (JTA) o `@TransactionAttribute` (EJB clásico)
B) `@Transaction`
C) `@JTA`
D) `@Commit`

**62.** ¿Qué anotación marca un método de un `@Singleton` EJB para que se ejecute automáticamente al iniciar la aplicación?

A) `@PostConstruct` combinado con `@Startup`
B) `@OnStartup`
C) `@Init`
D) `@ApplicationScoped`

**63.** ¿Qué anotación se usa para programar la ejecución periódica de un método en un EJB (temporizador)?

A) `@Scheduled` (Spring, no EJB estándar)
B) `@Schedule`
C) `@Cron`
D) `@Timer`

**64.** ¿Qué interfaz se inyecta típicamente en un EJB para acceder de forma programática al contexto transaccional (BMT)?

A) `jakarta.transaction.UserTransaction`
B) `jakarta.ejb.SessionContext` únicamente
C) `jakarta.persistence.EntityTransaction`
D) `jakarta.ejb.TransactionContext`

**65.** ¿Cuál es la diferencia principal entre un `@Stateless` y un `@Stateful` session bean?

A) No hay diferencia funcional
B) `@Stateful` mantiene estado conversacional entre invocaciones de un mismo cliente; `@Stateless` no retiene estado entre invocaciones
C) `@Stateless` es obsoleto en Jakarta EE
D) `@Stateful` no admite inyección de dependencias

---

## Sección 6: Bean Validation

**66.** ¿Qué anotación de Bean Validation asegura que un campo no sea `null`?

A) `@NotEmpty`
B) `@NotNull`
C) `@NotBlank`
D) `@Required`

**67.** ¿Cuál es la diferencia entre `@NotBlank` y `@NotEmpty`?

A) Son idénticas
B) `@NotBlank` aplica solo a `String` y además exige que, tras recortar espacios, quede al menos un carácter; `@NotEmpty` aplica a `String`, colecciones, arrays y mapas, exigiendo tamaño mayor a cero
C) `@NotEmpty` es exclusiva de colecciones y `@NotBlank` de números
D) `@NotBlank` permite valores `null`

**68.** ¿Qué anotación valida que un valor numérico esté dentro de un rango mínimo y máximo?

A) `@Range`
B) `@Min` y `@Max` (o `@DecimalMin`/`@DecimalMax` para tipos decimales)
C) `@Between`
D) `@Size`

**69.** ¿Qué anotación se usa para validar el formato de una dirección de correo electrónico?

A) `@Pattern` únicamente
B) `@Email`
C) `@Format(type = "email")`
D) `@Valid`

**70.** ¿Qué anotación activa la validación en cascada de los campos de un objeto anidado dentro de otro objeto validado?

A) `@Valid`
B) `@Cascade`
C) `@Nested`
D) `@Validated` (anotación de Spring, no de Bean Validation estándar)

**71.** ¿Cómo se define una restricción de validación personalizada en Bean Validation?

A) Creando una anotación anotada con `@Constraint(validatedBy = MiValidator.class)` y una clase que implemente `ConstraintValidator<A, T>`
B) Sobrescribiendo `equals()` en la clase del campo
C) Solo es posible mediante XML
D) Extendiendo la clase `Validator`

**72.** ¿Qué interfaz central se usa para invocar validaciones de forma programática (fuera de un contenedor)?

A) `jakarta.validation.Validator`
B) `jakarta.validation.ValidatorFactory` únicamente, sin `Validator`
C) `jakarta.validation.ConstraintValidator`
D) `jakarta.validation.BeanValidator`

**73.** ¿Qué anotación permite agrupar restricciones de validación para aplicarlas selectivamente según el contexto (grupos de validación)?

A) Interfaces marcadoras usadas en el atributo `groups` de cada restricción
B) `@Group`
C) `@ValidationContext`
D) No existe tal mecanismo en Bean Validation

---

## Sección 7: JSON-B / JSON-P

**74.** ¿Qué especificación de Jakarta EE define el binding automático entre objetos Java y JSON (serialización/deserialización)?

A) JSON-P (Jakarta JSON Processing)
B) JSON-B (Jakarta JSON Binding)
C) JAXB
D) Jackson (no es parte de la especificación Jakarta EE)

**75.** ¿Qué anotación de JSON-B permite renombrar una propiedad al serializarla a JSON?

A) `@JsonProperty` (esta es de Jackson, no de JSON-B)
B) `@JsonbProperty`
C) `@SerializedName`
D) `@Alias`

**76.** ¿Qué anotación de JSON-B excluye un campo de la serialización/deserialización?

A) `@JsonbTransient`
B) `@Transient` (esta es de JPA, no de JSON-B)
C) `@JsonIgnore` (es de Jackson)
D) `@JsonbSkip`

**77.** ¿Qué clase de la API JSON-B se usa como punto de entrada para serializar y deserializar objetos?

A) `jakarta.json.bind.Jsonb`
B) `jakarta.json.JsonObject`
C) `jakarta.json.bind.JsonbBuilder` únicamente (sin `Jsonb`)
D) `jakarta.json.stream.JsonParser`

**78.** ¿Qué API de bajo nivel (Jakarta JSON Processing) permite construir y recorrer estructuras JSON de forma programática, sin mapear a objetos Java?

A) JSON-B
B) JSON-P, mediante `JsonObjectBuilder`, `JsonArrayBuilder`, `JsonParser`, etc.
C) JAXB
D) StAX

**79.** ¿Qué interfaz de JSON-P representa un valor JSON de tipo objeto (equivalente a un `Map` de clave-valor)?

A) `jakarta.json.JsonArray`
B) `jakarta.json.JsonObject`
C) `jakarta.json.JsonValue`
D) `jakarta.json.JsonStructure` (es la superinterfaz común, no específicamente "objeto")

**80.** ¿Qué mecanismo de JSON-B permite personalizar completamente cómo se serializa/deserializa un tipo específico, cuando las anotaciones estándar no son suficientes?

A) Un `JsonbAdapter<Original, Adapted>` personalizado
B) Sobrescribir `toString()`
C) No es posible personalizar más allá de las anotaciones
D) Usar reflexión manual dentro del propio getter

**81.** Al usar JAX-RS junto con JSON-B, ¿qué sucede normalmente al devolver un objeto Java desde un método de recurso anotado con `@Produces(MediaType.APPLICATION_JSON)`?

A) Es necesario serializar el objeto a `String` manualmente siempre
B) El proveedor JSON-B integrado serializa automáticamente el objeto a JSON como parte del `MessageBodyWriter`
C) JAX-RS no soporta JSON de forma nativa
D) Se requiere Jackson obligatoriamente

---

## Sección 8: WebSocket

**82.** ¿Qué anotación marca una clase como un endpoint de servidor WebSocket y define su ruta?

A) `@WebSocket`
B) `@ServerEndpoint`
C) `@Endpoint`
D) `@Socket`

**83.** ¿Qué anotación marca el método que se ejecuta cuando se abre una nueva conexión WebSocket?

A) `@OnOpen`
B) `@OnConnect`
C) `@Init`
D) `@PostConstruct`

**84.** ¿Qué anotación marca el método que recibe los mensajes entrantes de un cliente WebSocket?

A) `@OnReceive`
B) `@OnMessage`
C) `@MessageReceived`
D) `@Consume`

**85.** ¿Qué clase representa la conexión activa con un cliente WebSocket y se usa para enviar mensajes de vuelta?

A) `jakarta.websocket.Session`
B) `jakarta.websocket.Connection`
C) `jakarta.websocket.Channel`
D) `jakarta.websocket.Endpoint` (es la clase base para el enfoque programático, no la conexión en sí)

**86.** ¿Qué anotación marca el método que se ejecuta cuando se cierra la conexión WebSocket?

A) `@OnClose`
B) `@OnDisconnect`
C) `@PreDestroy` únicamente
D) `@OnEnd`

---

## Sección 9: Seguridad (Jakarta Security)

**87.** ¿Qué anotación de Jakarta Security se usa para definir un mecanismo de autenticación basado en formulario personalizado?

A) `@FormAuthenticationMechanismDefinition`
B) `@BasicAuthenticationMechanismDefinition`
C) `@CustomFormLogin`
D) `@LoginConfig`

**88.** ¿Qué anotación restringe el acceso a un recurso (método o clase) a usuarios que tengan alguno de los roles especificados?

A) `@RolesAllowed`
B) `@PermitAll`
C) `@DenyAll`
D) `@Secured` (es de Spring Security, no estándar Jakarta EE)

**89.** ¿Qué anotación permite el acceso a un recurso sin restricción de rol alguna?

A) `@RolesAllowed("*")`
B) `@PermitAll`
C) `@Public`
D) `@Open`

**90.** ¿Qué anotación bloquea el acceso a un recurso para todos los usuarios, independientemente de su rol?

A) `@DenyAll`
B) `@RolesAllowed({})`
C) `@Forbidden`
D) `@Blocked`

**91.** ¿Qué interfaz se usa para implementar un `IdentityStore` personalizado en Jakarta Security, que valide credenciales contra un origen propio (por ejemplo, una base de datos)?

A) `jakarta.security.enterprise.identitystore.IdentityStore`
B) `jakarta.security.auth.spi.LoginModule` únicamente
C) `jakarta.security.enterprise.AuthenticationMechanism` (esta define el mecanismo, no el almacén de identidades)
D) `jakarta.security.UserStore`

**92.** ¿Qué anotación de Jakarta Security define un mecanismo de autenticación HTTP Basic de forma declarativa?

A) `@BasicAuthenticationMechanismDefinition`
B) `@HttpBasic`
C) `@WWWAuthenticate`
D) `@LoginConfig(authMethod = "BASIC")` (es el enfoque de `web.xml`, no la anotación de Jakarta Security)

**93.** ¿Qué método de `SecurityContext` (Jakarta Security) permite verificar programáticamente si el usuario autenticado tiene un rol determinado?

A) `isCallerInRole(String role)`
B) `hasRole(String role)`
C) `checkRole(String role)`
D) `getRoles().contains(role)`

**94.** En un contenedor de Servlets, ¿qué método de `HttpServletRequest` permite iniciar sesión programáticamente con credenciales explícitas?

A) `login(String username, String password)`
B) `authenticate(String username, String password)`
C) `signIn(String username, String password)`
D) `doLogin(String username, String password)`

---

## Sección 10: Concurrency Utilities

**95.** ¿Qué interfaz de Jakarta Concurrency permite obtener instancias de `ExecutorService` gestionadas por el contenedor?

A) `jakarta.enterprise.concurrent.ManagedExecutorService`
B) `java.util.concurrent.Executors`
C) `jakarta.enterprise.concurrent.ThreadFactory`
D) `jakarta.ejb.AsyncContext`

**96.** ¿Qué anotación permite invocar un método de forma asíncrona en un bean gestionado (por ejemplo, un EJB o un bean CDI compatible), devolviendo típicamente un `Future<T>`?

A) `@Asynchronous`
B) `@Async` (es de Spring, no estándar Jakarta EE, aunque conceptualmente análoga)
C) `@Concurrent`
D) `@Parallel`

**97.** ¿Qué interfaz gestionada por el contenedor permite programar tareas para ejecutarse en un momento futuro o de forma periódica?

A) `jakarta.enterprise.concurrent.ManagedScheduledExecutorService`
B) `java.util.Timer`
C) `jakarta.ejb.Timer` únicamente
D) `jakarta.enterprise.concurrent.ManagedThreadFactory`

**98.** ¿Por qué se recomienda usar `ManagedExecutorService` en lugar de crear hilos manualmente (`new Thread(...)`) dentro de un contenedor Jakarta EE?

A) Es más rápido en todos los casos
B) El contenedor propaga el contexto (seguridad, transacciones, `ClassLoader`, JNDI) a las tareas ejecutadas, algo que los hilos crudos no garantizan y que además está prohibido gestionar manualmente en un entorno gestionado
C) `new Thread(...)` está eliminado del lenguaje Java
D) No hay ninguna razón real, es solo una convención de estilo

**99.** ¿Qué interfaz de Jakarta Concurrency permite crear hilos gestionados por el contenedor, propagando su contexto, para uso en librerías que requieren una `ThreadFactory`?

A) `jakarta.enterprise.concurrent.ManagedThreadFactory`
B) `java.util.concurrent.ThreadFactory` estándar sin más
C) `jakarta.ejb.ManagedThread`
D) `jakarta.enterprise.concurrent.ContextService` (este propaga contexto a tareas ya creadas, no crea hilos directamente)

**100.** ¿Qué componente de Jakarta Concurrency permite envolver una tarea (`Runnable`/`Callable`) para que, al ejecutarse en un hilo no gestionado, herede el contexto del hilo que la creó?

A) `jakarta.enterprise.concurrent.ContextService`
B) `jakarta.enterprise.concurrent.ManagedExecutorService` únicamente
C) `jakarta.enterprise.concurrent.ManagedTask`
D) No existe tal componente

---

## Respuestas y explicaciones

### Sección 1: Servlets y JSP

1. **B** — `@WebServlet` reemplaza la declaración en `web.xml` y permite mapear la URL directamente en la clase.
2. **C** — `init()` se invoca una única vez al crear la instancia del Servlet, antes de procesar solicitudes.
3. **B** — Toda clase Servlet implementa, directa o indirectamente (vía `GenericServlet`/`HttpServlet`), la interfaz `Servlet`.
4. **A** — `doPost(...)` es el método estándar de `HttpServlet` para solicitudes POST.
5. **C** — Los atributos de `HttpServletRequest` tienen alcance de solicitud (request scope); desaparecen al finalizar la solicitud/respuesta.
6. **A** — `@WebFilter` declara un filtro sin necesidad de `web.xml`.
7. **B** — `<%@ include %>` inserta el contenido en tiempo de traducción (se combina en un solo Servlet compilado); `<jsp:include>` lo hace en tiempo de ejecución.
8. **C** — `application` es el objeto implícito que representa el `ServletContext` de toda la aplicación.
9. **C** — `sessionAttributeAdded` pertenece a `HttpSessionAttributeListener`, no a `HttpSessionListener`.
10. **C** — `sendRedirect()` genera por defecto un 302 (Found/redirección temporal).

### Sección 2: JAX-RS

11. **B** — `@Path` en una clase define la ruta base de un recurso raíz.
12. **C** — `@QueryParam` extrae parámetros de la cadena de consulta de la URL.
13. **B** — `@GET` marca un método para responder a solicitudes HTTP GET.
14. **A** — `jakarta.ws.rs.core.Response` (y su `Response.ResponseBuilder`) construye respuestas personalizadas.
15. **B** — `@PathParam` extrae segmentos definidos en la plantilla de `@Path`.
16. **A** — Se implementa `ExceptionMapper<E>` y se registra como provider.
17. **B** — `Application` configura la ruta base (`@ApplicationPath`) y puede registrar clases de recursos/providers.
18. **B** — `@Produces` indica los tipos MIME que el método puede generar como respuesta.
19. **B** — `@BeanParam` agrupa varios parámetros de distinta procedencia en un solo objeto.
20. **A** — `ClientBuilder` es el punto de entrada para crear un `Client` y construir solicitudes salientes.
21. **B** — `@Context` inyecta objetos contextuales como `UriInfo`, `HttpHeaders`, `Request`, etc.
22. **C** — Sin un `ExceptionMapper` específico, una excepción no controlada suele traducirse en un 500.
23. **B** — `@Suspended` se usa junto con el parámetro `AsyncResponse` para procesamiento asíncrono.
24. **D** — `@FETCH` no existe; los métodos estándar son GET, POST, PUT, DELETE, PATCH, HEAD, OPTIONS.
25. **A** — Los filtros `ContainerRequestFilter`/`ContainerResponseFilter` son el mecanismo transversal propio de JAX-RS.

### Sección 3: CDI

26. **B** — `@Inject` es la anotación estándar de CDI para solicitar inyección de dependencias.
27. **C** — Sin anotación de scope explícita, un bean es `@Dependent` (pseudo-scope, ligado al ciclo de vida de quien lo inyecta).
28. **B** — `@Produces` en un método/campo productor permite exponer instancias de tipos que no se pueden anotar directamente.
29. **A** — Un calificador personalizado es una anotación anotada a su vez con `@Qualifier`.
30. **B** — `@ConversationScoped` persiste durante una conversación de larga duración, iniciada/terminada explícitamente.
31. **A** — Los observadores se declaran como un parámetro de método anotado `@Observes`.
32. **B** — `@Alternative` marca un bean que debe activarse explícitamente para tomar efecto.
33. **B** — `beans.xml` históricamente activaba/configuraba el descubrimiento de beans en un archivo o módulo.
34. **A** — `@InterceptorBinding` define una anotación de enlace que conecta el interceptor con los beans que lo usan.
35. **B** — `@AroundInvoke` marca el método interceptor que envuelve la invocación del método de negocio.
36. **A** — `Instance<T>` da acceso programático y diferido a implementaciones de `T`, resolviendo la inyección dinámicamente.
37. **B** — Los decoradores están tipados al negocio decorado; los interceptores son genéricos y transversales.
38. **A** — Un método/campo `@Produces` en una clase productora calcula el valor a inyectar dinámicamente.
39. **B** — `@Vetoed` excluye una clase de ser considerada bean gestionado por CDI.
40. **D** — `@Dependent` es un pseudo-scope, no un scope normal (los normales son Request, Session, Application, Conversation).

### Sección 4: JPA

41. **B** — `@Entity` marca la clase como entidad persistente.
42. **B** — `@Id` es obligatoria para identificar el atributo de clave primaria.
43. **B** — `GenerationType.SEQUENCE` delega la generación de IDs a una secuencia de base de datos.
44. **B** — `@ManyToOne` mapea el lado "muchos" de una relación hacia el lado "uno".
45. **B** — `mappedBy` se coloca en el lado inverso (no propietario), típicamente el lado `@OneToMany`.
46. **A** — EAGER carga la asociación de inmediato; LAZY la difiere hasta el primer acceso.
47. **B** — JPQL es el lenguaje de consultas orientado a objetos definido por la especificación JPA.
48. **A** — `CriteriaBuilder` (junto con `CriteriaQuery`) permite construir consultas type-safe programáticamente.
49. **A** — `@Embeddable` marca una clase como embebible, sin identidad propia.
50. **B** — `@Embedded` se usa dentro de la entidad para incluir una instancia de una clase `@Embeddable`.
51. **B** — `@PrePersist` se ejecuta justo antes del `INSERT`.
52. **A** — `flush()` sincroniza los cambios pendientes con la base de datos sin finalizar la transacción.
53. **B** — `@Version` habilita control de concurrencia optimista basado en un número de versión/timestamp.
54. **B** — `@NamedQuery` define una consulta JPQL con nombre, reutilizable, a nivel de entidad.
55. **C** — `TABLE_PER_CLASS` genera una tabla independiente por cada clase concreta, replicando las columnas heredadas.

### Sección 5: EJB

56. **A** — `@Stateless` declara un bean de sesión sin estado.
57. **C** — `@Singleton` mantiene una única instancia compartida durante toda la vida de la aplicación.
58. **B** — `@EJB` es la anotación clásica para EJBs; `@Inject` también funciona si el EJB cumple los requisitos de un bean CDI.
59. **D** — `@MessageDriven` consume mensajes JMS de forma asíncrona.
60. **B** — Por defecto, los EJBs usan Container-Managed Transactions (CMT).
61. **A** — `@TransactionAttribute` (EJB) o `@Transactional` (JTA/CDI) definen el comportamiento transaccional del método.
62. **A** — `@Startup` en un `@Singleton`, junto con `@PostConstruct`, fuerza la inicialización temprana al desplegar la aplicación.
63. **B** — `@Schedule` (o `@Schedules` para múltiples) programa ejecuciones periódicas mediante el servicio de temporizador de EJB.
64. **A** — `UserTransaction` (JTA) se inyecta para gestionar transacciones manualmente en BMT.
65. **B** — Un `@Stateful` retiene estado conversacional entre invocaciones del mismo cliente; un `@Stateless` no.

### Sección 6: Bean Validation

66. **B** — `@NotNull` rechaza valores `null`.
67. **B** — `@NotBlank` es específica de `String` (recorta espacios y exige contenido); `@NotEmpty` aplica también a colecciones/arrays/mapas.
68. **B** — `@Min`/`@Max` (y variantes decimales) validan rangos numéricos.
69. **B** — `@Email` valida el formato de direcciones de correo.
70. **A** — `@Valid` activa la validación en cascada de objetos anidados.
71. **A** — Se define mediante una anotación meta-anotada con `@Constraint` y una clase `ConstraintValidator<A, T>` asociada.
72. **A** — `Validator` (obtenido típicamente desde un `ValidatorFactory`) ejecuta las validaciones programáticamente.
73. **A** — Los grupos de validación se definen con interfaces marcadoras usadas en el atributo `groups` de cada restricción.

### Sección 7: JSON-B / JSON-P

74. **B** — JSON-B (Jakarta JSON Binding) define el mapeo automático objeto-JSON.
75. **B** — `@JsonbProperty` renombra una propiedad en la representación JSON.
76. **A** — `@JsonbTransient` excluye un campo de la serialización/deserialización en JSON-B.
77. **A** — `Jsonb` (obtenido vía `JsonbBuilder`) es el punto de entrada para serializar/deserializar.
78. **B** — JSON-P ofrece una API de bajo nivel para construir/parsear JSON directamente, sin mapear a objetos Java.
79. **B** — `JsonObject` representa un valor JSON de tipo objeto (clave-valor).
80. **A** — Un `JsonbAdapter<Original, Adapted>` personaliza la conversión cuando las anotaciones estándar no alcanzan.
81. **B** — El proveedor JSON-B integrado actúa como `MessageBodyWriter`/`Reader`, serializando automáticamente en JAX-RS.

### Sección 8: WebSocket

82. **B** — `@ServerEndpoint` define la ruta y marca la clase como endpoint de servidor WebSocket.
83. **A** — `@OnOpen` se ejecuta al establecerse una nueva conexión.
84. **B** — `@OnMessage` maneja los mensajes entrantes del cliente.
85. **A** — `Session` representa la conexión activa y se usa para enviar mensajes de vuelta.
86. **A** — `@OnClose` se ejecuta cuando la conexión WebSocket se cierra.

### Sección 9: Seguridad

87. **A** — `@FormAuthenticationMechanismDefinition` define declarativamente un mecanismo de autenticación por formulario.
88. **A** — `@RolesAllowed` restringe el acceso a los roles indicados.
89. **B** — `@PermitAll` permite acceso sin restricción de rol.
90. **A** — `@DenyAll` bloquea el acceso a todos los usuarios sin excepción.
91. **A** — Se implementa `IdentityStore` para validar credenciales contra un origen personalizado.
92. **A** — `@BasicAuthenticationMechanismDefinition` define declarativamente autenticación HTTP Basic en Jakarta Security.
93. **A** — `isCallerInRole(String role)` de `SecurityContext` verifica si el usuario autenticado tiene un rol.
94. **A** — `HttpServletRequest.login(username, password)` autentica programáticamente al usuario.

### Sección 10: Concurrency Utilities

95. **A** — `ManagedExecutorService` provee ejecutores gestionados por el contenedor.
96. **A** — `@Asynchronous` invoca métodos de forma asíncrona en beans gestionados, devolviendo típicamente un `Future<T>`.
97. **A** — `ManagedScheduledExecutorService` permite programar tareas futuras o periódicas de forma gestionada.
98. **B** — El contenedor propaga contexto (seguridad, transacciones, classloader, JNDI) a las tareas; los hilos crudos no lo garantizan, y crearlos manualmente está desaconsejado/restringido en un entorno gestionado.
99. **A** — `ManagedThreadFactory` crea hilos gestionados que propagan el contexto del componente.
100. **A** — `ContextService` envuelve una tarea para que, al ejecutarse en un hilo no gestionado, herede el contexto de quien la creó.
