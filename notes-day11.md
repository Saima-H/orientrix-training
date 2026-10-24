# Saucedemo

The Basics: What is Playwright and QA Automation?
What is Playwright? Playwright is a tool made by Microsoft that writes code to control a web browser. Instead of you manually opening Chrome, typing a password, and clicking "Checkout", Playwright does it automatically in milliseconds.

What is End-to-End (E2E) Testing? It means testing the app exactly like a real user would. It clicks real buttons on a real website.

Why use TypeScript (.ts)? You used TypeScript in Next.js, and we are using it here. It gives you autocomplete and catches typos before you run the test.

What is a test block? It's just a function. It says: "Go to this website, fill in this box, click this button, and expect the page to change." If the page doesn't change, the test fails (turns red).

Headless vs. Headed:

Headless: The browser runs invisibly in the background. (Fast, used by companies).

Headed: You actually see the browser open, type, and click by itself. (Fun, used for debugging).
# HEADLESS
<img width="1274" height="636" alt="image" src="https://github.com/user-attachments/assets/88283ca4-ecdd-4f22-a256-ecf88db84912" />

# HEADED
(THE WEBSITE LITERALLY OPENED AND CLOSED LOL!)
<img width="638" height="320" alt="image" src="https://github.com/user-attachments/assets/e8eb3804-8eda-480d-a7a8-becea31c2b8d" />

Perfect plan. Let's nail the basics (SauceDemo) first to secure your grade, and then we will do the advanced version (Idea Vault) to make your portfolio shine.

Here is the absolute start-to-end guide for the **basic QA repository**.

---


### 🚀 Step 1: Setup the Folder and Install

Open your terminal (Command Prompt, PowerShell, or Git Bash). We will create a brand new folder outside of `idea-vault`.

```bash
# 1. Go to your Desktop
cd Desktop

# 2. Create the folder and go inside
mkdir qa-saucedemo-playwright
cd qa-saucedemo-playwright

# 3. Initialize Git
git init

# 4. Initialize Node.js (creates package.json)
npm init -y

# 5. Install Playwright
npm install -D @playwright/test

# 6. Install the Chromium browser
npx playwright install chromium
```

---

### 🚀 Step 2: Create the Files

Open the `qa-saucedemo-playwright` folder in VS Code. Create the following 4 files.

#### File 1: `saucedemo.spec.ts`
*(This is the actual test code. Create the file and paste this inside).*

```typescript
import { test, expect } from '@playwright/test';

test('1. Successful login', async ({ page }) => {
  await page.goto('https://www.saucedemo.com/');
  await page.fill('#user-name', 'standard_user');
  await page.fill('#password', 'secret_sauce');
  await page.click('#login-button');
  await expect(page).toHaveURL('https://www.saucedemo.com/inventory.html');
});

test('2. Login failure with incorrect password', async ({ page }) => {
  await page.goto('https://www.saucedemo.com/');
  await page.fill('#user-name', 'standard_user');
  await page.fill('#password', 'wrong_password');
  await page.click('#login-button');
  await expect(page.locator('[data-test="error"]')).toBeVisible();
});

test('3. Adding a product to the cart', async ({ page }) => {
  await page.goto('https://www.saucedemo.com/');
  await page.fill('#user-name', 'standard_user');
  await page.fill('#password', 'secret_sauce');
  await page.click('#login-button');
  
  await page.click('#add-to-cart-sauce-labs-backpack');
  await expect(page.locator('.shopping_cart_badge')).toHaveText('1');
});

test('4. Completing the checkout flow', async ({ page }) => {
  await page.goto('https://www.saucedemo.com/');
  await page.fill('#user-name', 'standard_user');
  await page.fill('#password', 'secret_sauce');
  await page.click('#login-button');
  
  await page.click('#add-to-cart-sauce-labs-backpack');
  await page.click('.shopping_cart_link');
  await page.click('#checkout');
  
  await page.fill('#first-name', 'Saima');
  await page.fill('#last-name', 'Khan');
  await page.fill('#postal-code', '12345');
  await page.click('#continue');
  await page.click('#finish');
  
  await expect(page.locator('.complete-header')).toHaveText('Thank you for your order!');
});

test('5. Logging out', async ({ page }) => {
  await page.goto('https://www.saucedemo.com/');
  await page.fill('#user-name', 'standard_user');
  await page.fill('#password', 'secret_sauce');
  await page.click('#login-button');
  
  await page.click('#react-burger-menu-btn');
  await page.click('#logout_sidebar_link');
  await expect(page).toHaveURL('https://www.saucedemo.com/');
});
```

#### File 2: `.gitignore`
*(This stops you from uploading massive browser files to GitHub).*

```text
node_modules/
test-results/
playwright-report/
```

#### File 3: `thinking.md`
*(This is required by your assignment).*

```markdown
# QA Thinking: Exam Results Application

**Question:** If an application shows exam results to students, what are the five worst things that could go wrong, and how would you test for each?

1. **Data Leakage (Student sees another student's results):** 
   * *How to test:* Log in as Student A. Try to manually change the URL or API request to fetch Student B's ID. The system should block it (403 Forbidden).
2. **Incorrect Grade Calculation (Math error):** 
   * *How to test:* Manually calculate the expected grade based on the input marks. Compare it to the system's output. Test edge cases like 0 marks, 100 marks, and decimal marks.
3. **Server Crash on High Traffic (Results day overload):** 
   * *How to test:* Use a load testing tool to simulate 10,000 students logging in at the exact same second. The server should not crash.
4. **Data Loss (Results disappear after refresh):** 
   * *How to test:* Load the results page, hit refresh 10 times, and verify the data remains intact and unchanged.
5. **Admin Bypass (Student accessing admin panel):** 
   * *How to test:* Log in as a student. Try to access `/admin/dashboard`. The system should deny access and redirect them to the home page.
```

#### File 4: `README.md`
*(Documentation for your new repo).*

```markdown
# SauceDemo QA Automation Tests

This repository contains 5 automated end-to-end (E2E) browser tests for [saucedemo.com](https://www.saucedemo.com), written using Playwright and TypeScript.

## Test Coverage
1. Successful Login
2. Login Failure (Incorrect Password)
3. Adding a product to the cart
4. Completing the checkout flow
5. Logging out

## Prerequisites
- Node.js installed

## How to Install Dependencies
```bash
npm install
npx playwright install chromium
```

## How to Run the Tests
**Headless (Invisible browser):**
```bash
npx playwright test
```

**Headed (Watch the browser click):**
```bash
npx playwright test --headed
```
```

---

### 🚀 Step 3: Run the Tests

In your terminal, run:
```bash
npx playwright test --headed
```

You should see a Chrome browser open, log in, click a backpack, and check out. At the end, your terminal will say **`5 passed`**. 

*(If any test fails, check if you accidentally missed a capital letter in the `page.fill` selectors).*

---

### 🚀 Step 4: Push to GitHub

1. Go to [github.com/new](https://github.com/new).
2. Name it `qa-saucedemo-playwright`.
3. **Do not** check any boxes (no README, no .gitignore). Click **Create repository**.
4. In your terminal, run:

```bash
git add .
git commit -m "Initial commit: Playwright tests and QA documentation"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/qa-saucedemo-playwright.git
git push -u origin main
```
*(Replace `YOUR_USERNAME` with your actual GitHub username).*

---

### 🏁 Finished with Basics!
Once you see the files on GitHub, the basic assignment is complete! 

**Reply when you have the `5 passed` and the repo is live.** Then we will do the **Bonus Idea Vault test** to make your portfolio stand out!



