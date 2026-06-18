import { test, expect } from '@playwright/test';

test('Rocketseed End-to-End Assessment', async ({ page }) => {

  await test.step('Navigate to Rocketseed website', async () => {

    await page.goto('https://www.rocketseed.com');

    await expect(page).toHaveURL(/rocketseed/i);

    console.log('Successfully reached Rocketseed');
  });

  await test.step('Complete Contact Us popup', async () => {

    // Update selectors based on actual site

    await page.getByText('Contact Us').click();

    await page.locator('input[name="name"]').fill('Giovanni');

    await page.locator('input[name="email"]').fill('test@test.com');

    await page.locator('textarea').fill('This is a test');

    await page.screenshot({
      path: 'screenshots/contact-form-completed.png',
      fullPage: true
    });

    console.log('Contact form completed');
  });

  await test.step('Capture Features dropdown items', async () => {

    await page.hover('text=Features');

    const featureLinks = page.locator('.dropdown-menu a');

    const count = await featureLinks.count();

    console.log(`Found ${count} feature options`);

    for (let i = 0; i < count; i++) {

      const text = await featureLinks.nth(i).textContent();

      console.log(`Feature ${i + 1}: ${text}`);
    }
  });

  await test.step('Navigate through all Features pages', async () => {

    await page.hover('text=Features');

    const featureLinks = page.locator('.dropdown-menu a');

    const count = await featureLinks.count();

    for (let i = 0; i < count; i++) {

      await page.hover('text=Features');

      const link = featureLinks.nth(i);

      const featureName = await link.textContent();

      console.log(`Opening: ${featureName}`);

      await link.click();

      await page.waitForLoadState('networkidle');

      await expect(page.locator('h1').first()).toBeVisible();

      await page.screenshot({
        path: `screenshots/feature-${i + 1}.png`,
        fullPage: true
      });

      console.log(`Successfully opened: ${featureName}`);

      await page.goBack();

      await page.waitForLoadState('networkidle');
    }
  });
});