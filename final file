import java.io.Serializable;

public class Customer implements Serializable {
    private int id;
    private String firstName;
    private String lastName;
    private double balance;

    // Constructor
    public Customer(int id, String firstName, String lastName, double balance) {
        this.id = id;
        this.firstName = firstName;
        this.lastName = lastName;
        this.balance = balance;
    }

    // Getter and Setter methods
    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getFirstName() {
        return firstName;
    }

    public void setFirstName(String firstName) {
        this.firstName = firstName;
    }

    public String getLastName() {
        return lastName;
    }

    public void setLastName(String lastName) {
        this.lastName = lastName;
    }

    public double getBalance() {
        return balance;
    }

    public void setBalance(double balance) {
        this.balance = balance;
    }

    @Override
    public String toString() {
        return "Customer{id=" + id + ", firstName='" + firstName + "', lastName='" + lastName + "', balance=" + balance + "}";
    }
}

import java.util.Comparator;

public class CustomerSorter implements Comparator<Customer> {
    @Override
    public int compare(Customer c1, Customer c2) {
        // Compare first by First Name
        int firstNameComparison = c1.getFirstName().compareTo(c2.getFirstName());
        if (firstNameComparison != 0) {
            return firstNameComparison;
        }

        // If First Name is the same, compare by Last Name
        int lastNameComparison = c1.getLastName().compareTo(c2.getLastName());
        if (lastNameComparison != 0) {
            return lastNameComparison;
        }

        // If Last Name is the same, compare by ID
        int idComparison = Integer.compare(c1.getId(), c2.getId());
        if (idComparison != 0) {
            return idComparison;
        }

        // If ID is the same, compare by Balance
        return Double.compare(c1.getBalance(), c2.getBalance());
    }
}


import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class CustomerApp {
    public static void main(String[] args) {
        // Create a list of customers
        List<Customer> customers = new ArrayList<>();
        customers.add(new Customer(3, "John", "Doe", 1500.0));
        customers.add(new Customer(1, "Jane", "Smith", 2000.0));
        customers.add(new Customer(2, "John", "Smith", 1800.0));
        customers.add(new Customer(4, "Jane", "Doe", 1200.0));

        // Sort customers using the CustomerSorter
        Collections.sort(customers, new CustomerSorter());

        // Print sorted customers
        for (Customer customer : customers) {
            System.out.println(customer);
        }
    }
}
