# Oasis-infobyte repo-1
I have successfully completed Task 2: Student Grade Calculator as part of my internship project. 
import java.util.Scanner;

public class StudentGradeCalculator {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int subjects = 5;
        int total = 0;
        double percentage;
        char grade;

        System.out.println("===== STUDENT GRADE CALCULATOR =====");

        for (int i = 1; i <= subjects; i++) {
            System.out.print("Enter marks for Subject " + i + " (0-100): ");
            int marks = sc.nextInt();

            while (marks < 0 || marks > 100) {
                System.out.print("Invalid marks! Enter marks between 0 and 100: ");
                marks = sc.nextInt();
            }

            total += marks;
        }

        percentage = (double) total / subjects;

        if (percentage >= 90)
            grade = 'A';
        else if (percentage >= 80)
            grade = 'B';
        else if (percentage >= 70)
            grade = 'C';
        else if (percentage >= 60)
            grade = 'D';
        else
            grade = 'F';

        System.out.println("\n===== RESULT =====");
        System.out.println("Total Marks      : " + total + "/" + (subjects * 100));
        System.out.printf("Percentage       : %.2f%%\n", percentage);
        System.out.println("Grade            : " + grade);

        sc.close();
    }
}