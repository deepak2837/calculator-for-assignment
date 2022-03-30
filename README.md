
here in this project we are going to make a scientific calculator 
Here is the basic logic behind each feature. 
So let's start it. 
The calculator will be purely in the java script. 
i will not use html text to display buttons, we will replace it with javascript . innerHTML method . 

lets go steps by steps :

step : 1

lets start with index.html page 
Let's discuss the logic.

input:
there will be two sections, one will be input where we will take input from the user on which user is clicking on

output:
  Within this we will display the output for the user.
  Output also has two sub-divisions.
  1)operations
  2) result 


 
=> so in html we need container for calculator 
=> inside the container we need input and output 
=>  inside the output we need  operations  ,and inside the operations we need result 

we're going to intiate the value of the result will be zero so when we start the calculator there will be zero value in the frame. 
 

we will use document.querySelector(.classanme ) to alter the internal html. 
we will create the whole button using javascript by the javscript datatype symbol . 




lets talk about the creation of buttons:
for this you can create an . 
var calculator_buttons = [];
  contains all the buttons on the calculator. 

 each button is a object 
 and each object has 4 property 
 properties are :
 ...
 so here are all buttons along with the properties :
];

we will show these buttons rows by rows
so lets say one row conatains 4 buttons


<div class="row"> </div>  
as we know  the number of buttons in a row is  fixed ...
so for that we will take a 
constant method to declare the varible so that we cant change the value of varible afterwards :
like this 

const buttons_per_row  = 4;
added_buttons = 0

then we will run a for loop 
like this 
calculator_buttons.forEach() 
index in objects will be like 0 1, 2 

so row are blank  at the start so we will start appending the the objects index  in it using the javascipt property .innerhtml to replcae  or append the value to the html file 
this added button  will be used to make the logic so that only 4 button should be added to a row 
by using if else and for loop statement
like if(added_buttons%buttons_per_row == 0)  
input_elements.innerHTML += `<div calss="row"></div>`
we will used the :last-child html property so that we will not select the first row always 
and here row will be = document.queryselector(".row:last-child");
row.innerHTML += <button id= "${button.name}">${button.symbol}</button>;





we will use event listener in order to see which button user has clicked 
so will apply eventlistener to the whole 
input_elements.addeventlistener("click", event => { 
    const target_button = event.target;
     calculator_buttons.forEach(button =>{
         if (button.name == target_button.id ) calcultor(button);

     })

} )




there are six  types of buttons :
number 
operator 
math function 
trigo function 
key 
calculate 


for this will will make a object data which will save two thing: operations and formula for it 

let data = {
    operation :[];
    formula : [];
}
 when a user will click on a number,  number will be pushed to operations and formula array
 data.operation.push(symbol)
 data.formula.push(symbol)


 same we will do with the operators,math ,trigo functions 
 and there are four keys   rad,deg,clear and backspace 



calculate is the our final function which will calculate the value added in the data 
we will use eval function which will calculate the string 


 then we will use the data.operation.join('') to join the whole input in order to calculate function 

functionality of some special character :

for deleteing the one element from the array (functionlity of backspace symbol)
we will use the pop function 
data.formaula.pop()
data.operation.pop()

for clearing the whole output or the functuonality of C  :
data.formula = []
data.opertaion = []


these two array are same one contains the real math function which will be used to evalalvate and second arrray consists of input values 
these both array are always in sync 
data.formula = []
data.opertaion = []



link of normal calculator 



this work is under progress ......... i will convert this in a scientific calcultor 
rest of the functionlity and complexcity 

complications for some speacials operators in math:
 formaula in math class 20 +20! +4^(10)
 formula in javascipt 20+ factorial(20) + math.pow(4,10)
 data.operation = [2,0,"+","!",2,"+",4^(10)]
 data.formaula= [2,0,"+",factorial,2,"+",4math.pow(10)] : this wil led to syntax error 
 but this is not the right way toparse the data to eval function of javascript for that we need to fic the functuionlity 

 

even though we will make a function for the factorial and the power
here is the factorial function :
function factorial(n){
  let answer = 1;
  if (n == 0 || n == 1){
    return answer;
  }else{
    for(var i = n; i >= 1; i--){
      answer = answer * i;
    }
    return answer;
  }  
}
let n = 4;
answer = factorial(n)
console.log("The factorial of " + n + " is " + answer);



for fixing the issue of factorial fuction 
for that we will  make the factorial_previous_number_gtter

for that we need to replace 2factorial to factorial(2)


same goes with the power function 
creation a power function here 
