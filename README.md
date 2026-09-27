# Nexura_Recrument02
import java.util.Scanner;
public class Nexura_Recrument02 {
static class Student {
    String name;
     int[] marks;
 int total;
   float average;
  int highest;
 int lowest;
 boolean isPassed;
 static final int PASSING_MARK = 33;
public void inputMarks() {
        Scanner sc = new Scanner(System.in);
 System.out.print("Enter student name: ");
        this.name = sc.nextLine();
 System.out.print("Enter the number of subjects: ");
        int subs = sc.nextInt();
        this.marks = new int[subs];
 for (int i = 0; i < marks.length; i++) {
            System.out.print("Enter the " + (i + 1) + "th subject mark: ");
            marks[i] = sc.nextInt();
        }

 //  total
        this.total = 0;
        for (int mark : marks) {
            this.total += mark;
        }
 // average
        this.average = (float) this.total / marks.length;

 //  highest
        this.highest = Integer.MIN_VALUE;
        for (int mark : marks) {
            if (mark > this.highest) {
                this.highest = mark;
            }
        }
  // lowest
        this.lowest = Integer.MAX_VALUE;
        for (int mark : marks) {
            if (mark < this.lowest) {
                this.lowest = mark;
            }
        }

 this.isPassed = true;
    for (int mark : marks) {
            if (mark < 33) {
                this.isPassed = false;
                break;
            }
        }
        if (this.average < PASSING_MARK) {
            this.isPassed = false;
        }
    }


public String getName() { return name; }
    public int[] getMarks() { return marks; }
    public int getTotal() { return total; }
    public float getAverage() { return average; }
    public int getHighest() { return highest; }
    public int getLowest() { return lowest; }
    public boolean getIsPassed() { return isPassed; }
}

 public static void main(String[] args) {
Scanner sc = new Scanner(System.in);
        System.out.println("Enter numbers of students : ");
int student = sc.nextInt();

 int pass = 0;
int fail = 0;

for(int i=0;i<student;i++) {
    Student Si = new Student();
    Si.inputMarks();
    System.out.println("S1 Average: " + Si.getAverage());
    System.out.println("S1 Total:   " + Si.getTotal());
    System.out.println("S1 Highest: " + Si.getHighest());
    System.out.println("S1 Lowest:  " + Si.getLowest());
    if(i<student-1) {
        System.out.println("Enter other student details : ");
    }
    if(Si.getLowest()<33) fail++;
    else pass++;
              }
 System.out.println("Total passed students is "+pass+" and fail is "+fail);
         }
}
