# ![[tktk Module Name] - Exercise](./assets/hero.png)

**Learning Objective:** By the end of this lesson, you will be able to

- define two sorting methods and when you'd use each.
- identify whether a sort is stable or unstable, and what impact that can have.
- explain how Big O complexity applies to sorting algorithms.

# What is Sorting?

Sorting in computer science is no different than sorting in real life. It's putting an unordered collection of stuff, like this pile of Legos, and putting them into an ordered collection of stuff, like these Legos here.

Sorting is the foundation for much more complex algorithms. Do you want to manage customer accounts on your e-commerce site? Search a database for information? Schedule computing jobs to minimize completion time? Behind all of these important processes is a solid sorting algorithm.

If the only thing we're trying to accomplish is putting things in order, how many sorting algorithms could there be? Surely it can’t be that complicated!

You'd be surprised. There are hundreds of sorting algorithms! There's bubble sort, merge sort, quick sort, heap sort, radix sort, cube sort, bucket sort, shell sort, tree sort, insertion sort, selection sort, counting sort... and those are just the more common ones!

Each sort we'll cover has its advantages and disadvantages. It's important for us to understand why some sorts are bad before we can improve them. As you'll discover, some of the most intuitive ways to sort are actually pretty terrible!

## Types of Sorting: Comparison Sort

There are two major types of sorting algorithms.

A comparison sort does what it says on the tin: it compares two items and decides which one to put first. If you're comparing numbers, use their values; if you're comparing words, use the alphabet; if you’re comparing Lego blocks, use their size, as below.

tktk Hunter - (GIF)

## Types of Sorting: Distribution Sort

Instead of comparing two items, distribution sort uses some property of the item itself to decide where it fits. Most of the time, this means dividing the items into groups based on some characteristic of the data itself. With our Lego blocks, this could mean grouping them by color.

tktk Hunter - (GIF)

Comparison and distribution sort aren't better or worse than one another. They simply function differently, which means that they’re better suited for different types of datasets.

## Knowledge Check

It’s time to clean out your closet and donate some old clothes to a thrift store. The thrift purchases items based on the current time of year, so you’re sorting your clothes by season (winter, spring, summer, fall).

What sorting method are you using here?

1. Comparison sort
2. Distribution sort

<details open>
<summary>Reveal the answer.
</summary>
<br>
Correct answer: 2 - Distribution. In this instance, you’re grouping items into categories of similar things, rather than comparing each individual item to the next. That’s a distribution sort. If you were to sort all your t-shirts from oldest to newest, you might use a comparison sort.
</details>

---

# Stability

Before we go too much further, let’s discuss one important characteristic of sorting: stability. Stability preserves the initial order of a collection. It allows you to sort by one factor and then by another, without the second sort screwing up the first one.

Let's say you want to sort these cards numerically. Here's what you’d get.

Next, you want to sort them by number AND by suit. If you used an unstable sort, your cards would end up looking like this. Sure, the cards are in order by suit, but you’ve lost the numerical ordering.

But if you use a stable sort, you can keep the numerical ordering when you next sort by suit. Much better!

Some algorithms are stable while others aren't. If your dataset needs to be sorted based on two factors, you need to make sure the sort you're using is stable.

## Knowledge Check

Imagine that you're running a programming contest. Everyone competes to answer 10 questions in one hour. Winners are determined first by how many problems they were able to solve. In the case of a tie, they’re next judged on how long it took them to finish all their problems.

Here are the results sorted by time:

```js
programmers = [
	{ solved: 8, minutes: 23 },
	{ solved: 6, minutes: 27 },
	{ solved: 2, minutes: 28 },
	{ solved: 6, minutes: 35 },
	{ solved: 6, minutes: 43 },
];
```

You then created this sort to determine the second place winner:

```js
programmers = [
	{ solved: 8, minutes: 23 },
	{ solved: 6, minutes: 35 },
	{ solved: 6, minutes: 27 },
	{ solved: 6, minutes: 43 },
	{ solved: 2, minutes: 28 },
];
```

Is this sort stable or unstable?

<details open>
<summary>Reveal the answer.
</summary>
<br>
Correct answer: Unstable. When we sorted the second time, we lost the relationship between the correct number of problems solved and time spent. Whoops! There might be some unhappy programmers after this… 
</details>

---

# Algorithms in Time and Space

Remember Big O Notation? We can compare sorting algorithms using Big O.

Big O can be used to describe the time and space complexities of algorithms. In software development, Big O focuses on the efficiency of an algorithm as its input increases.

- **Time complexity** refers to the amount of time an algorithm takes to run.
- **Space complexity** refers to the amount of memory or RAM an algorithm needs to run.

Both values look at the "worst case scenario" of these measures; that is, the maximum amount of time it could take for your algorithm to run, or the maximum amount of space it would require.

## Knowledge Check

Time for a review! Of the four types listed below, which type of complexity is the least efficient?

1. O(1)
2. O(N)
3. O(log(N))
4. O(N^2)

<details open>
<summary>Reveal the answer.
</summary>
<br>
Correct answer: 4 - Quadratic. Quadratic complexity algorithms are the least efficient. If you have a dataset with N items, you’ll perform an operation N*N times. Not good!
</details>

---

## Looking at Time Complexity

Big O is used as an estimate how many calculations you will need to perform, described by the “worst case scenario.”

The variable n is the size of the input, or more plainly, the number of items being sorted.

|                |      |         | Run Times |             |          |
| -------------- | ---- | ------- | --------- | ----------- | -------- |
| Input Size (n) | O(1) | O(logN) | O(N)      | O(N2)       | O(N!)    |
| 1              | 1    | 1       | 1         | 1           | 1        |
| 10             | 1    | 3       | 10        | 100         | 3628800  |
| 40             | 1    | 5       | 40        | 1600        | 8.16e+47 |
| 80             | 1    | 6       | 80        | 6400        | 80!      |
| 600            | 1    | 9       | 600       | 360000      | 600!     |
| 10000          | 1    | 13      | 10,000    | 100,000,000 | 10,000!  |

As we move from left to right across the table, we’re moving from very efficient runtimes like O(1) and O(log n), to extremely inefficient runtimes like O(N!). Stay away from the ones on the right!

## Looking at Space Complexity

When we measure space complexity, we are measuring how much extra space our algorithm requires as a function of the input.

Space complexity is usually described in one of two formats.

| Type         | Big O Complexity  | Description                                                                                   |
| ------------ | ----------------- | --------------------------------------------------------------------------------------------- |
| In place     | O(1) or (Olog(N)) | The space the algorithm takes is predictable and does not depend on the size of the input.    |
| Out of place | O(N)              | The algorithm uses an extra array, the same size as the input array, to sort the values into. |

## The Worst, the Best, and the Average

If talking about things based on the worst case sounds pessimistic, don’t despair! While worst-case, Big O, is the more common way to compare algorithms, we also discuss their best and average cases, too!

An algorithm’s best case performance is called "Big Omega". Big Omega describes how fast an algorithm would run if it performed the fewest possible actions on a dataset. If you were sorting an already sorted set, you'd get the Big Omega value.

An algorithm’s average case performance is called “Big Theta”. Big Theta describes the typical, average case runtime of an algorithm.

tktk Hunter - (GRAPHIC)

Check out how different algorithms perform relative to each other on the next slide. No need to watch the entire video, but check out as much as you want in order to get a feel for the different speeds of these algorithms. (Warning: there's lots of moving colors and fast speeds. If this isn't your thing, check out this [simpler version](https://www.toptal.com/developers/sorting-algorithms).)

## Time and Space, Visualized

[Click to watch](https://www.youtube.com/watch?v=ZZuD6iUe3Pc)

## Other Things to Consider

Understanding a sorting algorithm's time and space complexities helps us understand which algorithms to use when.

In addition to time and space complexity, there are a few other factors to think about when choosing a sort:

- Stability (whether the items in the set stay in order)
- Sorting method (comparison, distribution, or a combination of the two)
- The size and structure your data is in (sorted, unsorted, very large, etc.)

# Okay, where's the cheatsheet?

We gotcha.

You may not recognize all of these sorts, and that’s okay, because we’ll get to them soon. However, keep this comparison in mind as you learn about each of them in the lessons that follow. You can download this handout here (you know, to print, hang on your desk, and gaze at every day as you ponder the complexities of sorting algorithms).

| Sort           | Best Case | Average Case | Worst Case | Space  | Stable | Type |
| -------------- | --------- | ------------ | ---------- | ------ | ------ | ---- |
| Bubble Sort    | Ω(n)      | Θ(n^2)       | O(n^2)     | O(1)   | Yes     | Comparison   |
| Insertion Sort | Ω(n2)     | Θ(n^2)       | O(n^2)     | O(n)   | Yes     | Comparison   |
| Bucket Sort    | Ω(n+k)    | Θ(n+k)       | O(n^2)     | O(n+k) | Yes     | Distribution   |
| Merge Sort     | Ω(log(n)) | Θ(log(n))    | O(log(n))  | O(n)   | Yes     | Comparison   |
| Quick Sort     | Ω(log(n)) | Θ(log(n))    | O(n^2)     | O(log(n)) | No     | Comparison |


# The Perfect Sort Doesn't Exist

Your next question might be, “Can't you just tell me which algorithm is the best and teach me that one?!”

Unfortunately, the perfect sort--the one sort to rule them all--doesn’t exist. While there are a few choice sorts you should get very familiar with, there isn't one "best" algorithm because different sorts are good at different things. Based on your needs for a specific situation, you'll want to consider time complexity, space complexity, stability, and the kind of mechanism the algorithm uses to sort. We’ll dive into all of that nex!
