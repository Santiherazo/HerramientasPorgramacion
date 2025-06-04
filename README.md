
# Aplicación y uso de Visual Studio HP1

Visual Studio es un IDE (Entorno de Desarrollo Integrado), una herramienta eficiente que permite a los desarrolladores gestionar todo el ciclo de desarrollo en un solo entorno. En él se pueden escribir, editar, depurar y compilar programas de forma sencilla.

Este entorno incluye compiladores, herramientas de autocompletado, control de versiones, extensiones y muchas otras funcionalidades que facilitan todas las fases del proceso de desarrollo de software.

---

### Iniciación e instalación de Visual Studio

Para comenzar a utilizar Visual Studio (VS), siga los siguientes pasos:

1. Ingrese al sitio oficial: [https://visualstudio.microsoft.com/](https://visualstudio.microsoft.com/).
2. Descargue la versión **Community** compatible con su sistema operativo.
3. Ejecute el instalador y siga las instrucciones para completar la instalación en su equipo.

![visual studio](https://i.imgur.com/f1Ge9LH.png)

---

### Ventajas de Visual Studio

- Instalador basado en cargas de trabajo: instale solo lo que necesita.
- Herramientas integradas de desarrollo: edite, compile, depure y publique desde un mismo lugar.
- Compatibilidad con múltiples lenguajes.
- Desarrollo multiplataforma: cree aplicaciones para cualquier sistema operativo.
- Integración con sistemas de control de versiones: colabore fácilmente en proyectos grupales.
- Asistencia con inteligencia artificial: mejore su productividad mediante sugerencias automáticas de código.

---

### ¿Qué es C#?

C# (C Sharp) es un lenguaje de programación moderno y orientado a objetos que toma lo mejor de C y C++. Ha sido optimizado para ofrecer una sintaxis poderosa y limpia. Además, adopta facilidades de otros lenguajes como Visual Basic, convirtiéndolo en una opción versátil, robusta y de fácil aprendizaje.

---

### Ventajas de C#

- **Sencillez:** Elimina elementos innecesarios del entorno .NET.
- **Modernidad:** Incorpora automáticamente características útiles y actuales.
- **Seguridad:** Controla accesos a datos para evitar errores comunes.
- **Sistema de tipos unificado:** Todos los datos pueden reutilizarse de forma estructurada.
- **Extensibilidad:** Permite la adición de nuevos tipos de datos, operadores y modificadores.
- **Versionable:** Las mejoras pueden implementarse sin comprometer versiones anteriores.
- **Compatible:** Su sintaxis es similar a lenguajes como C, C++ o Java.
- **Eficiente:** Aun con restricciones, se pueden usar punteros para manipulación avanzada de memoria.

---

### Mapa conceptual

![Mapa](https://i.imgur.com/sHrjR1h.png)

---

# Aplicación del manejo de vectores y matrices en el desarrollo de aplicaciones y posicionamiento en consola

---

### ¿Qué son los arreglos?

Un **arreglo** (o *array*) es una estructura de datos que permite almacenar varios elementos del mismo tipo bajo un único identificador. Los elementos se acceden mediante un índice numérico y se almacenan en posiciones contiguas de memoria.

---

### Tipos de arreglos

#### Arreglos unidimensionales (vectores)

Son estructuras lineales que contienen una sola fila de elementos.

```csharp
int[] valores = new int[20];
```

#### Arreglos multidimensionales (matrices)

Son estructuras que almacenan datos en varias dimensiones: filas, columnas o más.

```csharp
int[,] matriz2D = new int[10,10];
int[,,] matriz3D = new int[10,10,10];
```

---

#### Arreglos como parámetros

Los arreglos pueden pasarse como parámetros a métodos para ser modificados.

```csharp
using System;

class Program {
    static void ModificarArreglo(int[] arr) {
        arr[0] = 99;
    }

    static void Main() {
        int[] miArreglo = {1, 2, 3};
        ModificarArreglo(miArreglo);
        Console.WriteLine(miArreglo[0]); // Salida: 99
    }
}
```

---

### Inicialización de arreglos

Se puede inicializar de dos formas:

#### Forma directa (con datos precargados)

```csharp
int[] valores = {3, 5, 2, 1, 5, 3, 7, 9, 8};
int[,] numeros = { {1, 2, 3, 4}, {9, 8, 7, 6}, {7, 6, 2, 5} };
```

#### Forma separada (declaración y llenado posterior)

```csharp
int[] valores;
valores = new int[] {3, 5, 2, 1, 5, 3, 7, 9, 8};

int[,] numeros;
numeros = new int[,] { {1, 2, 3, 4}, {9, 8, 7, 6}, {7, 6, 2, 5} };
```

---

### Manejo y posicionamiento en consola

El posicionamiento en consola permite mover el cursor a una posición específica para mostrar texto o crear interfaces visuales.

Se usa principalmente con los siguientes métodos de la clase `Console`:

- `Console.SetCursorPosition(int left, int top)`: establece la posición del cursor.
- `Console.CursorLeft` y `Console.CursorTop`: obtiene o define la posición actual del cursor.

#### Ejemplo:

```csharp
using System;

class Program {
    static void Main() {
        Console.Clear();

        Console.SetCursorPosition(10, 2);
        Console.WriteLine("¡Hola desde la posición (10,2)!");

        Console.SetCursorPosition(5, 5);
        Console.WriteLine("╔════════════╗");
        Console.SetCursorPosition(5, 6);
        Console.WriteLine("║  MENÚ      ║");
        Console.SetCursorPosition(5, 7);
        Console.WriteLine("╚════════════╝");
    }
}
```

### Mapa conceptual

![Mapa](https://i.imgur.com/Vm3OAJt.png)

---

## Video

[Link](https://drive.google.com/file/d/1R_l3mBVZJ_v85uyTU48aNCSx6gomeqZP/view?usp=sharing)

### Análisis

Al concluir esta unidad, valoro el fortalecimiento de mis habilidades en programación estructurada y el dominio de herramientas esenciales como Visual Studio. Si bien ya contaba con conocimientos previos en temas como arreglos, interfaces de consola y POO (Programación Orientada a Objetos), esta unidad me permitió profundizar en aspectos clave, consolidar bases fundamentales y descubrir técnicas prácticas que ampliaron mi perspectiva.

---

# Creación de aplicaciones de Window Forms en C#

La aplicación desarrollada en la actividad "TIA 2. Tarea: Proyecto Final" consiste en un sistema de gestión para una biblioteca escolar, el cual permite registrar, consultar, prestar y devolver libros, así como administrar usuarios y aplicar sanciones por retrasos en la entrega. El objetivo principal es automatizar y controlar el préstamo de libros, restringiendo el acceso a nuevos préstamos en caso de que el usuario tenga multas activas por entregas tardías.

La estructura central del sistema incluye:

Usuarios iniciales y libros precargados, que pueden ser gestionados desde el sistema.

Gestión de usuarios y libros, con funciones para agregar, editar, eliminar y consultar.

Préstamos: un libro solo puede ser prestado si existen ejemplares disponibles.

Multas automáticas: si un usuario entrega un libro después de la fecha límite del préstamo, se le genera una multa.

Restricción de acceso: los usuarios con multas no pueden volver a realizar préstamos hasta saldar sus sanciones.

El sistema fue desarrollado utilizando Windows Forms, una tecnología de desarrollo de interfaces gráficas en C#. A continuación, se detallan los elementos principales de Windows Forms utilizados:

Formularios (Form): cada ventana del sistema representa una sección de la aplicación, como el formulario de inicio de sesión, el panel principal del usuario o del administrador, y los formularios para agregar libros o usuarios.

TextBox: utilizados para la entrada de datos como nombre de usuario, contraseña, información del libro o datos personales del usuario.

Label: se usan para identificar los campos de entrada y proporcionar instrucciones al usuario.

Button: permiten ejecutar acciones como iniciar sesión, registrar un nuevo usuario, guardar un libro o realizar un préstamo.

DataGridView: utilizado para mostrar listas de libros, usuarios, préstamos y multas en forma de tabla.

ComboBox: desplegables usados para seleccionar roles de usuario, géneros de libros o filtros.

DateTimePicker: se emplea para seleccionar fechas como la de adquisición del libro, fecha de nacimiento del usuario o fecha de devolución esperada.

MessageBox: se muestra al usuario para confirmar acciones, advertencias o errores (por ejemplo, si un usuario intenta prestar un libro estando multado).

Esta aplicación permite no solo el aprendizaje práctico de la programación orientada a objetos en C#, sino también la comprensión de estructuras de datos simples como arreglos y listas, y la lógica necesaria para simular un flujo real de préstamos bibliotecarios con restricciones y controles básicos.

---
![visual studio](https://i.imgur.com/f1Ge9LH.png)
---

## Referencias

- Microsoft. (2025, 30 de enero). Introducción al IDE de Visual Studio. Microsoft Learn. https://learn.microsoft.com/es-es/visualstudio/get-started/visual-studio-ide?view=vs-2022
- Documentación oficial de C#: https://learn.microsoft.com/es-es/dotnet/csharp/
