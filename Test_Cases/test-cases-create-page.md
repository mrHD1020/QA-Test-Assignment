# Test Cases: Create Post

**Created By:** Mikhail Basov

**Date of Creation:** 2026-01-29

**Executed By:** Mikhail Basov

**Date of Execution:** 2026-01-31

## Creation page

### Validation: Initial state of New post creation page

**ID:** TC-CP-POS-01

**Summary:** Validation of **Post title** field remains empty

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin

**Steps:**

1. Open the [New post creation page](site/admin/create)
2. Observe **Post title**, **Post content**, **Post an author** and **Actual until** fields
3. Observe the state of the **Create!** button

**Expected Result:**

- **Post title**, **Post content** and **Post an author** fields are empty
- **Actual until** field set to default value - the actual date (today)
- **Create!** button is disabled
- No validation error messages are displayed

**Actual Result:**

- **Post title**, **Post content** and **Post an author** fields are empty - Pass
- **Actual until** field set to default value - the date after actual (tomorrow) - Fail (BUG-CP-01)
- **Create!** button is enabled - Fail (BUG-CP-02)
- No validation error messages are displayed - Pass

**Status:** Failed

**Related Bugss:**

- BUG-CP-01 - Incorrect default value Actual until field
- BUG-CP-02 - Incorrect default state Create! button

### Functionality: Post Creation with valid values

**ID:** TC-CP-POS-02

**Summary:** Functionality of post creation with valid required fields

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened

**Steps:**

1. Enter valid data into the **Post title**, **Post content** and **Post an author** fields
2. Click the **Create!** button
3. Verify the result matches the expected behavior

**Expected Result:**

- Post is created and displayed on the dashboard

**Actual Result:**

- Post is created and displayed on the dashboard - Pass

**Status:** Passed

## Post title field

### Functionality: Post Creation with 1 character title

**ID:** TC-PT-POS-01

**Summary:** Functionality of post creation with valid **Post title**

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Post title** field: string with 1 character

**Steps:**

1. Enter a string of 1 character into the **Post title** field
2. Click the **Create!** button

**Expected Result:**

- Post is created and displayed on the dashboard

**Actual Result:**

- Post is created and displayed on the dashboard - Pass

**Status:** Passed

### Functionality: Post Creation with 255 characters title

**ID:** TC-PT-POS-02

**Summary:** Validation of post creation with filled **Post title**

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Post title** field: string with 255 characters

**Steps:**

1. Enter a string of 255 characters into the **Post title** field
2. Click the **Create!** button

**Expected Result:**

- Post is created and displayed on the dashboard

**Actual Result:**

- Post is created and displayed on the dashboard - Pass

**Status:** Passed

### Validation: Leave title field empty

**ID:** TC-PT-NEG-01

**Summary:** Validation of **Post title** field remains empty

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Steps:**

1. Click on the **Post title** field
2. Click on another field
3. Verify that the **Post title** field shows an error message and the post cannot be created

**Expected Result:**

- **Post title** field is highlighted in red and displays the error message: "Title cannot be empty!"
- **Create!** button remains disabled

**Actual Result:**

- **Post title** field is highlighted in red and displays the error message: "Title cannot be empty!" - Pass
- **Create!** button still enabled from the start of the test - Blocked (BUG-CP-02)

**Status:** Partially Blocked

**Blocked by:** BUG-CP-02 - Incorrect default state Create! button

### Validation: Title input exceeds 255 characters

**ID:** TC-PT-NEG-02

**Summary:** Validation of **Post title** field for input longer than 255 characters

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Post title** field: string with 256 characters

**Steps:**

1. Enter a string of 256 characters into the **Post title** field
2. Verify that the **Post title** field shows an error and the post cannot be created

**Expected Result:**

- **Post title** field is highlighted in red and displays an error message: "Too long title"
- **Create!** button remains disabled

**Actual Result:**

- **Post title** field is highlighted in red without displaying an error message - Fail (BUG-CP-03)
- **Create!** button still enabled from the start of the test - Blocked (BUG-CP-02)

**Status:** Partially Blocked

**Blocked by:** BUG-CP-02 - Incorrect default state Create! button

**Related Bugs:** BUG-CP-03 - Incorrect Post title field validation (exceeds 255 characters)

### Validation: Title allow only string values

**ID:** TC-PT-NEG-03

**Summary:** Validation of **Post title** field for input allow only string values

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Post title** field: any complicated symbol (e.g. ' " < > / 🇪🇺 or surrogate pairs emoji)

**Steps:**

1. Enter any complicated symbol into the **Post title** field
2. Try to click **Create!** button if it is possible
3. Verify that the actual result matches at least one of the expected outcomes

**Expected Result:**

Input field should handle unexpected characters correctly. Possible outcomes include:

1. Unexpected characters cannot be entered (input is blocked)
2. Unexpected characters are entered but creating the post fails with an error
3. Post is created and unexpected characters is converted to a string or removed

**Actual Result:**

- Post is created and some unexpected characters is converted to a string another some was removed - Pass

**Status:** Passed

## Post content field

### Functionality: Post Creation with 1 character content

**ID:** TC-PC-POS-01

**Summary:** Functionality of post creation with valid **Post content**

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Post content** field: string with 1 character

**Steps:**

1. Enter a string of 1 character into the **Post content** field
2. Click the **Create!** button

**Expected Result:**

- Post is created and displayed on the dashboard

**Actual Result:**

- Post is created and displayed on the dashboard - Pass

**Status:** Passed

### Functionality: Post Creation with large text content

**ID:** TC-PC-POS-02

**Summary:** Validation of post creation with filled **Post content** with large text

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Post content** field: string with 10000 characters

**Steps:**

1. Enter a 10000 characters text into the **Post content** field
2. Click the **Create!** button

**Expected Result:**

- Post is created and displayed on the dashboard

**Actual Result:**

- Post is created and displayed on the dashboard - Pass

**Status:** Passed

### Functionality: Post Creation with inserted image content

**ID:** TC-PC-POS-03

**Summary:** Validation of post creation with inserted in **Post content** field image

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Post content** field: any image

**Steps:**

1. Insert any image into the **Post content** field
2. Click the **Create!** button

**Expected Result:**

- Post is created and displayed on the dashboard

**Actual Result:**

- Post is created and displayed on the dashboard - Pass

**Status:** Passed

### Functionality: Post Creation with complicated symbols content

**ID:** TC-PC-POS-04

**Summary:** Validation of post creation with filled **Post content** with complicated symbols

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Post content** field: any complicated symbol (e.g. ' " < > / 🇪🇺 or surrogate pairs emoji)

**Steps:**

1. Insert any complicated symbol into the **Post content** field
2. Click the **Create!** button

**Expected Result:**

- Post is created and displayed on the dashboard

**Actual Result:**

- Post is created and displayed on the dashboard - Pass

**Status:** Passed

### Validation: Leave content field empty

**ID:** TC-PC-NEG-01

**Summary:** Validation of **Post content** field remains empty

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Steps:**

1. Click on the **Post content** field
2. Click on another field
3. Verify that the **Post content** field shows an error message and the post cannot be created

**Expected Result:**

- **Post content** field is highlighted in red and displays the error message: "Content cannot be empty!"
- **Create!** button remains disabled

**Actual Result:**

- **Post content** remains unchanged - Fail (BUG-CP-04)
- **Create!** button still enabled from the start of the test - Blocked (BUG-CP-02)

**Status:** Partially Blocked

**Blocked by:** BUG-CP-02 - Incorrect default state Create! button

**Related Bugs:** BUG-CP-04 - Incorrect Post content field validation (empty field)

## Post an author field

### Functionality: Post Creation with 1 character author

**ID:** TC-PA-POS-01

**Summary:** Functionality of post creation with valid **Post an author**

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Post an author** field: string with 1 character

**Steps:**

1. Enter a string of 1 character into the **Post an author** field
2. Click the **Create!** button

**Expected Result:**

- Post is created and displayed on the dashboard

**Actual Result:**

- Post is created and displayed on the dashboard - Pass

**Status:** Passed

### Functionality: Post Creation with 127 character author

**ID:** TC-PA-POS-02

**Summary:** Validation of post creation with filled **Post an author**

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Post an author** field: string with 127 characters

**Steps:**

1. Enter a string of 127 characters into the **Post an author** field
2. Click the **Create!** button

**Expected Result:**

- Post is created and displayed on the dashboard

**Actual Result:**

- Post is created and displayed on the dashboard - Pass

**Status:** Passed

### Validation: Leave author field empty

**ID:** TC-PA-NEG-01

**Summary:** Validation of **Post title** field remains empty

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Steps:**

1. Click on the **Post title** field
2. Click on another field
3. Verify that the **Post title** field shows an error message and the post cannot be created

**Expected Result:**

- **Post title** field is highlighted in red and displays the error message: "Author cannot be empty"
- **Create!** button remains disabled

**Actual Result:**

- **Post title** field is highlighted in red and displays the error message: "Author cannot be empty" - Pass
- **Create!** button still enabled from the start of the test - Blocked (BUG-CP-02)

**Status:** Partially Blocked

**Blocked by:** BUG-CP-02 - Incorrect default state Create! button

### Validation: Author input exceeds 127 characters

**ID:** TC-PA-NEG-02

**Summary:** Validation of **Post an author** field for input longer than 127 characters

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Post an author** field: string with 128 characters

**Steps:**

1. Enter a string of 128 characters into the **Post an author** field
2. Click the **Create!** button
3. Verify that the post cannot be created

**Expected Result:**

- Any error indication is displayed
- The post was not created

**Actual Result:**

- **Post an author** field is highlighted in red without displaying an error message - Pass
- The post was not created - Pass

**Status:** Passed

### Validation: Author input exceeds 255 characters

**ID:** TC-PA-NEG-03

**Summary:** Validation of **Post an author** field for input longer than 255 characters

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Post an author** field: string with 256 characters

**Steps:**

1. Enter a string of 256 characters into the **Post an author** field
2. Verify that the **Post an author** field shows an error and the post cannot be created

**Expected Result:**

- **Post an author** field is highlighted in red and displays the error message: "Too long author name"
- **Create!** button remains disabled

**Actual Result:**

- **Post an author** field is highlighted in red without displaying an error message - Fail (BUG-CP-05)
- **Create!** button still enabled from the start of the test - Blocked (BUG-CP-02)

**Status:** Partially Blocked

**Blocked by:** BUG-CP-02 - Incorrect default state Create! button

**Related Bugs:** BUG-CP-05 - Incorrect Post an author field validation (exceeds 255 characters)

### Validation: Author allow only string values

**ID:** TC-PA-NEG-04

**Summary:** Validation of **Post an author** field for input allow only string values

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Post an author** field: any complicated symbol (e.g. ' " < > / 🇪🇺 or surrogate pairs emoji)

**Steps:**

1. Enter any complicated symbol into the **Post an author** field
2. Try to click **Create!** button if it is possible
3. Verify that the actual result matches at least one of the expected outcomes

**Expected Result:**

Input field should handle unexpected characters correctly. Possible outcomes include:

1. Unexpected characters cannot be entered (input is blocked)
2. Unexpected characters are entered but creating the post fails with an error
3. Post is created, but unexpected characters are converted to a string or removed

**Actual Result:**

- Post is created and some unexpected characters are converted to a string, another one was removed - Pass

**Status:** Passed

## Actual until field

### Functionality: Post Creation with today's date

**ID:** TC-AU-POS-01

**Summary:** Functionality of post creation with valid **Actual until** field

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Actual until** field: today's date

**Steps:**

1. Set the **Actual until** field on today's date
2. Click the **Create!** button

**Expected Result:**

- Post is created and displayed on the dashboard

**Actual Result:**

- Post is created and displayed on the dashboard - Pass

**Status:** Passed

### Functionality: Post Creation with future date

**ID:** TC-AU-POS-02

**Summary:** Functionality of post creation with future date in **Actual until** field

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Actual until** field: tomorrow's date

**Steps:**

1. Set the **Actual until** field on tomorrow's date
2. Click the **Create!** button

**Expected Result:**

- Post is created and displayed on the dashboard

**Actual Result:**

- Post is created and displayed on the dashboard - Pass

**Status:** Passed

### Validation: Post Creation with past date

**ID:** TC-AU-NEG-01

**Summary:** Validation of post creation with past date in **Actual until** field

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Actual until** field: past date

**Steps:**

1. Set the **Actual until** field on past date
2. Click the **Create!** button
3. Verify that the post cannot be created

**Expected Result:**

- Any error indication is displayed
- The post was not created

**Actual Result:**

- Any error indication is not displayed - Fail (BUG-CP-07)
- The post was not created - Pass

**Status:** Failed

**Related Bugs:** BUG-CP-07 - No past date error message for Actual until

### Validation: Post Creation with invalid date

**ID:** TC-AU-NEG-02

**Summary:** Validation of post creation with invalid date in **Actual until** field

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened
- All other required fields contain valid data

**Test Data:**

- **Actual until** field: invalid date (e.g. 2026-02-31)

**Steps:**

1. Set the **Actual until** field on invalid date
2. Click the **Create!** button
3. Verify that the post cannot be created

**Expected Result:**

- Any error indication is displayed
- The post was not created

**Actual Result:**

- The post was created with invalid **Actual until** date - Fail

**Status:** Failed

## Create! button

### Validation: Button becomes active with valid values in all required fields

**ID:** TC-CB-POS-01

**Summary:** Validation of **Create!** button if all required fields are filled with valid values

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened

**Steps:**

1. Enter valid data into the **Post title**, **Post content** and **Post an author** fields
2. Verify the result matches the expected behavior

**Expected Result:**

- **Create!** button becomes active

**Actual Result:**

- **Create!** button still enabled from the start of the test - Blocked (BUG-CP-02)

**Status:** Blocked

**Blocked by:** BUG-CP-02 - Incorrect default state Create! button

### Validation: Button becomes inactive after sending valid data

**ID:** TC-CB-POS-02

**Summary:** Validation of **Create!** button becomes inactive after click and sending valid data to the server

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened

**Steps:**

1. Enter valid data into the **Post title**, **Post content** and **Post an author** fields
2. Click the **Create!** button
3. Verify the result matches the expected behavior

**Expected Result:**

- **Create!** button becomes inactive after sending

**Actual Result:**

- **Create!** button becomes inactive after sending - Pass

**Status:** Passed

### Functionality: User redirection after sending valid data

**ID:** TC-CB-POS-03

**Summary:** Functionality of **Create!** button redirects user after click and sending valid data to server

**Pre-Conditions:**

- User is logged in [Test QA Site](site/) as admin
- [New post creation page](site/admin/create) is opened

**Steps:**

1. Enter valid data into the **Post title**, **Post content** and **Post an author** fields
2. Click the **Create!** button
3. Verify the result matches the expected behavior

**Expected Result:**

- User is redirected to the **Dashboard page** after sending

**Actual Result:**

- User is not redirected to the **Dashboard page** after sending - Fail (BUG-CP-06)

**Status:** Failed

**Related Bugs:** BUG-CP-06 - User is not redirected after successful post creation
