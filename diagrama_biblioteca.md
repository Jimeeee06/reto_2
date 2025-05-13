
```mermaid
classDiagram
  direction TB

  class Libro {
    -String titulo
    -String autor
    -String codigo
    -bool disponible
    +prestar()
    +devolver()
  }

  class Usuario {
    -String nombre
    -int ID
    -String correo
    -list prestamos
    +devolver_libro()
  }

  class Bibliotecario {
    +registrar_libro()
    +registrar_usuario()
    +gestionar_prestamos()
  }

  class Prestamo {
    -date fecha_prestamo
    -date fecha_devolucion_prevista
    -date fecha_devolucion_real
    -String estado_prestamo
    -int multa
    +registrar_devolucion()
    +calcular_multa()
  }

  Bibliotecario -- Prestamo : gestionar()
  Bibliotecario -- Libro : registrar()
  Usuario --* Libro
  Usuario --* Prestamo
  
```
