ement# Playwrite-with-JS-

     Extenstion used for JS : ESLint , Prettier – Code formatter , JavaScript (ES6) Code Snippets ,Live Server 
      Terminal : 
       Code gen / test gen :  npx playwright  codegen ( genrate ,Record and play automgenrated script.also pic the locator from the Website)
                              npx paywright codegen --help
              
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

          7. objcet :  Objects and arrays are stored by reference.
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
                         
                                  
