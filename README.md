package ACTIVITY_1;
import java.util.Scanner;
public class TestVehicle {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
 
       
        System.out.println("Enter Car Details:");
        System.out.print("Brand: ");
        String carBrand = scan.nextLine();
 
        System.out.print("Speed: ");
        int carSpeed = scan.nextInt();
        scan.nextLine();
 
        System.out.print("Fuel Type: ");
        String carFuel = scan.nextLine();
 
        System.out.print("Number of Doors: ");
        int doors = scan.nextInt();
        scan.nextLine();
 
        Car car = new Car(carBrand, carSpeed, carFuel, doors);
 
       
        System.out.println("\nEnter Motorcycle Details:");
        System.out.print("Brand: ");
        String motorBrand = scan.nextLine();
 
        System.out.print("Speed: ");
        int motorSpeed = scan.nextInt();
        scan.nextLine();
 
        System.out.print("Fuel Type: ");
        String motorFuel = scan.nextLine();
 
        boolean hasSidecar = false;
        while (true) {
            System.out.print("Has Sidecar (Yes or No): ");
            String sidecar = scan.nextLine();
 
            if (sidecar.equalsIgnoreCase("Yes")) {
                hasSidecar = true;
                break;
            } else if (sidecar.equalsIgnoreCase("No")) {
                hasSidecar = false;
                break;
            } else {
                System.out.println("Invalid input. Please enter Yes or No.");
            }
        }
 
        Motorcycle motorcycle = new Motorcycle(motorBrand, motorSpeed, motorFuel, hasSidecar);
 
       
        System.out.println("\n--- Car Information ---");
        car.displayInfo();
        System.out.println("Number of Doors: " + car.getNumDoors());
 
        System.out.println("\n--- Motorcycle Information ---");
        motorcycle.displayInfo();
        System.out.print("Has Sidecar: ");
        if (motorcycle.getHasSidecar()) {
            System.out.println("Yes");
        } else {
            System.out.println("No");
        }
 
        scan.close();
    }
}
 
 
class Vehicle {
    private String brand;
    private int speed;
    private String fuelType;
 
    public Vehicle(String brand, int speed, String fuelType) {
        this.brand = brand;
        this.speed = speed;
        this.fuelType = fuelType;
    }
 
    public String getBrand() {
        return brand;
    }
 
    public int getSpeed() {
        return speed;
    }
 
    public String getFuelType() {
        return fuelType;
    }
 
    public void displayInfo() {
        System.out.println("Brand: " + brand);
        System.out.println("Speed: " + speed + " kmph");
        System.out.println("Fuel Type: " + fuelType);
    }
}
 
 
class Car extends Vehicle {
    private int numDoors;
 
    public Car(String brand, int speed, String fuelType, int numDoors) {
        super(brand, speed, fuelType);
        this.numDoors = numDoors;
    }
 
    public int getNumDoors() {
        return numDoors;
    }
}
 
 
class Motorcycle extends Vehicle {
    private boolean hasSidecar;
 
    public Motorcycle(String brand, int speed, String fuelType, boolean hasSidecar) {
        super(brand, speed, fuelType);
        this.hasSidecar = hasSidecar;
    }
 
    public boolean getHasSidecar() {
        return hasSidecar;
    }
}
