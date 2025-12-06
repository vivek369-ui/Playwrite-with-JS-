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
                page.getByRole() to locate by explicit and implicit accessibility attributes.
                page.getByText() to locate by text content.
                page.getByLabel() to locate a form control by associated label's text.
                page.getByPlaceholder() to locate an input by placeholder.
                page.getByAltText() to locate an element, usually image, by its text alternative.
                page.getByTitle() to locate an element by its title attribute.
                page.getByTestId() to locate an element based on its data-testid attribute (other attributes can be configured).
