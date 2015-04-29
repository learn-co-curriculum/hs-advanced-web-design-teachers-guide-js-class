###SWABATs

+ understand how to use JS class to create objects
+ use the classical model to create classes and instances of classes
+ understand what instances of class are
+ understand public vs private methods and properties
+ understand how inheritance works
+ how to use the constructor method

###Motivation
Last week we learned about object literals - they are obviously useful but they are not exactly how the pros do OO programming. What if you wanted to create a pack of dogs that all have names, colors, breeds and ages - it would be much more useful to have a set template that contained the attributes you know you want/need for each dog. That’s what you guys are going to learn about today.

### Lesson Plan
+ What are some attributes that are the same for all dogs? What do all dogs have? Tails, ears, legs, etc. It would be great if we had a Dog template that we could use to automatically set up with some of these things.
+ How do we do that with JavaScript?
+ If we want to create a dog template we can use a JavaScript class. JavaScript classes are built with something called a Constructor Function it looks something like this:
	+ function Dog() {
	+ }
+ Notice that this looks similar to the functions you’ve already learned to build (it starts with the keyword function and it also includes the parentheses - but notice that the name of the function is capitalized. 
+ Let’s add some attributes to our Dog class. Let’s say that we want to set all dog’s to have an age or 0 when you create them. You can do that like this:
	+ function Dog(){
	+ this.age = 0;
	+ }
+ Maybe you also want all your dogs to be obedient too. And to have pink noses. You can do that too:
	+ function Dog(){
	+  this.age = 0;
	+  this.obedient = true;
	+  this.nose = “pink”;
	+ }
+ You can set default values with number, strings or booleans. 
+ The syntax for setting the attributes for a JS class is very specific. Notice that we are using dot notation similar to how we set attributes for Object literals but now we are using the keyword `this`.
+ What `this` is referring to is very important. The `this` we are using here is not referring to our Dog template - it is actually referring to a specific dog. We will be using our Dog template to make many copies of dogs. We call these dog copies instances of the Dog class. 
+ We create instances with the following syntax:
	+ var dog1 = new Dog();
+ This means that we’ve created a new copy of our Dog class - in essence a new little dog object. 
+ Now that we have a new dog object (dog1) <b>what do you think would happen if we did alert(dog1.age);? alert(fido.obedient);? alert(fido.nose);? Why?</b>
+ Cool. So so those things are already set for us but what if we wanted to set a name or a breed for the dog. <b>How would we do that? How did you do that for an object literal?</b>
	+ dog1.breed = “beagle”
	+ dog1.name = “Snoopy”
+ How do we check if these properties were set? Let’s alert them to the screen.
	+ alert(fido.breed);
	+ alert(fido.name);
+ If we had a real dog though it would be born with its breed already set. And guess what? There is a way to do that.
+ Notice the empty parenthesis next to our class name - we can insert arguments there that can be used to set the properties of the Dog like so:
	+ function Dog(breed){
    + this.age = 0;
    + this.obedient = true;
    + this.nose = “pink”;
    + this.breed = breed;
	+ }
+ And then when we create the dog we need to make sure that we incorporate an appropriate argument when we create an instance of the dog, like so:
	+ var dog2 = new Dog(“Husky”);
+ <b>How do we check to see that this breed was set? </b>dog2.breed
+ <b>Which attributes should also already be set for this Husky? </b>age, obedience, nose, breed
+ <b>And what if we wanted to set the dog’s name? </b>dog2.name = “Balto”
+ One last thing. What if we wanted to keep track of all the dogs we are creating? We can set up attributes for our Dog class as well as for instances of the Dog class.
+ For instance if we set up a Dog.all attribute and set it to an empty array like this:
	+ Dog.all = [];
+ Then we can add our doggies to this array as we create them.
+ The way that we do this is by adding a constructor method to our Dog class like this:
	+ function Dog(breed){
	+ this.age = 0;
	+ this.obedient = true;
	+ this.nose = “pink”;
	+ this.breed = breed;
	+ this.constructor.all.push(this);
	+ }
+ <b>What does this refer to again?</b> The instance of the dog. So when we want to refer to the Dog class or the constructor that is creating our doggies we need to do this.constructor. So essentially
	+ this.constructor.all is the same as this Dog.all
	+ <b>And what are we pushing into this array?</b> this <b>What is this?</b> this is the instance of the dog we are creating - dog1 or dog2 or dog3 etc.
	+ so each time we create a new dog this.constructor.all.push(this); is going to push our little doggie into the all array we are using to keep track of our dogs 
+ Let’s practice this with a lab. I’ll leave the code we created so far up here on the screen.
+ Everyone go to Learn and fork and clone the OO ATM lab.
+ <b>If the class seems to be moving quickly or for the advanced students:</b>
+ We have another lab on Learn that can help you get practice with OO JS. <b>This is a tougher more conceptual lab</b> and the format is a little different. 
+ It’s a test driven lab so you’ll find instructions/tasks and tests to see if you’ve completed each task. You can see these by opening up SpecRunner.html.
+ When you think you’ve completed one of the steps refresh the page to run the tests.
+ We don’t actually have any html files - this is straight JavaScript - and you’ll be writing all of your code in app/task-list.js.
+ This lab is a version of the Task Lister. It’s asking you to create a List class - or constructor - and a Task class - or constructor.
+ Ultimately you want to create list objects - To Do Lists - that are connected to task objects - which are the individual tasks on the To Do List. 
+ Again - THIS IS A TOUGH LAB. If you are up for the challenge work together, take it one step at a time and don’t be afraid to ask for help!

