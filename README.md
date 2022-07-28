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
   
   
 Using loops. <br>
    
 Repetition in rust or any other language is called 'looping' or 'iteration'. <br> 
 There's multiple types of loops , <br>
 - Infinite loooooooooooooooooo.....p . `loop`
 - Conditional loop. `while`  <br>
 
 Keep in mind that the variables decalred have the `mut` keyword. Incase you haven't mentioned the
 keyword, the loop won't execute. May the compiler be with you. <br>
    
         let mut a = 0;
         loop {
             if a == 5 {
                 break;
              }
              println! ("{:?}", a);
              a = a + 1;
          } //infinite loop executes without break statement.
    -----------------------------------------------------------------
          let mut a = 0;
          while a != 5; {
               println! ( "{:?}, a" );
               a = a + 1;
          }
          
  Break can be used with either loops.
  
  ## Match 
  
  Adding logic couldn't have been easier with the `match` keyword. <br>
  It's similar to if..else, but it has more of an exhaustive approach, ie, all options must be considered.
  
      fn main() {
         let a = true;
         match a {
            true => println! ( "It's true." );
            false => println! ( "It's a trap." ); 
            }
      }
  
 ----------------------------------------------------------
           
        fn main () {
          let a = 2;
          match a {
            1 => println! ( "one." );
            2 => println! ( "two." );
            3 => println! ( "three." );
            _ => println! ( "anuthing other than the value above." );
            }
         }
         
   An interesting fact about match is that its checked by the complier. If a new possibility is added, you will be notified. <br>
   if...else isn't checked by the complier. If a new possibility is added, your code may become buggy. <br>
   
   It's advised to prefer match over if..else.
   ( _ ) The underscore means "any other possibility or anything else.".
   
   
   ## Working with Data
   <br>
   <br>
   
   ### Enumeration
  
  By definition an enumeration is ordered listing of all items in a collection. <br>
  We can also say that data can be one of multiple possibilities. Each possibility is a "variant".
  
  
        enum Direction {
          Up,
          Down,
          Left,
          Right,
        }
  
        fn which_way(go: Direction) {
           match go {
              Direction::Up => "up",
              Direction::Down => "down",
              Direction::Left => "Left",
              Direction::RIght => "right",
            }
         }
         
   Programs are robust when `enum` is paired with `match`.
    
    
   ### Struct
   
   Structure : <br>
   
   Struct is a type that contains multiple peices of data. Each piece is called a field. <br>
   Similar data can be grouped together using a `struct`.
   
           struct ShippingBox {
             depth: i32;
             width: i32;
             height: i32;
           }
           
           let my_box = ShippingBox {
             depth : 3,
             width : 2,
             height : 5,
           };
           
           let tall = my_box.height;
           println! ( "the box is {:?} units tall", tall );
           
  Fields can be accessed from structs by dot (.).      
           
      
  
    
 ## Tuples
 
 Tuples are a type of record that's used to store data anonymously. <br>
 It's useful for returning pairs of data from functions while also having the ability to destructure into variables. <br>
 <br>
 `enum Access {
   Full,
   }
   
   fn one_two_three() -> (i32, i32, i32) {
     (1,2,3)
    }
    
    let numbers = one_two_three();
    let(x,y,z) = one_two_three;
    println!("{:?}", x, numbers.0);
    println!("{:?}", y, numbers.1);
    println!("{:?}", z, numbers.2);
    
    let (employee, access) = ("jake", Access::Full);`
    
<br>
Use of structs when there are more than 3 fields is advised.
<br>

## Expressions

Rust is an expression-based language where most things are evaluated and some type is returned. <br>
Expressions values come together to a single point and can be used for nesting logic when required, <br>

    let my_num = 3;
    let is_it_5 = if my_num < 5 {
      true
     } else {
      false 
     };
     
     let is_it_5 = my_num < 5;
<br>
 
     let my_num = 3;
     let message = match my_num {
        1 => "hello",
        _ => "goodbye"
     };
<br>

     enum Menu {
      Burger,
      Fries,
      Drink,
     }
     
     let paid = true;
     let item = Menu::Drink;
     let drink_type = "water";
     let order_placed = match item {
       Menu::Drink => {
       if drink_type == "water" {
         true
       } else {
         false
       }
          _ => true,
      };
   
<br>

Expressions allow nested logic.
<br>

## Intermediate Memory Concepts 

- Memory is stored in binary, ie 0 or 1.
- Computers are optimized for bytes, ie 1 byte = 8 contiguous bits.
<br>
##  Addresses
- All data in memory has an address.
- That's how computers locate data.
- Data dosen't utilize memory directly, it's usually handled by variables.
<br>
## Offsets
- Items can be located at an address using an "offset".
- Offsets begin at 0.
- Offsets represent number of bytes away from the original address normally dealing with indices.
<br>
##  Addresses & Offsets
- Memory uses addresses and offsets.
- Adresses are permanent, data differs and usually handled by variables.
- Offsets can be used to "index" into some data.
<br>

## Ownership 
The concept of ownership is an interesting topic in rust. Now, programs are supposed to track memory and if they fail to do so, a memory leak occurs.
- Rust utilizes an ownership model to manage memory, i.e, the owner of the memory is resposnible for cleaning up memory.
- Memory can either be moved or borrowed.

-------------------------------
|           Move              |
-------------------------------
     enum Light {
       Bright,
       Dull,
     }
     
     fn display_ligth (light: Light) {
       match light {
         Light::Bright => println!("bright"),
         Light::Dull   => println!("dull"),
        }
      }
      
      fn main() [
        let dull = Light::Dull;
        display_light(dull);
        display_light(dull);
      }
      
 ------------------------------------------
 |              Borrow                    |
 ------------------------------------------
      
      
      enum Light {
        Bright,
        Dull,
      }
      
      fn display_light(light:: &Light) {
         match light {
          Light::Bright => println!("bright");
          Light::Dull   => println!("dull");
        }
      }
      
      fn main() {
        let dull = Light::Dull;
        display_light(&dull);
        display_ligth(&dull);
      }
      
  ## Data Structures 
  
  Vectors <br>
  - Vectors in rust are used to represent data of the same type.
  - They can be used to add, read and traverse data.

    let my_number = vec! [1,2,3];
    for num in my_numbers {
      println!(""{:?}", num);
    }
  
  
   Strings<br>
   - Strings are of two types in rust.
   - String : owned .
   - &str : borrowed string slice.
   - An owned string(String) must be used to store data in struct.
   - &str must be used when passing data to a function.
   <br>
   
       fn println!(data: &str) {
         println!("{:?}", data);
       }
       
       fn main() {
        print_it("a string slice.");
         let owned_string = "owned string".to_owned();
         let another_owned = String::from("another");
         println!(&owned_string);
         println!(&another_owned);
        }
        
        ---------Struct-----------
        struct {
         name: String,
        }
        
        fn main() {
         let emp_name = "Jayson".to_owned();
         let emp_name = String::from("jayson");
         let emp = Employee {
           name: emp_name
           };
          }
          
  - String are automatically borrowed.
  - Use to.owned() or String::from() to create an owned copy of a string slice.
  - Use and owned String when storing in a struct.

<br>

## Type Annotations

- Required for function signatures.
- Types are usually inferred.
- Can also be specified in code if not present in function signature.

        -----------------------Basic------------------------
        fn print_many(msg: &str, count: i32) {}
     
        enum Mouse {
         LeftClick,
         RightClick,
         MiddleClick,
        }
     
         let num: i32 = 15;
         let a: char  = 'a';
         let left_click: Mouse = Mouse::LeftClick;
     
         ---------------------Generic-----------------------------
    
         let numbers: Vec<i32> = vec![1,2,3];
         let letters: Vec<char> = vec!['a','b','c'];
         let clicks: Vec<Mouse> = vec![
                 Mouse::LeftClick,
                 Mouse::RigthClick,
                 Mouse::MiddleClick,
             ];
 <br>
 
 ## A different way of working with enums.
 
 - Enum is a type that can represent one item at a time.
 - Each item is called a variant.
 - It's not limited to just plain variants.
 - Each variant can contain additional data, ie, type annotations.

          enum Mouse {
           LeftClick,
           RightClick,
           MiddleClick,
           Scroll(i32),
           Move(i32, i32),
         }

         enum PromoDiscount {
           NewUser,
           Holiday(String),
         }

          enum Discount {
           Percent(f64),
           Promo(PromoDiscount),
         }
 
- Note that other than type annotations, the data can also be another enum.
- More than one peice of data can be associated with a variant.
 
 
 
## Options

- A type maybe one of two things: Some data of a specified type or Nothing.
- Options is usually used in scenarios where data may not be required or is unavailable.
- Maybe the program is unable to find something, maybe it ran out of items in a list.

         enum Option<T> {
            Some(T),
            None
          }
          
          -------------------------------
          
         struct {
           age: Option<i32>,
           email: String,
         }
         
         let mark = Customer {
           age: Some(22), email: "monist998@gmail.com".to_owned(),
        };
        
        let becky = Customer {
          age: Some(22), email:"becky@example.com".to_owned(),
        };
        
        match becky.age {
          Some(age) => println!("customer is {:?} years old", age),
          None => println!("customer age not provided"),
        }
        
        --------------------------------------------------------------
    
<br>
- Options represent some data or nothing.
- Some (variable name) : data is available.
- None : no data available.
- It comes in use when no data is avaialable.
- Option<Type>.
 
 
<br>
 
## Result 
 
- A data type that contains one of two data types.
- "Successful" data or "Error" data.
- Used in scenarios where action needs to be taken but there is a possibility of failure.
- Maybe you failed to copy a file or a connection to server failed.
  
              enum Result<T, E> {
              Ok(T),
              Err(E),
             }

        ---------------------------------
  
                                      fn get_sound(name: &str) -> Result<SoundData, String>  {
                                       if name == "alert" {
                                         Ok(SoundData::new("alert")),
                                       } else {
                                        Err("unable to find sound data".to_owned())
                                       }
                                      }

                                       let sound = get_sound("alert");
                                       match sound {
                                        Ok(_) => println!("sound data located");
                                        Err(e) => println!("error: {:?}", e),
                                       }
  
    

 <br>
 
 - Result data type represents success or failure.
 - Ok(variable name) => operation completed.
 - Err(variable_name) => operation failed.
 
 - Useful when working with funcationlity that can fail.
 - Result<T, E>
 
 
 
  
  
