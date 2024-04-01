[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/Fmb6W2KK)
Design a C++ program for an employee payroll system. Create classes for Employee and Payroll. Users can add employees, enter hours worked, calculate salaries, and generate payroll reports.
#include <iostream>
#include <vector>
#include <string>

using namespace std;

class Employee {
private:
    string name;
    double hourlyRate;
    double hoursWorked;

public:
    Employee(string n, double rate) : name(n), hourlyRate(rate), hoursWorked(0) {}

    string getName() const {
        return name;
    }

    double getHourlyRate() const {
        return hourlyRate;
    }

    double getHoursWorked() const {
        return hoursWorked;
    }

    void setHoursWorked(double hours) {
        hoursWorked = hours;
    }

    double calculateSalary() const {
        return hourlyRate * hoursWorked;
    }
};

class Payroll {
private:
    vector<Employee> employees;

public:
    void addEmployee(const Employee& emp) {
        employees.push_back(emp);
    }

    void generatePayrollReport() const {
        cout << "Payroll Report:" << endl;
        cout << "---------------------------------------" << endl;
        for (const auto& emp : employees) {
            cout << "Employee: " << emp.getName() << endl;
            cout << "Hours Worked: " << emp.getHoursWorked() << endl;
            cout << "Salary:" << emp.calculateSalary() << endl;
            cout << "---------------------------------------" << endl;
        }
    }
};

int main() {
    Payroll payroll;

    // Example: Add employees
    Employee emp1("Jerry", 1500.0);
    Employee emp2("samarth", 2220.0);

    // Example: Enter hours worked
    emp1.setHoursWorked(7);
    emp2.setHoursWorked(15);

    // Add employees to payroll
    payroll.addEmployee(emp1);
    payroll.addEmployee(emp2);

    // Generate payroll report
    payroll.generatePayrollReport();

    return 0;
}
