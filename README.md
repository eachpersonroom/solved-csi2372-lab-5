Download Link: https://assignmentchef.com/product/solved-csi2372-lab-5
<br>



This lab is about Classes and Objects in C++.




<strong>Exercise 1 of 6)</strong> Define a class named <sub>Money</sub> that stores a monetary amount.  The class should have two private integer variables, one to store the number of dollars and another to store the number of cents.   Add accessor and mutator functions to read and set both member variables.   Add another function that returns the monetary amount as a double.  Write a program that tests all of your functions with at least two different <sub>Money</sub> objects.




<strong>Exercise 2 of 6)</strong> Do the Exercise 1, the definition of a <sub>Money</sub> class, except create a default constructor that sets the monetary amount to 0 dollars and 0 cents, and create a second constructor with input parameters for the amount of the dollars and cents variables.  Modify your test code to invoke the constructors.










<strong>Some Key Points: </strong>

<strong><u>Function </u></strong><strong><u>Inline</u></strong><strong><u>:</u></strong>

Placing the keyword <strong>inline</strong> before the declaration of a function is a hint to the compiler to put the body of the function in the code stream at the place of the call (with arguments appropriately substituted for the parameters). The compiler may or may not do this, and some compilers have strong restrictions on what function bodies will be placed inline. In order to generate an executable of reasonable size, it is, therefore in practice, used for “short” functions in terms of the number of instructions in functions.

The <strong>inline</strong> keyword has the advantage of speeding up a program if it regularly calls the inline function. It makes it possible to substantially condense the code, in particular for the accessors of a class. A class accessor is typically a member function which gets the values of class member.

The <strong>inline</strong> allows to declare and implement functions directly in a header (.h)  <strong><u>Function </u></strong><strong><u>const</u></strong><strong><u>:</u></strong>

In C ++, <strong>const</strong> at the <em>end</em> of the declaration of a function means that the function is not supposed to change the values of the class member variables.




<strong><u>Constructor </u></strong><strong><u>Definitions:</u></strong><strong>  </strong>

A constructor is a member function <strong>having the same name as the class name</strong>. The purpose of a class <strong>constructor</strong> is automatic allocation and initialization of resources involved in the definition of class objects. Constructors are called automatically at the definition of objects. Special declarator syntax for constructors uses the class name followed by a parameter list but no return type.




<strong><u>Constructor initialization section:</u> </strong>

The implementation of the constructor can have an initialization section:

classname:: classname (list of arguments): <strong>a(0), b(1)</strong>

{ //empty or implementation }

In the literature, this feature is sometimes called a <em>member initializer list</em>.  The purpose of a member initializer list is to initialize the class data members.   Only constructors may have member initializer lists.











































<strong>Exercise 3 of 6)</strong> Define a class called <sub>StartTime</sub> with the following attributes and methods




<strong>char d_hour;  char d_minutes;  </strong>

<strong>inline void get(char&amp; _hour, char&amp; _minutes) const;  inline void set(char _hour, char _minutes);  </strong>




<strong>inline StartTime(char _hour, char _minutes);  </strong>

<strong>inline void print() const;  </strong>




This class will be placed in the starttime.h file.

Header files are a good place to define classes.




<strong>Exercise 4 of 6)</strong> Define the class CourseActivity containing a pointer to a StartTime, a duration in minutes, and a location. These attributes must be private. A public method for changing the start time, a display method, and a full constructor are also required. The signatures of these methods and the type of the attributes are:

<table width="618">

 <tbody>

  <tr>

   <td width="618"><strong>StartTime* d_start;  double duration;  std::string location;  </strong><strong>CourseActivity( const StartTime* _start, double _duration, const std::string _location );  void reschedule( StartTime* _newStart );  void print() const;  </strong></td>

  </tr>

 </tbody>

</table>




This class will be placed in the activity.h file.

Define three public subclasses of CourseActivity (in the same cpp file activity.h). These classes are: <strong>Lecture</strong>, <strong>Laboratory</strong> and <strong>Tutorial</strong>. Each of these classes should define a method <strong>void print()</strong>; and must include a std::string to contain a <em><u>topic</u></em>, an <em><u>assignment</u></em>, and an <em><u>exercise</u></em>. The class definition must be in the activity.h file, while the methods will be defined in activity.cpp

<strong>Exercise 5 of 6)</strong>  Add the following constructors to the classes defined in exercise 4.




<table width="726">

 <tbody>

  <tr>

   <td width="726"><strong>Lecture( const StartTime* _start, double _duration, const string location,            const string&amp; _topic );  </strong><strong> </strong><strong>Lecture( const CourseActivity&amp; _oActivity, const string&amp; topic );   </strong><strong> </strong><strong>Laboratory( const StartTime&amp; _start, double _duration, const string location, const string&amp; _assignment );  </strong><strong> </strong><strong> </strong><strong>Tutorial( const StartTime&amp; _start, double _duration, const string location,                const string&amp; _exercise ); </strong><strong> </strong><strong> </strong><strong> </strong></td>

  </tr>

 </tbody>

</table>







<strong>  Exercise 6 of 6)</strong> Define a <em>main()</em> function in <strong>lab5.cpp</strong>. Create three instances of

StartTime for 11:30, 13:00 and 16:00. With these, create a <strong><u>Lecture</u></strong>, a

<strong><u>Laboratory</u></strong> and a <strong><u>Tutorial</u></strong> with a duration of 90 minutes. Then display each of these activities.

Construct two additional <em>Lecture</em> instances from <em>Tutorial</em> and <em>Laboratory</em> with

the constructor <strong>Lecture</strong>(const CourseActivity &amp; _oActivity, const std::string &amp; topic); Display these five activities.  Then change the time of two conflicting lectures for 19:00 and 7:00, respectively. Display the activities again.