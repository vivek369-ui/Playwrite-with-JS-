# Playwrite-with-JS-
Extenstion used for JS : ESLint , Prettier – Code formatter , JavaScript (ES6) Code Snippets ,Live Server 
LOCATORS :

        const loginButton = page.locator('#login');
CSS Selector (most common) : 
page.locator('#idName')          // by ID
page.locator('.className')       // by class
page.locator('button')           // by tag
page.locator('input[name="q"]')  // by attribute
Text Locator : 
page.locator('text=Login')
page.locator('text=Submit')
page.getByText('Sign in')
Role Locator (recommended!) :
page.getByRole('button', { name: 'Login' })
page.getByRole('textbox', { name: 'Username' })
page.getByRole('link', { name: 'Home' })
