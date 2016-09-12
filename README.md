# Evaluating Efficiency

1. Read [Big O Notation for Newbies with Ruby](http://www.datakicks.com/2016/06/04/big-o-notation.html)
2. Work through [this quiz](http://www.codequizzes.com/computer-science/beginner/big-o-algorithms) on Big O. Try out the code snippets and read the answers.
3. Do the assignment below and submit a PR with your answers.


## Assignment - Determine the big O
Give the efficiency of each of the following code snippets.

### Examples
[Examples](examples.md)

### Problems for you

Snippet 1 - Big O:
```ruby
def largest?(array, value)
  array.each do |item|
    return false if item > value
  end
  return true
end
```
**Snippet 1- Big O(n) because there is a linear relationship between data set growth and the increase in loop counts; every additional element in the array will increase run time proproptionally**  

Snippet 2 - Big O:
```ruby
def info_dump(customers)
  puts "Customer Names: "
  customers.each do |customer|
    puts "#{customer[:name]}"
  end
  puts "Customer Locations: "
  customers.each do |customer|
    puts "#{customer[:country]}"
  end
end
```
**Snippet 2- Big O(n) because even though there are two loops, those loops are not nested so there is a linear relationship between increase in number of customers and run time**   

Snippet 3 - Big O:
```ruby
def first_element_is_red?(array)
  array[0] == 'red' ? true : false
end
```
**Snippet 3- Big O(1) because adding more elements to the array won't affect the run time, there is a fixed constant run time that is not dependent on the amount of data** 

Snippet 4 - Big O:
```ruby
def duplicates?(array)
  array.each_with_index do |item1, index1|
    array.each_with_index do |item2, index2|
      next if index1 == index2
      return true if item1 == item2
    end
  end
  false
end
```
**Snippet 4 - Big 0(n^2) because there is a O(n) loop nested in a 0(n) loop; for each additional element in the array the run time will increase exponentially**

Snippet 5 - Big O:
```ruby
words = [chocolate, coconut, rainbow]
endings = [cookie, pie, waffle]

words.each do |word|
  endings.each do |ending|
    puts word + ending
  end
end
```
**Snippet 5 - Big 0(n^2) because there is a O(n) loop nested in a 0(n) loop; for each additional element in the array the run time will increase exponentially**

Snippet 6 - Big O:
```ruby
numbers = [1,2,3,4,5,6,7,8,9,10]

def print_array(array)
    array.each {|num| puts num}
end
```
**Snippet 6 - Big 0(n) because there is an linear relationship between increase in array size and run time; for each element added to the array the increase in loop count is 1**

Snippet 7 - Big O:
```ruby
# this is insertion sort
(2..num.length).each do |j|
    key = num[j]
    i = j - 1
    while i > 0 and num[i] > key
        num[i+1] = num[i]
        i = i - 1
    end
    num[i+1] = key
end
```
**Snippet 7 - Big 0(n^2) because it takes more and more time as the data set grows. For insertion sort, you find the first unsorte element and then iterate through the sorted elements to see where it should go. The worst case input is an array sorted in reverse order. In these cases every iteration of the inner loop will scan and shift the entire sorted subsection of the array before inserting the next element. This gives insertion sort a quadratic running time**

Snippet 8 - Big O:
```ruby
# this is selection sort
n.times do |i|
  index_min = i
  (i + 1).upto(n) do |j|
    index_min = j if a[j] < a[index_min]
  end
  a[i], a[index_min] = a[index_min], a[i] if index_min != i
end
```
**Snippet 8 - Big 0(n^2) because because it takes more and more time as the data set grows because there are more items to check the item of interest against. My understanding is that for selection sort you iterate through the unsorted elements to find the one of interest and then iterate through the sorted elements to find out where the item of interest should go. If there are at least 2 iterations for every new item, then the relationship is quadratic.**
