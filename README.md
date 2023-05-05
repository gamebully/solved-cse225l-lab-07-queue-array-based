Download Link: https://assignmentchef.com/product/solved-cse225l-lab-07-queue-array-based
<br>
In today’s lab we will design and implement the Queue ADT using array.

<table width="0">

 <tbody>

  <tr>

   <td width="301"><strong>quetype.h </strong><strong> </strong>#ifndef QUETYPE_H_INCLUDED#define QUETYPE_H_INCLUDED class FullQueue{};class EmptyQueue{};template&lt;class ItemType&gt; class QueType{     public:         QueType();QueType(int max);         ~QueType();         void MakeEmpty();         bool IsEmpty();         bool IsFull();         void Enqueue(ItemType);         void Dequeue(ItemType&amp;);     private:int front;         int rear;         ItemType* items;         int maxQue;}; #endif // QUETYPE_H_INCLUDED<strong>quetype.cpp </strong> #include “quetype.h” template&lt;class ItemType&gt;QueType&lt;ItemType&gt;::QueType(int max){maxQue = max + 1;     front = maxQue – 1;     rear = maxQue – 1;items = new ItemType[maxQue];} template&lt;class ItemType&gt;QueType&lt;ItemType&gt;::QueType(){maxQue = 501;     front = maxQue – 1;     rear = maxQue – 1;items = new ItemType[maxQue]; }</td>

   <td width="411">template&lt;class ItemType&gt; QueType&lt;ItemType&gt;::~QueType(){delete [] items;}template&lt;class ItemType&gt;void QueType&lt;ItemType&gt;::MakeEmpty(){     front = maxQue – 1;     rear = maxQue – 1;}template&lt;class ItemType&gt;bool QueType&lt;ItemType&gt;::IsEmpty(){return (rear == front);}template&lt;class ItemType&gt;bool QueType&lt;ItemType&gt;::IsFull(){return ((rear+1)%maxQue == front);}template&lt;class ItemType&gt;void QueType&lt;ItemType&gt;::Enqueue(ItemType newItem){if (IsFull())         throw FullQueue();     else     {rear = (rear +1) % maxQue;         items[rear] = newItem;} }template&lt;class ItemType&gt;void QueType&lt;ItemType&gt;::Dequeue(ItemType&amp; item){if (IsEmpty())         throw EmptyQueue();     else     {front = (front + 1) % maxQue;         item = items[front];} }</td>

  </tr>

 </tbody>

</table>







Generate the <strong>driver file (main.cpp) </strong>where you perform the following tasks. Note that you cannot make any change to the header file or the source file.

<table width="0">

 <tbody>

  <tr>

   <td width="423"><strong>Operation to Be Tested and Description of Action </strong></td>

   <td width="120"><strong>Input Values </strong></td>

   <td width="160"><strong>Expected Output </strong></td>

  </tr>

  <tr>

   <td width="423">        •     Create a queue of integers of size 5</td>

   <td width="120"> </td>

   <td width="160"> </td>

  </tr>

  <tr>

   <td width="423">        •     Print if the queue is empty or not</td>

   <td width="120"> </td>

   <td width="160">Queue is Empty</td>

  </tr>

  <tr>

   <td width="423">        •     Enqueue four  items</td>

   <td width="120">5  7  4  2</td>

   <td width="160"> </td>

  </tr>

  <tr>

   <td width="423">        •     Print if the queue is empty or not</td>

   <td width="120"> </td>

   <td width="160">Queue is not Empty</td>

  </tr>

  <tr>

   <td width="423">        •     Print if the queue is full or not</td>

   <td width="120"> </td>

   <td width="160">Queue is not full</td>

  </tr>

  <tr>

   <td width="423">        •    Enqueue another item</td>

   <td width="120">6</td>

   <td width="160"> </td>

  </tr>

  <tr>

   <td width="423">•     Print the values in the queue (in the order the values are given as input)</td>

   <td width="120"> </td>

   <td width="160">5  7  4  2  6</td>

  </tr>

  <tr>

   <td width="423">        •     Print if the queue is full or not</td>

   <td width="120"> </td>

   <td width="160">Queue is Full</td>

  </tr>

  <tr>

   <td width="423">        •    Enqueue another item</td>

   <td width="120">8</td>

   <td width="160">Queue Overflow</td>

  </tr>

  <tr>

   <td width="423">        •     Dequeue  two items</td>

   <td width="120"> </td>

   <td width="160"> </td>

  </tr>

  <tr>

   <td width="423">•     Print the values in the queue (in the order the values are given as input)</td>

   <td width="120"> </td>

   <td width="160">4  2  6</td>

  </tr>

  <tr>

   <td width="423">        •     Dequeue three items</td>

   <td width="120"> </td>

   <td width="160"> </td>

  </tr>

  <tr>

   <td width="423">        •     Print if the queue is empty or not</td>

   <td width="120"> </td>

   <td width="160">Queue is Empty</td>

  </tr>

  <tr>

   <td width="423">        •    Dequeue an item</td>

   <td width="120"> </td>

   <td width="160">Queue Underflow</td>

  </tr>

  <tr>

   <td width="423">•     Take an integer <strong>n</strong> from the user as input and use a queue to print binary values of each integer from 1 to <strong>n</strong>. Here is how it can be done.o    Create an empty queue o Enqueue the first binary number “1” to the queue.o    Now run a loop for generating and printing n binary numbers.&#x25aa;  Dequeue and print the value.&#x25aa;  Append “0” at the dequeued value and enqueue it.&#x25aa;  Append “1” at the dequeued value and enqueue it.</td>

   <td width="120">10</td>

   <td width="160">11011100101110111100010011010</td>

  </tr>

 </tbody>

</table>