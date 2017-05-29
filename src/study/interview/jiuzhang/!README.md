九章算法的练习。  

[《新鲜出炉，Amazon SDE 面经(电面+Onsite)》](http://www.jiuzhang.com/qa/3896/)  
[翻转字符串](https://github.com/zhuxiuwei/algo/blob/master/src/lintcode/round1/P053_ReverseWordsInAString.java)  
[划分数组](https://github.com/zhuxiuwei/algo/blob/master/src/lintcode/round1/P031_PartitionArray.java)。注意**一个bug**。  
[链表求和。要求O（n）的时间复杂度。](https://github.com/zhuxiuwei/algo/blob/master/src/lintcode/round1/P167_AddTwoNumbers.java). 很简单的题，结果弄错了好几次。状态不太好。  
[二叉树两个节点的最近公共祖先](https://github.com/zhuxiuwei/algo/blob/master/src/lintcode/round1/P088_LowestCommonAncestor.java). 还是要注意如何退出递归调用问题、**有状态的类可能引入bug**的问题。   
[在一个文件中，找出所有的Anagram](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P438_FindAllAnagramsInAString.java)我的[原始方法](https://github.com/zhuxiuwei/algo/blob/master/src/LeetCode/round1/easy/P438_FindAllAnagramsInAString.java#L81)超时了。可以用**滑动窗口**。思路绕，自己想不出来。  
后面还有几道题目，暂时没时间看了。  

[《Amazon HackerRank OA 面经》](http://www.jiuzhang.com/qa/748/)  
题目1：Find first repeating letter in a string. 比如输入“abcba”, 返回“a”。 [代码](https://github.com/zhuxiuwei/algo/blob/master/src/study/interview/jiuzhang/FindFirstRepeatingLetterInAString.java)  
题目2：Merge 2 arrays in 1 array. 两个sorted array都有M个元素，但是a的capacity是M， b的capacity是2M，最后是把a中的元素加入到b中，保持sorted。[代码](https://github.com/zhuxiuwei/algo/blob/master/src/study/interview/jiuzhang/Merge2ArraysInto1Array.java)  
感觉解决方法不是很优雅。虽然可以做到，每个元素只移动一次。  