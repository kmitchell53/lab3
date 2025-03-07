# lab3

----------------------------------auto
package assignment;

import java.security.Policy;

public class Auto extends Policy {
    private String make, model;
    private double liability, collision;

    public Auto(String firstName, String lastName, String make, String model, double liability, double collision) {
        super();
        this.make = make;
        this.model = model;
        this.liability = liability;
        this.collision = collision;
    }

    public double computeCommission() {
        return (liability + collision) * 0.3; // 30% commission
    }

    public void printPolicy() {
        printPolicyHeader("Auto");
        System.out.println("Make: " + make);
        System.out.println("Model: " + model);
        System.out.printf("Liability: $%,.2f%n", liability);
        System.out.printf("Collision: $%,.2f%n", collision);
        System.out.printf("Commission: $%,.2f%n", computeCommission());
    }

	private void printPolicyHeader(String string) {
		// TODO Auto-generated method stub
		
	}
}

----------------------------------------------home

package assignment;

import java.security.Policy;

public class home extends Policy {
    private int squareFootage;
    private double dwelling, contents, liability;

    public home(String firstName, String lastName, int squareFootage, double dwelling, double contents, double liability) {
        super();
        this.squareFootage = squareFootage;
        this.dwelling = dwelling;
        this.contents = contents;
        this.liability = liability;
    }

    public double computeCommission() {
        return (dwelling + contents + liability) * 0.2; // 20% commission
    }

    public void printPolicy() {
        printPolicyHeader("Home");
        System.out.println("Square Footage: " + squareFootage);
        System.out.printf("Dwelling: $%,.2f%n", dwelling);
        System.out.printf("Contents: $%,.2f%n", contents);
        System.out.printf("Liability: $%,.2f%n", liability);
        System.out.printf("Commission: $%,.2f%n", computeCommission());
    }

	private void printPolicyHeader(String string) {
		// TODO Auto-generated method stub
		
	}
}

--------------------------------------life

package assignment;

import java.security.Policy;

public class life extends Policy {
    private int age;
    private double term;

    public life(String firstName, String lastName, int age, double term) {
        super();
        this.age = age;
        this.term = term;
    }

    public double computeCommission() {
        return term * 0.2; // 20% commission
    }

    public void printPolicy() {
        printPolicyHeader("Life");
        System.out.println("Age: " + age);
        System.out.printf("Term: $%,.2f%n", term);
        System.out.printf("Commission: $%,.2f%n", computeCommission());
    }

------------------------------------driver

package assignment;

public class driver {
    public static void main(String[] args) {
        Auto autoPolicy = new Auto("John", "Doe", "Toyota", "Camry", 500.00, 1000.00);
        home homePolicy = new home("Jane", "Smith", 2000, 150000.00, 50000.00, 100000.00);
        life lifePolicy = new life("Alice", "Brown", 45, 250000.00);

        // Displaying commission for each policy
        calculator.displayCommission(autoPolicy);
        calculator.displayCommission(homePolicy);
        calculator.displayCommission(lifePolicy);
    }
}

------------------------------calculator

package assignment;

import java.security.Policy;

public class calculator {
    public static void displayCommission(Policy policy) {
        policy.getPolicy();
    }
}


--------------------------------parent

package assignment;

public abstract class parent {
    protected String firstName, lastName; // Common attributes

    public parent(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }

    // Abstract method to be implemented in derived classes
    public abstract double computeCommission();

    // Common method for printing policy headers
    public void printPolicyHeader(String policyType) {
        System.out.println("\n" + policyType + " Policy");
        System.out.println("-----------");
        System.out.println("Name: " + firstName + " " + lastName);
    }
}
