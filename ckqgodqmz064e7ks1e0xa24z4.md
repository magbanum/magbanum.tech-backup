## Octoprofile - the Django project

I am very happy to share with you the Django project I have been working on last 20 days, it's called an Octoprofile. Project Octoprofile displays the GitHub profile in a better way with Charts and sortable lists. 

Octoprofile collects the user information on GitHub using GitHub API endpoints and then Django's function-based view passes it to the template after manipulating the data.

To view your Octoprofile visit [octoprofile.herokuapp.com](https://octoprofile.herokuapp.com/) and enter your GitHub username. Don't have a GitHub profile, check mine by typing `magbanum` or by clicking [here](https://octoprofile.herokuapp.com/profile/?username=magbanum).
The website might be slower for the first load as the project is deployed on Heroku's free dyno.

I have worked a lot on the coding and researching part as I had to make everything from scratch.  As I didn't know JavaScript I faced problems in the beginning while sorting the list and displaying the charts. But with the basics of JavaScript and few JavaScript libraries (ChartJS & ListJS), I was able to make them all work.

#### About the project
I have created an app inside the Django project called `profiles` and created two templates `home.html` for the landing page and `profile_page.html` for the profile page. 

The function-based views `get_username` and `get_repodata` are used to collect and manipulate the data and pass it to the template `profile_page.html`. The class-based API views `TopLanguages`, `MostStarred`, and `StarsPerLanguages` are used to create API endpoints for top languages by the user, most starred repositories of the user, and stars per languages respectively. Check out  [GitHub repository](https://github.com/magbanum/octoprofile) for source code.

ChartJS uses these endpoints and displays charts accordingly. The project is then deployed on the Heroku (free dyno) using Heroku CLI.

### Few project features.
- Clean UI
- Responsive design
- Easy navigation
- Graphical view

### Coded with
- Python
- JavaScript
- HTML5
- CSS3

### Built with
- [Django](https://www.djangoproject.com/) High-level Python Web framework
- [Django REST framework](https://www.django-rest-framework.org/) Powerful and flexible toolkit for building Web APIs.
- [ChartJS](https://www.chartjs.org/) Simple yet flexible JavaScript charting for designers & developers
- [ListJS](https://listjs.com/) Perfect library for adding search, sort, filters to tables, lists and various HTML elements.
- [GitHub API](https://docs.github.com/en/rest) Create calls to get the data you need to integrate with GitHub.
- [Jquery](https://jquery.com/) Fast, small, and feature-rich JavaScript library.

### Deployed on
- [Heroku](http://heroku.com/) Platform as a service (PaaS) that enables developers to build, run, and operate applications entirely in the cloud.

Overall this project was really amazing experience and taught me a lot of things in the development process. I will love to see you acknowledge my efforts by visiting [octoprofile.herokuapp.com](https://octoprofile.herokuapp.com/).

How's that?

Any suggestions and feedbacks are always welcomed. Bugs are not welcomed but you can definitely let me know if you found one. Visit the project repository  [here](https://github.com/magbanum/octoprofile) and give it a ⭐ if you liked your Octoprofile and share it with everyone.

Click  [here](http://twitter.com/intent/tweet?text=I'm%20in%20love%20with%20my%20Octoprofile.%20See%20yours%3A&url=https%3A%2F%2Foctoprofile.herokuapp.com%2F&via=magbanum) to share my project on Twitter.

Thank you for taking the time to read this article.🌻

> Be better than yesterday's YOU!