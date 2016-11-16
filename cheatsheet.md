# Ruby Cheatsheet:

## General:
- puts == println
- print == print

## Variables:
```ruby
my_int = 4
my_string = "jesse"
my_array = [1, 2, 3, 4, 5]
```

## Common methods:
```ruby
# get input
my_input = gets.chomp

# print
print "string"

# print with new line
puts "string new line"
```

## Ifs:
```ruby
if user_num < 0
  puts "You picked a negative integer!"
elsif user_num > 0
  puts "You picked a positive integer!"
else
  puts "You picked zero!"
end
```

## Loops:

### while
```ruby
counter = 1
while counter < 11
  puts counter
  counter = counter + 1
end
```

### until
```ruby
counter = 1
until counter > 10
  puts counter
  counter += 1
end
puts counter
```

### for
... = exclusive  
.. = inclusive
```ruby
for num in 1...10
  puts num
end
```

### loop
```ruby
i = 20
loop do
  i -= 1
  print "#{i}"
  break if i <= 0
end
```
### array.each
```ruby
array = [1,2,3,4,5]
array.each do |x|
  x += 10
  print "#{x} "
end
```
or
```ruby
odds = [1,3,5,7,9]
odds.each { |item|
    print (item * 2)
}
```
### times
```ruby
14.times {
    print "Jbuss "
}
```

## Arrays
### Declaration
```ruby
my_array = ["one", "two", "three", "four"]
two_d_array = [[0,0,0,0],[0,0,0,0],[0,0,0,0],[0,0,0,0]]
```

### Access
```ruby
demo_array = [100, 200, 300, 400, 500]
print  demo_array[2]
# == 300
```

### Iteration
```ruby
languages = ["HTML", "CSS", "JavaScript", "Python", "Ruby"]

languages.each { |lang|
  puts lang
}
```

## Hashes
### Declaration
```ruby
#literal
my_hash = { "name" => "Jesse",
  "age" => 26,
  "hungry?" => true
}
```
```ruby
my_hash_2 = Hash.new
my_hash_2["ayy"] = "lmao"
```

### Iteration
```ruby
secret_identities = {
  "The Batman" => "Bruce Wayne",
  "Superman" => "Clark Kent",
  "Wonder Woman" => "Diana Prince",
  "Freakazoid" => "Dexter Douglas"
}

secret_identities.each { |hero, civ|
    puts "#{hero}: #{civ}"
}

secret_identities.each_key { |hero|
  puts hero
}

secret_identities.each_value { |civ|
  puts civ
}
```

### Default value
```ruby
my_hash = Hash.new(0)
puts my_hash["anything"] # prints 0
```

### Simple sort
```ruby
colors = {"blue" => 3, "green" => 1, "red" => 2}
colors = colors.sort_by { |color, count|
  count
}
```

### .select
```ruby
movie_ratings = {
  memento: 3,
  primer: 3.5,
  the_matrix: 5,
  truman_show: 4,
  red_dawn: 1.5,
  skyfall: 4,
  alex_cross: 2,
  uhf: 1,
  lion_king: 3.5
}

good_movies = movie_ratings.select {
    |movie, rating| rating > 3
}
```

## Methods
```ruby
def puts_1_to_10
  (1..10).each { |i| puts i }
end
```

### Arguments
```ruby
def cube(n)
  puts n ** 3
end

cube(8)
```

### Splat args
```ruby
# *bros accepts many strings
def what_up(greeting, *bros)
  bros.each { |bro| puts "#{greeting}, #{bro}!" }
end

what_up("What up", "Justin", "Ben", "Kevin Sorbo")
```

### Default args
```ruby
def alphabetize(words, reverse=false)
end

words = ["first", "second", "third"]
alphabetize(words)
alphabetize(words, true)
```

## Sorting
```ruby
books = ["Charlie and the Chocolate Factory",
  "War and Peace",
  "Utopia",
  "A Brief History of Time",
  "A Wrinkle in Time"]

# ascending (eafult)
books.sort! { |firstBook, secondBook| firstBook <=> secondBook }

# descending
books.sort! { |firstBook, secondBook|
    secondBook <=> firstBook
}
```

## Symbols
- Make good hash keys
- Are immutable
- Only one copy

```ruby
symbol_hash = {
  :one => 1,
  :two => 2,
  :three => 3,
}

symbol_hash = {
  one: 1,
  two: 2,
  three: 3
}

my_symbol = "hello".intern
# my_symbol = :hello

my_symbol = "hello".to_sym
# my_symbol = :hello
```
