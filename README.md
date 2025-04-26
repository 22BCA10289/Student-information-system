import java.util.ArrayList;
import java.util.Scanner;

class Student {
    String name;
    int id;
    String course;

    Student(int id, String name, String course) {
        this.id = id;
        this.name = name;
        this.course = course;
    }

    void display() {
        System.out.println("ID: " + id + ", Name: " + name + ", Course: " + course);
    }
}

public class StudentInfoSystem {
    public static void main(String[] args) {
        ArrayList<Student> students = new ArrayList<>();
        Scanner sc = new Scanner(System.in);
        int choice;

        do {
            System.out.println("\n--- Student Information System ---");
            System.out.println("1. Add Student");
            System.out.println("2. Display All Students");
            System.out.println("3. Search by ID");
            System.out.println("4. Exit");
            System.out.print("Enter choice: ");
            choice = sc.nextInt();

            switch (choice) {
                case 1:
                    System.out.print("Enter ID: ");
                    int id = sc.nextInt();
                    sc.nextLine(); // consume newline
                    System.out.print("Enter Name: ");
                    String name = sc.nextLine();
                    System.out.print("Enter Course: ");
                    String course = sc.nextLine();
                    students.add(new Student(id, name, course));
                    System.out.println("Student added successfully.");
                    break;

                case 2:
                    System.out.println("\nStudent List:");
                    for (Student s : students) {
                        s.display();
                    }
                    break;

                case 3:
                    System.out.print("Enter ID to search: ");
                    int searchId = sc.nextInt();
                    boolean found = false;
                    for (Student s : students) {
                        if (s.id == searchId) {
                            s.display();
                            found = true;
                            break;
                        }
                    }
                    if (!found) {
                        System.out.println("Student not found.");
                    }
                    break;

                case 4:
                    System.out.println("Exiting...");
                    break;

                default:
                    System.out.println("Invalid choice.");
            }
        } while (choice != 4);

        sc.close();
    }
}. 



Output 
--- Student Information System ---
1. Add Student
2. Display All Students
3. Search by ID
4. Exit
Enter choice: 1
Enter ID: 101
Enter Name: Alice
Enter Course: Computer Science
Student added successfully.

--- Student Information System ---
1. Add Student
2. Display All Students
3. Search by ID
4. Exit
Enter choice: 1
Enter ID: 102
Enter Name: Bob
Enter Course: Mathematics
Student added successfully.

--- Student Information System ---
1. Add Student
2. Display All Students
3. Search by ID
4. Exit
Enter choice: 2

Student List:
ID: 101, Name: Alice, Course: Computer Science
ID: 102, Name: Bob, Course: Mathematics

--- Student Information System ---
1. Add Student
2. Display All Students
3. Search by ID
4. Exit
Enter choice: 3
Enter ID to search: 102
ID: 102, Name: Bob, Course: Mathematics

--- Student Information System ---
1. Add Student
2. Display All Students
3. Search by ID
4. Exit
Enter choice: 4
Exiting...

