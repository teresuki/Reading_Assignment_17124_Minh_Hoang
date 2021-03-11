ID: 17124

_// Last update: Finished chapter 15._

**CHAPTER 10: ARRAYS**

Arrays are sequences of objects of the _ **same type,** _ _for example we can make an array that can store integers:_

_int main()
 {
 int arr[10];
 }_

The above array can store 10 variables of integer type, and elements are adjacent to each other (or their addresses are adjacent to each other.)

To initialize an array, we can use the **initialization list {}**

_int main()
 {
 int arr[4] = {32, -12, 0, 4};
 }_

Elements are put in the curly brackets **{ },** and each elements are separated by the comma &quot; **,**&quot;.

The order of the elements is from the left to the right: 32 is the first element, -12 is the second element, 0 is the third element and 4 is the last element.

However, it should be noted that array indexing **starts from 0, not 1.** So when you want to use the first element of **arr** , type **arr[0].**

- If the length of the array is **N** , then the index starts **from 0 to N-1.**

We can insert elements to the array from user input by using loop such as **for loop**

_int main(){_

_int arr[10]; // Create an array of integers that has the length of 10_

_for(int i=0; i\&lt;10; ++i)_

_cin \&gt;\&gt; arr[i];_

_}_

**CHAPTER 11: POINTERS**

Every objects are store in memory, so each objects has its own **value** and **address**. When talking about how to store the **address** of that object, we use a special variable called **pointers.** So a pointer is a type that can hold the address of a particular object.

To create a pointer, we use the &quot;\*&quot; mark before the pointer&#39;s name.

_int main()
 {
 int \*ptr;
 }_

Above is a pointer that can hold an **integer&#39;s address**. Conversely, we can make a pointer that can hold **char&#39;s address.**

_int main()
 {
 char \*ptr;
 }_

To make a pointer points to a specific variable, we use the &quot; **&amp;**&quot; operator to get the variable&#39;s address.

int main()
_{
 int x = 123;
 int\* p = &amp;x;
 }_

We can also initialize our pointer to let it points to **nowhere** , or **nullptr**.

_int main()
 {
 char\* p = nullptr;
 }_

p is now called a _ **null pointer** _.

To access the value of an object which is being pointed to by a pointer, we can use the &quot; **\***&quot; operator.

_#include \&lt;iostream\&gt;_

_using namespace std;_

_int main(){_

_int a = 5;_

_int \*ptr = &amp;a;_

_cout \&lt;\&lt; &quot;The value of a is:&quot; \&lt;\&lt; \*ptr; // Prints out 5_

_}_

We can also change the value of the object through pointer.

#include \&lt;iostream\&gt;

using namespace std;
 int main()
 {
 int x = 123;
 int\* p = &amp;x;
 \*p = 456; // change the value of pointed-to object
 cout \&lt;\&lt; &quot;The value of x is: &quot; \&lt;\&lt; x; // Prints out 456
 }

**CHAPTER 12: REFERENCES**

A reference type is an alias to an existing object in memory, and reference must be initialized. For example:

_int main()
 {
 int x = 65;
 int&amp; y = x;
 }_

Now we have two different names that refer to the same integer. If we assign or change value one of them, the value of both will be changed. In other words, they are using two different names for the same value.

_int main()
 {
 int x = 123;
 int&amp; y = x;
 x = 456;
 // both x and y now hold the value of 456
 y = 789;
 // both x and y now hold the value of 789
 }_

Note: The &quot; **\***&quot; operator is used when creating a pointer:

int \*ptr;

**But** , it is also used to refer to the value of the object being pointed by a pointer.

\*ptr = 350;

The &quot; **&amp;**&quot; operator is used to get the address of an object;

ptr = &amp;myVar;

**But** , it is also used as initializing a reference.

int &amp;y = x;

- It is important to look at the **context** to see what role does these operators play.

**CHAPTER 13: INTRODUCTION TO STRINGS.**

C++ library offers a compound type called string or rather std::string as it is part of the std namespace. We use it for storing and manipulating string of texts.

**Defining a string:**

To use the std::string type, we need to include the \&lt;string\&gt; header in our program.

_#include \&lt;iostream\&gt;
 #include \&lt;string\&gt;
 int main()
 {
 std::string s = &quot;Hello World.&quot;;
 std::cout \&lt;\&lt; s;
 }_

**Concatenating strings:**

We can add a string literal to our string using the compound operator &quot; **+=**&quot;

_#include \&lt;iostream\&gt;
 #include \&lt;string\&gt;
 int main()
 {
 std::string s = &quot;Hello &quot;;
 s += &quot;World.&quot;;
 std::cout \&lt;\&lt; s;
 }_

We can also connect 2 (or more) strings together with &quot; **+**&quot;

_#include \&lt;iostream\&gt;
 #include \&lt;string\&gt;
 int main()
 {
 std::string s1 = &quot;Hello &quot;;
 std::string s2 = &quot;World.&quot;;
 std::string s3 = s1 + s2;
 std::cout \&lt;\&lt; s3; // Prints out Hello World.
 }_

**Accessing Characters:**

Individual characters of a string can be accessed through a **subscript operator []** or via a
 member function _**.at(index)**_ **.** The index starts at 0. Example:
_#include \&lt;iostream\&gt;
 #include \&lt;string\&gt;
 int main()
 {
 std::string s = &quot;Hello World.&quot;;_

| _char c1 = s[0];
 char c2 = s.at(0);
 char c3 = s[6];
 char c4 = s.at(6);_ | _// &#39;H&#39;
 // &#39;H&#39;;
 // &#39;W&#39;
 // &#39;W&#39;;_ |
| --- | --- |

_std::cout \&lt;\&lt; &quot;First character: &quot; \&lt;\&lt; c1 \&lt;\&lt; &quot;, sixth character: &quot; \&lt;\&lt; c3;
 }_

**Comparing Strings:**

A string can be compared to string literals and other strings using the equality &quot; **==**&quot; operator. Comparing a string to a string literal:
 _#include \&lt;iostream\&gt;
 #include \&lt;string\&gt;
 int main()
 {
 std::string s1 = &quot;Hello&quot;;
 if (s1 == &quot;Hello&quot;)
 {
 std::cout \&lt;\&lt; &quot;The string is equal to \&quot;Hello\&quot;&quot;;
 }
 }_

_Comparing a string to another string is done using the equality operator &quot; __**==**__&quot;_
 _#include \&lt;iostream\&gt;
 #include \&lt;string\&gt;
 int main()
 {
 std::string s1 = &quot;Hello&quot;;
 std::string s2 = &quot;World.&quot;;
 if (s1 == s2)
 {
 std::cout \&lt;\&lt; &quot;The strings are equal.&quot;;
 }
 else
 {
 std::cout \&lt;\&lt; &quot;The strings are not equal.&quot;;
 }
 }_

_ **String input:** _

Preferred way of accepting a string from the standard input is via the_std::getline_
 function which takes std::cin and our string as parameters:
_#include \&lt;iostream\&gt;
 #include \&lt;string\&gt;
 int main()
 {
 std::string s;
 std::cout \&lt;\&lt; &quot;Please enter a string: &quot;;
 std::getline(std::cin, s);
 std::cout \&lt;\&lt; &quot;You entered: &quot; \&lt;\&lt; s;
 }_

We use the _std::getline_ because our string can contain white spaces. And if we
 used the _std::cin_ function alone, it would accept only a part of the string.

**A pointer to a string:**

A string has a member function .c\_str() which returns a pointer to its first element.

#include \&lt;iostream\&gt;
 #include \&lt;string\&gt;
 int main()
 {
 std::string s = &quot;Hello World.&quot;;
 std::cout \&lt;\&lt; s.c\_str();
 }

**Substrings:**

To create a substring from a string, we use the _.substr()_ member function.The signature of the function is: _.substring(starting\_position, length)_ _._Example:

#include \&lt;iostream\&gt;
 #include \&lt;string\&gt;
 int main()
 {
 std::string s = &quot;Hello World.&quot;;
 std::string mysubstring = s.substr(6, 5);
 std::cout \&lt;\&lt; &quot;The substring value is: &quot; \&lt;\&lt; mysubstring; // Prints out World
 }

**Finding a substring:**

To find a substring in a string, we use the _.find()_member function.If the substring is found, the function returns the position of the first found substring. If the substring is not found, the function returns a value that is _std::string::npos_.

To find a substring &quot;Hello&quot; inside the &quot;This is a Hello World string&quot; string, we write:
#include \&lt;iostream\&gt;
 #include \&lt;string\&gt;
 int main()
 {
 std::string s = &quot;This is a Hello World string.&quot;;
 std::string stringtofind = &quot;Hello&quot;;
 std::string::size\_type found = s.find(stringtofind);
 if (found != std::string::npos)
 {
 std::cout \&lt;\&lt; &quot;Substring found at position: &quot; \&lt;\&lt; found;
 }
 else
 {
 std::cout \&lt;\&lt; &quot;The substring is not found.&quot;;
 }
 }

**CHAPTER 14: AUTOMATIC TYPE DEDUCTION**

We can automatically deduce the type of an object using the **auto** specifier. The **auto**
specifier deduces the type of an object based on the object&#39;s **initializer type.**
Example:

| auto c = &#39;a&#39;; | // char type |
| --- | --- |
| This example deduces c to be of type char as the initializer &#39;a&#39; is of type char.
 Similarly, we can have: |
 |
| auto x = 123; | // int type |

Here, the compiler deduces the x to be of type int because an integer literal 123 is of type int.
 The type can also be deduced based on the type of expression:
 auto d = 123.456 / 789.10; // double

This example deduces d to be of type double as the type of the entire 123.456 / 789.10 expression is double.
 We can use auto as part of the reference type:
 int main()
 {
 int x = 123;
 auto&amp; y = x; // y is of int&amp; type
 }

or as part of the constant type:
 int main()
 {
 const auto x = 123; // x is of const int type
 }

We use the _auto_ specifier when the type (name) is hard to deduce manually or cumbersome to type due to the length.

**CHAPTER 15: EXERCISES**

**15.1: Array Definition:** Write a program that defines and initializes an array of five doubles. Change and print the values of the first and last array elements.

#include \&lt;iostream\&gt;
 int main()
 {
 double array[5] = { 3.14, -5.2, 0.05, 2.22, 50.0201 };
 arr[0] = 4.64;
 arr[4] = 2.17;
 std::cout \&lt;\&lt; &quot;The first array element is: &quot; \&lt;\&lt; arr[0] \&lt;\&lt; &#39;\n&#39;;
 std::cout \&lt;\&lt; &quot;The last array element is: &quot; \&lt;\&lt; arr[4] \&lt;\&lt; &#39;\n&#39;;
 }

**15.2:Pointer to an Object:** Write a program that defines an object of type double. Define a pointer that points to that object. Print the value of the pointed-to object by dereferencing a pointer.

#include \&lt;iostream\&gt;
 int main()
 {
 double myDouble = -5.12;
 double \*ptr = &amp;myDouble;
 std::cout \&lt;\&lt; &quot;The value of the pointed-to object is: &quot; \&lt;\&lt; \*p;
 }

**15.3:Reference Type:** Write a program that defines an object of type double called mydouble. Define an object of reference type called myreference and initialize it with mydouble. Change the value of myreference. Print the object value using both the reference and the original variable. Change the value of mydouble. Print the value of both objects.

#include \&lt;iostream\&gt;
 int main()
 {
 double mydouble = 3.14;
 double&amp; myreference = mydouble;
 myreference = 1.43;
 std::cout \&lt;\&lt; &quot;The values are: &quot; \&lt;\&lt; mydouble \&lt;\&lt; &quot; and &quot; \&lt;\&lt; myreference
 \&lt;\&lt; &#39;\n&#39;;
 mydouble = 7.35;
 std::cout \&lt;\&lt; &quot;The values are: &quot; \&lt;\&lt; mydouble \&lt;\&lt; &quot; and &quot; \&lt;\&lt; myreference \&lt;\&lt; &#39;\n&#39;;
 }

**15.4: Strings:** Write a program that defines two strings. Join them together and assign the result to a third-string. Print out the value of the resulting string.

#include \&lt;iostream\&gt;
 #include \&lt;string\&gt;
 int main()
 {
 std::string str1 = &quot;Miles&quot;;
 std::string str2 = &quot; Prower&quot;;
 std::string str3 = str1 + str2;
 std::cout \&lt;\&lt; &quot;The resulting string after joining is: &quot; \&lt;\&lt; str3;
 }

**15.5: Strings from standard input:**

Write a program that accepts the first and the last name from the standard input using
 the std::getline function. Store the input in a single string called fullname. Print out
 the string.

#include \&lt;iostream\&gt;
 #include \&lt;string\&gt;
 int main()
 {
 std::string fullname;
 std::cout \&lt;\&lt; &quot;Please enter your first name and your last name: &quot;;
 std::getline(std::cin, fullname);
 std::cout \&lt;\&lt; &quot;Your full name is: &quot; \&lt;\&lt; fullname;
 }

**15.6:Creating a substring:** Write a program that creates two substrings from the main string. The main string is made up of first and last names and is equal to &quot;John Doe.&quot; The first substring is the first name. The second substring is the last name. Print the main string and two substrings afterward.

#include \&lt;iostream\&gt;
 #include \&lt;string\&gt;
 int main()
 {
 std::string fullname = &quot;John Doe&quot;;
 std::string firstname = fullname.substr(0, 4);
 std::string lastname = fullname.substr(5, 3);
 std::cout \&lt;\&lt; &quot;The full name is: &quot; \&lt;\&lt; fullname \&lt;\&lt; &#39;\n&#39;;
 std::cout \&lt;\&lt; &quot;The first name is: &quot; \&lt;\&lt; firstname \&lt;\&lt; &#39;\n&#39;;
 std::cout \&lt;\&lt; &quot;The last name is: &quot; \&lt;\&lt; lastname \&lt;\&lt; &#39;\n&#39;;
 }

**15.7:Finding a single character:**

Write a program that defines the main string with a value of &quot;Hello C++ World.&quot; And checks if a single character &#39;C&#39; is found in the main string.

#include \&lt;iostream\&gt;
 #include \&lt;string\&gt;
 int main()
 {
 std::string s = &quot;Hello C++ World.&quot;;
 char c = &#39;C&#39;;
 auto characterIsFound = s.find(c);
 if (characterIsFound != std::string::npos)
 {
 std::cout \&lt;\&lt; &quot;Character found at position: &quot; \&lt;\&lt; characterIsFound \&lt;\&lt;&#39;\n&#39;;
 }
 else
 {
 std::cout \&lt;\&lt; &quot;Character was not found.&quot; \&lt;\&lt; &#39;\n&#39;;
 }
 }

**15.8:Finding a substring:**

Write a program that defines the main string with a value of &quot;Hello C++ World.&quot; and
 checks if a substring &quot;C++&quot; is found in the main string.

#include \&lt;iostream\&gt;
 #include \&lt;string\&gt;
 int main()
 {
 std::string s = &quot;Hello C++ World.&quot;;
 std::string mysubstring = &quot;C++&quot;;
 auto mysubstringfound = s.find(mysubstring);
 if (mysubstringfound != std::string::npos)
 {
 std::cout \&lt;\&lt; &quot;Substring found at position: &quot; \&lt;\&lt; mysubstringfound \&lt;\&lt;&#39;\n&#39;;
 }
 else
 {
 std::cout \&lt;\&lt; &quot;Substring was not found.&quot; \&lt;\&lt; &#39;\n&#39;;
 }
 }

**15.9:Automatic Type Deduction:**

Write a program that automatically deduces the type for char, int, and double objects
 based on the initializer used. Print out the values afterward.
#include \&lt;iostream\&gt;
 int main()
 {
 auto c = &#39;a&#39;;
 auto x = 123;
 auto d = 3.14;
 std::cout \&lt;\&lt; &quot;The type of c is deduced as char, the value is: &quot;\&lt;\&lt; c \&lt;\&lt;&#39;\n&#39;;
 std::cout \&lt;\&lt; &quot;The type of x is deduced as int, the value is: &quot;\&lt;\&lt; x \&lt;\&lt;&#39;\n&#39;;
 std::cout \&lt;\&lt; &quot;The type of d is deduced as double, the value is: &quot;\&lt;\&lt; d \&lt;\&lt;&#39;\n&#39;;
 }