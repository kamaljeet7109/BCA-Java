1.	Encapsulation is the bundling of data and methods that operate on the data into a single unit, called a class. It hides the internal state of an object from the outside world and only exposes the necessary functionality through well-defined interfaces. 
Create an Employee class having data members' Name, Eid, and Basic_Salary, to calculate the HRA is 20% of Basic Salary and DA is 25% of Basic salary and MA is 300 rupee. implement the following queries:
  a) Display the name and gross salary of an employee whose name starts With 'n'
  b).Display the Eid and gross salary whose Eid is equal to 107.
  c)  Count the total number of employees whose salary more than 20000/-
import java.util.ArrayList;

class Employee {
    private String name;
    private int eid;
    private double basicSalary;

    public Employee(String name, int eid, double basicSalary) {
        this.name = name;
        this.eid = eid;
        this.basicSalary = basicSalary;
    }

    public String getName() {
        return name;
    }

    public int getEid() {
        return eid;
    }

    public double getBasicSalary() {
        return basicSalary;
    }

    public double calculateHRA() {
        return 0.20 * basicSalary;
    }

    public double calculateDA() {
        return 0.25 * basicSalary;
    }

    public double calculateMA() {
        return 300.0;
    }

    public double calculateGrossSalary() {
        return basicSalary + calculateHRA() + calculateDA() + calculateMA();
    }

    public static void main(String[] args) {
        ArrayList<Employee> employees = new ArrayList<>();
        employees.add(new Employee("John", 101, 25000));
        employees.add(new Employee("Alice", 102, 22000));
        employees.add(new Employee("Nancy", 103, 28000));
        employees.add(new Employee("Bob", 104, 18000));
        employees.add(new Employee("Nathan", 105, 30000));
        employees.add(new Employee("David", 106, 21000));
        employees.add(new Employee("Nora", 107, 24000));

        // Query a) Display the name and gross salary of an employee whose name starts With 'n'
        System.out.println("Employees whose name starts with 'N':");
        for (Employee emp : employees) {
            if (emp.getName().toLowerCase().startsWith("n")) {
                System.out.println("Name: " + emp.getName() + ", Gross Salary: " + emp.calculateGrossSalary());
            }
        }

        // Query b) Display the Eid and gross salary whose Eid is equal to 107
        System.out.println("\nEmployee with Eid 107:");
        for (Employee emp : employees) {
            if (emp.getEid() == 107) {
                System.out.println("Eid: " + emp.getEid() + ", Gross Salary: " + emp.calculateGrossSalary());
            }
        }

        // Query c) Count the total number of employees whose salary more than 20000
        int count = 0;
        for (Employee emp : employees) {
            if (emp.getBasicSalary() > 20000) {
                count++;
            }
        }
        System.out.println("\nTotal number of employees with salary more than 20000: " + count);
    }
}
