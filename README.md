# filter-vote-items-mockup
## About the project
This project is to build a mockup application allowing us to search/filter, vote (up or down) on an item in a list of items. See sample of project output here

## Instructions
- Using vue cli to init the project
    - `vue create [project-name]`
    - choose default preset (Vue3)
- Sample data: `src/data.json`
- Style: `src/assets/styles.css`
- Create a new PostComponent.vue under components folder and paste the code below into the template section:
```
<div class="container">
    <div class="search-wrapper">
      <input type="text" placeholder="Search title.."/>
          <label>Search title:</label>
    </div>
    <div class="wrapper">
      <div class="card">


        <div class="votes">
          <div class="upvote"></div>
          <div class="number-of-votes">0</div>
          <div class="downvote"></div>
        </div>
        
        <a href="https://vuejs.org/" target="_blank">
          <img src="https://vuejs.org//images/logo.png"/>
          <small>posted by: Tim</small>
          VueJS
        </a>
      </div>
    </div>
  </div>
```
- Then import data.json in PostComponent and follow the instruction below
    - List each posts from data.json file
    - When user type on search box, filter all posts by title
    - When user click on up-vote button, increase post’s votes value by 1
    - When user click on down-vote button, decrease post’s votes value by 1
    - If votes value equal 0, show green color
    - If votes value smaller than 0, show red color
    - If votes value bigger than 0, show green color
    - If votes value smaller than or equal 10, disable down-vote click
