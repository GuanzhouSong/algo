题目总结
=
[371. Sum of Two Integers](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P371_SumofTwoIntegers.java) ★★★  
`Calculate the sum of two integers a and b, but you are not allowed to use the operator + and -.`  
`Example: Given a = 1 and b = 2, return 3.`  
__位操作__的题目，对我比较新，有些意思。一次通过。  

[258. Add Digits](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P258_AddDigits.java#L19) ★  
`Given a non-negative integer num, repeatedly add all its digits until the result has only one digit.`  
`For example:Given num = 38, the process is like: 3 + 8 = 11, 1 + 1 = 2. Since 2 has only one digit, return it.`  
第一次submit失败，因为少了对输入为0时的判断。导致输入0，错误返回9。  

[136. Single Number](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P136_SingleNumber.java) ★★★  
`Given an array of integers, every element appears twice except for one. Find that single one.`  
`Note:Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?`  
* [第一个的提交](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P136_SingleNumber.java#L53)思路是完全错的，典型的以偏概全。  
* [最优答案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P136_SingleNumber.java#L17)：用到了__异或__的性质：性质1：a ^ a = 0，性质2：0 ^ a = a。 性质3：交换律。  --->  a ^ a ^ b = b。 不熟，没想到。  
习题389.[Find the Difference](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P389_FindTheDifference.java)，可以用一样的解题思路。  

[260. Single Number III](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P260_SingleNumberIII.java) ★★★  
`Given an array of numbers nums, in which exactly two elements appear only once and all the other elements appear exactly twice. Find the two elements that appear only once.`  
`For example: Given nums = [1, 2, 1, 3, 2, 5], return [3, 5].?`  
`Note: The order of the result is not important. So in the above example, [5, 3] is also correct. Your algorithm should run in linear runtime complexity. Could you implement it using only constant space complexity?`    
还是异或的bit操作，对于一次全异或后，如何区分两个唯一出现一次数字没有想出好的思路。看的[答案](http://www.cnblogs.com/Anthony-Wang/p/5048762.html)。Bit操作的算法还是不熟练。  

[137. Single Number II](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P137_SingleNumberII.java) ★★★★  
`Given an array of integers, every element appears three times except for one. Find that single one. (注：这个single one只出现一次，不包括2次。)`  
`Note: Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?`  
先实现了[需要constant memory的solution](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P137_SingleNumberII.java#L14)。实现的过程中，注意__两个bug__:
* a. 不要忽略[负数的情况](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P137_SingleNumberII.java#L56)。（这里需要熟悉__[Java中对负数的二进制表示](http://blog.csdn.net/garybrother/article/details/5991918)__。）。同时注意用到了_无符号右移操作_。
* b. 对于[Integer.MIN_VALUE边界值的处理需要注意](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P137_SingleNumberII.java#L38)。  Integer.MAX_VALUE + 1 = Integer.MIN_VALUE。 Integer.MAX_VALUE只用到了31个bit，故表达的数字的绝对值，比Integer.MIN_VALUE是要小1的。  

[283. Move Zeroes](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P283_MoveZeroes.java) ★  
`Given an array nums, write a function to move all 0's to the end of it while maintaining the relative order of the non-zero elements.`  
`For example, given nums = [0, 1, 0, 3, 12], after calling your function, nums should be [1, 3, 12, 0, 0].`  
`Note: You must do this in-place without making a copy of the array. Minimize the total number of operations.`  
典型的不需要太思考算法，但是要注意边界值处理等。第一遍没仔细看题，没注意所有非0元素的要保持原来的顺序，错了。修改后一次AC。  

[167. Two SumII](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P167_TwoSumII_InputArrayIsSorted.java) ★★★  
`Given an array of integers that is already sorted in ascending order, find two numbers such that they add up to a specific target number. The function twoSum should return indices of the two numbers such that they add up to the target, where index1 must be less than index2. Please note that your returned answers (both index1 and index2) are not zero-based. You may assume that each input would have exactly one solution.`  
`Input: numbers={2, 7, 11, 15}, target=9`  
`Output: index1=1, index2=2`  
* [二分搜索](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P167_TwoSumII_InputArrayIsSorted.java#L27)写的还是不能bug free，导致reject了几次。  
* O(n) Runtime的__[双指针算法](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P167_TwoSumII_InputArrayIsSorted.java#L48)__，没有想到。看的指导。其实应该挺直观好想的。  

[382. LinkedList Random Node](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P382_LinkedListRandomNode.java) ★★★  
1. 首先用了[查询length的算法](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P382_LinkedListRandomNode.java#L73)。注意：  
1.1 Random ran = new Random();一定先生成好ran对象，不能放在for里： for(int i = 0; i < new Random().nextInt(length); i++)，这种不能AC;  
1.2  ran.nextInt(length); 要保证length >0，否则报错： java.lang.IllegalArgumentException: bound must be positive  
2. 正规解法是用“__[蓄水池抽样](http://www.cnblogs.com/grandyang/p/5759926.html)__”算法。不知道这个算法，搜索到的。 [自己写的](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P382_LinkedListRandomNode.java#L39)几次都不能AC。还是不太明白原理。不想浪费时间了。  

[237. Delete Node In A LinkedList](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P237_DeleteNodeInALinkedList.java) ★★★  
`delete a node (except the tail) in a singly linked list, given only access to that node`  
思路比较有意思，要开阔思路。  

[383. Ransom Note](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P383_RansomNote.java) ★★  
`Given  an  arbitrary  ransom  note  string  and  another  string  containing  letters from  all  the  magazines,  write  a  function  that  will  return  true  if  the  ransom   note  can  be  constructed  from  the  magazines ;  otherwise,  it  will  return  false. Each  letter  in  the  magazine  string  can  only  be  used  once  in  your  ransom  note.`  
1. [利用Int【32】数组的最佳思路canConstruct()](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P383_RansomNote.java#L23)没想到，注意学习思路 -- __当hash table的key是有限集合时，考虑能不能用数组代替hash table__。  
2. 暴力解法[canConstruct_JavaAPI()](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P383_RansomNote.java#L76)注意bug：replace()方法会替换全部match字符串，要用replaceFirst  

[100. Same Tree](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P100_SameTree.java) ★  
`Given two binary trees, write a function to check if they are equal or not. Two binary trees are considered equal if they are structurally identical and the nodes have the same value.`  
Note when get pre-order and mid-orde result, [must include string "null"](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P100_SameTree.java#L66). See this scenario:  
![](https://github.com/zhuxiuwei/algo/blob/master/Images/100%20Same%20Tree.png)  
As pre=oder, mid-order will both print(1,1), the bug will return "true" wrongly.  

[347. Top K Frequent Elements](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P347_TopKFrequentElements.java) ★  
`Given a non-empty array of integers, return the k most frequent elements. For example, Given [1,1,1,2,2,3] and k = 2, return [1,2]`  
Note for the __[usage of Map.Entry<K, V>](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P347_TopKFrequentElements.java#L31)__, which I was not familiar before.  

[121. Best Time to Buy and Sell Stock](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P121_BestTimeToBuyAndSellStock.java) ★  
`Say you have an array for which the ith element is the price of a given stock on day i. If you were only permitted to complete at most one transaction (ie, buy one and sell one share of the stock), design an algorithm to find the maximum profit.`  
[One bug](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P121_BestTimeToBuyAndSellStock.java#L43):  If not add that line, will fail such scenario: [1, 2]  

[238. Product of Array Except Self](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P238_ProductofArrayExceptSelf.java) ★★★★★  
`Given an array of n integers where n > 1, nums, return an array output such that output[i] is equal to the product of all the elements of nums except nums[i]. Solve it without division and in O(n). For example, given [1,2,3,4], return [24,12,8,6].`  
`Follow up: Could you solve it with constant space complexity?`  
* 开始自己做，花费了不少时间，画图考虑各种情况，试图找出规律，最后[花了很多时间结果也不对](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P238_ProductofArrayExceptSelf.java#L42)。看这密密麻麻的图：  
![](https://github.com/zhuxiuwei/algo/blob/master/Images/238%20Product%20of%20Array%20Except%20Self%20-%20failed.png)  
* [最终AC的方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P238_ProductofArrayExceptSelf.java#L19)参考的[LeetCode讨论区最热门答案](https://discuss.leetcode.com/topic/18864/simple-java-solution-in-o-n-without-extra-space)。__好的方案真的很优雅__。自己想不到。  

[168. Excel Sheet Column Title](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P168_ExcelSheetColumnTitle.java),[171. Excel Sheet Column Number](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P171_ExcelSheetColumnNumber.java) ★   
不难，但估计白板上写对有难度，尤其是168，一边看leetcode test result，一边debug来做的。  

[169. Majority Element](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P169_MajorityElement.java) ★★★★  
`Given an array of size n, find the majority element. The majority element is the element that appears more than ⌊ n/2 ⌋ times.`  
题不难，但是最优的space O(1)解决方案并不好想，__查的最佳答案，还是挺优雅的__。  
* [Space O(1)的方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P169_MajorityElement.java#L21)自己想不到，挺巧妙的。参考的[LeetCode最热方案](https://discuss.leetcode.com/topic/8692/o-n-time-o-1-space-fastest-solution)  
* 利用[quick sort partition思路的方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P169_MajorityElement.java#L67)居然Timeout了,理论上应该比[majorityElement_sort方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P169_MajorityElement.java#L58)更快，__可能是我写的partition在一些特殊输入时（如1,1,1,1,2,2,2,2,2）不够高效吧__。  

[343. Integer Break](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P343_IntegerBreak.java) ★  
`Given a positive integer n, break it into the sum of at least two positive integers and maximize the product of those integers. Return the maximum product you can get.For example, given n = 2, return 1 (2 = 1 + 1); given n = 10, return 36 (10 = 3 + 3 + 4).`    
典型的__DP算法__，比较简单。自底向上和自顶向下都自己实现。  

[405. Convert a Number to Hexadecimal](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P405_ConvertANumberToHexadecimal.java) ★★  
__Bit操作__问题。不难，但是要__注意三个bug__:  
* input为0的edge case;  
* 想表示11110000000000000000000000000000，不能写成2^31+2^30+2^29+2^28，结果不是预期的。应写成：```int base = 15 << 28;```  
* 每次得到temp后，别忘了右移到最低4位，才能做0到f的映射。具体见[43行](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P405_ConvertANumberToHexadecimal.java#L43)。  

[94. Binary Tree Inorder Traversal](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P094_BinaryTreeInorderTraversal.java) ★★★★  
`Binary Tree Inorder Traversal iteratively(non-recursive)`  
非递归的中序遍历，连错7次才AC成功，根本无法做到bug free，沮丧。。。  
我之前在[《算法导论》时也写过](https://github.com/zhuxiuwei/CLRS/blob/master/src/chap12_BinarySearchTree/BinaryTree.java#L60)，当时写的实现看起来更简单，虽然效率可能略低一些（进出栈次数会多一些）  
非递归的__[前序遍历](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P144_BinaryTreePreorder.java)__，比中序写起来顺利得多，很快一次AC。  

[206. Reverse Linked List](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P206_ReverseLinkedList.java) ★  
链表翻转的[非递归](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P206_ReverseLinkedList.java#L15)和[递归](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P206_ReverseLinkedList.java#L33)算法，都一次写对，比较欣慰。。  

[406. Queue Reconstruction by Height](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P406_QueueReconstructionByHeight.java) ★★★  
`一个二维数组记录了身高和这个人前面不比他高的人数，要求重新给二维数组排序。`  
不是很顺畅。问题：  
* 思路的问题，不是特别好想。[首先给的方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P406_QueueReconstructionByHeight.java#L61)思路完全是错的，完全只是符合题目sample的特例。  
* [正确方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P406_QueueReconstructionByHeight.java#L26)，不是很顺畅，想通思路花了一些时间。编程实现的时候也需要小心，不是特别直观的。  

[378. Kth Smallest Element in a Sorted Matrix](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P378_KthSmallestElementInASortedMatrix.java) ★★★  
`Given a n x n matrix where each of the rows and columns are sorted in ascending order, find the kth smallest element in the matrix.`  
* 注意straightForward方法的[bug](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P378_KthSmallestElementInASortedMatrix.java#L109)。  
* 用[heap的方法](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P378_KthSmallestElementInASortedMatrix.java#L37)，开始想到了用队列，但是发现插入的顺序没法保证，卡在那儿了，期初不想用优先级队列。后来看discussion，别人用的也是heap(优先级队列。)  
* 用heap的方法，注意使用[辅助class](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P378_KthSmallestElementInASortedMatrix.java#L66)来简化编程。如果都记录int下标和val的话，实现时比较麻烦。  

[318. Maximum Product of Word Lengths](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P318_MaximumProductOfWordLengths.java) ★★
`Given a string array words, find the maximum value of length(word[i]) * length(word[j]) where the two words do not share common letters. You may assume that each word will contain only lower case letters. If no such two words exist, return 0.`  
又一典型__bit操作__问题。  
 * 直观的[使用Set去重](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P318_MaximumProductOfWordLengths.java#L72)的算法，超时了(对于一个大case，bit算法27ms，此算法1200ms+)。  
 * 应该用Bit操作。需要注意，[当把一个char映射到一个bit时，用位移'>>'操作，比用幂指运算Math.pow(2, (int)(c - 'a')快很多](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P318_MaximumProductOfWordLengths.java#L49)。  

[416. Partition Equal Subset Sum  Solution](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P416_PartitionEqualSubsetSum.java) ★★  
`Given a non-empty array containing only positive integers, find if the array can be partitioned into two subsets such that the sum of elements in both subsets is equal.`  
貌似__此题的test case有问题__。我一个[投机取巧的方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P416_PartitionEqualSubsetSum.java#L64)被AC了，但感觉不对。我的Greedy方案现在不确定对不对。 已经[提问](https://discuss.leetcode.com/topic/62630/need-help-super-wired-test-cases-are-there-wrong-test-cases)了。  

[328. Odd Even Linked List](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P328_OddEvenLinkedList.java) ★★  
`Given a singly linked list, group all odd nodes together followed by the even nodes. Please note here we are talking about the node number and not the value in the nodes.`  
`Example:`  
`Given 1->2->3->4->5->NULL,`  
`return 1->3->5->2->4->NULL.`  
类似__链表翻转__，很直观，但是考验编程技巧。需要注意边界值、空指针等。注意一个没判断null导致NullPointer的[bug](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P328_OddEvenLinkedList.java#L32)。  

[287. Find the Duplicate Number Solution](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/hard/P287_FindTheDuplicateNumber.java) ★★  
`Given an array nums containing n + 1 integers where each integer is between 1 and n (inclusive). Assume that there is only one duplicate number, find the duplicate one.`  
__第一个__接触到的`hard`的题目。[符合条件的bit方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/hard/P287_FindTheDuplicateNumber.java#L28)，思考出来还是花了一些时间的。有意思的是，这个符合条件的方案是O(n)的，速度竟然比[一个不符合条件的O(NlgN)方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/hard/P287_FindTheDuplicateNumber.java#L58)的AC时间还慢。好几次遇到__这种时间分析的结果优劣不是绝对的__。  

[230. Kth Smallest Element in a BST](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P230_KthSmallestElementInABST.java) ★★★★  
`Given a binary search tree, write a function kthSmallest to find the kth smallest element in it.`  
[递归写的并不顺利](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P230_KthSmallestElementInABST.java#L22)。开始不想定义全局变量current res，但是各种出错。只好最后弄这种简单的写法了。  这样可以让递归方法void，而不是返回int，或者Node。  
`Follow up:What if the BST is modified (insert/delete operations) often and you need to find the kth smallest frequently? How would you optimize the kthSmallest routine?`  
答： 可以给TreeNode增加一个filed，记录其左孩子的数目，也就是小于它的节点数。每次插入删除节点时，都可以更新受牵连的节点的这个field值。  

[453. Minimum Moves to Equal Array Elements Solution](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P453_MinimumMovesToEqualArrayElements.java) ★★★★  
`Given a non-empty integer array of size n, find the minimum number of moves required to make all array elements equal, where a move is incrementing n - 1 elements by 1. For example, input [1,2,3], result is 3. Explanation: [1,2,3]  =>  [2,3,3]  =>  [3,4,3]  =>  [4,4,4]`  
纯**数学**向的题目。虽是Easy的，还是折腾了不少时间。  
 * [最开始的方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P453_MinimumMovesToEqualArrayElements.java#L63)是平铺直叙的，就是老老实实的一步步来，直到得出结果。结果这种方案超时。  
 * [接受的方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P453_MinimumMovesToEqualArrayElements.java#L25)，**完全是凭借看规律看出来的，花了不少时间。并不是很明白其中的数学道理**。如果面试遇到这样问题肯定懵逼了，  

[423. Reconstruct Original Digits from English](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P423_ReconstructOriginalDigitsFromEnglish.java) ★★★★★  
`Given a non-empty string containing an out-of-order English representation of digits 0-9, output the digits in ascending order. Example  Input: "owoztneoer" Output: "012"`  
**花费了很多时间的一个问题。**  
* [超时的解法](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P423_ReconstructOriginalDigitsFromEnglish.java#L108)就花费了很多时间，写了非常ugly的code，最后还超时了。其中**一个问题始终没解决**，就是不知道为啥从HashSet的Iterator移除一个元素死活不管用，我另写test case就没有这个问题。在第145行附近。  
* [巧妙地解法](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P423_ReconstructOriginalDigitsFromEnglish.java#L40)，基于以下思路：  
![](https://github.com/zhuxiuwei/algo/blob/master/Images/423_Reconstruct_Original_Digits_from_English.png)  

[447. Number of Boomerangs](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P447_NumberOfBoomerangs.java) ★★  
`Given n points in the plane that are all pairwise distinct, a "boomerang"(回旋镖) is a tuple of points (i, j, k) such that the distance between i and j equals the distance between i and k (the order of the tuple matters).Find the number of boomerangs. You may assume that n will be at most 500 and coordinates of points are all in the range [-10000, 10000] (inclusive).`  
开始的思路完全是错的，提交两次错误答案。第三次才捋清楚。编程本身不复杂。关键的公式在[第42行](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P447_NumberOfBoomerangs.java#L42)。**对排列组合又有点拎不清了**。  

[436. Find Right Interval](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P436_FindRightInterval.java) ★★  
典型**二分查找**的题目。**代码写起来比较繁琐**，因为又要一顿折腾地sort，又要二分查找。 写的时候有点小bug。 错误AC了两次。  

[459. Repeated Substring Pattern](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P459_RepeatedSubstringPattern.java) ★★  
`Given a non-empty string check if it can be constructed by taking a substring of it and appending multiple copies of the substring together. You may assume the given string consists of lowercase English letters only and its length will not exceed 10000. Example 1: Input: "abab" Output: True  Explanation: It's the substring "ab" twice.`  
**字符串处理**。[最后判断结果该返回true false的条件](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P459_RepeatedSubstringPattern.java#L39)需要小心，写错了一次。 构造pattern什么的倒是很顺利。  

[39. Combination Sum](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P039_CombinationSum.java) ★★★★★★  
`Given a set of candidate numbers (C) and a target number (T), find all unique combinations in C where the candidate numbers sums to T. The same repeated number may be chosen from C unlimited number of times. For example, given candidate set [2, 3, 6, 7] and target 7, A solution set is: [[7], [2, 2, 3]]`  
**！！！！极其不顺利，典型回溯法问题！！！！**。一个题目弄到凌晨一点多。主要是总超时，然后还不会剪枝，一剪枝结果根本就不对了，跟踪递归堆栈还跟不明白。。 最后只好用了一个很傻逼的memorized cache来尽量减少无效递归，虽然AC了，也只打败了1.9%更sb的。  

[22. Generate Parentheses](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P022_GenerateParentheses.java) ★★★★★  
`Given n pairs of parentheses, write a function to generate all combinations of well-formed parentheses. For example, given n = 3, a solution set is:["((()))",  "(()())",  "(())()",  "()(())",  "()()()"]`  
**！！！！典型回溯法问题，依旧不顺利！！！！**。在[一个判断条件](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P022_GenerateParentheses.java#L40)的地方卡了半天，感觉一个应该进去的if条件死活进不去，还以为是eclipse debug时候的bug，后来仔细想是我理解的不对。   

[401. Binary Watch](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P401_BinaryWatch.java.java) ★★★  
![](https://github.com/zhuxiuwei/algo/blob/master/Images/401_BinaryWatch.png)  
**！典型回溯法问题，还算顺利！** 难得还算顺利。但是依然没有信心手写，因为IDE里debug时还是有点小问题。  

[21. Merge Two SortedLists](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P021_MergeTwoSortedLists.java) ★  
有一个[Bug](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P021_MergeTwoSortedLists.java#L21)。  

[108. Convert Sorted Array to Binary Search Tree](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P108_ConvertSortedArrayToBinarySearchTree.java) ★  
典型**递归算法**。有一个[低级bug](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P108_ConvertSortedArrayToBinarySearchTree.java#L27): 算数组的mid index，是mid=(start+end)/2， 而不是(end-start)/2..... 太低级的错误了。  

[435. Convert Sorted Array to Binary Search Tree](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P435_NonOverlappingIntervals.java) ★★★★  
`Given a collection of intervals, find the minimum number of intervals you need to remove to make the rest of the intervals non-overlapping.`  
花的时间比较长。[第一次的思路](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P435_NonOverlappingIntervals.java#L75)完全是错的，而且各种hash操作很费时间。  
正确的**Greedy**思路也有一个[bug](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P435_NonOverlappingIntervals.java#L57)。  

[46. Permutations](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P046_Permutations.java) ★★★  
`Given a collection of distinct numbers, return all possible permutations(排列).`  
**！典型回溯法问题，不算困难也不算顺利。还是debug着写的。**  

[394. Decode String](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P394_DecodeString.java) ★★★★  
`Given an encoded string, return it's decoded string. Example: s = "2[abc]3[cd]ef", return "abcabccdcdcdef".`  
**典型的实现前需要想清楚、写起来比较复杂的代码，写出来的东西是典型的面相过程的风格。这种code一旦出现bug就很难维护**。有点类似我在IBM时做的Json生成器。  
写了两次才成功。[第一次](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P394_DecodeString.java#L102) 花了不少时间，最后成了垃圾代码。拆西墙补东墙的状态。发现一个新fail case，修改，老的case又过不了。**失败的原因，是可能出现的情况没有想清楚。导致一出现一个新情况，就开始打补丁，越搞越乱。**想清楚后，重新再实现一遍，就快很多了。  
[新实现](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P394_DecodeString.java#L23)比较顺利，只有一个[容易出现的bug](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P394_DecodeString.java#L41)。  

[326. Power of Three](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P326_PowerOfThree.java) ★★★  
最直观的算法最开始都[写错了](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P326_PowerOfThree.java#L57)，弱爆了。。。  
[不用递归的算法](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P326_PowerOfThree.java#L13)很巧妙，看的讨论方案。

[424. Longest Repeating Character Replacement](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P424_LongestRepeatingCharacterReplacement.java) ★★★★★  
`Given a string that consists of only uppercase English letters, you can replace any letter in the string with another letter at most k times. Find the length of a longest substring containing all repeating letters you can get after performing the above operations. Excample: Input: s = "ABAB", k = 2, Output:4`  
**REFER. FAIL.**  
* 用**Sliding Window**. 不会，[参考答案](https://discuss.leetcode.com/topic/64833/sliding-window-java-easy-explanation-15-lines)。  

[421. Maximum XOR of Two Numbers in an Array](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P421_MaximumXORofTwoNumbersInAnArray.java) ★★★★★  
`Given a non-empty array of numbers, a0, a1, a2, … , an-1, where 0 ≤ ai < 2^31. Find the maximum result of ai XOR aj, where 0 ≤ i, j < n in O(n) time.`  
**REFER. FAIL.**  
* [我的方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P421_MaximumXORofTwoNumbersInAnArray.java#L70)花了很长时间，而且OJ时复杂case超时了。  
* [参考答案](https://discuss.leetcode.com/topic/63213/java-o-n-solution-using-bit-manipulation-and-hashmap)。不是很明白。  

[198. House Robber](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P198_HouseRobber.java) ★★★  
* [最开始](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P198_HouseRobber.java#L36)没用DP，思路完全错的。花了些时间。  
* 调整思路用[DP解法](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P198_HouseRobber.java#L19)，很快就写出来了。  

[213. House RobberII](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P213_HouseRobberII.java) ★★  
就是(198. House Robber)的一个延伸。  
* [最开始](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P213_HouseRobberII.java#L49)的DP思路是错的。  
* 然后调整思路，仔细想了下有[简单解法](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P213_HouseRobberII.java#L19)，基于[198. House Robber]比较容易写出来。  

[337. House RobberIII](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P337_HouseRobberIII.java) ★★★★  
**REFER.**  
* [最开始](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P337_HouseRobberIII.java#L74)的DP思路是错的。  
* [最终答案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P337_HouseRobberIII.java#L47)参考了https://discuss.leetcode.com/topic/41572/1ms-java-solution。  

[202. Happy Number](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P202_HappyNumber.java) ★★★  
虽然是easy，还是出现了几个bug，编程上有点小复杂，  

[96. Unique Binary Search Tree](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P096_UniqueBinarySearchTrees.java) ★★★  
* [算法超时](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P096_UniqueBinarySearchTrees.java#L47)没想到用DP，用数组表示树去老老实实的计算。问题是拷贝新数组，和生成数组的字符串表示放到Set里来去重很费时间，最后**算法超时**。  
* [最终答案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P096_UniqueBinarySearchTrees.java#L26)，**看到了DP的tag提示，才想到用DP**。还算顺利，有点小Bug。  

[62. Unique Paths](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P062_UniquePaths.java) ★  
`A robot is located at the top-left corner of a m x n grid. The robot can only move either down or right at any point in time. The robot is trying to reach the bottom-right corner of the grid. How many possible unique paths are there?`
**DP问题**。注意一个数组越界的bug。  

[35. Search Insert Position](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P035_SearchInsertPosition.java) ★  
`Given a sorted array and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.`  
**二分查找问题**。注意还是有[小bug](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P035_SearchInsertPosition.java#L20)。  

[112. Path Sum](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P112_PathSum.java) ★  
`Given a binary tree and a sum, determine if the tree has a root-to-leaf path such that adding up all the values along the path equals the given sum.`  
挺简单的问题，因为没考虑仔细，还是搞了个[bug](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P112_PathSum.java#L28)，错误了三遍才AC。  
[113. Path SumII](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P113_PathSumII.java)稍微复杂一点儿，典型**DFS/Backtracking**问题，一遍过。  

[89. Gray Code](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P089_GrayCode.java) ★★  
`The gray code is a binary numeral system where two successive values differ in only one bit. Given a non-negative integer n representing the total number of bits in the code, print the sequence of gray code. A gray code sequence must begin with 0. For example, given n = 2, return [0,1,3,2].`  
**位操作**问题，不算难，但是有俩编程实现时的bug。  

[53. Maximum Subarray](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P053_MaximumSubarray.java) ★★★★  
`Find the contiguous subarray within an array (containing at least one number) which has the largest sum. For example, given the array [-2,1,-3,4,-1,2,1,-5,4], the contiguous subarray [4,-1,2,1] has the largest sum = 6.`  
**FAIL(PARTIAL)** **分治法**问题。  
* [O(n)的方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P053_MaximumSubarray.java#L16)很快就写好了。  
* [分治法的方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P053_MaximumSubarray.java#L39)缝缝补补花了不少时间，最后结果还不对。思路不对。[参考](https://discuss.leetcode.com/topic/42213/my-divide-and-conquer-solution-in-java-under-instruction-of-clrs-o-nlogn/2)也懒得看了。  

[386. Lexicographical Numbers](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P386_LexicographicalNumbers.java) ★★★★★  
`Given an integer n, return 1 - n in lexicographical order. For example, given 13, return: [1,10,11,12,13,2,3,4,5,6,7,8,9].`  
**REFER** 可转化成**DFS**问题。  
编程角度不好写。[开始思路](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P386_LexicographicalNumbers.java#L75)是错的，后来[O(n)方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P386_LexicographicalNumbers.java#L40)写到一半写不下去了。最后[DFS方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P386_LexicographicalNumbers.java#L18)也是参考的讨论区。  

[70. Climbing Stairs](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P070_ClimbingStairs.java) ★  
`You are climbing a stair case. It takes n steps to reach to the top.Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?`  
题目本身挺简单。一个很好地说明了**循环比递归快得多**的例子。[循环方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P070_ClimbingStairs.java#L14)用0ms,[递归方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P070_ClimbingStairs.java#L35)就AC超时了。  

[173. Binary Search Tree Iterator](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P173_BinarySearchTreeIterator.java) ★★  
`二叉搜索树的iterator`  
我的方案貌似不符合题目要求的使用o(h) space的条件。符合o(h) space条件的方案是用Stack，参考https://discuss.leetcode.com/topic/6604/ideal-solution-using-stack-java/11  

[437. Path Sum III](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P437_PathSumIII.java) ★★★★  
**REFER, FAIL**  
* [我的方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P437_PathSumIII.java#L57)有错，先修复包含0的case，修复后最后整个code比较ugly了，但还是有case不对，不调了。肯定是递归思路有问题。  递归方案对的话，肯定不用这么修修补补。  
* 参考的https://discuss.leetcode.com/topic/64388/simple-ac-java-solution-dfs  

[153. Find Minimum in Rotated Sorted Array](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P153_FindMinimumInRotatedSortedArray.java) ★  
有一个特殊case时的[bug](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P153_FindMinimumInRotatedSortedArray.java#L13)。  

[199. Binary Tree Right Side View](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P199_BinaryTreeRightSideView.java) ★★  
有BFS和DFS两种方案。 [BFS](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P199_BinaryTreeRightSideView.java#L28)有一个bug。 [DFS](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P199_BinaryTreeRightSideView.java#L58)思路完全错了。  

[341. Flatten Nested List Iterator] [实现1](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P341_FlattenNestedListIterator.java) [实现2](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P341_FlattenNestedListIterator2.java)  
**实现1**：  ★★★★  
`迭代器`和`Stack`的题目. 花了比较多的时间， Fail AC好多次。  
复杂的是因为**需要处理包含empty list的情形**，尤其是有**nested empty list**的情况更复杂。因为包含empty list的时候，hasNext应该也要返回false而不是true，必须提前就要清除掉（迭代器只能next，不能prve回滚，所以不能先next以下试探看看，没问题再prve），因此我的方案是在[构造函数里先过一遍List，递归删除掉所有的空list](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P341_FlattenNestedListIterator.java#L40)。  
**实现2**： ★  
不同于实现1, 不用Stack。 递归遍历List<NestedInteger>，把所有的integer放到一个intList里，然后next和hasNext都可以直接调用intList的iterator相应方法。  

[59. Spiral Matrix II](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P059_SpiralMatrixII.java) ★★  
`Given an integer n, generate a square matrix filled with elements from 1 to n2 in spiral order. For example, Given n = 3,You should return the following matrix: [[ 1, 2, 3 ],  [ 8, 9, 4 ],  [ 7, 6, 5 ]]`  
考察**编程技巧**的题。有俩小bug。  

[390. Elimination Game](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P390_EliminationGame.java) ★★★★  
**REFER, TIMEOUT**  
* AC的方案是需要O(LgN)的，参考的 https://discuss.leetcode.com/topic/59293/java-easiest-solution-o-logn-with-explanation  
* [我的方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P390_EliminationGame.java#L47)是O(N)的，超时了。在算1000000000需要1.8s而O(lgn)算法瞬间完成。而且有些bug。  

[367. Valid Perfect Square](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P367_ValidPerfectSquare.java) ★★  
* 我的方案注意一个[bug](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P367_ValidPerfectSquare.java#L42)。  
* 参考 https://discuss.leetcode.com/topic/49325/a-square-number-is-1-3-5-7-java-code  

[342. Power of Four](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P342_PowerOfFour.java) ★★  
* 参考了一个[一行code搞定](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P342_PowerOfFour.java#L20)的解法，注意里面两个很fancy的地方：对`2^n的判断`，和`对16进制的利用`来判断是否奇数位为1。[231. Power of Two](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P231_PowerOfTwo.java)也相应改了。  
* power of 3的解法，[对于power of 4 不适用](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P342_PowerOfFour.java#L39)。**因为4不是质数**。  

[448. Find All Numbers Disappeared in an Array](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P448_FindAllNumbersDisappearedInAnArray.java) ★★★  
**REFER**  
参考的[top solution](https://discuss.leetcode.com/topic/65738/java-accepted-simple-solution)，对不利用extra space的**思路挺巧妙的**。  
[442. Find All Duplicates in an Array](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P442_FindAllDuplicatesInAnArray.java)也用类似的思路实现。  

[2. Add Two Numbers](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P002_AddTwoNumbers.java) ★  
属于编程有点小复杂容易出错的题目。  
* 第一次理解错了，完全写的不对。  
* 重新理解题目后，有[一个bug](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P002_AddTwoNumbers.java#L63)。总体顺利。  

[477. Total Hamming Distance](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P477_TotalHammingDistance.java) ★★★  
刚开始**O(n^2)**的思路会超时。**O(n)**的思路想了半天想到了。有思路了编程实现不难。  

[445. Add Two Numbers II](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P445_AddTwoNumbersII.java) ★★★★  
**典型的换个思路就很好解决的问题，不要钻牛角尖**  
* [最开始的方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P445_AddTwoNumbersII.java#L98)，和[2. Add Two Numbers](https://leetcode.com/problems/add-two-numbers/)一样，但是2的思路在这里实现要很困难，最后放弃了。  
* 后来一眼瞄到top solution里有人提到用到一种数据结构很容易解决，[改变思路后的方案](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P445_AddTwoNumbersII.java#L27)很容易就解决了。  

[345. Reverse Vowels of a String](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P345_ReverseVowelsOfAString.java) ★  
* 注意区分大小写。  
* 实现了两种解法。其中更高效的那种解法需要注意一个bug。  

[300. Longest Increasing Subsequence](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P300_LongestIncreasingSubsequence.java) ★★★★★  
**REFER**  
**典型DP问题。**看了一会感觉没思路，直接参考的某[top solution](https://discuss.leetcode.com/topic/30721/my-easy-to-understand-o-n-2-solution-using-dp-with-video-explanation)  

[309. Best Time to Buy and Sell Stock with Cooldown](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P309_BestTimeToBuyAndSellStockWithCooldown.java) ★★★★★  
**REFER**  
和300类似也是典型DP问题。不会。参考的https://discuss.leetcode.com/topic/30421/share-my-thinking-process  

[513. Find Bottom Left Tree Value](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P513_FindBottomLeftTreeValue.java) ★★★  
树的层次遍历的问题。不是特顺。第一次实现的有bug。第二次重写才OK。主要难点是，在**树的层次遍历时，如何分辨新的一层开始了。**  

[485. Find Bottom Left Tree Value](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P485_MaxConsecutiveOnes.java) ★  
注意一个[bug](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P485_MaxConsecutiveOnes.java#L33)。  

[492. Construct the Rectangle](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P492_ConstructTheRectangle.java) ★  
题目如果用最直接的解法不难，想提高些效率，[失败](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P492_ConstructTheRectangle.java#L53)。  

[563. Binary Tree Tilt](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P563_BinaryTreeTilt.java) ★★★  
**典型的二叉树递归算法问题**。自己对二叉树递归问题挺有信息，而且这个题目还是Easy，但是还是费了些时间。提交错了两次。递归返回值需要考虑清楚，比如tilt的定义是**全部**子树之和与**全部**右子树之和的差的绝对值，不只是左子树之和与右子树之和的差的绝对值。  

[501. Find Mode in Binary Search Tree](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P501_FindModeinBinarySearchTree.java) ★★  
其实本身不难，但是有个地方还是[bug](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P501_FindModeinBinarySearchTree.java#L61)了两次。  

[110. Balanced Binary Tree](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P110_BalancedBinaryTree.java) ★★★  
递归法稍微费劲儿点。[非递归](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P110_BalancedBinaryTree.java#L61)反倒挺顺利。  
1. 首先有个[bug](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P110_BalancedBinaryTree.java#L55)。  
2. 注意递归过程中既然无法退出，但是我们可以[设法降低递归深度](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P110_BalancedBinaryTree.java#L47)。  

[438. Find All Anagrams In A String](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P438_FindAllAnagramsInAString.java) ★★★★  
**REFER**  
**典型sub string的滑动窗口问题**。开始[我的解法超时](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P438_FindAllAnagramsInAString.java#L81)了。  
参考的"Sliding Window algorithm template to solve all the Leetcode substring search problem": [Link](https://discuss.leetcode.com/topic/68976/sliding-window-algorithm-template-to-solve-all-the-leetcode-substring-search-problem)。  
**这种sub string的滑动窗口问题都有一套比较固定的template解决方法**。思路绕，自己想不出来。  

[340. Find smallest range containing elements from k lists](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/hard/P340_LongestSubstringWithAtMostKDistinctCharacters.java) ★★★  
是个hard题目。也和上一题目438类似，利用**滑动窗口算法**来解决。总体顺利。注意写的时候还是有bug。最开始我想用**DP**来解决，放弃了。  

[460. LFU Cache](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/hard/P146_LRUCache.java) ★★★  
提交错了4次。。。属于本身逻辑不算复杂，但是实现起来步骤多、繁琐，容易出错的问题。  
几个问题：  
* 注意如果cache里有key，再添加时属于**UPDATE**的情况。这块当时漏掉了，引入了bug。  
* 对于LRU Cache的size，只需要用map的size即可，不需要引入单独一个变量。加入一个变量，就加入bug的风险。  

[42. Trapping Rain Water](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/hard/P042_TrappingRainWater.java) ★★★★★  
![](https://github.com/zhuxiuwei/algo/blob/master/Images/42_Trapping_Rain_Water.png)  
**REFER**  
典型**对撞型双指针**问题。当年google面过，就没答上来。[我自己的思路](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/hard/P042_TrappingRainWater.java#L47)错了，而且写起来很复杂。参考的[这个方案](https://discuss.leetcode.com/topic/3016/share-my-short-solution)。  

[200. Number Of Islands](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P200_NumberOfIslands.java) ★★  
典型DFS问题。写起来稍微麻烦。 注意一个**投机取巧的**[点子](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P200_NumberOfIslands.java#L80)，以后可以利用。  

[207。 Course Schedule](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P207_CourseSchedule.java) ★★  
典型**DFS**问题。提交总体顺利。 就是通过DFS来检测途中是否有环。 DFS又熟悉了一次。总体有点小啰嗦，有两个注意。  

[210。 Course Schedule II](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P210_CourseScheduleII.java) ★★  
典型**DFS**问题。2个注意：  
* 注意，我不用Vertex类、Color枚举类这些比较heavy的方式了，直接用Integer表示Vertex, Set<Integer>表示邻居集合。然后，基于本题业务需要，必须用grey、black两个颜色区分，这里用了个Set（visiting，visited）代表两个颜色。  
* 注意2个bug。其中第一个图初始化的错误比较严重，会导致丢失结果，其实上面【207 Course Schedule】我也犯过类似错误。  

[138。 Copy List With Random Pointer](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/medium/P138_CopyListWithRandomPointer.java) ★★★  
用了**DFS**思路，不知道有没有必要。而且有一个**严重bug**。写的时候没有完全考虑清楚造成的。  

