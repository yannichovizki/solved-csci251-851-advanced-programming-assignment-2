Download Link: https://assignmentchef.com/product/solved-csci251-851-advanced-programming-assignment-2
<br>
<strong>Aim:</strong>

This assignment is to familiarise you with the use of classes in your programs.

<strong>On completion you should know how to:</strong>

<ul>

 <li>Write programs with class objects.</li>

 <li>Implement programs incrementally to minimise debugging.</li>

 <li>Design class objects for software applications.</li>

</ul>

<strong> </strong>

<strong>Requirements: </strong>

This assignment involves the implementation of a simple class to hold sets of playing cards. This structure can be used in any card games requiring decks of cards or hands of cards. A standard deck of cards is represented by the numbers 0 to 51. Thus the contents of the class will be a (dynamic) array of integers with values in that range. These integers will represent the usual 52 cards, starting from the 2 of spades (denoted 2S) followed by 3,…,10 (denoted as XS), followed by J(ack), Q(ueen), K(ing) and A(ce). Then will follow the clubs, diamonds and hearts. To facilitate the output of a card, the file <strong>CardSet.cpp</strong> contains a function PrintCard(int) which will print one card. This file will also hold the implementation of the class CardSet whose interface file is provided as <strong>CardSet.h</strong>. The contents of this class:




<strong>class CardSet </strong>

<strong>{ </strong>

<strong>       public: </strong>

<strong>              CardSet(); </strong>

<strong>          CardSet(int);    ~CardSet();          int Size() const;       bool IsEmpty() const;           void Shuffle(); </strong>

<strong>              int Deal(); </strong>

<strong>          void Deal(int,CardSet&amp;,CardSet&amp;);          void Deal(int,CardSet&amp;,CardSet&amp;,CardSet&amp;,CardSet&amp;);       void AddCard(int);       void MergeShuffle(CardSet&amp;);          void Print() const;  private: </strong>

<strong>              int* Card; </strong>

<strong>              int nCards; </strong>

<strong>}; </strong>




A driver program in <strong>main.cpp</strong> has also been provided for testing the class Cardset. Before commencing any work familiarise yourself with these files and the task performed by each class function described below. All work is to be done in CardSet.cpp and CardSet.h. Do not alter <strong>main.cpp</strong>.

<strong>Implementation:</strong>

The task for this assignment is to add the implementations of the member functions to the file <strong>CardSet.cpp</strong>. Here is a description of the required member functions:




<strong>(i) CardSet(); </strong>

This is the (default) constructor. It should set up a set of 0 cards. (0.5 marks)




<strong>             </strong>

<h1>(ii) CardSet(int);</h1>

This is the initialising constructor. It should set up a set of cards, where the number of cards is the argument passed. The array Card should be filled with cards starting from 0, up to the number of cards needed, but never exceeding the number 51. For example if a set of 104 cards is requested, the array would contain 0 to 51 twice. (1 mark)




<ul>

 <li><strong>~CardSet(); </strong></li>

</ul>

The destructor should clean up any dynamic memory used. (0.5 marks)




<ul>

 <li><strong>int Size() const; </strong></li>

</ul>

This accessor function should return the value of nCards. (0.5 marks)




<ul>

 <li><strong>bool IsEmpty() const; </strong></li>

</ul>

This function should return true if there are no cards in this set. (0.5 marks)




<h1>(vi) void  Shuffle();</h1>

This function rearranges the cards in the set in a random manner. There are many ways of doing this. The simplest method follows this algorithm:




<strong>     FOR each card i in the set           SET j to be a random number on range 0 to number of cards -1        IF i is not equal to j THEN            exchange card i and card j </strong>




You should use the cstdlib library function rand() to generate the random integers needed. (1 mark)




<h1>(vii) int  Deal();</h1>

This function should return the value of the first card in the set, located in the 0th element of the array. The function should then create fresh memory, transfer the rest of the set to this new memory, and then delete the old memory. That is, this class never has any vacant space in it. The array is always the same size as the number of actual cards it holds. If the set is empty, this function should print an error message and terminate the program. (1 mark)




<h1>(viii) void  Deal(int,CardSet&amp;,CardSet&amp;);</h1>

This function deals two hands into the two CardSet arguments passed. The number of cards to be placed into each hand is the first argument. The cards should be removed from the current set one at a time, placing the cards into alternate hands. For example. if the current set held 2S, 3S, 4S, 5S, 6S, 7S (the integers 0 to 5) and we had to deal 3 cards, then the two hands would get 2S, 4S, 6S (integers 0, 2, 4) and 3S, 5S, 7S (1, 3, 5) respectively. The two hands may already have cards in them, and the additional cards will require new memory. Do not create new memory more often than is required. Remember that the current set has to be reduced in size as well. If there aren’t enough cards in the current set to perform the deal, print an error message and terminate. (1 mark)




<ul>

 <li><strong>void Deal(int,CardSet&amp;,CardSet&amp;,CardSet&amp;,CardSet&amp;); </strong></li>

</ul>

Same as above but for four hands. (1 marks)




<ul>

 <li><strong>void AddCard(int); </strong></li>

</ul>

Function to add a card to the current hand. (1 marks)




<h1>(xi) void  MergeShuffle(CardSet&amp;);</h1>

This function takes the current set and the set provided as an argument and makes the current set contain all the cards from the two sets, with cards alternating from each set as far as possible. After this function the argument set will be empty. (1 mark)




<h1>(xii) void  Print() const;</h1>

This accessor function, uses PrintCard to print the contents of the set, five cards to a line. (1 mark)




Commence this assignment by providing stubs for all the above functions so that the program will compile. Keep compiling the program regularly even if this requires parts of the code to commented out. The order in which the functions are implemented is left entirely up to you. However, this should be done to facilitate incremental development and testing of the program and not necessarily in the order given above.




<strong>Demo (2 marks):</strong>

During your week-6 lab class you should demo Test 1 in the main() function. This will require completion of  the constructors, destructor, Size() and Print() functions in ass2.cpp. Do not alter the code in main.cpp.




<strong>Submit (8 marks):</strong>

Submit your files using the submit facility on UNIX ie:




<strong>$ submit -u login -c CSCI251 –a 2 CardSet.cpp CardSet.h main.cpp </strong>

<strong> </strong><strong>where ‘login’ is your UNIX login ID.  </strong>

<strong> </strong>

Deductions will be made for untidy work or for failing to comply with the submission instructions. Requests for alternative demo or submission arrangements will only be considered before the due date. An extension of time for the assignment submission may be granted in certain circumstances.  Any request for an extension of the submission deadline must be made to the Subject Coordinator before the submission deadline. Supporting documentation should accompany the request for any extension.  Late assignment submissions without granted extension will be marked but the points awarded will be reduced by 1 mark for each day late.  Assignments will not be accepted if more than four days late.


