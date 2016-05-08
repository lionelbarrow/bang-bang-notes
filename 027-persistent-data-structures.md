### They're Functional! They're Efficient! They're Persist Data Structures!

_Anjana Vakil_

In functional programming, functions can't have side effects. This naturally pushes people to use immutable data structures. This leads to inefficiences, though, because small modifications to data structures often manifest as full copies of the existing structure.

Persistent data structures solve this problem by re-using the unchanged parts of the old data structure.

In Javascript, can use Mori or Immutable.js. Most languages have libraries of immutable data structures. Clojure is especially notable as its core data structures are immtuable; the language was built from the beginning using these techniques.
