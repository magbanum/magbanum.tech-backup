# How to save Environment Variables in Python virtual env

Saving environment variables in a Python virtual environment can be a great way to keep your project's dependencies and settings organized and separate from other tasks on your machine.

I use Django to create APIs for the front end of my website. Django needs many credentials that should not be exposed to the public or in the GitHub repository. I have already created an article on [**How to hide Django SECRET\_KEY on Public Repositories.**](https://magbanum.com/blog/how-to-hide-django-secret_key-on-public-repositories) But if we want to use it on a local machine then still have to replace the code with the original credentials.

Here are the steps to take to save environment variables in a Python virtual environment:

### Create a virtual environment:

To create a virtual environment, you can use the virtualenv package. To install it, open a terminal and run `pip install virtualenv`. Once it is installed, you can create a new virtual environment by running a command `virtualenv venv`, where "venv" is the name of your virtual environment.

### Activate the virtual environment:

To activate the virtual environment, run `source myenv/bin/activate` on Linux and macOS or `source myenv\Scripts\activate` on Windows. Once the virtual environment is active, the name of the virtual environment will appear in the command prompt.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674969239910/77a4306e-9081-4a39-a74b-c17165aaff64.png align="center")

### Set environment variables:

To set an environment variable, you can use the export command on Linux and macOS or the set command on Windows. For example, to set an environment variable named `DJANGO_SETTINGS_MODULE` with the value `myproject.settings`, you can run `export DJANGO_SETTINGS_MODULE=myproject.settings` on Linux and macOS or `set DJANGO_SETTINGS_MODULE=myproject.settings` on Windows.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674969173395/9e6b444c-93ea-449f-902e-dac0bb42bfc7.png align="center")

Keep in mind that the environment variables set through the command prompt are temporarily saved in the environment and will be destroyed once the environment is deactivated. Use the following method to set the variables automatically every time the environment is activated.

### Save environment variables:

To save environment variables so they persist even after you close the terminal or deactivate the virtual environment, you need to add the `export` or `set` commands to a shell script.

On Linux and macOS, create a file named activate in the bin directory of your virtual environment with the following contents:

```bash
#!/bin/sh
export SECRET_KEY="django-insecure-*************"
```

On Windows, find the file named activate or create a file named `activate` in the `Scripts` directory of your virtual environment with the following contents:

```bash
set SECRET_KEY="django-insecure-*************"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674969514960/74427318-3eb3-4463-b2cd-3dff18b41d10.png align="center")

### Use saved environment variables:

We can use the saved variables using `os.environ.get()`. In my case, I want to use the saved secret key for my Django project. In `settings.py` file, I will import the OS module using `import os`. Then I will get the saved environment variable `SECRET_KEY` using the command `os.environ.get('SECRET_KEY')`.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674970193681/fe8edf6a-5c04-4cbb-abd4-010047476e48.png align="center")

> Note: Make sure you do not expose `activate` file in your GitHub repository. To ensure this add your env directory to `.gitignore` file. Directories and files included in `.gitignore` are not included while pushing the code to the repository.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1674970408251/41b9cdae-6304-4136-9880-d9fe82025b33.png align="center")

### Deactivate the virtual environment:

To deactivate the virtual environment, you can run the `deactivate` command. This will take you out of the virtual environment and return to the global Python installation on your machine.

By following these steps, you can successfully save environment variables in a Python virtual environment, keeping your project dependencies and settings organized and separate from other projects on your machine.

Please let me know if I am missing something in this tutorial or need help with any step.

Thanks for reading. See you in the next article.