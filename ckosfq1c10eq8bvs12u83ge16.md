## How to use Hashnode APIs in Python.

The Hashnode GraphQL APIs public beta was released in 2019 to allow the users to create apps based on it. Even if it was minimal release, it has a lot of queries and mutations that can be used.

Today we are going to learn how to use those Hashnode API queries in python to get the most out of it. 

Steps for creating a python program to get the user details with Hashnode GraphQL API:
- Create query in GraphQL
- Add queries and headers in the program
- Create a function to run the JSON Query
- Get the output as JSON Dictionary

Some prerequisites are,
- Make sure you have the Requests module installed on your system using ```pip install requests```.
- You will need to create/revote the Personal Access Token for the Authentication purpose. You can find it at  [Hashnode Developer settings](https://hashnode.com/settings/developer).

> Personal Access Token is like a private key to your Hashnode account. You can use a personal access token to interact with your Hashnode account using our APIs. Never disclose your access tokens and always keep them private. You can revoke the generated tokens at any time. @Hashnode

### Creating queries in GraphQL

In this tutorial, we are going to get user details like 
```name
```,
```tagline 
```,
```numFollowers
```,
```publicationDomain
```, etc. So we will need to create a query for those in GraphQL.
<pre><code>query {
  user(username: "magbanum") {
    username
    name
    tagline
    numFollowers
    publicationDomain
  }
}</code></pre>

 You can add more properties like 
```numFollowings
```,
```numReactions
```, 
```location
```,
```photo
```,
```coverImage
``` with the help of DOCS and SCHEMA available at  [Hashnode GraphQL API](https://api.hashnode.com/).

For now, let's stick to this query. You can replace "magbanum" with your own username to get personalised results.

Visit https://api.hashnode.com/ and paste the above query there and click the play button to run the script. The output will look like this,

![Hashnode GraphQL API](https://cdn.hashnode.com/res/hashnode/image/upload/v1621191480661/kM1fJWDH4.png)

### Adding Query and Headers in Python program

You have now created your first query in GraphQL, let's use it in our python program. 

Create a Python file named "hashnode-user.py", you can name it whatever you want but let's stick to "hashnode-user.py" for this tutorial.

Firstly import the ```requests``` module, by adding the following line,
<pre><code>import requests</code></pre>

Remember the Personal Access Token which you created earlier in prerequisites, we will need it now. Authorization header with the Personal access token is needed to run the queries or mutations hence we will pass them to the variable named ```headers```.

<pre><code>headers = {
    "Authorization": "your_personal_access_token"
}</code></pre>

Create the Variable named ```query``` to store the query that we created in GraphQL as a multi-line string.

<pre><code>query = """{
  user(username: "magbanum") {
    username
    name
    tagline
    numFollowers
    publicationDomain
  }
}"""</code></pre>

### Function to run JSON Query

We have now reached the final step of our tutorial. As of now we have created a query and added it to our program. In this step, we will create a function that takes query as an argument and returns the output in JSON format.

- Create a function named ```run_query``` which takes the query and the headers we created as arguments.
- Now post a request in a variable named ```response``` with the Hashnode API URL, query and headers as parameters.
- If ... else statement is used to return the JSON output if status code is 200 else raise the exception with status code. Learn more about status codes in HTTP requests  [here](https://httpstatuses.com/).

The function will look like this,
<pre><code>def run_query(query, headers):
    response = requests.post(url="https://api.hashnode.com", json={'query': query}, headers=headers)
    if response.status_code == 200:
        return response.json()
    else:
        raise Exception("Query failed to run by returning code of {}. {}".format(response.status_code, query))</code></pre>

Also, we need to call our function and get the data from it. Add few lines in the program but outside the function.
<pre><code>result = run_query(query, headers)
print(result)</code></pre>
And we are all done. The final code will look like this,
<pre><code>import requests

headers = {
    "Authorization": "your_personal_access_token"
}

def run_query(query, headers):
    response = requests.post(url="https://api.hashnode.com", json={'query': query}, headers=headers)
    if response.status_code == 200:
        return response.json()
    else:
        raise Exception("Query failed to run by returning code of {}.".format(response.status_code))

query = """{
    user(username: "magbanum"){
        username
        name
        tagline
        numFollowers
        publicationDomain
    }
}"""

result = run_query(query,headers)
print(result)</code></pre>

now let's run the code.

<pre><code>>>> python hashnode-user.py
{'data': {'user': {'username': 'magbanum', 'name': 'Shantanu Nighot', 'tagline': 'Electrical engineer | Self-taught developer | Hashnode blogger', 'numFollowers': 2, 'publicationDomain': 'magbanum.tech'}}}</code></pre>

And look at that, we have just used Hashnode API to collect the information from the Hashnode profile. You can see that the data is in form of a dictionary and what if we don't want the whole dictionary but the part of it. We can do that too. This ```result``` dictionary works the same as the Python dictionary so we will be able to index using its keys.

For example, if we want to get the tagline of a user, we just need to index the "result" dictionary as 
```result["data"]["user"]["tagline"]
```. Replace the last line in the code with the following,
<pre><code>print(result["data"]["user"]["tagline"])</code></pre>
See the result, you will get your own tagline if you replace "magbanum" with your username.
<pre><code>>>> python hashnode-user.py
Electrical engineer | Self-taught developer | Hashnode blogger</code></pre>
This look really clean and personalized. Try printing out bunch of other things like ```name```, ```publicationDomain```, and ```numFollowers```.

We have successfully created a query in GraphQL, used it in our Python program, created the function to run the query, and got the expected results. This concludes the tutorial, and I hope you were able to use Hashnode APIs in your python programs. 

As a next step, you can add user Input to get the username for more personalized results. Visit the  [GitHub repo](https://github.com/magbanum/python-codes/blob/master/hashnode_test.py)  for this code.

I hope the above information was helpful to you. Please comment if you are facing trouble with the above code, I will try my best to fix it. And follow me on Hashnode for more such tutorials.