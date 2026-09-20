# Employee-structure
A java Program on the basic structure of a Employee

public class Employee {
    // Encapsulated fields
    private int id;
    private String name;
    private double salary;

    // Constructor
    public Employee(int id, String name, double salary) {
        this.id = id;
        this.name = name;
        this.salary = salary;
    }

    // Getters and Setters
    public int getId() { return id; }
    public void setId(int id) { this.id = id; }

    public String getName() { return name; }
    public void setName(String name) { this.name = name; }

    public double getSalary() { return salary; }
    public void setSalary(double salary) { this.salary = salary; }

    // Polymorphic method to calculate a standard bonus (e.g., 5%)
    public double calculateBonus() {
        return this.salary * 0.05;
    }

    // Method to display basic info
    public void displayDetails() {
        System.out.println("ID: " + id + " | Name: " + name + " | Base Salary: $" + salary);
    }
}
Use code with caution.2. The Subclass: Manager.javaThe Manager class inherits from Employee but adds unique traits, like tracking a team size and offering a higher performance bonus. Coddy Tech +1javapublic class Manager extends Employee {
    private int teamSize;

    // Constructor leveraging the parent class constructor using 'super'
    public Manager(int id, String name, double salary, int teamSize) {
        super(id, name, salary);
        this.teamSize = teamSize;
    }

    public int getTeamSize() { return teamSize; }
    public void setTeamSize(int teamSize) { this.teamSize = teamSize; }

    // Overriding the bonus calculation for managers (e.g., 12% bonus)
    @Override
    public double calculateBonus() {
        return getSalary() * 0.12;
    }

    // Overriding display details to include manager-specific information
    @Override
    public void displayDetails() {
        super.displayDetails();
        System.out.println("Role: Manager | Team Size: " + teamSize + " | Bonus: $" + calculateBonus());
    }
}
