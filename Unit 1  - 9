class Employee:
    def __init__(self, employee_id: int, name: str, salary: float):
        self.employee_id = employee_id
        self.name = name
        self.salary = salary

    @property
    def category(self) -> str:
        """Categorize employee based on salary."""
        if self.salary >= 70000:
            return "High Salary"
        elif self.salary >= 40000:
            return "Medium Salary"
        else:
            return "Low Salary"

    def display(self) -> None:
        print(f"Employee ID : {self.employee_id}")
        print(f"Name        : {self.name}")
        print(f"Salary      : ₹{self.salary:,.2f}")
        print(f"Category    : {self.category}")
        print("-" * 40)


class Company:
    def __init__(self, company_name: str):
        self.company_name = company_name
        self.employees: list[Employee] = []

    def add_employee(self, employee: Employee) -> None:
        """Add an employee to the company."""
        self.employees.append(employee)
        print(f"Employee '{employee.name}' added successfully!")

    def display_all_employees(self) -> None:
        """Display information of all employees."""
        if not self.employees:
            print("No employees found.")
            return

        print("\n" + "=" * 40)
        print(f"      {self.company_name}")
        print("      EMPLOYEE DETAILS")
        print("=" * 40)

        for employee in self.employees:
            employee.display()

    def display_by_category(self, category: str) -> None:
        """Display employees belonging to a particular salary category."""
        filtered_employees = [
            employee for employee in self.employees
            if employee.category.lower() == category.lower()
        ]

        if not filtered_employees:
            print(f"No employees found in {category}.")
            return

        print(f"\n--- {category} Employees ---")
        for employee in filtered_employees:
            print(
                f"ID: {employee.employee_id} | "
                f"Name: {employee.name} | "
                f"Salary: ₹{employee.salary:,.2f}"
            )


def main():
    company = Company("ABC Technologies")

    while True:
        print("\n========== EMPLOYEE MANAGEMENT SYSTEM ==========")
        print("1. Add Employee")
        print("2. Display All Employees")
        print("3. Display High Salary Employees")
        print("4. Display Medium Salary Employees")
        print("5. Display Low Salary Employees")
        print("6. Exit")

        choice = input("Enter your choice: ")

        if choice == "1":
            try:
                employee_id = int(input("Enter Employee ID: "))
                name = input("Enter Employee Name: ").strip()
                salary = float(input("Enter Salary: ₹"))

                if not name:
                    print("Name cannot be empty.")
                    continue

                if salary < 0:
                    print("Salary cannot be negative.")
                    continue

                employee = Employee(employee_id, name, salary)
                company.add_employee(employee)

            except ValueError:
                print("Invalid input! Please enter valid details.")

        elif choice == "2":
            company.display_all_employees()

        elif choice == "3":
            company.display_by_category("High Salary")

        elif choice == "4":
            company.display_by_category("Medium Salary")

        elif choice == "5":
            company.display_by_category("Low Salary")

        elif choice == "6":
            print("Thank you for using Employee Management System!")
            break

        else:
            print("Invalid choice! Please select 1-6.")


if __name__ == "__main__":
    main()
