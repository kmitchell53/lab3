# lab3

// Abstract Parent Class
abstract class Policy {
    protected int policyNumber;
    protected String policyHolder;
    protected double premium;

    public Policy(int policyNumber, String policyHolder, double premium) {
        this.policyNumber = policyNumber;
        this.policyHolder = policyHolder;
        this.premium = premium;
    }

    // Abstract method to be implemented in derived classes
    public abstract double computeCommission();

    // Method to display policy details
    public void displayPolicyInfo() {
        System.out.println("Policy Number: " + policyNumber);
        System.out.println("Policy Holder: " + policyHolder);
        System.out.printf("Premium: $%.2f%n", premium);
        System.out.printf("Commission: $%.2f%n", computeCommission());
        System.out.println("--------------------------");
    }
}

// Auto Policy Class
class Auto extends Policy {
    public Auto(int policyNumber, String policyHolder, double premium) {
        super(policyNumber, policyHolder, premium);
    }

    @Override
    public double computeCommission() {
        return premium * 0.10; // 10% commission
    }
}

// Home Policy Class
class Home extends Policy {
    public Home(int policyNumber, String policyHolder, double premium) {
        super(policyNumber, policyHolder, premium);
    }

    @Override
    public double computeCommission() {
        return premium * 0.12; // 12% commission
    }
}

// Life Policy Class
class Life extends Policy {
    public Life(int policyNumber, String policyHolder, double premium) {
        super(policyNumber, policyHolder, premium);
    }

    @Override
    public double computeCommission() {
        return premium * 0.15; // 15% commission
    }
}

// Driver Class
public class PolicyDriver {
    public static void main(String[] args) {
        // Create instances of Auto, Home, and Life policies
        Policy autoPolicy = new Auto(101, "John Doe", 1200);
        Policy homePolicy = new Home(102, "Jane Smith", 2000);
        Policy lifePolicy = new Life(103, "Alice Brown", 3000);

        // Display policy details
        autoPolicy.displayPolicyInfo();
        homePolicy.displayPolicyInfo();
        lifePolicy.displayPolicyInfo();
    }
}
