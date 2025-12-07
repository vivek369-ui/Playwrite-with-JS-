# Playwrite-with-JS-

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
       await expect(page.locator('#submit')).toBeEnabled(); // control is enable.
       await expect(submitButton).toBeDisabled(); // Element is disable.
       await expect(checkbox).toBeChecked();    //  radio/checkbox  is checked.
       await expect(link).toHaveAttribute('href', '/home'); // Element has attribut.
      await expect(page.locator('#message')).toContainText('Success'); // Element contains text.
      await expect(page.locator('.product')).toContainText([
       'Apple',
       'Banana',
       'Orange'
     ]);


       
 






         
