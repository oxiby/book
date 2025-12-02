# Associating values with maps

Lists are useful for representing ordered collections of values, but aren't the right tool when we want to associate values with one another.
For example, if we had a shopping list, where each type of food was associated with the quantity of that food to buy, it would be awkward to represent as a list.
The right tool is a map.

```oxiby
let shopping_list = ["apple" = 3, "banana" = 1, "carrot" = 2]
```

As we can see, a map looks very much like a list, but instead of each item being a single expression, each item is two expressions separated by an equals sign.
The expression on the left is called the **key** and the expression on the right is called the **value**.
For this reason, we'll sometimes hear maps referred to as key-value pairs.
Maps may also be referred to as dictionaries or associative arrays.

## Iterating through key-value pairs

```oxiby
for (food, quantity) in shopping_list {
    print_line("Number of #{food} to buy: #{quantity}")
}
```

Just like a list, we use a `for` loop to iterate through the key-value pairs in a map.
The only difference is the variable we use to bind each pair is compound.
Instead of a single variable name like `item`, we have two variables in parenthesis, separated by a comma: `(key, value)`.

The reason we're able to do this is that the expression that comes after `for` is not just a variable name, but a pattern.
Remember that patterns allow us to **destructure** compound values into their constituent parts.
Don't worry about that for now.
We'll explore patterns further in a future chapter.
For now, just remember that when using a `for` loop with a map, we must bind both the key and the value.

## Inserting values

To insert a new value into a map, use the indexing operator plus an assignment:

```oxiby
shopping_list["dragonfruit"] = 1
```

If there was already a value associated with the key, it will be replaced with the one we're assigning.

## Retrieving a value by key

To access a specific value in a map, use the indexing operator, just as with lists, but with a key instead of an integer offset:

```oxiby
shopping_list["carrot"]
```

What does the above expression evaluate to?
We might have guessed 2, based on the initial value of `shopping_list` at the start of this chapter.
But it's a little more complicated than that.
We'll find out why in the next chapter.
