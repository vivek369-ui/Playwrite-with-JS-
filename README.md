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


-------------------------------------------------------------------------------TS-------------------------------------------------------------------------------

 installtion: 
 
         1. node.js
         2. TS compiler
         3.  VSCode Editor
       
DataType : 

     1.null : 
                    Intentionally empty.
                    let struendtName:null=null;
                    studentName="raghav";
                    console.log(studentName);

     2.undefined : 
                   Variable exists, but value is not given yet.

     3. any : 
              any type of data allowed

     4. unknown : 
               also means we do not know the type yet.
               But it is safer than any.

    5. boolean, string , number, null, any :
              
              let studentName: string = "Aarav";
               let studentSecondName: string = "sham";
               let joine:string =studentName+studentSecondName;
               let studentAge:number=200;
               let studentSecAge=200;
               let passStatus:boolean=true;
               if(passStatus)
                    {console.log("student is passed");
                    }
                    else{
               console.log("student is failed");
                    }
               
               let struendtName:null=null;
               studentName="raghav";
               console.log(studentName);
               
               let anything:any="Hello";
               console.log(anything);
               
               console.log(joine);
               console.log(`first student name${studentName} and second student name${studentSecondName}`);
               console.log(studentAge+studentSecAge);

       6.  array : 
          let fruits:string[]=["apple","banna"];
          for(let fruit of fruits){
          console.log(fruit);
          }
            let fruits:(string|number)[]=["apple",1,"banana",2,"cherry",3];
          for(let fruit of fruits){
          console.log(fruit);
          }

        8.
           Ternary Operator : 

            Ternary operator is a short form of if else.

                         Syntax:
                         
                         condition ? valueIfTrue : valueIfFalse;
                         
                         Example:
                         
                         let age: number = 13;
                         
                         let message: string = age >= 18 ? "Adult" : "Minor";
                         
                         console.log(message);

      9 . 18. Truthy and Falsy Values

               In JavaScript/TypeScript, some values behave like false.
               
               These are called falsy values:
               
               false
               0
               ""
               null
               undefined
               NaN
                         
     10.    for...of Loop

          for...of is easier when we want values from an array.
          
          let fruits: string[] = ["Apple", "Banana", "Mango"];
          
          for (let fruit of fruits) {
            console.log(fruit);
          }
          
          Output:
          
          Apple
          Banana
          Mango

          15. for...in Loop

               for...in is mostly used for object keys.
               
               Example:
               
               let student = {
                 name: "Jane Doe",
                 age: 25,
                 city: "New York"
               };
               
               for (let key in student) {
                 console.log(key);
               }
               
               Output:
               
               name
               age
               city
               
               To print values:
               
               let student = {
                 name: "Jane Doe",
                 age: 25,
                 city: "New York"
               };
               
               for (let key in student) {
                 console.log(student[key as keyof typeof student]);
               }
               
               Output:
               
               Jane Doe
               25
               New York
               
               This is the same concept you practiced earlier.


               An array stores multiple values in one variable.

               Important points:
               
               Array index starts from 0
               array.length gives item count
               push() adds item at end
               pop() removes last item
               unshift() adds item at start
               shift() removes first item
               for...of reads array values
               TypeScript checks array value types
               Arrays are reference types
               const array can still be modified internally 
               Use readonly if array should not be changed
        
        ----------------------------------tuples------------
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

     --------------Function----------- 
      Function are the block of program.
      - we can reuse several time 
       type of function  : 

        1. name functions :  where we declare and call a function by given name

                       function displayName(){
                   
                   let name: string = "John Doe";
                       console.log(name);
               }
               displayName();
               
        2.Anonymous Function: 
             function(){}

                              let firstFunction-->(to invok the function firstFunction()) = function (x: number, y: number):number-->return type{
              
              let name: string = "John Doe";
                  console.log(name);
              return x + y;
          }
          console.log(firstFunction(5, 10));

          3. arrow function:
          ()=>     {}
           if the function body cosists of only one statment
           then no need for the curly brackts and the return keywrod.
          ...Parameters in Functions: 

            parameters are values or arg passed to a function        

          ... optioanl Parameters in Function;
                                        ---> this is the optinal variable, if we dont pass any value, it dont have any problem  
          function green(name:string, cell?:number)

          ....Default parameters in function

          function green(age:number, name:string="vivek")

          ....Rest Parameters 
           
               function green(age:number, ...name:string[])

     ------------------aliases ------------------------
                      {custom datatype }

          type UserId = number;
               
               UserId is another name (alias) for the number type.

                              | Keyword        | Meaning                             |
               | -------------- | ----------------------------------- |
               | `type`         | Keyword used to create a type alias |
               | `AliasName`    | Custom name chosen by the developer |
               | `=`            | Assigns the original type           |
               | `ExistingType` | Any valid TypeScript type           |

                                   type data ={
                              name:string;
                              age:number;
                              isactive:boolean;
                              }
               
               let user:data={
                   name:"john",
                   age:30,
                   isactive:true
               }
               for(let key in user){
                   console.log(user[key as keyof data]);
               }



    --------------Classs and Object-----------


                            
          1 . objcet :  Objects and arrays are stored by reference.
                       after initilization we can add more value
            
               let secDetalis: {
                   name: string;
                   age: number| string;
                   city: string;
               } = {
                   name: "Jane Doe",
                   age: 25,
                   city: "New York"
               };
               
               console.log(secDetalis);
               console.log(secDetalis.age);

                    let secDetalis= {
                   name: "Jane Doe",
                   age: 25,
                   city: "New York"
               };
               secDetalis.name="vivek";
               console.log(secDetalis);
    
