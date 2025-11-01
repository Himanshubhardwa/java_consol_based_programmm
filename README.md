package first;

import java.util.Scanner;
import java.util.ArrayList;

class Details
{
    String Name;
    int rollNumber;
    String Department;
    String Grade;

    Details(String Name, int rollNumber, String Department,String Grade)
    {
        this.Name=Name;
        this.rollNumber=rollNumber;
        this.Department=Department;
        this.Grade=Grade;
    }

    void display()
    {
        System.out.println("Name| "+ Name +"| Roll Numbre |"+ rollNumber +"| Department "+ Department +"| Grade "+Grade);
    }
}


class A
{
    public static void main(String[] args)
    {
//        Details dt =null;
        Scanner sc = new Scanner(System.in);
        ArrayList<Details> student = new ArrayList<>();
        while(true)
        {
            System.out.println("=======================================");
            System.out.println("Student Information Sysytem ");
            System.out.println("=======================================");
            System.out.println("choose option");
            System.out.println(" 1. Insert Details");
            System.out.println(" 2. View Details");
            System.out.println(" 3. Exit Loop");
            System.out.println("Enter the choice (1,2,3)");
            int choice = sc.nextInt();
            if (choice == 1)
            {
                System.out.println("Enter the Name :");
                String Name = sc.next();
                System.out.println("Enter the Roll Number :");
                int rollNumber = sc.nextInt();
                System.out.println("Enter the Department :");
                String Department = sc.next();
                System.out.println("Enter the Grade :");
                String Grade = sc.next();

//               student.add(new Details(Name,rollNumber,Department,Grade));
                Details dt = new Details(Name,rollNumber,Department,Grade);
                student.add(dt);
                System.out.println("Successful Added Details :");
            }
            else if (choice == 2)
            {
                if (student.isEmpty()) {
                    System.out.println("Not Any Data :");
                    System.out.println("Please Enter the entry ");
                } else {
                    for (Details d:student)
                    {
                        d.display();
                    }
                }
            }
            else if (choice == 3)
            {
                System.out.println("Exiting the information Details! ");
                break;
            }
            else
            {
                System.out.println("! Invalid Choice !");
            }
        }
        sc.close();
    }
}
