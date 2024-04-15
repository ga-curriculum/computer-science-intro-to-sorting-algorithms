# ![[tktk Module Name] - Exercise](./assets/hero.png)

**Learning Objectives:** By the end of this lesson, you will be able to:

- describe the time and space complexities of bubble and insertion sort.
- implement bubble and insertion sort.

# Back to Basics

Remember when you learned long division in middle school? Not to knock math teachers, but long division was a slow, painful way to get to an answer - even though eventually, you did.

Then in high school, your math teacher finally said it was okay to just use a calculator. You probably grabbed your calculator and never looked back. All that time you spent carrying numbers and finding a remainder? Sayanora!

And if you ever bugged your teachers to explain why you’d spent so many hours learning long division when you could have just used a calculator, they probably told you how important it was to learn the basics so you’d understand more complicated functions down the road.

The same logic applies when we learn sorting algorithms.

This lesson covers the “long division” of basic sorts: **bubble sorts** and **insertion sorts**.

Your math teachers would agree they’re like long division, because:

- They’re slow, inefficient, and almost never used
- They’ll equip you to be able to tackle more complex sorting algorithms

Bubble and insertion sorts are almost never used in programming. You’re much more likely to use quick or merge sorts in the programs and languages you work with; they’re kinda like the calculators of algorithms.

We learn these basic sorts, however, because they’re simple and intuitive. By learning these algorithms, you’ll understand the more complicated sorts we’ll describe in another lesson.

# Meet Bubble Sort

Bubble sorts are used for unsorted arrays, to put the values into order. It works by iterating through a dataset and comparing neighboring numbers. When the sort encounters a smaller value before a greater value, it swaps the values. The sort continues through the dataset, one by one, and swapping them until the array is sorted.

Here’s the basic process of the bubble sort algorithm:

1. Start at the beginning of a list (array) of items.
2. Compare the item you're looking at to the next item in the list.
3. If this item is greater than the next one, swap them.
4. Move on to the next item.
5. Repeat steps 1-4 until you go through the whole list without doing any swaps.

tktk Hunter - gif here

## How Bubble Sort works

Let’s use a bubble sort to sort this array of playing cards from smallest to largest. We’ll start at the beginning.

10 is bigger than the Queen, so we’ll keep them. Then we’ll move on to the next one. The Queen is bigger than the 7, so we can swap them.

We’ll keep moving across the cards, swapping cards, so that the larger cards move to the right and the smaller ones to the left.

### Knowledge Check

Is bubble sort a stable or unstable sort?

<details open>
<summary>Reveal the answer.
</summary>
<br>
Correct answer: Stable. The cards remained sorted, even as we completed more iterations through the set. That means it’s a stable sort.
</details>

---

What's the Big O **space efficiency** for bubble sort?

1. O(1)
2. O(N)
3. O(log(N))

<details open>
<summary>Reveal the answer.
</summary>
<br>
Correct answer: 1 - O(1). We didn’t have to find a new space for any of our cards while we were sorting them. That makes the space efficiency O(1), because amount of space used doesn’t change as the inputs increase.
</details>

---

What is the Big O time efficiency for bubble sort?

1. O(1)
2. O(N)
3. O(N^2)
4. O(Log(N))

<details open>
<summary>Reveal the answer.
</summary>
<br>
Correct answer: 3 - O(N^2). Bubble sort has an exponential runtime - the worst one! Think about how many iterations we had to make to sort just our array of 8 cards. Even President Barack Obama knows how slow bubble sort is. Check it out on the next page.
</details>

---

## Obama on Bubble Sort

[Click to watch](https://www.youtube.com/watch?v=k4RRi_ntQc8)

# Meet Insertion Sort

Now we’ll cover insertion sorts, which are also used on unsorted arrays. Basically, an insertion sort takes each item and inserts it into the right place in the array. 

Like bubble sort, insertion sort isn’t terribly efficient--it ends up traversing over and over the array many times. However, it’s definitely faster than Bubble sort and works more efficiently in a wider variety of circumstances. It’s mainly used in real life in conjunction with Bucket sort, which we'll learn about soon.

tktk Hunter - gif here

## Insertion Sort Visualized

One way to visualize insertion sort is to think of playing a game of cards.

Imagine you’re playing poker. As the dealer hands you your cards, you're picking up them one by one and ordering them as you go.

The first card you pick up is "sorted" by the fact that it's the only card you have. Any subsequent cards you pick up can be ordered according to how they fit into your existing hand. The cards in your hand have already been ordered how you want them. Each time you pick up a new card, you can simply insert in into the proper location.

The next card is X. It’s higher than your existing card, so you can move it to the [right/left]. You’ll continue sorting cards this way as you pick them up.

### Knowledge Check

Is insertion sort a stable or unstable sort?

<details open>
<summary>Reveal the answer.
</summary>
<br>
Correct answer: Stable. Like bubble sort, the cards in your hand remain sorted as you pick them up. That means it’s a stable sort.
</details>

---

What’s the Big O **space efficiency** for insertion sort?

1. O(1)
2. O(N)
3. O(Log(N))

<details open>
<summary>Reveal the answer.
</summary>
<br>
Correct answer: 1 - O(1). Like bubble sort, the cards in your hand remain sorted as you pick them up. That means it’s a stable sort.
</details>

---

What’s the Big O time efficiency for insertion sort?

1. O(1)
2. O(N)
3. O(N^2)
4. O(Log(N))

<details open>
<summary>Reveal the answer.
</summary>
<br>
Correct answer: 3 - O(N^2). Insertion sort is a lot like bubble sort in terms of time efficiency: lousy. Even though insertion sort works a bit faster, we still talk about both in the same Big O language.
</details>

