# pessimal_sorting
The untapped field of deliberately inneffective logic.


# Common Sorting Algorithms
The field of sorting optimization is ubiquitous and essential to computer science, especially in foundations. An almost humorous reference point for the effectiveness of sorting is bogosort, which randomizes the order of a list then checks if if has been sorted. Bogosort has an average performance value of O((n+1)!). Another algorithm used for reference in ineffectiveness is bubblesort, which has an average performace of O(n^2). The most effective algorithms, such as quicksort or mergesort, have average performances roughly on the order of O(n log(n)).

# Existing Literature
For practical reasons optimization has been explored thoroughly, but I think there is a world of less effective methodology which could be just as fun to build on. I have been further inspired by the Andrei Broder and Jorge Stolfi in their paper Pessimal Algorithms and Simplexity Analysis (https://www.mipmip.org/tidbits/pasa.pdf), where a slowsort is outlined which has performance even lower than bubblesort, but still higher than bogosort. This paper proves that there is likely a range of pessimal effectiveness that is presently undocumented.

# Goal
The ultimate goal of this project is to create an algorithm which satisfies rules 1-3, and still has an average performance value is below bogosort O((n+1)!)

# Rules
For consideration, an algorithm must satisfy the following perameters:

1. The sorting algorithm created must be a functional and closed system. (it has to work)
2. The central logic has to be responsible for the speed of the system. (bells and whistles to add time are cheating)
3. The target average performance value must be below that of bubblesort O(n^2)


# Current ideas to be developed:

pessimal_median_sort: iterate through a list to repeatedly calculate a median (or nearest to mean) value which is appended to a new list. The new list is then split between all values above and below the first value. The lower half is flipped then stitched to the top half to make a completed sort. May violate rule 3.

pessimal_transient_derivative_sort: sort by derivative of largest transient from nearest values. Then sort it, i guess. more to come. May violate rule 1.

pessimal_ml_bogosort: by randomizing a list multiple times, data can be taken which trains an ai to reduce noise by perturbing the randomization in some way. Sounds like a tensorflow problem, may violate rule 2.

# Progress so far: 

brutebogo is a sorting algorithm that creates random lists of random sizes within a certain allowance, then checks to see if they are sorted. If they are sorted, the length of the list is compared to the random list. The sorting completes if this last comparison is a match. The assumption is made that the list in need of sorting is made of all integers between zero and the list length -1.

brutebogo check is a script which compares bogosort to brute bogo. Currently brutebogo is slightly more efficient that bogo with an efficiency value of O(n!). I believe I'm on the right track here, it may just be an logic implementation issue.

pessimal mean sort works by finding the mean or median value depending on list length and appending them to a new list. The new list is then split in half and stitched together to create a sorted list. While not objectively efficient, it is even more efficient than bubblesort, which is a disaster. This script is included as a research benchmark despite failing rule 3.

