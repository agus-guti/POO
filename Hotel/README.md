### Ejercicio de Hotel

## Clase Main.

```java
package ejerciciohotel;

public class EjercicioHotel {

    public static void main(String[] args) {
        AccionHotel accion;
        
        accion = new ReservarHabitacion("Habitación 101", "Juan Pérez");
        accion.ejecutarAccion();
        
        accion = new Pago("Tarjeta de crédito", 5000);
        accion.ejecutarAccion();
    }
    
}

```

## Clase abstracta.

```java

package ejerciciohotel;

public abstract class AccionHotel {
    public abstract void ejecutarAccion();
}

```

## Clase pago.

```java

package ejerciciohotel;

public class Pago extends AccionHotel{
    private String tipoTarjeta;
    private int monto;

    public Pago() {
    }

    public Pago(String tipoTarjeta, int monto) {
        this.tipoTarjeta = tipoTarjeta;
        this.monto = monto;
    }

    public String getTipoTarjeta() {
        return tipoTarjeta;
    }

    public void setTipoTarjeta(String tipoTarjeta) {
        this.tipoTarjeta = tipoTarjeta;
    }

    public int getMonto() {
        return monto;
    }

    public void setMonto(int monto) {
        this.monto = monto;
    }

    @Override
    public void ejecutarAccion() {
        System.out.println("Tipo de tarjeta: "+this.tipoTarjeta);
        System.out.println("Monto: "+this.monto);
    }
    
    
}

```

## Clase ReservarHabitacion.

```java

package ejerciciohotel;

public class ReservarHabitacion extends AccionHotel {
    private String numHab;
    private String nombre;

    public ReservarHabitacion() {
    }

    public ReservarHabitacion(String TipoHab, String nombre) {
        this.numHab = TipoHab;
        this.nombre = nombre;
    }

    public String getTipoHab() {
        return numHab;
    }

    public void setTipoHab(String TipoHab) {
        this.numHab = TipoHab;
    }

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    @Override
    public void ejecutarAccion() {
        System.out.println("Numero de habitacion:"+this.numHab);
        System.out.println("Nombre del inquilino: "+this.nombre);
    }
    
    
    
    
}

```
