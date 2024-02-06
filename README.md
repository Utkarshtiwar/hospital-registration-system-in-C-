# hospital-registration-system-in-C++<br>
1.This project is simple and contains very basic levels of the cpp programming language.<br>
2.
firstly you have to make an id and password for the user.<br>
3.
Now you can ask the user to enter the id and password in the terminal ,if password mathches then send a password mismatch message and exit the program ,else if id is worng just simply show user not found and then ext the program .<br>
4.
when user entered correct user id and password just show list of diseases which are available to cure in our hospital with a welcome message .<br>
5.
now select the disease and then go to the list of specialist doctors with their degree and experience .<br>
6.
now select the doctor you want .<br>
7.
press y for continue registration .<br>
8.
enter name,age ,dob,and gender .<br>
congratulation !!! you have completed your registration.<br>
author -Utkarsh tiwari 
#include <iostream>
#include <string>
#include <sstream>
#include <vector>
#include <limits>
using namespace std;
#define ANSI_COLOR_RED "\x1b[31m"
#define ANSI_COLOR_ROYAL_BLUE "\x1b[34;1m"
#define ANSI_COLOR_RESET "\x1b[0m"
// user id and password verification function
int user_id_password(const string &user_id, const string &password, const string &user_id1, const string &password1)
{
    if (user_id.empty() || password.empty())
    {
        cout << "Empty input !!!!";
        return -1;
    }
    if (user_id1 == user_id)
    {
        if (password1 == password)
        {
            return 1;
        }
        else
        {
            std::cout << "Incorrect Password\n";
            return -2;
        }
    }
    else
    {
        std::cout << "User " << user_id << " cannot be found \n";
        return -3;
    }
    return 0;
}
// function to find the disease of the patient
int specification(int a)
{
    do
    {
        std::cout << ANSI_COLOR_RED << "Our hospital have these below specification and there speciality :\n"
                  << ANSI_COLOR_RESET;
        std::cout << "1. Infectious Diseases \n";
        std::cout << "2. Chronic Diseases \n";
        std::cout << "3. Genetic Diseases \n";
        std::cout << "4. Mental Health Disorders \n";
        std::cout << "5. Lifestyle-Related Diseases:\n- Type 2 Diabetes (often related to diet and lifestyle)\n- Chronic Liver Disease (often related to alcohol consumption)\n- Substance Use Disorders (e.g., addiction to drugs or alcohol)\n";
        std::cout << "6. Rare Diseases:\n- Duchenne Muscular Dystrophy\n- Progeria\n- Huntington's Disease\n";
        std::cout << "7. Autoimmune Diseases (e.g., rheumatoid arthritis, lupus)\n";
        std::cout << "8. Vector-Borne Diseases:\n- Malaria (transmitted by mosquitoes)\n- Lyme Disease (transmitted by ticks)\n";
        std::cout << "9. Gastrointestinal Diseases:\n- Irritable Bowel Syndrome (IBS)\n- Crohn's Disease\n";
        std::cout << "10. Skin Conditions:\n- Eczema\n- Psoriasis\n- Acne\n";
        std::cout << "11. Neurological Disorders:\n- Epilepsy\n- Multiple Sclerosis (MS)\n";
        std::cout << "12. Cardiovascular Diseases:\n- Heart Attack\n- Stroke\n";
        int choice;
        std::cout << endl;
        // std::cout << "Enter the number mentioned before the diseases : ";
        while (true)
        {
            std::cout << "Enter a number mentioned before the disease : ";
            if (!(std::cin >> choice))
            {
                std::cin.clear();
                std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
                std::cout << "Invalid input. Please enter a number.\n";
            }
            else
            {
                if (choice >= 1 && choice <= 12)
                {
                    return choice;
                    break; // Exit the loop if input is valid.
                }
            }
            cout << ANSI_COLOR_RED << "Invalid choice!!! " << ANSI_COLOR_RESET;
            cout << "Enter number in between 1 to 12 : \n";
        }
    } while (true);
}
// 1
int infectious_diseases(void)
{
    std::cout << endl;
    std::cout << "Doctor for Infectious Diseases : \n";
    std::cout << endl;
    std::cout << "1.Name : Dr. Piyush dixit \n";
    std::cout << "Specialization : Infectious Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : piyush@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "\n2.Name : Dr. Shweta Kumari \n";
    std::cout << "Specialization : Infectious Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : shwetakumari@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n3.Name : Dr. Manish kumar \n";
    std::cout << "Specialization : Infectious Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : manishkumar@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n4.Name : Dr. Nirbhay singh \n";
    std::cout << "Specialization : Infectious Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : nirbhaysingh@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "press 1 for Dr. Piyush Dixit \n press 2 for Dr. shweta kumari \n press 3 for Dr. Manish kumar \n press 4 for Dr. Nirbhay kumar \n";
    std::cout << "\nPlease enter your choice: ";
    int choice;
    while (true)
    {
        std::cout << "Enter a number: ";
        if (!(std::cin >> choice))
        {
            std::cin.clear();
            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
            std::cout << "Invalid input. Please enter a number.\n";
        }
        else
        {
            if (choice >= 1 && choice <= 4)
            {
                return choice;
                break;
            }
        }
        cout << ANSI_COLOR_RED << "Invalid choice!!! " << ANSI_COLOR_RESET;
        // exit(-1);
    }
}
// 2
int chronic_disorder()
{
    int a;
    std::cout << endl;
    std::cout << "Doctor for Chronic Disorder Diseases : \n";
    std::cout << endl;
    std::cout << "1.Name : Dr. Piyush dixit \n";
    std::cout << "Specialization : Chronic Disorder \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : piyush@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "\n2.Name : Dr. Shweta Kumari \n";
    std::cout << "Specialization : Chronic Disorder \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : shwetakumari@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n3.Name : Dr. Manish kumar \n";
    std::cout << "Specialization : Chronic Disorder \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : manishkumar@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n4.Name : Dr. Nirbhay singh \n";
    std::cout << "Specialization : Chronic Disorder \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : nirbhaysingh@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "press 1 for Dr. Piyush Dixit \n press 2 for Dr. shweta kumari \n press 3 for Dr. Manish kumar \n press 4 for Dr. Nirbhay kumar \n";
    std::cout << "\nPlease enter your choice: ";
    int choice;
    while (true)
    {
        std::cout << "Enter a number: ";
        if (!(std::cin >> choice))
        {
            std::cin.clear();
            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
            std::cout << "Invalid input. Please enter a number.\n";
        }
        else
        {
            if (choice >= 1 && choice <= 4)
            {
                return choice;
                break;
            }
        }
        cout << ANSI_COLOR_RED << "Invalid choice!!! " << ANSI_COLOR_RESET;
        // exit(-1);
    }
}
// 3
int genetic_Diseases(void)
{
    int a;
    std::cout << endl;
    std::cout << "Doctor for Genetic Diseases : \n";
    std::cout << endl;
    std::cout << "1.Name : Dr. Piyush dixit \n";
    std::cout << "Specialization : Genetic Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : piyush@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "\n2.Name : Dr. Shweta Kumari \n";
    std::cout << "Specialization : Genetic Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : shwetakumari@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n3.Name : Dr. Manish kumar \n";
    std::cout << "Specialization : Genetic Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : manishkumar@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n4.Name : Dr. Nirbhay singh \n";
    std::cout << "Specialization : Genetic Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : nirbhaysingh@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "press 1 for Dr. Piyush Dixit \n press 2 for Dr. shweta kumari \n press 3 for Dr. Manish kumar \n press 4 for Dr. Nirbhay kumar \n";
    std::cout << "\nPlease enter your choice: ";
    int choice;
    while (true)
    {
        std::cout << "Enter a number: ";
        if (!(std::cin >> choice))
        {
            std::cin.clear();
            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
            std::cout << "Invalid input. Please enter a number.\n";
        }
        else
        {
            if (choice >= 1 && choice <= 4)
            {
                return choice;
                break;
            }
        }
        cout << ANSI_COLOR_RED << "Invalid choice!!! " << ANSI_COLOR_RESET;
        // exit(-1);
    }
}
// 4
int mental_health_Diseases(void)
{
    int a;
    std::cout << endl;
    std::cout << "Doctor for Mental Health Disorder : \n";
    std::cout << endl;
    std::cout << "1.Name : Dr. Piyush dixit \n";
    std::cout << "Specialization : Mental Health Disorder \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : piyush@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "\n2.Name : Dr. Shweta Kumari \n";
    std::cout << "Specialization : Mental Health Disorder \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : shwetakumari@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n3.Name : Dr. Manish kumar \n";
    std::cout << "Specialization : Mental Health Disorder \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : manishkumar@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n4.Name : Dr. Nirbhay singh \n";
    std::cout << "Specialization : Mental Health Disorder \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : nirbhaysingh@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "press 1 for Dr. Piyush Dixit \n press 2 for Dr. shweta kumari \n press 3 for Dr. Manish kumar \n press 4 for Dr. Nirbhay kumar \n";
    std::cout << "\nPlease enter your choice: ";
    int choice;
    while (true)
    {
        std::cout << "Enter a number: ";
        if (!(std::cin >> choice))
        {
            std::cin.clear();
            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
            std::cout << "Invalid input. Please enter a number.\n";
        }
        else
        {
            if (choice >= 1 && choice <= 4)
            {
                return choice;
                break;
            }
        }
        cout << ANSI_COLOR_RED << "Invalid choice!!! " << ANSI_COLOR_RESET;
        // exit(-1);
    }
}
// 5
int lifestyle_related_Diseases(void)
{
    int a;
    std::cout << endl;
    std::cout << "Doctor for Lifestyle related Diseases : \n";
    std::cout << endl;
    std::cout << "1.Name : Dr. Piyush dixit \n";
    std::cout << "Specialization : Lifestyle related Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : piyush@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "\n2.Name : Dr. Shweta Kumari \n";
    std::cout << "Specialization : Lifestyle related Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : shwetakumari@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n3.Name : Dr. Manish kumar \n";
    std::cout << "Specialization : Lifestyle related Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : manishkumar@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n4.Name : Dr. Nirbhay singh \n";
    std::cout << "Specialization : Lifestyle related Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : nirbhaysingh@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "press 1 for Dr. Piyush Dixit \n press 2 for Dr. shweta kumari \n press 3 for Dr. Manish kumar \n press 4 for Dr. Nirbhay kumar \n";
    std::cout << "\nPlease enter your choice: ";
    int choice;
    while (true)
    {
        std::cout << "Enter a number: ";
        if (!(std::cin >> choice))
        {
            std::cin.clear();
            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
            std::cout << "Invalid input. Please enter a number.\n";
        }
        else
        {
            if (choice >= 1 && choice <= 4)
            {
                return choice;
                break;
            }
        }
        cout << ANSI_COLOR_RED << "Invalid choice!!! " << ANSI_COLOR_RESET;
        // exit(-1);
    }
}
// 6
int rare_Diseases(void)
{
    int a;
    std::cout << endl;
    std::cout << "Doctor for Rare Diseases : \n";
    std::cout << endl;
    std::cout << "1.Name : Dr. Piyush dixit \n";
    std::cout << "Specialization : Rare Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : piyush@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "\n2.Name : Dr. Shweta Kumari \n";
    std::cout << "Specialization : Rare Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : shwetakumari@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n3.Name : Dr. Manish kumar \n";
    std::cout << "Specialization : Rare Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : manishkumar@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n4.Name : Dr. Nirbhay singh \n";
    std::cout << "Specialization : Rare Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : nirbhaysingh@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "press 1 for Dr. Piyush Dixit \n press 2 for Dr. shweta kumari \n press 3 for Dr. Manish kumar \n press 4 for Dr. Nirbhay kumar \n";
    std::cout << "\nPlease enter your choice: ";
    int choice;
    while (true)
    {
        std::cout << "Enter a number: ";
        if (!(std::cin >> choice))
        {
            std::cin.clear();
            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
            std::cout << "Invalid input. Please enter a number.\n";
        }
        else
        {
            if (choice >= 1 && choice <= 4)
            {
                return choice;
                break;
            }
        }
        cout << ANSI_COLOR_RED << "Invalid choice!!! " << ANSI_COLOR_RESET;
        // exit(-1);
    }
}
// 7
int autoimmune_Diseases(void)
{
    int a;
    std::cout << endl;
    std::cout << "Doctor for Autoimmune Diseases : \n";
    std::cout << endl;
    std::cout << "1.Name : Dr. Piyush dixit \n";
    std::cout << "Specialization : Autoimmune Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : piyush@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "\n2.Name : Dr. Shweta Kumari \n";
    std::cout << "Specialization : Autoimmune Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : shwetakumari@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n3.Name : Dr. Manish kumar \n";
    std::cout << "Specialization : Autoimmune Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : manishkumar@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n4.Name : Dr. Nirbhay singh \n";
    std::cout << "Specialization : Autoimmune Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : nirbhaysingh@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "press 1 for Dr. Piyush Dixit \n press 2 for Dr. shweta kumari \n press 3 for Dr. Manish kumar \n press 4 for Dr. Nirbhay kumar \n";
    std::cout << "\nPlease enter your choice: ";
    int choice;
    while (true)
    {
        std::cout << "Enter a number: ";
        if (!(std::cin >> choice))
        {
            std::cin.clear();
            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
            std::cout << "Invalid input. Please enter a number.\n";
        }
        else
        {
            if (choice >= 1 && choice <= 4)
            {
                return choice;
                break;
            }
        }
        cout << ANSI_COLOR_RED << "Invalid choice!!! " << ANSI_COLOR_RESET;
        // exit(-1);
    }
}
// 8
int vector_borne_Diseases(void)
{
    int a;
    std::cout << endl;
    std::cout << "Doctor for Vector borne Diseases : \n";
    std::cout << endl;
    std::cout << "1.Name : Dr. Piyush dixit \n";
    std::cout << "Specialization : Vector borne Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : piyush@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "\n2.Name : Dr. Shweta Kumari \n";
    std::cout << "Specialization : Vector borne Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : shwetakumari@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n3.Name : Dr. Manish kumar \n";
    std::cout << "Specialization : Vector borne Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : manishkumar@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n4.Name : Dr. Nirbhay singh \n";
    std::cout << "Specialization : Vector borne Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : nirbhaysingh@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "press 1 for Dr. Piyush Dixit \n press 2 for Dr. shweta kumari \n press 3 for Dr. Manish kumar \n press 4 for Dr. Nirbhay kumar \n";
    std::cout << "\nPlease enter your choice: ";
    std::cin >> a;
    int choice;
    while (true)
    {
        std::cout << "Enter a number: ";
        if (!(std::cin >> choice))
        {
            std::cin.clear();
            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
            std::cout << "Invalid input. Please enter a number.\n";
        }
        else
        {
            if (choice >= 1 && choice <= 4)
            {
                return choice;
                break;
            }
        }
        cout << ANSI_COLOR_RED << "Invalid choice!!! " << ANSI_COLOR_RESET;
        // exit(-1);
    }
}
// 9
int gastrointenstial_Diseases(void)
{
    int a;
    std::cout << endl;
    std::cout << "Doctor for Gastrointenstial Diseases : \n";
    std::cout << endl;
    std::cout << "1.Name : Dr. Piyush dixit \n";
    std::cout << "Specialization : Gastrointenstial Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : piyush@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "\n2.Name : Dr. Shweta Kumari \n";
    std::cout << "Specialization : Gastrointenstial Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : shwetakumari@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n3.Name : Dr. Manish kumar \n";
    std::cout << "Specialization : Gastrointenstial Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : manishkumar@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n4.Name : Dr. Nirbhay singh \n";
    std::cout << "Specialization : Gastrointenstial Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : nirbhaysingh@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "press 1 for Dr. Piyush Dixit \n press 2 for Dr. shweta kumari \n press 3 for Dr. Manish kumar \n press 4 for Dr. Nirbhay kumar \n";
    std::cout << "\nPlease enter your choice: ";
    int choice;
    while (true)
    {
        std::cout << "Enter a number: ";
        if (!(std::cin >> choice))
        {
            std::cin.clear();
            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
            std::cout << "Invalid input. Please enter a number.\n";
        }
        else
        {
            if (choice >= 1 && choice <= 4)
            {
                return choice;
                break;
            }
        }
        cout << ANSI_COLOR_RED << "Invalid choice!!! " << ANSI_COLOR_RESET;
        // exit(-1);
    }
}
// 10
int skin_Diseases(void)
{
    int a;
    std::cout << endl;
    std::cout << "Doctor for Skin Diseases : \n";
    std::cout << endl;
    std::cout << "1.Name : Dr. Piyush dixit \n";
    std::cout << "Specialization : Skin Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : piyush@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "\n2.Name : Dr. Shweta Kumari \n";
    std::cout << "Specialization : Skin Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : shwetakumari@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n3.Name : Dr. Manish kumar \n";
    std::cout << "Specialization : Skin Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : manishkumar@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n4.Name : Dr. Nirbhay singh \n";
    std::cout << "Specialization : Skin Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : nirbhaysingh@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "press 1 for Dr. Piyush Dixit \n press 2 for Dr. shweta kumari \n press 3 for Dr. Manish kumar \n press 4 for Dr. Nirbhay kumar \n";
    std::cout << "\nPlease enter your choice: ";
    int choice;
    while (true)
    {
        std::cout << "Enter a number: ";
        if (!(std::cin >> choice))
        {
            std::cin.clear();
            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
            std::cout << "Invalid input. Please enter a number.\n";
        }
        else
        {
            if (choice >= 1 && choice <= 4)
            {
                return choice;
                break;
            }
        }
        cout << ANSI_COLOR_RED << "Invalid choice!!! " << ANSI_COLOR_RESET;
        // exit(-1);
    }
}
// 11
int neurological_disorder(void)
{
    int a;
    std::cout << endl;
    std::cout << "Doctor for neurological disorder\n";
    std::cout << endl;
    std::cout << "1.Name : Dr. Piyush dixit \n";
    std::cout << "Specialization : Neurological Disorders \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : piyush@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << "\n2.Name : Dr. Shweta Kumari \n";
    std::cout << "Specialization : Neurological Disorders \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : shwetakumari@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << "\n3.Name : Dr. Manish kumar \n";
    std::cout << "Specialization : Neurological Disorders \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : manishkumar@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << "\n4.Name : Dr. Nirbhay singh \n";
    std::cout << "Specialization : Neurological Disorders \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : nirbhaysingh@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << "press 1 for Dr. Piyush Dixit \n 2 for Dr. shweta kumari \n press 3 for Dr. Manish kumar \n press 4 for Dr. Nirbhay kumar \n";
    std::cout << "\nPlease enter your choice: ";
    int choice;
    while (true)
    {
        std::cout << "Enter a number: ";
        if (!(std::cin >> choice))
        {
            std::cin.clear();
            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
            std::cout << "Invalid input. Please enter a number.\n";
        }
        else
        {
            if (choice >= 1 && choice <= 4)
            {
                return choice;
                break;
            }
        }
        cout << ANSI_COLOR_RED << "Invalid choice!!! " << ANSI_COLOR_RESET;
        // exit(-1);
    }
}
// 12
int doctors_of_Cardiovascular_Diseases(void)
{
    int a;
    std::cout << endl;
    std::cout << "Doctor for Cardiovascular Diseases : \n";
    std::cout << endl;
    std::cout << "1.Name : Dr. Piyush dixit \n";
    std::cout << "Specialization : Cardiovascular Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : piyush@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "\n2.Name : Dr. Shweta Kumari \n";
    std::cout << "Specialization : Cardiovascular Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : shwetakumari@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n3.Name : Dr. Manish kumar \n";
    std::cout << "Specialization : Cardiovascular Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : manishkumar@gmail.com \n";
    std::cout << "Qualifications : MD,PhD,10+year experience \n";
    std::cout << endl;
    std::cout << "\n4.Name : Dr. Nirbhay singh \n";
    std::cout << "Specialization : Cardiovascular Diseases \n";
    std::cout << "Contact Number : +91 96565 55555 \n";
    std::cout << "Email ID : nirbhaysingh@gmail.com \n";
    std::cout << "Qualifications : MBBS,MS,10+year experience \n";
    std::cout << endl;
    std::cout << "press 1 for Dr. Piyush Dixit \n press 2 for Dr. shweta kumari \n press 3 for Dr. Manish kumar \n press 4 for Dr. Nirbhay kumar \n";
    // std::cout << "\nPlease enter your choice: ";
    int choice;
    while (true)
    {
        std::cout << "\nPlease enter your choice : ";
        if (!(std::cin >> choice))
        {
            std::cin.clear();
            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
            std::cout << "Invalid input. Please enter a number.\n";
        }
        else
        {
            if (choice >= 1 && choice <= 4)
            {
                return choice;
                break;
            }
        }
        cout << ANSI_COLOR_RED << "Invalid choice!!! " << ANSI_COLOR_RESET;
        // exit(-1);
    }
}

// function to select the specialised doctor of related disease
int doctor(int a)
{
    switch (a)
    {
    case 1:
        infectious_diseases();
        break;
    case 2:
        chronic_disorder();
        break;
    case 3:
        genetic_Diseases();
        break;
    case 4:
        mental_health_Diseases();
        break;
    case 5:
        lifestyle_related_Diseases();
        break;
    case 6:
        rare_Diseases();
        break;
    case 7:
        autoimmune_Diseases();
        break;
    case 8:
        vector_borne_Diseases();
        break;
    case 9:
        gastrointenstial_Diseases();
        break;
    case 10:
        skin_Diseases();
        break;
    case 11:
        neurological_disorder();
        break;
    case 12:
        doctors_of_Cardiovascular_Diseases();
        break;
    default:
        std::cout << "Invalid Choice";
    }
}
char display(vector<int> &array)
{
    cout << "So you have selected mentioned disease and doctor for your patient :\n";
    if (array[0] == 1)
    {
        cout << "Infectious Disease \n";
        if (array[1] == 1)
            cout << "Dr. Piyush Dixit \n";
        else if (array[1] == 2)
            cout << "Dr. Shweta Kumari \n";
        else if (array[1] == 3)
            cout << "Dr. Manish Kumar \n";
        else if (array[1] == 4)
            cout << "Dr. Nirbhay Singh \n";
    }
    else if (array[0] == 2)
    {
        cout << "Chronic Diseases\n";
        if (array[1] == 1)
            cout << "Dr. Piyush Dixit \n";
        else if (array[1] == 2)
            cout << "Dr. Shweta Kumari \n";
        else if (array[1] == 3)
            cout << "Dr. Manish Kumar \n";
        else if (array[1] == 4)
            cout << "Dr. Nirbhay Singh \n";
    }
    else if (array[0] == 3)
    {
        cout << "Genetic Diseases\n";
        if (array[1] == 1)
            cout << "Dr. Piyush Dixit \n";
        else if (array[1] == 2)
            cout << "Dr. Shweta Kumari \n";
        else if (array[1] == 3)
            cout << "Dr. Manish Kumar \n";
        else if (array[1] == 4)
            cout << "Dr. Nirbhay Singh \n";
    }
    else if (array[0] == 4)
    {
        cout << "Mental health Diseases\n";
        if (array[1] == 1)
            cout << "Dr. Piyush Dixit \n";
        else if (array[1] == 2)
            cout << "Dr. Shweta Kumari \n";
        else if (array[1] == 3)
            cout << "Dr. Manish Kumar \n";
        else if (array[1] == 4)
            cout << "Dr. Nirbhay Singh \n";
    }
    else if (array[0] == 5)
    {
        cout << "Life style Related Diseases \n";
        if (array[1] == 1)
            cout << "Dr. Piyush Dixit \n";
        else if (array[1] == 2)
            cout << "Dr. Shweta Kumari \n";
        else if (array[1] == 3)
            cout << "Dr. Manish Kumar \n";
        else if (array[1] == 4)
            cout << "Dr. Nirbhay Singh \n";
    }
    else if (array[0] == 6)
    {
        cout << "Rare Diseases \n";
        if (array[1] == 1)
            cout << "Dr. Piyush Dixit \n";
        else if (array[1] == 2)
            cout << "Dr. Shweta Kumari \n";
        else if (array[1] == 3)
            cout << "Dr. Manish Kumar \n";
        else if (array[1] == 4)
            cout << "Dr. Nirbhay Singh \n";
    }
    else if (array[0] == 8)
    {
        cout << "Vector-Brone diseases \n";
        if (array[1] == 1)
            cout << "Dr. Piyush Dixit \n";
        else if (array[1] == 2)
            cout << "Dr. Shweta Kumari \n";
        else if (array[1] == 3)
            cout << "Dr. Manish Kumar \n";
        else if (array[1] == 4)
            cout << "Dr. Nirbhay Singh \n";
    }
    else if (array[0] == 9)
    {
        cout << "Gastrointenstial Diseases \n";
        if (array[1] == 1)
            cout << "Dr. Piyush Dixit \n";
        else if (array[1] == 2)
            cout << "Dr. Shweta Kumari \n";
        else if (array[1] == 3)
            cout << "Dr. Manish Kumar \n";
        else if (array[1] == 4)
            cout << "Dr. Nirbhay Singh \n";
    }
    else if (array[0] == 7)
    {
        cout << "Autoimmune Diseases \n";
        if (array[1] == 1)
            cout << "Dr. Piyush Dixit \n";
        else if (array[1] == 2)
            cout << "Dr. Shweta Kumari \n";
        else if (array[1] == 3)
            cout << "Dr. Manish Kumar \n";
        else if (array[1] == 4)
            cout << "Dr. Nirbhay Singh \n";
    }
    else if (array[0] == 10)
    {
        cout << "Skin diseases \n";
        if (array[1] == 1)
            cout << "Dr. Piyush Dixit \n";
        else if (array[1] == 2)
            cout << "Dr. Shweta Kumari \n";
        else if (array[1] == 3)
            cout << "Dr. Manish Kumar \n";
        else if (array[1] == 4)
            cout << "Dr. Nirbhay Singh \n";
    }
    else if (array[0] == 11)
    {
        cout << "Neurological Disorder \n";
        if (array[1] == 1)
            cout << "Dr. Piyush Dixit \n";
        else if (array[1] == 2)
            cout << "Dr. Shweta Kumari \n";
        else if (array[1] == 3)
            cout << "Dr. Manish Kumar \n";
        else if (array[1] == 4)
            cout << "Dr. Nirbhay Singh \n";
    }
    else if (array[0] == 12)
    {
        cout << "Cardiovascular Disease \n";
        if (array[1] == 1)
            cout << "Dr. Piyush Dixit \n";
        else if (array[1] == 2)
            cout << "Dr. Shweta Kumari \n";
        else if (array[1] == 3)
            cout << "Dr. Manish Kumar \n";
        else if (array[1] == 4)
            cout << "Dr. Nirbhay Singh \n";
    }
    char select;
    cout << "type y for proceed and press any other key except y for cancel registration : ";
    cin >> select;
    return select;
}

bool isValidDate(int day, int month, int year)
{
    if (year < 1000 || year > 9999)
        if (month < 1 || month > 12)
            return false;
    if (day < 1 || day > 31)
        return false;
    return true;
}
// registration function
int registration(vector<string> &name, int &age, string &DOB, char &sex)
{
    cout << "Please enter the name of the patient: ";
    string patientName;
    cin.ignore();
    getline(cin, patientName);
    name.push_back(patientName);

    cout << "Enter Age: ";
    //cin >> age;
    while (true)
    {
        if (std::cin >> age)
        {
            break;
        }
        else
        {
            std::cin.clear();
            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n'); // Discard invalid input
            std::cout << "Age cannot be in characters, Please enter an integer value ." << std::endl;
        }
    }
    std::string date;
    int day, month, year;
    char delim;
    while (true)
    {
        std::cout << "Enter Date Of Birth in dd/mm/yyyy format: ";
        std::getline(std::cin, date);
        std::stringstream ss(date);

        if (ss >> day >> delim >> month >> delim >> year && isValidDate(day, month, year))
        {
            // std::cout << "Day: " << day << ", Month: " << month << ", Year: " << year << std::endl;
            break;
        }
        else
        {
            std::cout << "Invalid format!!!!!. Please use dd/mm/yyyy format and ensure day, month, and year are numerical.\n";
        }
    }
    cout << "Select your gender : \n";
    cin >> sex;

    return 0;
}
int main()
{
    vector<int> list;
    string id1 = "11";
    string password1 = "11";
    string id;
    string passwrd;
    int disease;
    cout << "Enter your ID: ";
    cin >> id;
    cout << "Enter your Password: ";
    cin >> passwrd;
    int result = user_id_password(id, passwrd, id1, password1);
    if (result == 1)
    {
        cout << ANSI_COLOR_ROYAL_BLUE << "############## Welcome to the United medicity ################## \n"
             << ANSI_COLOR_RESET;
        disease = specification(1);
        list.insert(list.begin(), disease);
    }
    else if (result == -2)
    {
        cout << ANSI_COLOR_RED << "incorrect password !!!!! \n"
             << ANSI_COLOR_RESET;
    }
    int doctor_name = doctor(disease);
    list.insert(list.begin() + 1, doctor_name);
    list.resize(2);
    char select = display(list);
    vector<string> names;
    int age;
    string DOB;
    char gender;
    if (select == 'y')
    {
        registration(names, age, DOB, gender);
    }
    else
    {
        return 0;
    }
    std::cout << "Mr. " << names[0] << " you have completed your registration successfully \n";
    return 0;
}
