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

main()
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

main()
