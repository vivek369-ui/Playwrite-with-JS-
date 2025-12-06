# Playwrite-with-JS-

     Extenstion used for JS : ESLint , Prettier – Code formatter , JavaScript (ES6) Code Snippets ,Live Server 

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

         Label Selectors
                page.getByLabel("Email");
                page.getByLabel("Password");

         Placeholder Selectors
                page.getByPlaceholder("Search");
                page.getByPlaceholder("Enter your email");

        Built_In_Locators : 
          await page.getByAltText("Australian Aboriginal flag");// alt attribut value 
          await page.getByPlaceholder("linktr.ee/yourname").focus//use placeholder value
          await page.getByRole('button', { name: 'Open language dropdown' });;// get implicit & explicit. get the web element base on that role like button,checkbox 
          use tag and attribute=value for locat the element
          await page.getByText("Log in").click;// using inner text 
          await page.getByLabel("");// using the lable tag.
          await page.getByTitle("");//Allows locating elements by their title attribute.
          awiat page.getByTestId("")//You can locate the element by it's test id attribute.
