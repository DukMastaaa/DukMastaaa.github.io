`bundle exec jekyll s --no-watch`


start numbering category depth at 0 to be consistent with list indexing

pseudocode of original algorithm:

```python
sort_categories = list(sorted(site.categories))
for category in sort_categories:
    category_name = category[0]
    posts_of_category = category[-1]
    first_post = posts_of_category[0]

    # safety check. if this doesn't hold, we just skip to next category
    if category_name == first_post.categories[0]:
        sub_categories = []
        for post in posts_of_category:
            second_category = post.categories[1]
            if second_category:
                if second_category not in sub_categories:
                    sub_categories.append(second_category)
        
        sub_categories.sort()
        sub_categories_size = len(sub_categories)
```

pseudocode of general case:

```python
max_depth = 4

for category in sort_categories:
    category_name = category[0]
    posts_of_category = category[-1]
    first_post = posts_of_category[0]

    for i in range(1, max_depth):
        
```


