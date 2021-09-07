Mapreduce starts with assumption that there is an input and this input is in chunks in some nature, maybe different files?

Then you can write a map function that runs on each of these chunks independently, and is supposed to output a list of key value pairs called intermediate outputs.

Then a call to a reduce function is used to map each key as input to reduce function.

# e.g. word_count
- Input 1 -> Map a,1 b,1
- Input 2 -> Map     b,1
- Input 3 -> Map         c,1

<br />

- Reduce(all a's), Reduce(all b's), Reduce(all c's)

- Entire computation is called a job, and each call to map or reduce is called a task (Map task, or reduce task).

# code
```
map(k(usually a file name), v(actual text)){
  split v into words
  for each word w
    emit(w, "1")
}
```

* emit is a function from map reduce framework. takes a key and value.

```
reduce(k, v (vector of all values associated with key)){
  emit(len(v))
}
```

* reduce has it's own emit function.

- It is reduce to compose multiple map reduce jobs.

- maps and reduces have to be functional!

Homework:
- PAPER: http://research.google.com/archive/mapreduce-osdi04.pdf

- LAB: https://pdos.csail.mit.edu/6.824/labs/lab-mr.html

