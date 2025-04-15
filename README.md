import java.util.InputMismatchException;
import java.util.Scanner;
 
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
        System.out.println("Speed: " + speed + " km/h");
        System.out.println("Fuel Type: " + fuelType);
    }
}
 
class Car extends Vehicle {
    private int numberOfDoors;
 
    public Car(String brand, int speed, String fuelType, int numberOfDoors) {
        super(brand, speed, fuelType);
        this.numberOfDoors = numberOfDoors;
    }
 
    @Override
    public void displayInfo() {
        super.displayInfo();
        System.out.println("Number of Doors: " + numberOfDoors);
    }
}
 
class Motorcycle extends Vehicle {
    private boolean hasSidecar;
 
    public Motorcycle(String brand, int speed, String fuelType, boolean hasSidecar) {
        super(brand, speed, fuelType);
        this.hasSidecar = hasSidecar;
    }
 
    @Override
    public void displayInfo() {
        super.displayInfo();
        System.out.println("Has Sidecar: " + (hasSidecar ? "Yes" : "No"));
    }
}
 
public class TestVehicle {
    public static void main(String[] args) {
        try (Scanner scanner = new Scanner(System.in)) {
            try {
                System.out.println("Enter the details for the Car:");
                System.out.print("Brand: ");
                String carBrand = scanner.nextLine();
                System.out.print("Speed: ");
                int carSpeed = scanner.nextInt();
                scanner.nextLine(); // Consume newline
                System.out.print("Fuel Type: ");
                String carFuelType = scanner.nextLine();
                System.out.print("Number of Doors: ");
                int numberOfDoors = scanner.nextInt();
                scanner.nextLine(); // Consume newline
 
                Car car = new Car(carBrand, carSpeed, carFuelType, numberOfDoors);
 
                System.out.println("\nEnter the details for the Motorcycle:");
                System.out.print("Brand: ");
                String motorcycleBrand = scanner.nextLine();
                System.out.print("Speed: ");
                int motorcycleSpeed = scanner.nextInt();
                scanner.nextLine(); // Consume newline
                System.out.print("Fuel Type: ");
                String motorcycleFuelType = scanner.nextLine();
                System.out.print("Has Sidecar (true/false): ");
                boolean hasSidecar = scanner.nextBoolean();
                scanner.nextLine(); // Consume newline
 
                Motorcycle motorcycle = new Motorcycle(motorcycleBrand, motorcycleSpeed, motorcycleFuelType, hasSidecar);
 
                System.out.println("\nCar Details:");
                car.displayInfo();
 
                System.out.println("\nMotorcycle Details:");
                motorcycle.displayInfo();
            } catch (InputMismatchException e) {
                System.out.println("Invalid input. Please enter the correct data type.");
            }
        }
    }
}




