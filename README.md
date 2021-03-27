# MyNotes: README
* [Basics](https://github.com/atgarg11/iPrep-MyNotes/blob/main/Basics.md)
* [cProject](https://github.com/atgarg11/cProject/blob/master/README.md)
* [LcExplore Cards](https://github.com/atgarg11/iPrep-MyNotes/blob/main/lcexploreCards.md)
* [Arrays](https://github.com/atgarg11/iPrep-MyNotes/blob/main/Arrays.md)
* [Segment Trees](https://github.com/atgarg11/iPrep-MyNotes/blob/main/SegmentTree.md)
* [Bitwise Operations](https://github.com/atgarg11/iPrep-MyNotes/blob/main/bitOperations.md)
* [Divide And Conquer](https://github.com/atgarg11/iPrep-MyNotes/blob/main/DivideNConquer.md)
* [STL](https://github.com/atgarg11/iPrep-MyNotes/blob/main/STL.html)
* [OverFlow](https://github.com/atgarg11/iPrep-MyNotes/blob/main/overFlow.md)

# Tricks: 
## See if the loop you are running, can they be run on smaller numbers. For example instead of running on the length of the dictionary, can it be run on the length of the word to reduce from O(n2) to smaller order
* Instead of running for loop on the dictionary length, run once on word lenght as word length < dic.length
    * [820. Short Encoding of Words](https://leetcode.com/problems/short-encoding-of-words/)

## Some times the solution that comes first to mind is not Best solution. And if you feel the solution is getting dirty, there is probably another alternative / Trick to it. 
* Reduce a minimum problem to a maximum problem and vice versa.
    * [LC1658 Minimum Operations](https://leetcode.com/problems/minimum-operations-to-reduce-x-to-zeroo)
    
    This problem is easily reduced to a maximum subarray sum problem, which is much more
        easier and manageable to solve. 
* Reduce a multiplcation addition problem to division and subtraction problem. This is useful for minimization problems.
[991. Broken Calculator](https://leetcode.com/problems/broken-calculator/)

* Hash is found to be more faster than sets for element search. 
    * [820. Short Encoding of Words](https://leetcode.com/problems/short-encoding-of-words/)