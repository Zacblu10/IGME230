# Project 2 Documentation
My project uses The Meal DB api(https://www.themealdb.com/api.php) to create a platform where users can search to find something they could 
cook for dinner. Each result contains the name of the recipe, the category of the recipe, the cuisine of the recipe, as well as a link to 
a youtube video detailing the process for making the recipe. I believe that my project is an A level project.
## Basic Features
* Search box
  * The user can type any search term into the box and if a recipe exists with the search term in the name then the results will be 
  displayed below. 
  * This method is prioritized over the method below.  If anything is in the search box it will search by term as opposed to
  by category
* Category Search
  * The user can also simply select a category from the drop down list and the top 25 recipies in that category will be displayed.  This 
  method of searching takes longer to finish then searching by term since a query has to be made for each recipe instead of as a whole.
  This is neccessary because searcing by category only returns the name of the recipe and the rest of the information has to be gained by 
  querying another api offered my The Meal DB.  "Searching" will be displayed on the bottom of the scene.  
* Filters
  * The user has two options to filter the results. Filters can be reached by clicking on the "Filters" button.  They must be applied 
  before the go button is clicked
    * Filter by category: Only the results of the category chosen will be displayed. Note: filtering by category while searching by category
    will not change the results.
    * Filter by cuisine: Only results matching the selected cuisine will be returned 
### Error handling
* The message "No results found" will be printed whenever no results are returned from the API
* The message "Please enter a search term or category" will be displayed when the user does not enter either a search term or a category
### Web storage
The last term searched will be stored for the user. The message "Enter a search term!" is set as the placeholder text if no stored 
value is found. 
## Above and Beyond Features
* Sorting
  * Once the results are loaded the user can sort by clicking on the category headers(Note: this is not available in mobile mode as the 
  UI changes significantly enough that this feature is not necessary).  The "Name", "Category", and "Cuisine" column can all be sorted. 
  The sorting is accomplished using customing sorting methods used to put the results in alphabetical order. 
* Mobile interface change
  * The table interface for the results was less intuitive on mobile and therefore was changed to be capsule oriented.  A combination 
  of CSS and JavaScript media queries were used to accomplish this.  The dom event onResize has a method hooked up to it that will change 
  the text within each recipe to contain the category headers as part of the capsule instead of column headers in the grid.  This is 
  done by grabbing hidding the main column headers with display:"none" and then modifying the text.  This method works both ways and will 
  return the layout to the orignal format if the window gets above a certain width.  A call to this method was added to the end of the
  method to display the results so that if search is called while in mobile mode the results will be returned in mobile mode without have 
  to resize the windows to trigger onResize. CSS was used to style the capsules to be visually appealing as standalone units as opposed
  in a grid. 
## Resources
  * Background image: Created for this project by Zoe Martin - zgm5012@psu.edu 
  * CSS: Skeleton Framework by Dave Gamache
  * Fonts: Titan One, Cherry Cream Soda - Obtained from Google Fonts
