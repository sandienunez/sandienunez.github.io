---
layout: post
title:      "Linked lists? Why should you care?"
date:       2021-03-28 18:57:55 +0000
permalink:  linked_lists_why_should_you_care
---


![Screen Shot 2021-03-28 at 2 56 47 PM](https://user-images.githubusercontent.com/61069416/112764293-d89e6f80-8fd5-11eb-818c-85bea5757fb6.png)

Linked lists are a special type of data structure that will be helpful in saving you time in your journey to mastering data structures and algorithms. If you didn’t major in computer science and want more clarity on the concept of linked lists then keep reading on!


## Wait...what’s a pointer?
Linked lists are made of elements called nodes that are organized consecutively. Each node has both the desired data that needs to be stored as well as a pointer. Don’t get confused with this concept of a pointer. This “pointer” is a variable that literally points to the location of the value or the next node in the linked list. The pointer’s job is to store a memory address. A memory address is a “specific memory location” in a computer’s hardware made up of unique digits that a central processing unit (CPU) or device uses to track data.

Back to Linked Lists...
 The last node in the linked list has a null pointer. In order to store a new element in the linked list, it’s sufficient to remember the location of the first node in the linked list. From there, you can use the pointers as guides to easily find the other nodes. InterviewCake says to think of them as paper clips chained together. The first paper clip in the chain is called the head. The tail is the last paper clip. The tail can also be referred to as the group of the paperclips excluding the first leading paper clip (the head). You can also think of linked lists like a line of people waiting at the DMV. Each node has the next node in the linked list, where node.next is the following person in line. And node.value is the name of the person. InterviewCake shares this great example coded in Ruby that explains this well. 


![Screen Shot 2021-03-28 at 1 57 58 PM](https://user-images.githubusercontent.com/61069416/112764055-f0c1bf00-8fd4-11eb-8d59-0a4fa1f50a8d.png)

## Linked Lists > Arrays

Using linked lists over arrays have two big advantages. First, when inserting and deleting elements in arrays it can get very expensive. Meaning that it can take a lot of space and time. 

On the other hand, using linked lists to insert or delete elements saves space and time.

### Resources

1. https://www.interviewcake.com/question/ruby/linked-list-cycles
2. https://study.cs50.net/linked_lists
3. https://www.geeksforgeeks.org/linked-list-set-1-introduction/
4. https://en.wikipedia.org/wiki/Memory_address
5. https://www.educative.io/edpresso/what-is-a-linked-list

 




