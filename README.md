  TS/PR:

               * JS (ES3 -ES6)* 
                 ESMAScript-(standerd (rule and regulation) to which all JS new  code must comply)
                 javascript want to the add new features in the JS code but it not possible because they are not follow the ESMAScipt standard to crate the TS 
                 
                * TS/PR (KT):
                     library  -->The Playwright library contains classes and methods and runs on Node.js. Therefore, we need to install Node.js to run Playwright tests                                       written in JavaScript or TypeScript.
                        playwrite is a framework + (node.js)library  for the end to end testing. 
                        feature : 
                        chross browser (mulitple browser support)
                        cross platform (windows,mac & linux diff os)
                        cross lang (js, ts,java,python)
                        native app (downlaod form Play store dont directly test them)
                        test mobile web (surrport mobile testing for chrome & safari)
                        auto waith(redule the flakiness).
                        handles compelx elements : shadow dom, frames, parell execution in multiple browser faster.
                        built in report : HTML, json, thrid party reoprt Allure.
                        inspector : verifying locators in real times. 
                        code gen tool : record the action and genrate the script and convert in any supproted lang.
                        tracing(trace viewer) : captures screenshorts, records videos, retries flaky tests, and log steps automatically (capture alll the info to investigate the test failure)


                        
              --------------------------------------- 
LOCATORS :
          
           const loginButton = page.locator('#login');

            CSS Selector (most common) : 
                page.locator('#idName')          // by ID
                page.locator('.className')       // by class
                page.locator('button')           // by tag
                page.locator('input[name="q"]')  // by attribute
                
           XPath Selectors : 
               page.locator("//div[@class='item']");
               page.locator("(//a)[1]");

           Text Locator : 
                page.getByText("Login");
                page.getByText("Submit", { exact: true });
                page.locator('text=Login')
                page.getByText('Sign in')

           Locate multiple WebElement : 
                       page.$$(locator)
                
            Role Locator (recommended!) :
                page.getByRole('button', { name: 'Login' })
                page.getByRole('textbox', { name: 'Username' })
                page.getByRole('link', { name: 'Home' })

           Test ID Selectors:
                Playwright supports data-testid, data-test, and data-test-id.
                page.getByTestId("login-button");

         Label Selectors :
                page.getByLabel("Email");
                page.getByLabel("Password");

         Placeholder Selectors : 
                page.getByPlaceholder("Search");
                page.getByPlaceholder("Enter your email");

        Built_In_Locators : 
          await page.getByAltText("Australian Aboriginal flag");// alt attribut value 
          await page.getByPlaceholder("linktr.ee/yourname").focus//use placeholder value
          await page.getByRole('button', { name: 'Open language dropdown' });;// get implicit & explicit. get the web element base on that role like button,checkbox 
          use tag and attribute=value for locat the element
          await page.getByText("Log in").click;// using inner text 
          await page.getByLabel("");// using the lable tag innner value.
          await page.getByTitle("");//Allows locating elements by their title attribute.
          awiat page.getByTestId("")//You can locate the element by it's test id attribute.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------

Assertions : 
            
       await expect(page).tohaveURL('https://www.org.com/') // Verifies that the page has navigated to the given URL.
       await expect(page).toHaveTitle('My Page Title'); // verifies that the page has a equal title.
        await expect(page.locator('selector')).toBeVisible()// Element  is visible.
       await expect(page.locator('#submit')).toBeEnabled(); // element  is enable or not.
       await expect(submitButton).toBeDisabled(); // Element is disable.
       await expect(checkbox).toBeChecked();    //  radio/checkbox  is checked ot not.
       await expect(link).toHaveAttribute('href', '/home'); // Element has attribut.
      await expect(page.locator('#message')).toContainText('Success'); // Element contains text.
      await expect(page.locator('.product')).toContainText([
       'Apple',
       'Banana',
       'Orange'
     ]);
     
------------------------------------------------------------------------------------------------------------------------------------------------------------------------

DropDown : 

            /**drop down (value , visible / label text, index)*/
            await page.locator("//*[@id='dropdown']").selectOption({ label: "Option 1" });
            await page.locator("#country").selectOption({ label: "Afghanistan" });
            await page.locator(".form-control").selectOption({ value: "50" });
            await page.locator(".form-control").selectOption({ index: 3 });
            await expect(page.locator(.form-control option)).toHaveCount(4);
            const numberOfOption = await page.locator(".form-control option");
            await expect(numberOfOption).toHaveCount(4);

-----------------------------------------------------------------TS--------------------------------------------------------------------

 installtion: 
 
         1. node.js (npm--> node package manager) and set the envirment variable
         2. TS compiler (npm install -g typescript) cmd
         3.  VSCode Editor
         4. Ts Executer to run the Ts file directly (npm install -g tsx)
           comand to run TS directly : (tsx Start_Day\F_Prog.ts)

Variables: 
          
          var, let, const 
         1. scop  :
          2type of scope in TS functioanl(var) & block scope(let, const) 
         A child block can access variables from its parent block, but a parent block cannot access variables declared inside its child block.
         Declare let/const in the function → Accessible everywhere inside that function, including nested blocks.
         Declare let/const inside a block (if, for, while, {}) → Accessible only inside that block.
          
         2. Declaration/value assignment : 
            var and let (we can declar without and initialize)
            const (we can not declar without and initialize)
            
         3. redeclration: 
         ex : 
              var name =30;
              var name =20;
         var allowed redeclration
         let and const not allow redeclration for code safety
         
         4. re-initialization\re-assignment: 
              var & let (re-assignmentallowed)
              const (re-assignment not allowed)
              
         5. hosting : 
            without declaring and assign variable we try to access.
            var : it shows undefine.
            let & const  : it shows not intitallize.
            
         
DataType/Loops : 
                    
      let age:number=30
     data type --> number
     annotation-->:number
     type inference--> (let age=30)automatically assgin the type base on value which we provided.
      console.log(typeof(passStatus))-> which type of datatype
      
      1. 2types of the DT : 
         premitive : (store singal value)number, string boolean, null, undefined , any, union type, void , unknown
         non-premitive :(store multiplae value) array, function,classes, interface, tuple
                   
      1.null : 
                    Intentionally empty.
                    let studentName:null=null;


      2.undefined : 
                   Variable exists, but value is not given yet.

      3. any : 
              any type of data allowed
                    let studentName:any=null;
                    studentName="raghav";
                    console.log(studentName);

     4. unknown : 
               also means we do not know the type yet.
               But it is safer than any.
               
     5. Union : 
             combine multiple type 
            let studentName:string |null| number=null;

     6. void : 
            used for the Fun that don't return anything
             function test():void
                {
                    let studentName:string |null| number=null;
                    studentName ="raghav";
                    console.log(studentName);
                    }test();

          
      7. Ternary Operator : 

            Ternary operator is a short form of if else.

                         Syntax:
                         
                         condition ? valueIfTrue : valueIfFalse;
                         
                         Example:
                         
                         let age: number = 13;
                         
                         let message: string = age >= 18 ? "Adult" : "Minor";
                         
                         console.log(message);
  
      8. Truthy and Falsy Values

               In JavaScript/TypeScript, some values behave like false.
               
               These are called falsy values:
               
               false
               0
               ""
               null
               undefined
               NaN :  return +"nextyear"; JavaScript tried to perform a number operation, but the value couldn't become a valid number.
                    
          
        **Loops**
         1. while Loop : 
                initialization
                while(condition)
                {
                statment;
                ++ or --
                }
                
          2. do While Loop :      
          Execute atlest once before checking the Codition
          do{
            statment;
            ++ or --
            } while(condition);

          3. for...of Loop
          for...of is easier when we want values from an array.
          
          let fruits: string[] = ["Apple", "Banana", "Mango"];
          
          for (let fruit of fruits) {
            console.log(fruit);
          }
          
          Output:
          Apple
          Banana
          Mango

Function\ Array 

       Function are the block of program, we can reuse several time 
      
       type of function  : 

       1. name functions :  where we declare and call a function by given name

                       function displayName(){
                   
                   let name: string = "John Doe";
                       console.log(name);
               }
               displayName();
               
       2.Anonymous Function: 
                    --> the variable name act as a function name. 
               let callFun = function(){}

             let firstFunction-->(to invok the function firstFunction()) = function (x: number, y: number):number-->return type{
              
              let name: string = "John Doe";
                  console.log(name);
              return x + y;
          }
          console.log(firstFunction(5, 10));                  

       3. arrow/Lamda function:

           --> the variable name act as a function name. 
          let callFun = ()=>{}
          
           if the function body cosists of only one statment
           then no need for the curly brackts and the return keywrod.
           
          4...Parameters in Functions: 

            parameters are values or arg passed to a function        

          ... optioanl Parameters in Function;
                                         ---> this is the optinal variable, if we dont pass any value, it dont have any problem  
           function green(name:string, cell?:number)
           - if we declaer the one parameter as a optional the following parameter should be optional, otherwise it shows complie error

          ...Default parameters in function

          function green(age:number, name:string="vivek")
              
          ....Rest Parameters 
           function green(age:number, ...name:string[])

    5. call Back function: 
                we can pass the the function as argument inside the another function and gets executed later
                // call back fun 
                function message()
                {
                    console.log("message");
                }
                //2. fun that take other fun as para
                function paraent(test:()=>void)
                {
                console.log("tes");
                test();
                }
                paraent(message);
                
                function callback(parameter1: Type1, parameter2: Type2): ReturnType {
                // callback code
            }
            
            function parent(cb: (parameter1: Type1, parameter2: Type2) => ReturnType): void {
                cb(value1, value2);
            }
            
            parent(callback);

      **Array**



  Class\Object

              . An object is a collection of related data stored as key-value pairs.      
              .object contains variable & methods
              . Object contains properties and behaviour.
          Ex. 
                 ------> Object    --->properties/variable
                 Employ-->      Name, Designation, salary 
                                bonus(), getdetails(), setdetails()
                                 -------------->method/behaviour
               diff way to crate the object:

               1. using 'object' type - directly define the value for variable.
               
                                     -----> if i add object here, then we only store key value pair and if not add, then it allow the method inside the {}
                      let secDetalis= {
                       name: "Jane Doe",
                       age: 25,
                       city: "New York",
                       ----------------------------> crate function inside the object is called method. and it crate in Key value pair
                       getDetails:function:string()
                       { 
                       return`${this.name}, ${this.city}};  
                       }
                       // modify the value 
                        secDetails.ity="jalna";
                        //access the object
                       console.log(secDetails.name);
                       console.log(prima.getDetails());
                       console.log(prima["age"]);

                 
               2. Inline type Object - we also define the datatype for variable (TS).

                      Objects and arrays are stored by reference.
                       after initilization we can add more value
             
               let secDetalis: {
                   name: string,
                   age: number| string,
                   city: string,
                   getSummery:()=>string
               } = {
                   name: "Jane Doe",
                   age: 25,
                   city: "New York",
                   getSummery:function()     
                   {
                    return`${this.name}`;
                   }
               };
               
               3. Using type aliases(ts/js) - 
                         {custom datatype } crate once and use multiple time

          type UserId = number;
               
               UserId is another name (alias) for the number type.

              | Keyword         |    Meaning                           |
               | -------------- | ----------------------------------- |
               | `type`         | Keyword used to create a type alias |
               | `AliasName`    | Custom name chosen by the developer |
               | `=`            | Assigns the original type           |
               | `ExistingType` | Any valid TypeScript type           |

                                   type data ={
                              name:string,
                              age:number,
                              isactive:boolean,
                              }
               
               let user:data={
                   name:"john",
                   age:30,
                   isactive:true
               }
               for(let key in user){
                   console.log(user[key as keyof data]);
               }


               
               4. using the classes -

               constructor use for assign data and method used for display the data

               class contains the : constructor , method, properties (variable name)
               
            class Details{
               --------------> the instance must be initialization or added in the construction
               name:string="vivek";
               num:number=3424;
               ------------------> Read only property(can only be assign once)
               readonly sid:number;
               ----------> its a share between all objects if we modifiy in object it reflect on the all objects. we can directly access using class name
               static schoolNmae:sring ="sb";
               -------------> varibale and method not only belong to class also to the obj because of that not access using .this , ass using the class name directly
               static demo(){
               
               }
                dataq()
              {
          console.log ("data function");
          console.log(this.name, this.num)
          }
          }
          
           let  data  = new Details();
          data.dataq();

           new Student(...) → Creates the object (constructor runs automatically).
           access.scoreCardAccess() → Uses that object to run one of its methods manually.

         4.3 method overloading and constructor overloading:

          1 constructor : 
           A constructor is a special method named constructor.
            It runs automatically when you create an object with new.
            It is mainly used to:
            Initialize properties.
            Accept values while creating objects.
            Perform one-time setup or initialization.
            A class can have only one constructor in TypeScript.
             - multiple sig of consructor but implimentaion match with the bith constructor
           class calculator{
            constructor();
            constructor(a:number,b:number);
            constructor(a?:number, b?:number) {  
        if(a!=undefined && b!=undefined)
        {
            console.log("correct")
        }
        else{
            console.log("false");
        }
    }
    }
    let execute = new calculator(4,2);
    let execute1 = new calculator();

      2. method overloading: 
        one method can be called with different types or different numbers of arguments.
        multiple signatures + one implementation.
        class methodOverload{
            firstMethos(name:string,id:number):void;
            firstMethos(name:string,id:number,code:string):void;
            firstMethos(name:string,id:number,code?:string):string
            {
                 if(this.firstMethos!=undefined)
                 {
                    console.log("its true");
                 }
                 return ""+name+id;
            } 
        }
        let execute = new methodOverload()
        console.log(execute.firstMethos("3",4))

        3. inheritance : 
                              ----> ()use parent class as a type when we want to access the properties and method belong to only both child and parent class
         let printFamilyDetails:Employe = new EmployeFamily();
                            
        super(): user to invoke immediate parent class constructor.
        constructor()
          {
            super()
          }
        super:used to invoke immediate parent class method. not invoke the parent class prorty
            calculatebonus(){
           super.callEmploye();
             return 3;
         }
         use the property of other class using "extends"
         a subclass/child class can provide a specific implementation of a method that is already defined in the superclass.
         the method must have a same name, return type, and parameter.


         4. interface: 
                 it's a way to define the structure of object. 
                 interface contains the properties and methods.
                 it's like blue print of object.
        
        -------------------- --------------tuples------------
         is simpler like array but in that we can store (hetrogeneous)diff diff type of data

         let allData:[string,number]=["d",3,0];

          //accessing tuple elements
          console.log(allData[0]);
          console.log(allData[1]);
          console.log(allData[2]);
          
          // add element to tuple
          allData.push(4);
          console.log(allData);
          
          //removing element from tuple, it removes the last element added to the tuple
          allData.pop();
          console.log(allData);   
          
          // updateing tuple element
          allData[0]="dinesh";
          console.log(allData);  


