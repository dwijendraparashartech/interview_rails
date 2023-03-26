select_method.ruby ::

Link ::   https://www.rubyguides.com/2019/04/ruby-select-method/

..........................


1. Array.select ::

a = [18, 22, 33, 3, 5, 6]
b = [1, 4, 1, 1, 88, 9]
c = [18, 22, 3, 3, 50, 6]

puts "select method : #{a.select {|num| num > 10 }}\n\n"
puts "select method : #{a.select {|num| num > 10 }}\n\n"
puts "select method : #{b.select {|x| x.odd? }}\n\n"
puts "select! method : #{a.select! {|num| num > 10 }}\n\n"


.............................................

example_array1 = [1, 2, 3, 4, 5, 6]
example_array1.select { |item| item.even? }
example_array1.select { |item| item.odd? }
.............................................

example_array2 = ['dog', 'chicken', 'cow', 'goat']
example_array2.select { |item| item.length >= 4 }
example_array2.select { |item| item.length = 3 }

.............................................

example_array3 = ['dog', 4, 'chicken', 8,  'cow', 10,  'goat']
example_array3.select { |item| item.class == String }
example_array3.select { |item| item.class == Integer }

.............................................

Using Select method find out the vowel in Ruby ??

a = %w{ a b c d e f }
a.select { |v| v =~ /[aeiou]/ }  #=> ["a", "e"]

.............................................

The .find method
This Ruby method iterates through an array and gives you the first match for which the expression within a block returns true.

.............................................

>> [1,2,3,4,5,6,7].find { |x| x.between?(3,4) }
=> 3
>> [1,2,3,4,5,6,7].find { |x| x.between?(3,6) }
=> 3
>> [1,2,3,4,5,6,7].detect { |x| x.between?(3,7) }
=> 3
>> [1,2,3,4,5,6,7].detect { |x| x.between?(2,7) }
=> 2










..........................


2. Hash.select :: 

b = {"a" => 100}
c = {"a" => 100, "c" => 300, "b" => 200}

puts "Hash b select form : #{b.select{|key, value| value < 200}}\n\n"
puts "Hash c select form : #{c.select{|key, value| key < "b"}}\n\n"

Output :

Hash b select form : {"a"=>100}

Hash c select form : {"a"=>100}

..........................


3. Write a Programs For Even Numbers  using Simple Programs :::

even_numbers = []
[1,2,3,4,5,6].each do |n|
  if n.even?
    even_numbers << n
  end
end
even_numbers

..........................


4. Write a Programs For Even Numbers  using Select Method  :::

[1,2,3,4,5,6].select { |n| n.even? }

[1,2,3,4,5,6].select(&:even?)

..........................


5. Write other programs for select ::

stock = { apples: 10,oranges: 5,bananas: 1}
stock.select { |k, v| v > 1 }
# {:apples=>10, :oranges=>5}

..........................


6.  Write a program to get any array start with a paritcular character or letter ?

fruits = %w(apple orange banana)
fruits.select! { |fruit| fruit.start_with? "a" }

..........................


7, Find Method ::  Select for the first element of the array or return nil 

You can use the find method.
Find gives you the first match, or nil if it can't be found.

letters = %w(a aa aaa aaaa)
letters.find { |l| l.size == 3 }
# "aaa"
letters.find { |l| l.size == 10 }
# nil


..........................


8. Select and Reject Methods in Ruby ::

[1,2,3,4,5,6].select { |n| n != 4 }
[1,2,3,4,5,6].select { |n| n != 4 }




..........................




9. Write a program to find the duplicate items in an array ::

......


def find_duplicates(array)
  duplicates = []
  array.each do |element|
    duplicates << element if array.count(element) > 1
  end
  duplicates.uniq
end

p find_duplicates([1, 2, 3, 1, 5, 6, 7, 8, 5, 2]) #=> [1, 5, 2]


......


array = [1, 2, 1, 3, 5, 4, 5, 5]
dup = array.select{|element| array.count(element) > 1 }
dup.uniq


......

dups = [1,1,1,2,2,3].group_by{|e| e}.keep_if{|_, e| e.length > 1}

dups.keys
# => [1, 2]
If you want the number of duplicates:

dups.map{|k, v| {k => v.length}}
# => [{1=>3}, {2=>2}]

......

def list_duplicates(array)
  duplicates = array.select { |e| array.count(e) > 1 }
  duplicates.uniq
end
 print list_duplicates([1,1,4,5,6,6,9])

......

 def duplicate_array(arr)
  duplicates = []
  while arr.size != 1
    pivot = arr.shift
    arr.each do |element|
      if element.eql?(pivot)
        next if duplicates.include?(element)
        duplicates << element
      end
    end
  end
  duplicates
end
print duplicate_array([1,1,2,2,3])



..........................


10. Write a program to sort an array in Ruby ??


a = [ 0,9,6,12,1]
print sorted_ary = a.sort_by { |number| -number }
print sorted_ary = a.sort.reverse
print a.sort {|x,y| -(x <=> y)}

...........

my_array = ["a", "aa", "aaaa", "aaa"]
puts my_array.sort_by { |item| item.size },"\n"
puts my_array.sort_by { |item| -item.size }

...........


..........................



