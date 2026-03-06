import { test } from '@playwright/test'

test.beforeEach(async ({ page }) => {
  await page.goto('http://localhost:4200/')
})

test.describe('Charts Suite', () => {

  test.beforeEach(async ({ page }) => {
    // optional setup
  })

  test('the first test', async ({ page }) => {
    await page.getByText('Form Layouts').click()
  })

  test('navigate to datepicker page', async ({ page }) => {
    await page.getByText('Datepicker').click()
  })

})

test.describe('Forms Suite', () => {

  test.beforeEach(async ({ page }) => {
    await page.getByText('Forms').click()
  })

  test('the first test1', async ({ page }) => {
    await page.getByText('Form Layouts').click()
  })

  test('navigate to datepicker page1', async ({ page }) => {
    await page.getByText('Datepicker').click()
  })

  test('Locator syntax rules', async ({ page }) => {

    page.locator('input')
    page.locator('#inputEmail1')
    page.locator('.shape-rectangle')
    page.locator('[placeholder="Email"]')

    page.locator('[class="input-full-width size-medium status-basic shape-rectangle nb-transition"]')

    page.locator('input[placeholder="Email"].shape-rectangle')

    page.locator('//*[@id="inputEmail1"]')

    page.locator(':text("Using")')

    page.locator(':text-is("Using the Grid")')
  })

})
