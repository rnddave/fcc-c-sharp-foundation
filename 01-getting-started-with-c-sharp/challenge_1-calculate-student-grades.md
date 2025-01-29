We start with: 

Sophia: 93, 87, 98, 95, 100

Nicolas: 80, 83, 82, 88, 85

Zahirah:   84, 96, 73, 85, 79

Jeong:  90, 92, 98, 100, 97

We want it to look like: 

```
Student     Grade
Sophia      94.6  A
Nicolas     83.6  B
Zahirah     83.4  B
Jeong       95.4  A
```

Let's begin... 


```csharp

// First plan was to creat single dimension array for each student. 
double[] sophia = new double[5] {93,87,98,95,100};
double[] nicholas = new double[5] {80,83,82,88,85};
double[] zamirah = new double[5] {84,96,73,85,79};
double[] jeong = new double[5] {90,92,98,100,97};

// Console.WriteLine($"Sophia = {sophia.Average()}"); 
// testing this works, indeed it does
// However, I think I am going to have to make multiple console statements to present the scores, this seems inefficent as they will mostly say the same thing. 

// ------------------------

// Second plan was to use a multi-dimension array for all scores,
// then have an array for Students, and an array for Grades

double[,] studentsScore = new double[4,5]{{93,87,98,95,100},{80,83,82,88,85},{84,96,73,85,79},{90,92,98,100,97}};
string[] students = new string[4]{"Sophia", "Nicholas", "Zamirah", "Jeong"};
char[] grade = new char[3] {'A', 'B', 'C'};

// Now to start presenting the data to the console:
string presentationHead = "Student\t\tGrade";
Console.WriteLine(presentationHead); // Header

// Plan 2.a was to do a foreach on Students, and then a foreach on scores. H
// owever I could not figure out how to access the data in the inner arrays.
foreach (string student in students)
{
    Console.Write($"{student}\t\t");
    // 2.a - because I could not figure out the inner array, I had to go for a series of nested if's 
    // this looks pretty shit and is highly inefficient, I should revisit this.
    if (student == "Sophia")
    {
        Console.Write($"{sophia.Average()}\t");
        if (sophia.Average() > 89)
        {
            Console.Write($"{grade[0]}\n");
        }
        else if (sophia.Average() > 79)
        {
            Console.Write($"{grade[1]}\n");
        }
    }
    else if (student == "Nicholas")
    {
        Console.Write($"{nicholas.Average()}\t");
        if (nicholas.Average() > 89)
        {
            Console.Write($"{grade[0]}\n");
        }
        else if (nicholas.Average() > 79)
        {
            Console.Write($"{grade[1]}\n");
        }
    }
    else if (student == "Zamirah")
    {
        Console.Write($"{zamirah.Average()}\t");
        if (zamirah.Average() > 89)
        {
            Console.Write($"{grade[0]}\n");
        }
        else if (zamirah.Average() > 79)
        {
            Console.Write($"{grade[1]}\n");
        }
    }
    else if (student == "Jeong")
    {
        Console.Write($"{jeong.Average()}\t");
        if (jeong.Average() > 89)
        {
            Console.Write($"{grade[0]}\n");
        }
        else if (jeong.Average() > 79)
        {
            Console.Write($"{grade[1]}\n");
        }
    }
}
```

## Output: 

```
Student		Grade
Sophia		94.6	A
Nicholas		83.6	B
Zamirah		83.4	B
Jeong		95.4	A
```

It's too rigid, will not scale, also I did not figure out why the tab sizes are different for Nicholas, indeed it is a longer word, but if I increases tabs, the offset remains. This does not meet my expectation of tabs. 

**I realised I spelled Nicolas incorrectly - this sort of fixes the tab issue...**

```
Student		Grade

Sophia:		94.6	A
Nicolas:	83.6	B
Zahirah:	83.4	B
Jeong:		95.4	A
```

---

## Proposed solution from Microsoft: 

```csharp
int currentAssignments = 5;

int sophia1 = 93;
int sophia2 = 87;
int sophia3 = 98;
int sophia4 = 95;
int sophia5 = 100;

int nicolas1 = 80;
int nicolas2 = 83;
int nicolas3 = 82;
int nicolas4 = 88;
int nicolas5 = 85;

int zahirah1 = 84;
int zahirah2 = 96;
int zahirah3 = 73;
int zahirah4 = 85;
int zahirah5 = 79;

int jeong1 = 90;
int jeong2 = 92;
int jeong3 = 98;
int jeong4 = 100;
int jeong5 = 97;

int sophiaSum = sophia1 + sophia2 + sophia3 + sophia4 + sophia5;
int nicolasSum = nicolas1 + nicolas2 + nicolas3 + nicolas4 + nicolas5;
int zahirahSum = zahirah1 + zahirah2 + zahirah3 + zahirah4 + zahirah5;
int jeongSum = jeong1 + jeong2 + jeong3 + jeong4 + jeong5;

decimal sophiaScore = (decimal) sophiaSum / currentAssignments;
decimal nicolasScore = (decimal) nicolasSum / currentAssignments;
decimal zahirahScore = (decimal) zahirahSum / currentAssignments;
decimal jeongScore = (decimal) jeongSum / currentAssignments;

Console.WriteLine("Student\t\tGrade\n");
Console.WriteLine("Sophia:\t\t" + sophiaScore + "\tA");
Console.WriteLine("Nicolas:\t" + nicolasScore + "\tB");
Console.WriteLine("Zahirah:\t" + zahirahScore + "\tB");
Console.WriteLine("Jeong:\t\t" + jeongScore + "\tA");
```

output works. annoyingly... 