# Ruby Cheatsheet

## Variables:
```ruby
my_int = 4
my_string = "jesse"
my_array = [1, 2, 3, 4, 5]
```

### Conditional assignment
```ruby
favorite_book = nil
puts favorite_book
# nil

favorite_book ||= "Slaughterhouse 5"
puts favorite_book
# "Slaughterhouse 5"

favorite_book ||= "Thinking Fast and Slow"
puts favorite_book
# "Slaughterhouse 5"
```

## Common methods:
```ruby
# get input
my_input = gets.chomp

# print
print "string"

# print with new line
puts "string new line"

age = 26
# respond_to? returns true if the variable can do the action passed in
age.respond_to?(:next) # true
age.respond_to?(:hihihih) # false
```

## Methods:
```ruby
def multiple_of_three(n)
  return n % 3 == 0 ? "True" : "False"
end
```
Equivalent to:
```ruby
def multiple_of_three(n)
  n % 3 == 0 ? "True" : "False"
end
```
Ruby always returns the evaluation of the last evaluated expression.

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

### Inline
```ruby
x = 50
x = 10 if x > 5
# x = 10
```
```ruby
x = 50
x = 10 unless x > 500
# x = 10
```

### Ternary
```ruby
my_string = 1 > 2 ? "impossible" : "always is"
# my_string == "always is"
```

### Case statement
```ruby
case language
when "JS"
  puts "Websites!"
when "Python"
  puts "Science!"
when "Ruby"
  puts "Web apps!"
else
  puts "I don't know!"
end
```

```ruby
case greeting
    when "hi" then puts "Nice"
    when "sup" then puts "Dawg"
    when "lol" then puts "lol"
    when "ayyy" then puts "lmao"
    else puts "idk"
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

### upto
```ruby
95.upto(100) { |num| print num, " " }
# 95 96 97 98 99 100
```

### downto
```ruby
100.downto(100) { |num| print num, " " }
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

### Push
```ruby
alphabet = "a", "b", "c"
alphabet.push("d")
# { "a", "b", "c", "d"}
```
```ruby
alphabet = ["a", "b", "c"] << "d"
# {"a", "b", "c", "d"}
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

### Add/Update/Delete
```ruby
my_hash = Hash.new
my_hash["new"] = "value"
my_hash["new"] = "value2"
my_hash.delete("new")
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


## Blocks
- Chunks of executable code
- Are not objects

```ruby
5.times {
  puts "This is a block"
}
```

### Yields:
```ruby
def block_test
  puts "We're in the method!"
  puts "Yielding to the block..."
  yield
  puts "We're back in the method!"
end

block_test { puts ">>> We're in the block!" }

# Output:
# "We're in the method!"
# "Yielding to the block..."
#  >>> We're in the block!
# "We're back in the method!"
```

### Yields w/ Parameter
 ```ruby
 def yield_name(name)
  puts "In the method! Let's yield."
  yield("Kim")
  puts "In between the yields!"
  yield(name)
  puts "Block complete! Back in the method."
end

yield_name("Jesse") { |n| puts "My name is #{n}." }

# Output:
# In the method! Let's yield.
# My name is Kim.
# In between the yields!
# My name is Jesse.
# Block complete! Back in the method.
```

### Procs
- Essentially a saved block
- Is an object

```ruby
multiples_of_3 = Proc.new do |n|
  n % 3 == 0
end

(1..100).to_a.select(&multiples_of_3)
```

```ruby
#actual use case
group_1 = [4.1, 5.5, 3.2, 3.3, 6.1, 3.9, 4.7]
group_2 = [7.0, 3.8, 6.2, 6.1, 4.4, 4.9, 3.0]
group_3 = [5.5, 5.1, 3.9, 4.3, 4.9, 3.2, 3.2]

over_4_feet = Proc.new { |height| height >= 4 }

can_ride_1 = group_1.select(&over_4_feet)
can_ride_2 = group_2.select(&over_4_feet)
can_ride_3 = group_3.select(&over_4_feet)

# no need to re-write height >= 4 in three separate blocks
```
```ruby
hi = Proc.new { puts "Hello!" }
hi.call
# Hello!
```

### Lambdas
- Essentially a Proc w/ different syntax
- 2 Main differences
-- 1) Lambdas check the number of args passed, procs don't
-- 2) When a lambda returns, it passes control back to the calling method; when a proc returns, it does so immediately, without going back to the calling method.
```ruby
strings = ["leonardo", "donatello", "raphael", "michaelangelo"]

symbolize = lambda { |string| string.to_sym }

symbols = strings.collect(&symbolize)
```
