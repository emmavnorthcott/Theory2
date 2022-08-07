#Theory 2 
Submitted by: Emma Northcott 

## 1. How does Object Oriented Programming differ from Process Oriented Programming?
Object Oriented Programming (OOP) and Process Oriented Programming (POP) are both high-level programming languages, but they differ in a number of different ways. 

OOP divides a programme into objects while POP divides the programme into functions. The OOP objects are sub-classes of classes. The class defines all the properties of the objected that are associated with it. 

In general OOP is faster the POP to execute and to build. OOP has a clear structure and is easier to maintain. The format makes it easier to maintain "DRY" principles. 

Modifying POP can be more complex because you're likely to need to rewrite larger amounts of code, whereas OOP is constructed in a more independent, modular way meaning changes are smaller. 

## 2. What's polymorphism in OOP?
Polymorphism is a core OOP concept. It means when something occurs in several different forms. One way to test whether an object is polymorphic is to run multiple `is-a` or `instanceof` tests. In Python this means we can define methods in the child class with the same name as defined in their parent class. 

There are two kinds of polymorphism: static of compile time and dynamic. 

Example of polmorphism with Classes. We can call the methods in the class without naming the class specifically: 

    class Dog:
    	def breed(self): 
    		print('Labrador')
    	def name(self):
    		print('Bruno')
    
    class Cat:
    	def breed(self):
    		print('Bengal')
    	def name(self):
    		print('Tiger')
    
    obj_dog = Dog()
    obj_cat = Cat()
    
    for pet in (obj_dog, obj_cat):
	    pet.breed()
	    pet.name()
    		

## 3. What's inheritance in OOP
Inheritance is when a class derives, or inherits, from another class. The inheriting class will reflect all the public and private methods of the parent class and can have it's own unique methods. 

    class Pet():  
        def __init__(self, name):  
            self.name = name  
        def printname(self):  
            print(self.name)  
      
      
    class Species(Pet):  
        def __init__(self, name, breed):  
            super().__init__(name)  
            self.breed = breed  
        def welcome(self):  
            print("Welcome to the zoo! This is ", self.name, "the", self.breed)  
      
    new_pet = Species('Joey', "kangaroo")  
    new_pet.welcome()

## 4. If you had to make a program that could vote for the top three funniest people in the office, how would you do that? How would you make it possible to vote on those people?

The 3 priorities for creating a voting product would be: 

 - Creating an input to collect votes 
 - Recording the input votes 
 - Calculating the total votes per person 
 - Listing the top 3 votes
 
Set up the class list: 

    students = ['Jarno', 'Katie', 'Wendy', 'Chris', 'Laura', 'Aron']  
    submitted_votes = []  
    counted_votes = []

Creating the input & record votes: 

    def collect_votes(students):  
        for student in range(len(students)):  
            vote = (input('Who is the funniest person in class? ')).strip()  
            submitted_votes.append(vote)
           
 Calculating the total votes per person:

    def vote_counting():  
        for student in students:  
            count_votes = submitted_votes.count(student)  
            counted_votes.append([student, count_votes])

Listing top 3:

    vote_counting()  
    top3 = counted_votes[0:3]  
      
    print(f"The 3 funniest classmates are {top3}")

 ## 5. What's the software development cycle?
 The software development cycle is the process teams go through to make sure that they built relevant, robust and maintainable code. This process allows for analysis and improvement at each stage. This allows teams to be more efficient and productive. The eight main stages of the software development cycle are: Planning, Requirements, Design, Build, Document, Test, Deploy, Maintain. Within each of these steps there may be more detailed processes. 

 - Planning: This is the stage when the problem space is identified and research is carried out. In this stage you'd make sure you have a clear budget, team structure, and objectives. Stakeholders feedback at this stage. 
 - Requirements: This is potentially a sub-process of planning. It is where you define user stories and the functionality the product needs to have in order to meet the objectives of the projects. 
 - Design and prototyping: This stage defines what the product will look like and the technical architecture of the product. The architecture includes things like decidied the programming languages to be used, use of any templates or boilerplates. The user interface, usually defined by a Product Designer, sets out how the customer interacts with the software. Platforms defines which operating systems and platforms the code will run on (Eg. Apple, Android, Windows, Linux). Other areas to be considered, security, server interaction, error handling and more. 
 - Software development: At this stage the team starts writing the code and solving the problem. Teams will work together through platforms like GitHub to track changes and merge their independent code together. At this stage it's not just about writing code, but also documenting what they're building so it can be easily worked on or fixed in the future. Engineers should be writing tests for their code to reduce the risk of shipping buggy code. 
 - Testing: Testing is crucial before shipping code. This stage you test to make sure the app performs as intended. Automated testing ensures that aspects like security are functioning correctly. 
 - Deployment: This is when the product becomes available to users. For mobile release this would include things like getting App Store or Google PlayStore approval which can take some time. For larger releases there are additional things the team may need to do like update support articles, write press releases, coordinate with marketing, etc.
 - Operations and maintenance: After deploying the code the team will need to make sure they monitor the performance of the code, assessing and recording bugs, updating dependencies and planning for any future iterations of the product. 
 
 ## 6. What's the difference between agile and waterfall?
 Agile and waterfall are two ways to manage your software development cycle. Waterfall is the type of development that was often used before cloud computing, when software was released once a year via CD-rom. It is called waterfall because you flow from one stage to the next without iteration or going back to the previous stage "upstream". In waterfall you define all your requirements up front, then design, then build, then QA test, then release. There is no iteration or deviation from the original requirements. 

Agile is a modern modern development approach, aided by new technologies. Agile allows us to iterate at each stage of the development process to create a product. The idea is to launch smaller iterations of your products more frequently in order to meet the customer and business needs. Plans and results are constantly reviewed and changes made to the product. 
 
 ## 7. What is a reduced function used for?
 The reduce() function allows you to apply a particular function, passed through the argument, to all the list elements. You can use lambda functions or operators to calculate items in a list or manipulate strings. An example of what you can do:
 
    import functools  
    import operator  
      
    lis = [10, 20, 30, 40, 50 ]  
      
    print("The sum of the list items is : ", end="")  
    print(functools.reduce(operator.add, lis))  
      
    print("The product of list items is : ", end="")  
    print(functools.reduce(operator.mul, lis))  
      
    print("The concatenated product is : ", end="")  
    print(functools.reduce(operator.add, ["summer", "time"]))

 
## 8. How does merge sort work
Merge sort takes a divide and conquer approach to sorting information. At first the array is divided in two. Then it is continuously divided until it can no longer be divided. Once you are at this stage it will pair then it starts paring them back together, but this time comparing the order of the items to each other as these lists build. In time & space complexity merge sort is O(nLogn). 

Example visualisation:
    
    array = [ 10, 30, 50, 20] 
    
    [10,30] / [50, 20]
    [10]/[30]/[50]/[20]
    [10, 30] / [20, 50] 
    [10, 20, 30, 50]

## 9. Generators - Generator functions allow you to declare a function that behaves like an iterator, i.e. it can be used in a for loop. What is the use case? 
There are a few use cases for generators. One use case is when you have a large dataset to manage, for example a large .CSV or data stream. A generators lazy iterator does not store the contents in the memory so you'r not likely to overwhelm your machine like you would using other techniques. 

A generator is also used for infinite sequences. Again since you don't have infinite memory the `yield` over `return` will ensure that you don't crash your machine will working through an infinite sequence. 

Generators are also great for detecting palindromes because it can run through an infinite sequence of numbers and check whether the number generated is the same forwards and backwards. 


## 10. Decorators - A page for useful (or potentially abusive?) decorator ideas. What is the return type of the decorator?

A decorator returns a callable. 

Potentially useful decorators:

 - To format the response of a function in a nicely displayed way.
 - To adjust the timing of a function 
 - To add logging to a function 
 
 Harmful decorators: 
 - Create backdoors for malicious attacks. 
 - Use to collect credentials and send them to an external party. 
 - Use to deploy remote code. 
 - Steal credit card information 
 
 Lots of malicious decorators are called "typo-squatters" because they use a spelling very close to a genuine decorator. 
 
