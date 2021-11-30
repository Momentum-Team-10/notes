# Queries CheatSheet

## Querying with models

### Get all objects

```py
Recipe.objects.all()
```

### Get one object when you know the pk

_This throws `DoesNotExist` error if the exact match is not found._

```py
Recipe.objects.get(id=1)
```

### Get one object when you know any single attribute

_This throws `DoesNotExist` error if the exact match is not found._

```py
Recipe.objects.get(title='grilled cheese')
```

### Create a new object for a given user, then save it

Creating the object just creates it in memory. It is not saved to the database until you call the `save()` method on it.

```py
user = User.objects.get(id=1)
new_recipe = Recipe(user=user, title="grilled cheese", public=True)
new_recipe.save()
```

### Filter objects using fields

This returns a QuerySet instead of a single instance. If a match is not found, you will get an empty queryset instead of an error.

```py
Recipe.objects.filter(name__icontains="soup")
Recipe.objects.filter(prep_time_in_minutes__lte=30)

Habit.objects.filter(user=request.user)
```

### Filter on more than one model field

This query will find objects that meet _both_ conditions (logical `AND`).

```py
Recipe.objects.filter(ingredients__item__icontains='cheddar', public=True)
```

### Filter with an OR condition

This is more complicated. We need to use Django's `Q` objects and the pipe operator to do this.

This query will return a QuerySet containing records that meet _either_ of the conditions.

```py
from django.db.models import Q

Recipe.objects.filter(Q(user=u) | Q(public=True))
```

### Sort queried objects in order

```py
Mealplan.objects.order_by('date') # ascending order
Mealplan.objects.order_by('-date') # descending order
```

## Related Objects

Objects are "related" if their models are connected to each other by ForeignKey (one-to-many), ManyToMany, or OneToOne relationships.

### Get related objects for a given object

This uses the related manager instead of `objects`.

```py
recipe = Recipe.objects.get(id=1)
recipe.ingredients.all()
```

### Query by fields on a related object

This query will look for recipes that have ingredients whose name contains a case-insensitive match for the given string.

```py
Recipe.objects.filter(ingredients__item__icontains='cheese')
```

### Queries that traverse across multiple relationships

```py
Record.objects.filter(habit__user=request.user)
```

## Aggregations: derive a value from an entire QuerySet

When you want to count or calcuate a value derived from your data, you can use an aggregation.

```py
Recipe.objects.aggregate(Avg('prep_time_in_minutes'))
```

## Annotations: generate a value for _each item_ in a QuerySet

When you want derived information for each individual item, like the number of times each recipe has been favorited. You can use aggregation functions here too.

```py
recipe = Recipe.objects.get(id=4)
recipe.favorited_by.count() # you could do this but there is a better way
Recipe.objects.annotate(
    times_favorited=Count("favorited_by", distinct=True)
).first().times_favorited
```
