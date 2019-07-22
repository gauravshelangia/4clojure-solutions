1. This is a clojure form. Enter a value which will make the form evaluate to true. Don't over think it! If you are confused, see the getting started page. Hint: true is equal to true.
```clojure
(= __ true)
``` 
```clojure
true
```

2. If you are not familiar with polish notation, simple arithmetic might seem confusing.
Note: Enter only enough to fill in the blank (in this case, a single number) - do not retype the whole problem.
```clojure
(= (- 10 (* 2 3)) __)
```
```clojure
4
```

3. Clojure strings are Java strings. This means that you can use any of the Java string methods on Clojure strings.
```clojure
(= __ (.toUpperCase "hello world"))
```
```clojure
"HELLO WORLD"
```

4. Lists can be constructed with either a function or a quoted form.
```clojure
(= (list __) '(:a :b :c))
```
```clojure 
:a :b :c
```

5. When operating on a list, the conj function will return a new list with one or more items "added" to the front.
Note that there are two test cases, but you are expected to supply only one answer, which will cause all the tests to pass.
```clojure
(= __ (conj '(2 3 4) 1))
(= __ (conj '(3 4) 2 1))
```
```clojure
'(1 2 3 4)
```

6. Vectors can be constructed several ways. You can compare them with lists. 
Note: the brackets [] surrounding the blanks __ are part of the test case.
```clojure
(= [__] (list :a :b :c) (vec '(:a :b :c)) (vector :a :b :c))
(= [__] (list :a :b :c) (vec '(:a :b :c)) (vector :a :b :c))
```
```clojure
:a :b :c
```

7. When operating on a Vector, the conj function will return a new vector with one or more items "added" to the end.
```clojure
(= __ (conj [1 2 3] 4))
(= __ (conj [1 2] 3 4))
```
```clojure
[1 2 3 4]
```

8. Sets are collections of unique values.
```clojure
(= __ (set '(:a :a :b :c :c :c :c :d :d)))
(= __ (clojure.set/union #{:a :b :c} #{:b :c :d}))
```
```clojure
#{:a :b :c :d}
```
9. When operating on a set, the conj function returns a new set with one or more keys "added".
```clojure
(= #{1 2 3 4} (conj #{1 4 3} __))
```
```clojure
2
```

10. Maps store key-value pairs. Both maps and keywords can be used as lookup functions. Commas can be used to make maps more readable, but they are not required.
```clojure
(= __ ((hash-map :a 10, :b 20, :c 30) :b))
(= __ (:b {:a 10, :b 20, :c 30}))
(= __ (:b {:a 10, :b 20, :c 30}))
```
```clojure
20
```

11. When operating on a map, the conj function returns a new map with one or more key-value pairs "added".
```clojure
(= {:a 1, :b 2, :c 3} (conj {:a 1} __ [:c 3]))
```

```clojure
{:b 2}
```

12. All Clojure collections support sequencing. You can operate on sequences with functions like first, second, and last.
```clojure
(= __ (first '(3 2 1)))
(= __ (second [2 3 4]))
(= __ (last (list 1 2 3)))
```
```clojure
3
```

13. The rest function will return all the items of a sequence except the first.
```clojure
(= __ (rest [10 20 30 40]))
```
```clojure
[20 30 40]
```

14. Clojure has many different ways to create functions.
```clojure
(= __ ((fn add-five [x] (+ x 5)) 3))
(= __ ((fn [x] (+ x 5)) 3))
(= __ (#(+ % 5) 3))
(= __ ((partial + 5) 3
(= __ ((partial + 5) 3))
```
```clojure
8
```

15. Write a function which doubles a number.
```clojure
(= (__ 2) 4)
(= (__ 3) 6)	
(= (__ 11) 22)	
(= (__ 7) 14)
```
```clojure
(fn twice [x] ( * x 2))
( partial * 2 )
#( * % 2)
(fn [x] (* x 2))
```

16. Write a function which returns a personalized greeting.
```clojure
(= (__ "Dave") "Hello, Dave!")
(= (__ "Jenn") "Hello, Jenn!")
(= (__ "Rhea") "Hello, Rhea!")
```
```clojure
#( str "Hello, " % "!")
```

17. The map function takes two arguments: a function (f) and a sequence (s). Map returns a new sequence consisting of the result of applying f to each item of s. Do not confuse the map function with the map data structure.
```clojure
(= __ (map #(+ % 5) '(1 2 3)))
(= __ (map #(+ % 5) '(1 2 3)))
```
```clojure
'(6 7 8)
```

18. The filter function takes two arguments: a predicate function (f) and a sequence (s). Filter returns a new sequence consisting of all the items of s for which (f item) returns true.
```clojure
(= __ (filter #(> % 5) '(3 4 5 6 7)))
```
```
'(6 7)
```

19. Write a function which returns the last element in a sequence.
```	clojure
(= (__ [1 2 3 4 5]) 5)
(= (__ '(5 4 3)) 3)
(= (__ ["b" "c" "d"]) "d")
```
```clojure
(fn [x] (.get x(- (count x) 1)))
#(.get %(- (count %) 1))
```

20. Write a function which returns the second to last element from a sequence.
```clojure
(= (__ (list 1 2 3 4 5)) 4)
(= (__ ["a" "b" "c"]) "b")
(= (__ [[1 2] [3 4]]) [1 2])
```
```clojure
(fn [x] (.get x (- (count x) 2 )))
#(.get %(- (count %) 2))
```

21. Write a function which returns the Nth element from a sequence.
```clojure
(= (__ '(4 5 6 7) 2) 6)
(= (__ [:a :b :c] 0) :a)
(= (__ [1 2 3 4] 1) 2)
(= (__ '([1 2] [3 4] [5 6]) 2) [5 6])
```
```clojure
(fn [x y] (.get x y))
```

22. Clojure lets you give local names to values using the special let-form.
```clojure
(= __ (let [x 5] (+ 2 x)))
(= __ (let [x 3, y 10] (- y x)))
(= __ (let [x 21] (let [y 3] (/ x y))))
```
```clojure
7
```

23. Can you bind x, y, and z so that these are all true?
```clojure
(= 10 (let __ (+ x y)))
(= 4 (let __ (+ y z)))
(= 1 (let __ z))
```
```clojure
[x 7 y 3 z 1]
```

24. Regex patterns are supported with a special reader macro.
```clojure
(= __ (apply str (re-seq #"[A-Z]+" "bA1B3Ce ")))
```
```clojure
"ABC"
```

25. Reduce takes a 2 argument function and an optional starting value. It then applies the function to the first 2 items in the sequence (or the starting value and the first element of the sequence). In the next iteration the function will be called on the previous return value and the next item from the sequence, thus reducing the entire collection to one value. Don't worry, it's not as complicated as it sounds.
```clojure
(= 15 (reduce __ [1 2 3 4 5]))
(=  0 (reduce __ []))
(=  6 (reduce __ 1 [2 3]))
```
```clojure
+
```

26. A recursive function is a function which calls itself. This is one of the fundamental techniques used in functional programming.
```clojure
(= __ ((fn foo [x] (when (> x 0) (conj (foo (dec x)) x))) 5))
```
```clojure
[5 4 3 2 1]
```

27. Clojure only has one non-stack-consuming looping construct: recur. Either a function or a loop can be used as the recursion point. Either way, recur rebinds the bindings of the recursion point to the values it is passed. Recur must be called from the tail-position, and calling it elsewhere will result in an error.
```clojure
(= __
  (loop [x 5
         result []]
    (if (> x 0)
      (recur (dec x) (conj result (+ 2 x)))
      result)))
```
```clojure
[7 6 5 4 3]
```

28. Let bindings and function parameter lists support destructuring.
```clojure
(= [2 4] (let [[a b c d e] [0 1 2 3 4]] __))
```
```clojure
[c e]
```

29. Set A is a subset of set B, or equivalently B is a superset of A, if A is "contained" inside B. A and B may coincide.
```clojure
(clojure.set/superset? __ #{2})
(clojure.set/subset? #{1} __)
(clojure.set/superset? __ #{1 2})
(clojure.set/subset? #{1 2} __)
```
```clojure
#{1 2}
```

30. The -> macro threads an expression x through a variable number of forms. First, x is inserted as the second item in the first form, making a list of it if it is not a list already. Then the first form is inserted as the second item in the second form, making a list of that form if necessary. This process continues for all the forms. Using -> can sometimes make your code more readable.
```clojure
(= (__ (sort (rest (reverse [2 5 4 1 3 6]))))
   (-> [2 5 4 1 3 6] (reverse) (rest) (sort) (__))
   5)
```
```clojure
last
```

31. The ->> macro threads an expression x through a variable number of forms. First, x is inserted as the last item in the first form, making a list of it if it is not a list already. Then the first form is inserted as the last item in the second form, making a list of that form if necessary. This process continues for all the forms. Using ->> can sometimes make your code more readable.
```clojure
(take 3 (drop 2 [2 5 4 1 3 6]))
(= (__ (map inc (take 3 (drop 2 [2 5 4 1 3 6]))))
   (->> [2 5 4 1 3 6] (drop 2) (take 3) (map inc) (__))
   11)
```
```clojure
reduce +
```

32. Clojure's for macro is a tremendously versatile mechanism for producing a sequence based on some other sequence(s). It can take some time to understand how to use it properly, but that investment will be paid back with clear, concise sequence-wrangling later. With that in mind, read over these for expressions and try to see how each of them produces the same result.
```clojure	
(= __ (for [x (range 40)
            :when (= 1 (rem x 4))]
        x))
test not run	
(for [x (iterate #(+ 4 %) 0)
            :let [z (inc x)]
            :while (< z 40)]
        z)
(= __ (for [x (iterate #(+ 4 %) 0)
            :let [z (inc x)]
            :while (< z 40)]
        z))
test not run	
(for [[x y] (partition 2 (range 20))]
        (+ x y))
(= __ (for [[x y] (partition 2 (range 20))]
        (+ x y)))
```
```clojure
'(1 5 9 13 17 21 25 29 33 37)
```

33. In Clojure, only nil and false represent the values of logical falsity in conditional tests - anything else is logical truth.
```clojure
(= __ (if-not false 1 0))
(= __ (if-not nil 1 0))
(= __ (if true 1 0))
(= __ (if [] 1 0))
(= __ (if [0] 1 0))
(= __ (if 0 1 0))
(= __ (if 1 1 0))
```
```clojure
1
```

34. When retrieving values from a map, you can specify default values in case the key is not found:

(= 2 (:foo {:bar 0, :baz 1} 2))

However, what if you want the map itself to contain the default values? Write a function which takes a default value and a sequence of keys and constructs a map.
```clojure
(= (__ 0 [:a :b :c]) {:a 0 :b 0 :c 0})
(= (__ "x" [1 2 3]) {1 "x" 2 "x" 3 "x"})
(= (__ [:a :b] [:foo :bar]) {:foo [:a :b] :bar [:a :b]})
(= (__ [:a :b] [:foo :bar]) {:foo [:a :b] :bar [:a :b]})
```
```clojure
(fn [default_value vect] (reduce #(assoc %1 %2 default_value) {} vect))
```

35. Write a function which returns the total number of elements in a sequence.
```clojure
(= (__ '(1 2 3 3 1)) 5)
(= (__ "Hello World") 11)
(= (__ [[1 2] [3 4] [5 6]]) 3)
(= (__ '(13)) 1)
(= (__ '(:a :b :c)) 3)
```

```clojure
reduce (fn[n _] (inc n)) 0
```

36. Write a function which returns the sum of a sequence of numbers.
```clojure
(= (__ [1 2 3]) 6)
(= (__ (list 0 -2 5 5)) 8)
(= (__ #{4 2 1}) 7)
(= (__ '(0 0 -1)) -1)
(= (__ '(1 10 3)) 14)
```
```clojure
reduce + 0 
```

37. Write a function which returns only the odd numbers from a sequence.
```clojure
(= (__ #{1 2 3 4 5}) '(1 3 5))
(= (__ [4 2 1 6]) '(1))
(= (__ [2 2 4 6]) '())
(= (__ [1 1 1 3]) '(1 1 1 3))
```
```clojure
filter odd?
```

38. Write a function which reverses a sequence.
```clojure
(= (__ [1 2 3 4 5]) [5 4 3 2 1])
(= (__ (sorted-set 5 7 2 7)) '(7 5 2))
(= (__ [[1 2][3 4][5 6]]) [[5 6][3 4][1 2]])
```
```clojure
reduce (fn[coll n ] (conj coll n) ) ()
```

39. Write a function which returns true if the given sequence is a palindrome.
Hint: "racecar" does not equal '(\r \a \c \e \c \a \r)
```clojure
(false? (__ '(1 2 3 4 5)))
(true? (__ "racecar"))
(true? (__ [:foo :bar :foo]))
(true? (__ '(1 1 3 3 1 1)))
(false? (__ '(:a :b :c)))
```
```clojure
(fn [coll] (= (seq coll) (reverse coll)))
(fn[collection] ( = (seq ( reduce (fn[coll n ] (conj coll n) ) () collection)) (seq collection) )) ; using reduce, not a good solution
```




































