Download Link: https://assignmentchef.com/product/solved-project-1-the-art-of-the-cart
<br>



<p style="text-align: center;"><img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2020/09/318.png?w=980&amp;ssl=1" class="aligncenter lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" class="aligncenter" src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2020/09/318.png?w=980&amp;ssl=1" data-recalc-dims="1">

 </noscript>Your objective for this project is to implement a high level shopping simulator. To do so you will use

<p style="text-align: center;">inheritance to model a class, ShoppingCart , after another class, DynamicArray , that you willmodify to make functional. You will proceed to create an abstract Grocery class and to create itsconcrete children Vegetable , Drink , and JunkFood , which will collectively represent everytype of item with which you can populate a ShoppingCart object. For this project you will useseparate compilation with g++ to link multiple classes into one executable, and, in order tosuccessfully complete this project, you must understand the prerequisite material from Project 0, theconcept of an abstract data type, template classes, dynamic memory allocation, and polymorphism.

<strong>Concept of an Abstract Data Type</strong>

<a href="https://www.geeksforgeeks.org/abstract-data-types">Geeks for Geeks</a> <a href="http://web.mit.edu/6.005/www/fa14/classes/08-abstract-data-types/">MIT</a>

<strong>Dynamic Memory Allocation</strong>:

<a href="http://www.cplusplus.com/doc/tutorial/dynamic/">C++ Documentation</a> <a href="https://www.tutorialspoint.com/cplusplus/cpp_dynamic_memory.htm">Tutorialspoint</a>

<strong>Template Classes</strong>: <a href="https://www.tutorialspoint.com/cplusplus/cpp_templates.htm">tutorialspoint</a> <a href="https://www.geeksforgeeks.org/templates-cpp/">Geeks for Geeks</a>

<strong>Polymorphism</strong>: <a href="https://www.javatpoint.com/cpp-polymorphism">j</a><a href="https://www.javatpoint.com/cpp-polymorphism">avaTpoint</a> <a href="https://medium.com/@deryacortuk17/polymorphism-in-c-5a7b188fa94f/">Medium</a>

###<strong>Implementation:</strong>

<strong>Work incrementally!</strong> Work through the tasks sequentially (implement and test). Only move on to a task when you are positive that the previous one has been completed correctly. Remember that the names of function prototypes and member variables must exactly match those declared in the respective header file when implementing a class.

####<strong>Definition:</strong>

Let a dynamically resizable array be an array whose maximum capacity increases by a factor of 2 in the event that an insertion is attempted when it is already at maximum capacity and whose maximum capacity decreases by a factor of 2 when the number of elements within it drops below a quarter of its maximum capacity.

<em>Examples:</em>

<table width="504">

 <tbody>

  <tr>

   <td width="299">              arr1 &lt;- {1, 2, 3, 4}arr1.add(5)</td>

   <td width="51"></td>

   <td width="51"></td>

   <td width="103">(capacity == 4)</td>

  </tr>

  <tr>

   <td width="299">arr1 == {1, 2, 3, 4, 5, _, _, _}&lt;/p&gt;&lt;/p&gt;</td>

   <td width="51"></td>

   <td width="51"></td>

   <td width="103">(capacity == 8)</td>

  </tr>

  <tr>

   <td width="299">arr2 &lt;- {1, 2, 3, 4, 5, _, _, _} arr2.remove(5) arr2.remove(4) arr2.remove(3) arr2.remove(2)</td>

   <td width="51"></td>

   <td width="51"></td>

   <td width="103">(capacity == 8)</td>

  </tr>

  <tr>

   <td width="299">              arr2 == {1, _, _, _}</td>

   <td width="51"></td>

   <td width="51"></td>

   <td width="103">(capacity == 4)</td>

  </tr>

 </tbody>

</table>

<em>Addendum: removal in this fashion ensures the efficient execution of future anticipated insertions by minimizing the amount of resize() operations that need to be called later.</em>

<em>go grocery shopping. What your parents don’t realize is that now you’re in charge. You have the money and the list! The list… how do you make a list again?</em>

Modify the DynamicArray.cpp file to implement the following methods (I highly suggest that you complete them in the presented order). The prototypes have already been written for you. i)

template&lt;class T&gt; void DynamicArray&lt;T&gt;::resize()

which carries out the dynamic sizing behavior mentioned in the definition.

<em>Hint: You must dynamically allocate a new array of the appropriate altered size, and then you must copy all elements from the initial array into this new one. Finally, you must update and reassign the private members of the caller.</em>

ii)

template&lt;class T&gt;

bool DynamicArray::add(const T &amp;new_entry)

which inserts an item into the last position of the caller – it <strong>must</strong> call resize and it <strong>must</strong> take into account the possibility that the pointer that represents the caller array could be == nullptr.

iii)

template&lt;class T&gt;

bool DynamicArray::remove(const T &amp;an_item)

which removes the first instance of an item from the caller – it <strong>must</strong> check whether the element to be removed is within the array and it <strong>must</strong> call resize

<em>Hint: Before you call resize you could copy all of the items except the one to be removed into a new dynamically allocated array.</em>

<em>That’s right; you heard me! FOOD! Everything you could ever want! Grab whatever your heart desires!</em>

Define and implement the Vegetable , Drink , and JunkFood classes as polymorphic children of the Grocery class.

<strong>Vegetable</strong><strong> must contain the following methods:</strong>

/**

unit of price: dollars       unit of weight: pounds (lb)

*/ Vegetable(std::string name, double price, double weight)

/*

total_price_ &lt;- product of: quantity, weight per item, and price per pound

*/ void updateCost() which updates total_price_ by multipling the following:

<strong>Drink</strong><strong> must contain the following methods:</strong>

/**

unit of price: dollars       unit of weight: pounds (lb)

*/ Drink(std::string name, double price, double weight)

/**

total_price_ &lt;- product of: quantity, weight per liter, and price per liter

*/ void updateCost() which updates total_price_ by multipling the following:

<em>Note: weight/liter == (unit_weight_ * 16 / FLOZ_PER_LITER) </em><strong>JunkFood</strong><strong> must contain the following methods:</strong>

/**

unit of price: dollars       unit of weight: pounds (lb)

*/

JunkFood(std::string name, double price, double weight)




/**

total_price_ &lt;- product of: quantity and price per unit

*/ void updateCost() which updates total_price_ by multipling the following:







<em>Did you get everything you wanted? Great! Time to check out and head back home. Hope you remembered to get the bread…</em>

Define the ShoppingCart class as a child of the DynamicArray class in a file entitled

ShoppingCart.hpp . <strong>All shopping carts have a maximum carrying capacity of 350 pounds. </strong>Implement the class in a file entitled ShoppingCart.cpp ; you must include but are not limited to the following methods and members:

public:




/* Default Constructor */

ShoppingCart();

/**

must call the destructor of DynamicArray         */         ~ShoppingCart();




/**

adds new_entry to the caller; if the entry                 already exists in the caller, increment                 quantity_ in the object

@pre    :   the addition of the weight of                          new_entry does not bring the                         curr_contents_weight_ over the                          carrying capacity

@return :   true if the addition is successful                     */

bool add(Grocery * new_entry);

/**

removes the first instance of an_item from the caller; if the entry                 already exists in the caller, decrement                 quantity_ in the object.

–&gt; !!!THIS FUNCTION MUST CALL garbageClear()!!! &lt;–

@pre    :   the addition of the weight of                          an_item does not bring the                         curr_contents_weight_ over the                          carrying capacity

@return :   true if the addition is successful                     */

bool remove(Grocery * an_item);




/**

displays shopping cart contents in required format               –&gt; !!!THIS FUNCTION MUST CALL clear()!!! &lt;–

*/

double checkout();          /**

iterates through caller and removes items that have quantity_ == 0              –&gt; !!!THIS FUNCTION MUST CALL DynamicArray::remove()!!! &lt;–




@post   :   every item in the caller has quantity_ &gt;= 1

*/

void garbageClear();

/* Getter: curr_contents_weight_ */         double getCurrentWeight();       private:

double curr_contents_weight_;




<em>Here is a freebie that you must include in </em><em>ShoppingCart.cpp </em><em>:</em>

double ShoppingCart::checkout()

{

if (item_count_ == 0)

{

std::cout &lt;&lt; “Your cart is empty!” &lt;&lt; std::endl;         return 0;

}

double total = 0;

for (size_t i = 0; i &lt; item_count_; i++)

{

std::cout &lt;&lt; “
”

&lt;&lt; std::setw(10) &lt;&lt; std::left &lt;&lt; items_[i]-&gt;getName() &lt;&lt; “t” &lt;&lt; items_         total += items_[i]-&gt;getTotalPrice();

}

std::cout &lt;&lt; std::setfill(‘-‘) &lt;&lt; std::setw(40) &lt;&lt; “
”

&lt;&lt; std::endl

&lt;&lt; “Total:                  ” &lt;&lt; total &lt;&lt; std::endl

&lt;&lt; std::endl;

clear();     return total;

}

###<strong>Testing</strong> How to compile: g++ ShoppingCart.cpp Grocery.cpp Vegetable.cpp

JunkFood.cpp Drink.cpp &lt;test main file&gt; -std=c++17 You must always implement and test you programs <strong>INCREMENTALLY!!!</strong>

####<strong><em>What does this mean?</em></strong>

-Implement and test one method at a time. -For each class:         1. Implement one function/method and test it thoroughly (multiple test cases + edge cases if applicable)         2. Implement the next function/method and test in the same fashion.

####<strong><em>How do you do this?</em></strong> Write your own main() function to test your classes. In this course you will never submit your test program, but you must always write one to test your classes. Choose the order in which you implement your methods so that you can test incrementally (i.e. implement mutator functions before accessor functions). Sometimes functions depend on one another. If you need to use a function you have not yet implemented, you can use stubs: a dummy implementation that always returns a single value for testing (don’t forget to go back and implement the stub!!! If you put the word STUB in a comment, some editors will make it more visible.

####<strong><em>Grading Rubric</em></strong> • <strong>Correctness 80%</strong> (distributed across unit testing of your submission) •

<strong>Documentation 10%</strong> • <strong>Style and Design 10%</strong> (proper naming, modularity, and organization)

<strong>Important:</strong> You must start working on the projects as soon as they are assigned to detect any problems with submitting your code and to address them with us <strong>well before</strong> the deadline so that we have time to get back to you <strong>before</strong> the deadline. This means that you must submit and resubmit your project code <strong>early</strong> and <strong>often</strong> in order to resolve any issues that might come up <strong>before</strong> the project deadline.

There w<span style="text-decoration: line-through;">i</span>ll be no negotiation about project grades after the subm<span style="text-decoration: line-through;">i</span>ssion deadl<span style="text-decoration: line-through;">i</span>ne.

Subm<span style="text-decoration: line-through;">i</span>ssion<span style="text-decoration: line-through;"><u>:</u></span>

You will submit <strong>the following files</strong>:

DynamicArray.cpp

Drink.cpp

Drink.hpp

JunkFood.cpp

JunkFood.hpp Vegetable.cpp

Vegetable.hpp

ShoppingCart.cpp

ShoppingCart.hpp

Your project must be submitted on Gradescope. Although Gradescope allows multiple submissions, it is not a platform for testing and/or debugging and it should not be used for that. You MUST test and debug your program locally. Before submitting to Gradescope you MUST ensure that your program compiles (with g++) and runs correctly on the Linux machines in the labs at Hunter (see detailed instructions on how to upload, compile and run your files in the “Programming Rules” document). That is your baseline, if it runs correctly there it will run correctly on Gradescope, and if it does not, you will have the necessary feedback (compiler error messages, debugger or program output) to guide you in debugging, which you don’t have through Gradescope. “But it ran on my machine!” is not a valid argument for a submission that does not compile. Once you have done all the above you submit it to Gradescope.