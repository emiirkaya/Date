# BIL142 C++ Fınal Project for TOBB ETU

This piece of code features a project that provides a robust and flexible Date class in C++ for safe and convenient calendar date operations (day, month, year).
The class focuses on typical needs such as date validation, comparison, and arithmetic operations.

Features
* Validation: Catches invalid dates (raises a custom bad_date exception).

* Increment/Decrement: Use ++ and -- operators to navigate days; month/year transitions are handled automatically.

* Leap Year Support: Correct leap year logic according to the Gregorian calendar.

* Comparison Operators: Easily compare and sort dates using ==, !=, <, >, <=, >=.

* Day of Year Calculation: get_year_day() returns which day of the year the date is.

* Random Date Generation: Generate a random valid date within a certain year range (great for testing or dummy data).

* Construct From String: Build a date from a "DD MM YYYY" formatted string.

Usage Example:
```
#include "Date.h"
#include <iostream>

int main() {
    try {
        project::Date d1(15, 3, 2022);
        std::cout << "Date: " << d1.get_month_day() << "/" << d1.get_month() << "/" << d1.get_year() << std::endl;
        
        ++d1; // Move forward by one day
        std::cout << "Next day: " << d1.get_month_day() << "/" << d1.get_month() << "/" << d1.get_year() << std::endl;
        
        project::Date d2("28 02 2024");
        ++d2; // After Feb 28 on a leap year
        std::cout << "Jump: " << d2.get_month_day() << "/" << d2.get_month() << "/" << d2.get_year() << std::endl;
        
        if (d1 > d2) {
            std::cout << "d1 is a newer date than d2." << std::endl;
        }
    }
    catch (const project::bad_date& e) {
        std::cerr << "Invalid date: " << e.what() << std::endl;
    }
}
```
