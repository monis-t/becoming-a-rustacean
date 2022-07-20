# becoming-a-rustacean
An introduction to Rust.

Rust is a systems programming language used in a similar way to C/C++. They are used for writing low level code which is closest to the hardware. Similiar to C/C++, Rust can also be used to write programs for embedded devices, web backends, web assembly and networking.

This repo is a journal of my journey with rust. I'll be starting with the very basics and slowly move to some advanced topics. Frens, if you do find it a good read, feel free to use it.

To infinity & beyond !!

Let's begin.
Since most of computation is based on data, it's evident that there willl be types of data.

## Fundamentals

Data types :
 Rust, like any other programming language has the basic data types, 
 - Boolean :        true, false.            `bool`
 - Integer :        1, 2, 3, 4, -2.         `int`
 - Double/ Float :  1.1, 2.2, 5.6.          `f64`
 - Character :      'A','B','C','56','44'.  `char`
 - String :         'Hello','string','this'.`str`
 
 Now, in rust data is represented in binary. Meaning,
  ` let a = 40;` will represent the value of a in binary.
  The code is directly compiled to binary.
  
  
  Hold on !! What is `let a` ?
  
  ## Variables 
  
  `a` is what we call a variable. A variable is used to assign a memory location to a data type.
  It can be set to any value and type.<br>
  `Let` is the keyword that helps us and the computer understand that we are assigning or letting the
  value of datatype `a` to be an `int`.<br>
  
  Here's an interesting fact, variables in rust are immutable by default. <br>
  Meaning it cannot be changed unless we say so by adding the `mut`/ mutable keyword, like so : `let mut 
  a = 40;`.<br>
  
  `let one = 1;` <br>
  `let hi = 'hi` <br>
  `let bye = 'bye';` <br>
  `let mut greeting = 'hi';` <br>
  `let go = "let's go";` <br>
  
  
  ## Functions
  
   Funcitons are a way to encapsulate program functionality. <br>
   We can provide them the privilage of accepting data or returning data.<br>
   They make it really easy to read code and also compile it when requried. <br.
   
   
   `fn add( a: i32, b: i32) -> i32 { <br>
    a + b<br>
    }`<br>
    fn name ( parameter1: parameter type, parameter2: parameter type) - return type { <br> body <br> }
    <br>
    
   Usage :
    
    
    fn add( a: i32, b: i32 ) -> i32 {
      a + b 
      } 
      
      let x = add(1, 1); 
      let y = add(3, 0); 
      let z = add(x, 1); 
      
   As seen above, functions can be executed by calling the function itself.
    
    
## println! Macro
    println! macro displays information to the terminal. <br>
    
       let age = 43;
       println!("hello");
       println!("I am {:?} years old", age);
       
   {:?} is used a debugger to assign the value of a variable.
   
   
   
## Control FLow

 When writing a fairly medium sized program, we might have to use control flow statements. <br>
 By control flow I mean, making choices betweeen decisions based on input. <br>
 - if.
 - else.
 - else if.   
 
 These keywords are universally used in almost all programming languages to direct control flow.
 
 Simple flow: 
 
    let a = 1;
    let b = 2;
    let c = 3;
   
    
 if...else flow :
 
    let a = 100;
    if a > 100 {
    println!("Big number."); 
    } else {
     println!("Small number.")
    }
  
 nested if...else :
   
    let a  = 100 ;
      if a > 100 {
        if a > 191 {
        println! ("Big number."); 
      } else {
        println! ("A little big. ") ;
      } 
    } else {
        println! ("Small number.")
    }
    
  if...else if...else :
  
     let a = 99;
     if a > 200 {
        println! ( " Huge number." );
     else if a > 99 {
        println! ( "Big number." );
     } else {
        println! ( "Small number." );
     }
   
   
   
   It's important to remember that code executes line by line and therefore it becomes necessary to
   mention the steps correctly.
   
   ## Repetition 
   
    
 
  
  
