# Checklist: Admin Dashboard

**Created By:** M.B.

**Date of Creation:** 2026-01-31

**Executed By:** M.B.

**Date of Execution:** 2026-01-31

**Environment:** Edge v144 (latest stable)

## Header Navigation

- [x] **Admin panel** title is displayed in the header
- [ ] Clicking the **Admin panel** title redirects to the **Admin dashboard** page - Fail (BUG-AD-01)
- [x] **Main** link is displayed in the header
- [x] Clicking the **Main** link redirects to the **Admin dashboard** page
- [x] **Main** tab is highlighted with dark-brown when the **Admin dashboard** page is active
- [x] **Create post** link is displayed in the header
- [x] Clicking the **Create post** link redirects to the New post creation page
- [x] **Create post** tab is highlighted with dark-brown when the New post creation page is active
- [x] **To user's app** link is displayed in the header
- [x] Clicking the **To user's app** link redirects to the Home page
- [x] **Logout** link is displayed in the header
- [x] Clicking the **Logout** link finishes the user session
- [x] After logout, the user is redirected to the Login page

## Search Functionality

- [x] Search input is displayed on the **Admin dashboard** page
- [ ] Search input is highlighted with red when focused - Fail (BUG-AD-02)
- [x] Search input accepts text input
- [x] Entering a value in the search input filters posts in the table

## Table Header

- [x] Table header contains the following column titles:
  - [x] **#**
  - [x] **Author**
  - [x] **Title**
  - [x] **Created date**
  - [x] **Action**
- [x] Column titles **Author**, **Title**, and **Created date** are clickable

## Sorting

- [x] Clicking the **Author** column title sorts posts by author in ascending order
- [x] Clicking the **Title** column title sorts posts by title in ascending order
- [x] Clicking the **Created date** column title sorts posts by date in ascending order
- [x] Second click on **Author** sorts posts in descending order
- [x] Second click on **Title** sorts posts in descending order
- [x] Second click on **Created date** sorts posts in descending order

## Table Body

- [x] Table body displays post number
- [x] Table body displays post author
- [x] Table body displays post title
- [x] Table body displays post creation date
- [x] Table body displays **Edit** and **Delete** action buttons for each post

## Edit Post

- [x] **Edit** button is displayed for each post
- [x] Clicking **Edit** redirects the user to the Post edit page

## Delete Post

- [x] **Delete** button is displayed for each post
- [ ] Clicking **Delete** displays a confirmation message - Fail (BUG-AD-03)
- [ ] After confirming the deletion, deletes the post completely - Blocked (BUG-AD-03)
- [x] Deleted post disappears from the table immediately

## Loading State

- [x] While the post list is loading, the table displays the **Loading...** layout
- [ ] If there are no posts, the table displays the **Loading...** layout instead of posts - Blocked
