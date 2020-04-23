# Choosing your collection
These first two weeks we have looked deeper into three collections - HashMap, ArrayList and BST.

The Java collection framework has several more, and it sometimes become an issue of which one to select for a specific situation.

This table tries to give you an overview of big O for the operations of the most commonly used operations:

Java class | elements in order | insert | add | find | delete 
---|---|---|---|---|---
ArrayList | true | O(n) | O(1) | O(n) (unless sorted) | O(1) if last, O(n) in general.
LinkedList | true | O(n) | O(1) if added in either end | O(n) | O(n) in the middle, O(1) at ends.
HashMap | false | O(1) | O(1) | O(1) | O(1) 
TreeMap | true | O(log(n)) | O(log(n)) | O(log(n)) | O(log(n)) 
Sets (like list, but no dublicates) | false |  O(1) | O(1) | O(1) | O(1) 
Array | true | - | - | O(n) | -

The two datastructures which will cover 90% of your needs are **ArrayList** and **HashMap**.

## Converting from one collection to an other

An other situation you often end up in is that you have a collection of one type, but need one of the others. This table tries to give that overview:

Source/Target | ArrayList | LinkedList | HashMap | TreeMap | Set | Array
---|---|---|---|---|---|---
ArrayList al| - | new LinkedList(al) | - | - | new HashSet(al) | al.toArray()
LinkedList ll| new ArrayList(ll) | - |-|-| new HashSet(ll) | ll.toArray()
HashMap hm| - | - | - | - | hm.keySet()<br>hm.values()
TreeMap tm|| - | - | - | - | tm.keySet()<br>tm.values()
Set s| new ArrayList(s) | new LinkedList(s) | - | - | - | s.toArray()
Array a| new ArrayList<>(Arrays.asList(a)) | new LinkedList<>(Arrays.asList(array)) | - | - | new Set<>(Arrays.asList(array)) |-

## Exercises

1. Imagine a method which will get an array of Strings, each String being will contain just one word. You need to answer how many different words are there in the array. Which collection is well suited for this?
	- For example: ["up","down","ip","a","a", "up", "down"] will return 4 (up, down, ip, a).
2. This time you will still read the same file, but afterwards you are asked to write out how many times each word occured in the list. Which collection is well suited for this?
	- for example: ["up","down","ip","a","a", "up", "down"] will print "up: 2, down: 2, ip: 1, a: 2 
3. Same as above, but when you have to write out the words in alphabetic order.
	- for example: ["up","down","ip","a","a", "up", "down"] will print "a: 2, down: 2, ip: 1, up: 2 
4. In which situation would it be better to use a linked list than an arraylist.
5. What do you see as the advantage of array over ArrayList?
	

