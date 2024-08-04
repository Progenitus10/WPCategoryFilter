# WPCategoryFilter
Dynamic Category Filter for WordPress Sidebar  This code dynamically filters sidebar categories based on the current page or category. It hides specified categories unless the user is on certain pages, ensuring a clean and relevant display of categories. Perfect for blogs with multiple sections needing distinct category visibility.

1. Purpose:
   - The goal is to show specific categories in the sidebar only on their relevant pages and to hide them on other pages.

2. When You're Not on a Specific Page:
   - Imagine you have a list of categories that are meant for a specific page. When you're visiting any other page, these categories will be hidden.

3. When You're Not on Another Specific Page:
   - Similarly, you have a list of categories for another specific page. When you're on any page other than this specific page, these categories will be hidden.

4. Applying the Rules:
   - These rules are automatically applied to your sidebar. When you visit a page, it checks which page you're on and hides the categories that don't belong to that page.

### Example:

- Visiting the First Specific Page:
  - All the categories intended for this page will be shown.
  - The categories intended for other pages will be hidden.

- Visiting the Second Specific Page:
  - All the categories intended for this page will be shown.
  - The categories intended for other pages will be hidden.

- Visiting Any Other Page:
  - The categories specific to other pages will be hidden.

By setting it up this way, each page only shows the categories that are relevant to it, keeping the sidebar clean and organized.

### The Code Explanation:

1. Function Definition:
   - `function filter_widget_categories($args) {}`: This starts a function that will filter which categories are shown in the sidebar.

2. Checking the Page:
   - `if (!is_page('specific-page-slug-1') && !is_category(array(IDs for categories of first page))) {}`:
     - This checks if the current page is not the first specific page or its related categories. If true, it hides the categories for this page.

   - `elseif (!is_page('specific-page-slug-2') && !is_category(array(IDs for categories of second page))) {}`:
     - This checks if the current page is not the second specific page or its related categories. If true, it hides the categories for this page.

3. Hiding Categories:
   - `$args['exclude'] = 'category-IDs-to-hide';`:
     - This tells the sidebar to exclude (hide) the categories listed by their IDs.

4. Applying the Filter:
   - `add_filter('widget_categories_args', 'filter_widget_categories');`:
     - This applies the function to the categories widget in the sidebar, making sure the right categories are shown or hidden based on the page you're on.
    
     - 
