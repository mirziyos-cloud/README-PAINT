<!-- This is the markdown template for the final project of the Building AI course, 
created by Reaktor Innovations and University of Helsinki. 
Copy the template, paste it to your GitHub README and edit! -->

# BOOKBUDDY

Final project for the Building AI course
By Mirziyor Sodikov


## Summary

BookBuddy is a simple AI tool that suggests new books to read based on books a person already liked. It compares books by their descriptions and recommends the ones that are most similar, so readers spend less time searching and more time reading.


## Background

Finding a good book to read next can take a long time. Online stores show thousands of options, and it's hard to know which ones actually match what you enjoy.

Readers waste time browsing long lists of books that don't interest them
Small libraries and local bookshops often don't have a recommendation system at all
Generic "bestseller" lists don't consider personal taste

I chose this topic because I love reading, and I've often given up looking for a new book simply because there were too many choices. A simple, honest recommendation tool would have saved me a lot of time — and could help other readers too


## How is it used?

How is it used?

A user types in the name of a book they liked. BookBuddy looks at the words used to describe that book (its genre, summary, and themes) and compares them to all the other books in its dataset. It then prints out a short list of the most similar books.

This is useful for:

Someone who just finished a book and doesn't know what to read next
A small library wanting to offer basic recommendations without expensive software
A student learning how recommendation systems work, using a small and understandable example

This is a beginner-level project, so the example below uses very simple Python — no advanced libraries required
Images will make your README look nice!

Once you upload an image to your repository, you can link link to it like this (replace the URL with file path, if you've uploaded an image to Github.)
![research](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRNNuGPQqjrRjYZz-ETVpcnQv67bq4oGmC6BuvSWgtBb6BoS0Qh6NIGUuhy&s=10)

If you need to resize images, you have to use an HTML tag, like this:
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQyRztgiXLqHhjc9wyDQxun2XIDWf_eeTHaOCCqXBymk990EboiZoAj-CV5&s=10" width="300">

This is how you create code examples:
```
def main():
    # a very small example "database" of books and their descriptions
    books = {
        "Dune": "desert planet politics prophecy spice empire",
        "The Hobbit": "adventure dragon treasure journey friendship",
        "Foundation": "empire politics future science prediction",
        "The Lord of the Rings": "adventure journey friendship fellowship quest"
    }

    # ask the user which book they liked
    liked_book = "Dune"  # in a real program, this would come from user input

    liked_words = set(books[liked_book].split())

    print("Because you liked '%s', you might also like:" % liked_book)

    # compare the liked book to every other book
    for title, description in books.items():
        if title == liked_book:
            continue  # don't recommend the same book

        words = set(description.split())
        shared_words = liked_words & words  # words in common

        if len(shared_words) > 0:
            print("- %s (%d shared theme(s): %s)" % (title, len(shared_words), ", ".join(shared_words)))
```


## Data sources and AI methods
The book descriptions could come from a public source, such as:

Open Library API

A more advanced version of BookBuddy could use the tf-idf and nearest-neighbor methods covered in the Building AI course: each book's description is turned into a list of numbers (a vector), and the books whose vectors are "closest" to the liked book are recommended — the same idea used to compare cabin prices or classify data points in the course exercises, just applied to text instead of numbers.

Method	What it does
tf-idf	Turns each book's description into a set of weighted numbers, giving more importance to distinctive words
Nearest neighbor	Finds the books whose numbers are most similar to the liked book

[Twitter API](https://developer.twitter.com/en/docs)

| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title       |
| Paragraph   | Text        |

## Challenges

What does your project _not_ solve? Which limitations and ethical considerations should be taken into account when deploying a solution like this?

## What next?

How could your project grow and become something even more? What kind of skills, what kind of assistance would you  need to move on? 


## Acknowledgments

* list here the sources of inspiration 
* do not use code, images, data etc. from others without permission
* when you have permission to use other people's materials, always mention the original creator and the open source / Creative Commons licence they've used
  <br>For example: [Sleeping Cat on Her Back by Umberto Salvagnin](https://commons.wikimedia.org/wiki/File:Sleeping_cat_on_her_back.jpg#filelinks) / [CC BY 2.0](https://creativecommons.org/licenses/by/2.0)
* etc
