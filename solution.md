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
Note that there are two 
cases, but you are expected to supply only one answer, which will cause all the tests to pass.
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
        
(for [x (iterate #(+ 4 %) 0)
            :let [z (inc x)]
            :while (< z 40)]
        z)
(= __ (for [x (iterate #(+ 4 %) 0)
            :let [z (inc x)]
            :while (< z 40)]
        z))

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

40. The some function takes a predicate function and a collection. It returns the first logical true value of (predicate x) where x is an item in the collection.
```clojure
(= __ (some #{2 7 6} [5 6 7 8]))
(= __ (some #(when (even? %) %) [5 6 7 8])
(= __ (some #(when (even? %) %) [5 6 7 8]))
```
```clojure
6
```

41. Write a function which takes a variable number of parameters and returns the maximum value.
```clojure
(= (__ 1 8 3 4) 8)
(= (__ 30 20) 30)
(= (__ 45 67 11) 67)
```
```clojure
(fn max-of-args [& args] (reduce #(if (< %1 %2) %2 %1) (flatten args)))
```

42. Write a function which duplicates each element of a sequence.
```clojure
(= (__ [1 2 3]) '(1 1 2 2 3 3))
(= (__ [:a :a :b :b]) '(:a :a :a :a :b :b :b :b))
(= (__ [[1 2] [3 4]]) '([1 2] [1 2] [3 4] [3 4]))
(= (__ [[1 2] [3 4]]) '([1 2] [1 2] [3 4] [3 4]))
```
```clojure
(fn[collection] ( reverse ( reduce (fn[coll n ] (conj coll n n) ) () collection)  ))
```

43. Write a function which replicates each element of a sequence a variable number of times.
```clojure
(= (__ [1 2 3] 2) '(1 1 2 2 3 3))
(= (__ [:a :b] 4) '(:a :a :a :a :b :b :b :b))
(= (__ [4 5 6] 1) '(4 5 6))
(= (__ [[1 2] [3 4]] 2) '([1 2] [1 2] [3 4] [3 4]))
(= (__ [44 33] 2) [44 44 33 33])
```
```clojure
(fn[collection times] ( reverse ( reduce (fn[coll n ] (into coll (repeat times n) )  ) () collection)  ))
```

44. Write a function which creates a list of all integers in a given range.
```clojure
(= (__ 1 4) '(1 2 3))
(= (__ -2 2) '(-2 -1 0 1))
(= (__ 5 8) '(5 6 7))
```
```clojure
(fn [from to] (reverse (loop [coll () cnt from] (if (= cnt to) coll  (recur (conj  coll cnt) (inc cnt))))) )
```

45. Write a function which takes two sequences and returns the first item from each, then the second item from each, then the third, etc.
```clojure
(= (__ [1 2 3] [:a :b :c]) '(1 :a 2 :b 3 :c))
(= (__ [1 2] [3 4 5 6]) '(1 3 2 4))
(= (__ [1 2 3 4] [5]) [1 5])
(= (__ [30 20] [25 15]) [30 25 20 15])
```
```clojure
(fn [seq1 seq2 ] (#(flatten (map list seq1 seq2)) ))

#(flatten (map list %1 %2))
```

46. Given a set of sets, create a function which returns true if no two of those sets have any elements in common1 and false otherwise. Some of the test cases are a bit tricky, so pay a little more attention to them.
**Such sets are usually called pairwise disjoint or mutually disjoint.**

```clojure
(= (__ #{#{\U} #{\s} #{\e \R \E} #{\P \L} #{\.}})
   true)
#{#{:a :b :c :d :e}
         #{:a :b :c :d}
         #{:a :b :c}
         #{:a :b}
         #{:a}}
(= (__ #{#{:a :b :c :d :e}
         #{:a :b :c :d}
         #{:a :b :c}
         #{:a :b}
         #{:a}})
   false)
(= (__ #{#{[1 2 3] [4 5]}
         #{[1 2] [3 4 5]}
         #{[1] [2] 3 4 5}
         #{1 2 [3 4] [5]}})
   true)
(= (__ #{#{'a 'b}
         #{'c 'd 'e}
         #{'f 'g 'h 'i}
         #{''a ''c ''f}})
   true)
(= (__ #{#{'(:x :y :z) '(:x :y) '(:z) '()}
         #{#{:x :y :z} #{:x :y} #{:z} #{}}
         #{'[:x :y :z] [:x :y] [:z] [] {}}})
   false)
(= (__ #{#{(= "true") false}
         #{:yes :no}
         #{(class 1) 0}
         #{(symbol "true") 'false}
         #{(keyword "yes") ::no}
         #{(class '1) (int \0)}})
   false)
(= (__ #{#{distinct?}
         #{#(-> %) #(-> %)}
         #{#(-> %) #(-> %) #(-> %)}
         #{#(-> %) #(-> %) #(-> %)}})
   true)
#{#{(#(-> *)) + (quote mapcat) #_ nil}
         #{'+ '* mapcat (comment mapcat)}
         #{(do) set contains? nil?}
         #{, , , #_, , empty?}}
(= (__ #{#{(#(-> *)) + (quote mapcat) #_ nil}
         #{'+ '* mapcat (comment mapcat)}
         #{(do) set contains? nil?}
         #{, , , #_, , empty?}})
   false)
```
```clojure
(fn [coll] (apply distinct? (apply concat coll)) )
#(apply distinct? (apply concat %)) 
```

47. Write a function which takes a string and returns a new string containing only the capital letters.
```clojure
(= (__ "HeLlO, WoRlD!") "HLOWRD")
(empty? (__ "nothing"))
(= (__ "$#A(*&987Zf") "AZ")
```
```clojure
(fn [x] (apply str (re-seq #"[A-Z]" x)))
#(apply str (re-seq #"[A-Z]" %))
```

48. Write a function which removes consecutive duplicates from a sequence.
```clojure
(= (apply str (__ "Leeeeeerrroyyy")) "Leroy")
(= (__ [1 1 2 3 3 2 2 3]) '(1 2 3 2 3))
(= (__ [[1 2] [1 2] [3 4] [1 2]]) '([1 2] [3 4] [1 2]))
```
```
(fn[coll in] (reduce (fn[coll input] (if (not= (last coll) input) (conj coll input) coll) ) coll in )) []
```

49. Write a function which packs consecutive duplicates into sub-lists.
```clojure
(= (__ [1 1 2 1 1 1 3 3]) '((1 1) (2) (1 1 1) (3 3)))
(= (__ [:a :a :b :b :c]) '((:a :a) (:b :b) (:c)))
(= (__ [[1 2] [1 2] [3 4]]) '(([1 2] [1 2]) ([3 4])))
```
```
partition-by identity
```

50. Write a function which separates the items of a sequence by an arbitrary value.
```clojure
(= (__ 0 [1 2 3]) [1 0 2 0 3])
(= (apply str (__ ", " ["one" "two" "three"])) "one, two, three")
(= (__ :z [:a :b :c :d]) [:a :z :b :z :c :z :d])
```
```
(fn[sep sequ] (->> (reduce #(conj %1 sep %2) [] sequ) (drop 1)) )
```

51. Write a function which calculates factorials.
```clojure
(= (__ 1) 1)	
(= (__ 3) 6)	
(= (__ 5) 120)
(= (__ 8) 40320)
```
```clojure
(fn factorial [number] (
            cond 
            (= number 1) 1   
            (> number 1) (* number (factorial (dec number)) )
            )
             )
             
(fn factorial[number]
  (if (<= number 1) 1 (* number  (factorial (- number 1))  )))

(fn [n] (reduce * (range 1 (inc n))))
```

52. The iterate function can be used to produce an infinite lazy sequence.
```clojure
iterate #(+ 3 %) 1)))
(= __ (take 5 (iterate #(+ 3 %) 1)))
```
```clojure
'(1 4 7 10 13)
```

53. Write a function which flattens a sequence.
```clojure
(= (__ '((1 2) 3 [4 [5 6]])) '(1 2 3 4 5 6))
(= (__ ["a" ["b"] "c"]) '("a" "b" "c"))
(= (__ '((((:a))))) '(:a))
```
```clojure
(fn flat-seq [sequ]
  (if (coll? sequ)
    (mapcat flat-seq sequ)
    [sequ]))
```

54. Write a function which drops every Nth item from a sequence.
```clojure
(= (__ [1 2 3 4 5 6 7 8] 3) [1 2 4 5 7 8])
(= (__ [:a :b :c :d :e :f] 2) [:a :c :e])
(= (__ [1 2 3 4 5 6] 4) [1 2 3 5 6])
```
```clojure
(fn drop-every-nth [result coll n] (
                     if(not (empty? coll))
                     	(do 
                          (concat result (take (dec n) coll)
                          (drop-every-nth result (drop n coll) n)        
                                  ))
                     	result
 						
              
              )
  ) '()
```

55. The contains? function checks if a KEY is present in a given collection. This often leads beginner clojurians to use it incorrectly with numerically indexed collections like vectors and lists.
```clojure
(contains? #{4 5 6} __)
(contains? [1 1 1 1 1]
(contains? [1 1 1 1 1] __)
(contains? {4 :a 2 :b} __)
(not (contains? [1 2 4] __))
```
```clojure
4
```

56. Write a function which will split a sequence into two parts.
```clojure
(= (__ 3 [1 2 3 4 5 6]) [[1 2 3] [4 5 6]])
(= (__ 1 [:a :b :c :d]) [[:a] [:b :c :d]])
(= (__ 2 [[1 2] [3 4] [5 6]]) [[[1 2] [3 4]] [[5 6]]])
```
```clojure
#(reverse (conj '() (take %1 %2) (drop %1 %2)))
```

57. Here is an example of some more sophisticated destructuring.
```clojure
(= [1 2 [3 4 5] [1 2 3 4 5]] (let [[a b & c :as d] __] [a b c d]))
```
```clojure
[1 2 3 4 5]
```

58. Write a function which takes a variable number of booleans. Your function should return true if some of the parameters are true, but not all of the parameters are true. Otherwise your function should return false.
```clojure
(= false (__ false false))
(= true (__ true false))
(= false (__ true))
(= true (__ false true false))
(= false (__ true true true))
(= true (__ true true true false))
```
```clojure
not=
```

59. Write a function which takes a vector of keys and a vector of values and constructs a map from them.
```clojure
(= (__ [:a :b :c] [1 2 3]) {:a 1, :b 2, :c 3})
(= (__ [1 2 3 4] ["one" "two" "three"]) {1 "one", 2 "two", 3 "three"})
(= (__ [:foo :bar] ["foo" "bar" "baz"]) {:foo "foo", :bar "bar"})
```
```
#(into (sorted-map) (map hash-map %1 %2))
#(into {} (map hash-map %1 %2))
```

60. Given a side-effect free function f and an initial value x write a function which returns an infinite lazy sequence of x, (f x), (f (f x)), (f (f (f x))), etc.
```clojure
(= (take 5 (__ #(* 2 %) 1)) [1 2 4 8 16])
(= (take 100 (__ inc 0)) (take 100 (range)))
(= (take 9 (__ #(inc (mod % 3)) 1)) (take 9 (cycle [1 2 3])))
```
```clojure
(fn re-iterate[f n](
                    cons n (lazy-seq (re-iterate f (f n)))
                    )
  )
```

61. Given two integers, write a function which returns the greatest common divisor.
```clojure
(__ 2 4)
(= (__ 2 4) 2)
(= (__ 10 5) 5)
(= (__ 5 7) 1)
(= (__ 1023 858) 33)
```
```clojure
(fn gcd[n1, n2] (
               if(= n2 0 )
               n1
               (gcd n2 (rem n1 n2))
               ))
```

62. Write a function which returns the intersection of two sets. The intersection is the sub-set of items that each set has in common.
```clojure
#{0 1 2 3}
(= (__ #{0 1 2 3} #{2 3 4 5}) #{2 3})
(= (__ #{0 1 2} #{3 4 5}) #{})
(= (__ #{:a :b :c :d} #{:c :e :a :f :d}) #{:a :c :d})
```
```clojure
(fn[s1 s2] (set (reduce #( if(contains? s1 %2) (conj %1 %2) %1 ) '() s2 )) )

(fn [s1 s2] (into #{} (filter #(s2 %) s1)))

```

63. Write a function which multiplies two numbers and returns the result as a sequence of its digits.
```clojure
(= (__ 1 1) [1])
(= (__ 99 9) [8 9 1])
(= (__ 999 99) [9 8 9 0 1])
```
```clojure
(fn[n1 n2] (map #(Character/digit % 10) (str (* n1 n2)) ))
```

64. Given a function f and a sequence s, write a function which returns a map. The keys should be the values of f applied to each item in s. The value at each key should be a vector of corresponding items in the order they appear in s.
```clojure
#(> % 5
(= (__ #(> % 5) [1 3 6 8]) {false [1 3], true [6 8]})
(= (__ #(apply / %) [[1 2] [2 4] [4 6] [3 6]])
   {1/2 [[1 2] [2 4] [3 6]], 2/3 [[4 6]]})
(= (__ count [[1] [1 2] [3] [1 2 3] [2 3]])
   {1 [[1] [3]], 2 [[1 2] [2 3]], 3 [[1 2 3]]})
 ```
 ```clojure
 (fn g-by[f s] (reduce #(if(contains? %1 (f %2) ) (assoc %1 (f %2) (conj (get %1 (f %2)) %2)) (assoc %1 (f %2) (conj (vector) %2)) ) {} s ))
 ```

65. Create a function that computes the dot product of two sequences. You may assume that the vectors will have the same length.
```clojure
(__ [0 1 0] [1 0 0])
(= 0 (__ [0 1 0] [1 0 0]))
(= 3 (__ [1 1 1] [1 1 1]))
(= 32 (__ [1 2 3] [4 5 6]))
(= 256 (__ [2 5 6] [100 10 1]))
```
```clojure
#(reduce + (map * %1 %2))
```

66. Map is one of the core elements of a functional programming language. Given a function f and an input sequence s, return a lazy sequence of (f x) for each element x in s.
```clojure
(= [3 4 5 6 7]
   (__ inc [2 3 4 5 6]))
(= (repeat 10 nil)
   (__ (fn [_] nil) (range 10)))
(= [1000000 1000001]
   (->> (__ inc (range))
        (drop (dec 1000000))
        (take 2)))
```
```clojure
;(fn c-map [f s] (reduce #(conj %1 (f %2) ) [] s  ) ) ;; not a good solution
(fn c-map [f s]
  (lazy-seq
    (if (seq s)
      (cons (f (first s)) (c-map f (rest s)))
      nil
      )))
```

67. Lexical scope and first-class functions are two of the most basic building blocks of a functional language like Clojure. When you combine the two together, you get something very powerful called lexical closures. With these, you can exercise a great deal of control over the lifetime of your local bindings, saving their values for use later, long after the code you're running now has finished.

It can be hard to follow in the abstract, so let's build a simple closure. Given a positive integer n, return a function (f x) which computes xn. Observe that the effect of this is to preserve the value of n for use outside the scope in which it is defined.

```clojure
(= 256 ((__ 2) 16),
       ((__ 8) 2))
(= [1 8 27 64] (map (__ 3) [1 2 3 4]))
(= [1 2 4 8 16] (map #((__ %) 2) [0 1 2 3 4]))
```
```clojure
(fn f[n] 
  (fn x-n[x] 
    (int (Math/pow x n))))
```

68. For any orderable data type it's possible to derive all of the basic comparison operations (<, ≤, =, ≠, ≥, and >) from a single operation (any operator but = or ≠ will work). Write a function that takes three arguments, a less than operator for the data and two items to compare. The function should return a keyword describing the relationship between the two items. The keywords for the relationship between x and y are as follows:
x = y → :eq
x > y → :gt
x < y → :lt

```clojure
(= :gt (__ < 5 1))
(__ (fn [x y] (< (count x) (count y))) "pear" "plum")
(= :eq (__ (fn [x y] (< (count x) (count y))) "pear" "plum"))
(= :lt (__ (fn [x y] (< (mod x 5) (mod y 5))) 21 3))
(= :gt (__ > 0 2))
```
```clojure
(fn cmp[f x y] (cond (f x y) :lt (f y x ) :gt :else :eq))

```

69. Enter a value which satisfies the following:
```clojure
(let [x __]
  (and (= (class x) x) x))
```
```clojure
Class
```

70. Transform a sequence into a sequence of pairs containing the original elements along with their index.
```clojure
[:a :b :c]
(= (__ [:a :b :c]) [[:a 0] [:b 1] [:c 2]])
(= (__ [0 1 3]) '((0 0) (1 1) (3 2)))
(= (__ [[:foo] {:bar :baz}]) [[[:foo] 0] [{:bar :baz} 1]])
```
```clojure
#(map-indexed (fn [index itm] [itm index]) %)
#(map vector % (range 0 (count %)))
```

71. Convert a binary number, provided in the form of a string, to its numerical value.
```clojure
(= 0     (__ "0"))
(= 7     (__ "111"))
(= 8     (__ "1000"))
(= 9     (__ "1001"))
(= 255   (__ "11111111"))
(= 1365  (__ "10101010101"))
(= 65535 (__ "1111111111111111"))
```
```clojure
#(Integer/parseInt % 2)
```





