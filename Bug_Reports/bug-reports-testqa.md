# Bug Reports: Test QA Site

**Reported By:** M.B.

**Date of Reporting:** 2026-01-31

**Environment:** Edge v144 (latest stable)

## BUG-CP-01: Incorrect default value Actual until field

**ID:** BUG-CP-01

**Summary:** Default value **Actual until** field is not the actual date (today)

**Severity:** Minor

**Priority:** Medium

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin

**Steps to Reproduce:**

1. Open the [New post creation page](site/admin/create)
2. Observe the value of the **Actual until** field

**Expected Result:**

- **Actual until** field set to default value - the actual date (today)

**Actual Result:**

- **Actual until** field set to default value - the date after actual (tomorrow)

**Attachments:** None

**Status:** Open

## BUG-CP-02: Incorrect default state Create! button

**ID:** BUG-CP-02

**Summary:** **Create!** button is enabled when required fields are empty

**Severity:** Medium

**Priority:** Medium

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin

**Steps to Reproduce:**

1. Open the [New post creation page](site/admin/create)
2. Observe the state of the **Create!** button

**Expected Result:**

- **Create!** button is disabled

**Actual Result:**

- **Create!** button is enabled

**Attachments:** None

**Status:** Open

## BUG-CP-03: Incorrect Post title field validation (exceeds 255 characters)

**ID:** BUG-CP-03

**Summary:** Validation error message does not appear when the value **Post title** field exceeds 255 characters

**Severity:** Trivial

**Priority:** Medium

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Post title** field: string with 256 characters

**Steps to Reproduce:**

1. Enter a string of 256 characters into the **Post title** field
2. Verify that the **Post title** field shows an error and the post cannot be created

**Expected Result:**

- **Post title** field is highlighted in red and displays the error message: "Too long title"

**Actual Result:**

- **Post title** field is highlighted in red without displaying an error message

**Attachments:** None

**Status:** Open

## BUG-CP-04: Incorrect Post content field validation (empty field)

**ID:** BUG-CP-04

**Summary:** Validation error message does not appear when the value **Post content** field remains empty

**Severity:** Trivial

**Priority:** Medium

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Steps to Reproduce:**

1. Click on the **Post content** field
2. Click on another field
3. Verify that the **Post content** field shows an error message and the post cannot be created

**Expected Result:**

- **Post content** field is highlighted in red and displays the error message: "Content cannot be empty!"

**Actual Result:**

- **Post content** remains unchanged

**Attachments:** None

**Status:** Open

## BUG-CP-05: Incorrect Post an author field validation (exceeds 255 characters)

**ID:** BUG-CP-05

**Summary:** Validation error message does not appear when the value of the **Post an author** field exceeds 255 characters

**Severity:** Trivial

**Priority:** Medium

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Post an author** field: string with 256 characters

**Steps to Reproduce:**

1. Enter a string of 256 characters into the **Post an author** field
2. Verify that the **Post an author** field shows an error and the post cannot be created

**Expected Result:**

- **Post an author** field is highlighted in red and displays the error message: "Too long author name"

**Actual Result:**

- **Post an author** field is highlighted in red without displaying an error message

**Attachments:** None

**Status:** Open

## BUG-CP-06: User is not redirected after successful post creation

**ID:** BUG-CP-06

**Summary:** User is not redirected to **Dashboard page** after clicking **Create!** button and successful post creation

**Severity:** Minor

**Priority:** Medium

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened

**Steps to Reproduce:**

1. Enter valid data into the **Post title**, **Post content** and **Post an author** fields
2. Click the **Create!** button
3. Verify the result matches the expected behavior

**Expected Result:**

- User is redirected to the **Dashboard page**

**Actual Result:**

- User is not redirected to the **Dashboard page**

**Attachments:** None

**Status:** Open

## BUG-CP-07: No past date error message for Actual until

**ID:** BUG-CP-07

**Summary:** No error message if user tries to create a post with **Actual until** field is set to a past date

**Severity:** Trivial

**Priority:** Low

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Actual until** field: past date

**Steps to Reproduce:**

1. Set the **Actual until** field to a past date
2. Click the **Create!** button
3. Verify that the post cannot be created

**Expected Result:**

- Any error indication is displayed

**Actual Result:**

- Any error indication is not displayed

**Attachments:** None

**Status:** Open

## BUG-AD-01: Incorrect Admin panel title redirection

**ID:** BUG-AD-01

**Summary:** **Admin panel** title in the header redirects to **Home page** instead of **Admin dashboard**

**Severity:** Trivial

**Priority:** Medium

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin

**Steps to Reproduce:**

1. Open any admin page except **Admin dashboard**
2. Click **Admin panel** title in the header
3. Verify the result matches the expected behavior

**Expected Result:**

- User was redirected to **Admin dashboard**

**Actual Result:**

- User was redirected to **Home page**

**Attachments:** None

**Status:** Open

## BUG-AD-02: Incorrect highlighting color for focused search field

**ID:** BUG-AD-02

**Summary:** Focused search field highlighted with black instead of red

**Severity:** Trivial

**Priority:** Low

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [Admin dashboard page](site/admin/dashboard) is opened

**Steps to Reproduce:**

1. Click the search field
2. Verify the result matches the expected behavior

**Expected Result:**

- Search input is highlighted in red when focused

**Actual Result:**

- Search input is highlighted in black when focused

**Attachments:** None

**Status:** Open

## BUG-AD-03: Delete confirmation message is not displayed

**ID:** BUG-AD-03

**Summary:** Delete confirmation message is not displayed after clicking the **Delete** button in the table body

**Severity:** Medium

**Priority:** High

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [Admin dashboard page](site/admin/dashboard) is opened
- At least 1 post was created in the **Create post** page

**Steps to Reproduce:**

1. Click **Delete** button in the table body on any existing post
2. Verify the result matches the expected behavior

**Expected Result:**

- Any confirmation message is displayed

**Actual Result:**

- Confirmation message is not displayed

**Attachments:** None

**Status:** Open
