## Python program to make text URL safe.

Hi, everyone, I have been busy few weeks due to my job search and the project I am working on. While building a blogging platform using Django, I reached the point where I decided to add a customized URL for each blog post just like Hashnode.

> A slug is the part of a URL that identifies a particular page on a website in an easy to read form.

To create unique URLs for each blog post we need to have a unique and URL safe Slug for each post. But luckily Django handles It all. Django has an inbuilt method called ```slugify()``` which converts input string to URL safe slug. But what if Django is not there to help us? That's why I have created a simple Python program to create URL safe slug from the input string.

One important thing to note is that there are few characters that are not allowed in URL slug or may cause URLs to redirect to unexpected Webpage. These characters are called non URL safe characters and should be avoided at any cost.

Non URL safe characters are ```"``` ```#``` ```$``` ```%``` ```&``` ```+``` ```,``` ```/``` ```:``` ```;``` ```=``` ```?``` ```@``` ```[``` ```\\``` ```]``` ```^``` ``` ` ```   ```{``` ```|``` ```}``` ```~``` ```'``` and whitespace.

The logic for this one is very simple. If there are any non URL safe characters in the input string then we need to replace them with a safe one like ```-``` or ```_```.

First, we need to create a list of non URL safe characters just like the following.
```
non_url_safe = ['"', '#', '$', '%', '&', '+',
                    ',', '/', ':', ';', '=', '?',
                    '@', '[', '\\', ']', '^', '`',
                    '{', '|', '}', '~', "'"]
```

And the function required is,
```
def slugify(text):
    non_safe = [character for character in text if character in non_url_safe]
    if non_safe:
        for i in non_safe:
            text = text.replace(i, '')
    text = u'-'.join(text.split())
    return text
```

What's happening here is that the function,
1. Collects non URL safe characters in a string and replace each with whitespace.
2. Split the string and join each word using ```-```.

So our final code becomes,
```
non_url_safe = ['"', '#', '$', '%', '&', '+',
                    ',', '/', ':', ';', '=', '?',
                    '@', '[', '\\', ']', '^', '`',
                    '{', '|', '}', '~', "'"]

def slugify(text):
    non_safe = [character for character in text if character in non_url_safe]
    if non_safe:
        for i in non_safe:
            text = text.replace(i, '')
    text = u'-'.join(text.split())
    return text

text = input("Enter the text to slugify >>> ")
slug = slugify(text)
print("Slugified text:   ",slug)
```

Example:
```
>>> python slugify.py
Enter the text to slugify >>> this is the slug
Slugified text:   this-is-the-slug
```
That's all, now you can add this as your URL slug without any worries.

Check out more codes like this on my  [Python-codes](https://github.com/magbanum/python-codes)  repository and Give a 🌟 to repo if you find it helpful.

I am currently looking for job opportunities in the technical field so please let me know if you have any to recommend.

Thanks for reading this article and see you in the next one.
