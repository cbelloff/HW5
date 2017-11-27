# SI 364 - Final Project questions

## Overall

* **What's a one-two sentence description of what your app will do?**
As a senior I am constantly applying for jobs upon graduation, but am having a hard time keeping track of the companies I applied to, the specific job I applied for, and its location. Therefore, my application will provide users with the ability to store the companies that they applied to on LinkedIn along with where these companies are located as well as the position they applied for.

## The Data

* **What data will your app use? From where will you get it? (e.g. scraping a site? what site? -- careful not to run it too much. An API? Which API?)**
I will use LinkedIn's API.

* **What data will a user need to enter into a form?**
Users will be required to enter their desired job title/ field and their desired location.

* **How many fields will your form have? What's an example of some data user might enter into it?**
Therefore, my form will have 2 fields: job and location.

* **After a user enters data into the form, what happens? Does that data help a user search for more data? Does that data get saved in a database? Does that determine what already-saved data the user should see?**
Once users enter their desired job field and their desired location to work, then the LinkedIn API will be called and a list of companies that meet these requests will be provided. If users have not already applied to these companies, then they can apply and the company, its location, and its job title will be stored into a database.

* **What models will you have in your application?**
I will create a model that includes the name of each company users applied to, the locations they applied to, and the specific jobs they applied for as well. 

* **What fields will each model have?**
Within the company table, there will be a column for the name of each company and the company ID. In the locations model, there will be a field for the location as well as the location ID. Lastly, in the jobs model, there will not only be a column for the job and the job ID, but there will also be a column for company ID and location ID, as they will act as foreign keys.

* **What uniqueness constraints will there be on each table? (e.g. can't add a song with the same title as an existing song)**
I will program my application to check if there is a job in the database that exists already with that company and location, and if it already exists, then it cannot be added into the database again.

* **What relationships will exist between the tables? What's a 1:many relationship between? What about a many:many relationship?**
A many to many relationship would exist between the companies table and locations table because one company can have many locations and one location can have many companies. A 1:many relationship exists between the companies table and jobs table because for one company there are many jobs, but there is only one specific job per company. For example, the job business analyst position 5 only exists for one company. A 1:many relationship also exists between the location table and jobs table because one location can have many jobs, but one specific job can only exist in its one location.

* **How many get_or_create functions will you need? In what order will you invoke them? Which one will need to invoke at least one of the others?**
I will create 3 get_or_create functions. First, I will get the name of the company, then its location, and then its job title. 

## The Pages

* **How many pages (routes) will your application have?**
I will have an index route that contains my form and an all_companies route that will have all the companies that result from the form data.

* **How many different views will a user be able to see, NOT counting errors?**
There will be a form view and an information page view.

* **Basically, what will a user see on each page / at each route? Will it change depending on something else -- e.g. they see a form if they haven't submitted anything, but they see a list of things if they have?**
Users will only see the company page (all_companies) if they filled out the form with their desired location and job. 
## Extras

* **Why might your application send email?**
My application may send emails to remind users what jobs they just applied to and added to their database, or it can send an email reminding them what they searched for as soon as they submit the form in order to prevent users from performing the same search more than once.

* **If you plan to have user accounts, what information will be specific to a user account? What can you only see if you're logged in? What will you see if you're not logged in -- anything?**
N/A

* **What are your biggest concerns about the process of building this application?**
I am concerned with the fact that a company ID can be used multiple times in the jobs table because users can be applying for many different jobs from the same company, but can this information not be repeated if song titles were not able to be used more than once? Was this a constraint that you added yourself, but it is in fact allowed to repeat? This also will occur with location ID column in the job table because different jobs can be located in the same location. Also, I was wondering if there was any other information I can add to my companies and location table, so the only columns in the table are not just the company or location and its ID.