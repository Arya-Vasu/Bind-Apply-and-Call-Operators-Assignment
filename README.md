# Bind-Apply-and-Call-Operators-Assignment

## .bind()

Use **.bind()** when you want to create a new function and call that function later with a certain context. It does not invoke the function, it just allows you to bind whatever object(s) you want.

### Example :

let runner = {

    name: 'Vasu Arya'
    
    run: function(speed) {
    
        return this.name + 'runs at' + speed + 'mps.';
        
    }
    
};

let flyer = {

    name: 'Karan Mahariya'
    
    run: function(speed) {
    
        return this.name + 'flies at' + speed + 'mps.';
        
    }
    
};

let run = runner.run.bind(flyer, 10);

run();

### Output : 

Karan Mahariya runs at 10mps.


## .call() and .apply()

Use **.call() or .apply()** when you want to invoke the function immediately, and modify the context. **.call() and .apply()** call the function immediately. The difference is how you pass the arguments.

**.call()** passes the arguments one by one.

**.apply()** instead of passing in arguments one by one, we pass in an array of arguments that gets spread into the function.

### Example 1 :

const person = {

  fullName: function(friend1, friend2) {
  
    return this.firstName + " " + this.lastName + " " + friend1 + " " + friend2;
    
  }
  
};

const person1 = {

  firstName:"Vasu",
  
  lastName: "Arya"
  
};

const person2 = {

  firstName:"Karan",
  
  lastName: "Mahariya"
  
};

console.log(person.fullName.call(person1, "Raksha Singh", "Aditya Kumar"));

### Output :

Vasu Arya Raksha Singh Aditya Kumar

### Example 2 :

const person = {

  fullName: function(friend1, friend2) {
  
    return this.firstName + " " + this.lastName + " " + friend1 + " " + friend2;
    
  }
  
};

const person1 = {

  firstName:"Vasu",
  
  lastName: "Arya"
  
};

const person2 = {

  firstName:"Karan",
  
  lastName: "Mahariya"
  
};

console.log(person.fullName.apply(person1, ["Raksha Singh", "Aditya Kumar"]));

### Output :

Vasu Arya Raksha Singh Aditya Kumar
