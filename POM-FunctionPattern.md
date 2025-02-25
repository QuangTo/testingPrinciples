## Description

POM used to a supper star pattern for a while with very much benefits (come along with Selenium/WebDriver). But the thing has changed, web app nowday is designed and builded as a micro component blocks rather than a page. Otherwise many new Framework support very well for get and use web element like Cypress, or Playwright. It making Inheritance Pattern is out of date.

For example Playwright build-in has its own function like:

```
await page.goto('https://example.com');
await page.getByRole('button', { name: 'Login' }).click();
await test.use(customFunction)
```

### POM problem

- Too much unnecessary code (duplication code & over-abstraction)
- Too hard for debugging

## Code sample

#### Traditional POM

```
import { Page, Locator, expect } from "@playwright/test";
export class Footer {
  readonly page: Page;
  readonly privacyPolicy: Locator;

  constructor(page: Page) {
    this.page = page;
    this.privacyPolicy = page.getByTestId("privacyPolicy");
  }
  async clickPrivacyLink(): Promise<void> {
    expect(this.privacyPolicy).toBeVisible();
    expect(this.privacyPolicy).toHaveAttribute("href");
    await this.privacyPolicy.click();
  }
}
```

Usage

```
let footer: Footer;
footer = new Footer(page);
await footer.clickPrivacyLink();
```

#### Function Pattern

- Simple and use directly.

```
import { Page, expect } from "@playwright/test";

export const Footer = {
  async clickPrivacyLink(page: Page, policyId: string = "privacyPolicy") {
    const privacyLink = page.getByTestId(policyId);
    expect(privacyLink).toBeVisible();
    expect(privacyLink).toHaveAttribute("href");
    await privacyLink.click();
  },
};
```

Usage

```
await Footer.clickPrivacyLink(page)
```

## Centralize Code Locator

```

export const loginLocators = {
    username: '[data-testid="username"]',
    password: '[data-testid="password"]',
    submitButton: '[data-testid="login-id"]',
};

// Using Login data

import { loginLocators } from './locators.js';

export async function enterUsername(page, username) {
    await page.fill(loginLocators.username, username);
}

export async function login(page, username, password) {
    await enterUsername(page, username);
    await page.fill(loginLocators.password, password);
    await page.click(loginLocators.submitButton);
}

// Usage in a test
await enterUsername(page, 'testUser');
await login(page, 'testUser', 'password123');
```

### Centralize and use test-data
