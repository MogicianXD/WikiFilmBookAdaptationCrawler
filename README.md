# A Crawler for Adaptation 

## Adaptation Relations

> File 1 outputs `film_book.txt` in 'w'(write) mode, while file 2 and 3 output in 'a'(attach) mode. You can run them in order or change modes.

> `/data/film_book.txt` is a previous output file. Codes is modified recently, so re-run may result in a different version.

1. `list_film_book_en.py` for [Category:Lists of Films based on books](https://en.wikipedia.org/wiki/Category:Lists_of_films_based_on_books), which saves tabular records. 

2. `tv_book_en.py` for [Category:Television shows based on books](https://en.wikipedia.org/wiki/Category:Television_shows_based_on_books).

3. `film_book_en.py` for [Category:Films based on books](https://en.wikipedia.org/wiki/Category:Films_based_on_books). It is similar with tv. 

But note that, in `film_book_en.py`, if a book name is not found, we use the category instead.
 
> For example, `Arabian Nights (2015 film)` belongs to `Category:Films based on One Thousand and One Nights‎`. Then `One Thousand and One Nights‎` may be the potential base.

It may raise noise, and you can change codes following the pattern `tv_book_en.py` to avoid. There's little difference in corresponding codes.  

     
## Categories

Categories of a film or a book can be extracted after requesting [wiki metadata api]('https://en.wikipedia.org/api/rest_v1/page/metadata/'). 

Codes to extract have been written in the above-mentioned .py files, but they have been commented out. In this way, you will crawl adaptation relations and categories at the same time.

`get_category()` in `kg_category.py` provides another way to use `wikipedia` library.


## Match for amazon dataset

Movie and Book datasets is published in (Amazon Reviews)[http://deepyeti.ucsd.edu/jianmo/amazon/index.html].

`join.py` matches movies and books which have adaptation relations.

You can also change codes commented out in match() and ceiling() for the rule of matching and filtering.

## Apology

Code is polished before push. For time reason, I haven't run them yet. Problems maybe exist.

You can commit issues or contact [me](mogician233@outlook.com) whenever you need help.