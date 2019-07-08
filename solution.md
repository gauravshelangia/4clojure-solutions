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













































