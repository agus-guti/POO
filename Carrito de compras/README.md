### Trabajo practica de Carrito de compras.

## Clase main.

```java
package carrito.de.compras;

public class CarritoDeCompras {

    public static void main(String[] args) {
        Producto p1 = new Producto("Teclado Mecánico", 4500.50);
        Producto p2 = new Producto("Mouse Óptico", 1200.00);
        Producto p3 = new Producto("Monitor 24'", 15000.90);

        Carrito miCarrito = new Carrito();
        
        miCarrito.añadir(p1);
        miCarrito.añadir(p2);
        miCarrito.añadir(p3);

        System.out.println("--- Resumen de Compra ---");
        miCarrito.mostrarDetalle();

        double total = miCarrito.calcularTotal();
        System.out.println("\nTOTAL A PAGAR: $" + total);

    }

}

```

## Clase producto.

```java

package carrito.de.compras;

public class Producto {
    private String nombre;
    private double precio;
    
    public Producto (String nombre, double precio){
        this.nombre = nombre;
        this.precio = precio;
    }

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public double getPrecio() {
        return precio;
    }

    public void setPrecio(double precio) {
        this.precio = precio;
    }
    
    
}

```

## Clase Carrito.

```java

package carrito.de.compras;

import java.util.ArrayList;
import java.util.List;

public class Carrito {
    private List <Producto> carrito = new ArrayList<>();
    
    public Carrito (){
        
    }

    public List<Producto> getCarrito() {
        return carrito;
    }

    public void setCarrito(List<Producto> carrito) {
        this.carrito = carrito;
    }
    public void añadir (Producto carrito){
        this.carrito.add(carrito);
    }
    public void mostrarDetalle (){
        for (Producto p : carrito) {
            System.out.println("Producto: "+p.getNombre());
            System.out.println("Precio: "+p.getPrecio());
        }
    }
    public double calcularTotal (){
        
        double total = 0;
        
        for (Producto p : carrito) {
            total = total + p.getPrecio();
        }
        return total;
    }
    
}

```