## How to hide Django SECRET_KEY on Public Repositories.

While working on the Django project you may have seen variables like SECRET_KEY and other DATABASE-related information which is considered sensitive. When uploading the source code of deployed Django project on the internet, these data should be properly managed to avoid any misuse. But removing them from repo every time you push your data can become a hectic job and can cause errors in production.

Let's consider my Django project named " [quotes-gen-project](https://quotes-gen-project.herokuapp.com/) " deployed on Heroku. It shows the random quote from the database with its author name and also allows visitors to add more quotes. This is my first Django project so I kept it as simple as possible.


<kbd>
  <img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1620478049620/prlbhzLq4.png" alt="quotes-gen-project" />
</kbd>

You can visit the  [Github repo](https://github.com/magbanum/quotes-gen-project)  for the source code of this project.

After Deploying the project on Heroku, you will have the following variables in the settings.py file.

<pre><code>SECRET_KEY = 'your-django-secret-key'</code></pre>

<pre><code>DATABASES = {
      'default': {
        'ENGINE': 'your-database-engine name',
        'NAME': 'database-name',
        'USER': 'database-username',
        'PASSWORD': 'database-password',
        'HOST': 'database-host'
        'PORT': '5432',
    }
}</code></pre>

Now follow the below steps to add the above environment variables in our Heroku config vars.

- Login to your Heroku account
- Select your Heroku app
- Go to settings
- And click on 
```Reveal Config vars```.

<kbd>
  <img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1620479327803/WpVHZ5vD3.png" alt="Heroku-settings">
</kbd>

Here you need to add the key and value for the variables you want to add. For example, add ```SECRET_KEY``` in key and ```your-django-secret-key``` in value without quotes. Do this for all other variables like NAME, USER, PASSWORD, and HOST.


<kbd>
  <img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1620479371517/PZYvWOXZ5_.png" alt="Heroku-config-vars">
</kbd>

You have now added config vars in the app and need to do some changes to address them from our code.

Go to the settings.py file and do the following changes.

<pre><code>SECRET_KEY = os.getenv('SECRET_KEY')</code></pre>

<pre><code>DATABASES = {
      'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': os.getenv('NAME'),
        'USER': os.getenv('USER'),
        'PASSWORD': os.getenv('PASSWORD'),
        'HOST': os.getenv('HOST'),
        'PORT': '5432',
    }
}</code></pre>

And that's it.

Now run the following commands in the command prompt in your project root directory and check that everything is working as before.

<pre><code>git add -A
git commit -m "commit messege"
git push heroku master
heroku open</code></pre>

Hurray, you were able to hide sensitive data from source code and can now share your work with the world without any worries.

Thanks for checking out this blog. I hope this information was helpful for you. Let me know by commenting below.