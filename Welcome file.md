<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Welcome file</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__html"><h2 id="intersection-of-two-arrays">349.  Intersection of Two Arrays</h2>
<p>Given two arrays, write a function to compute their intersection.</p>
<p><strong>Example 1:</strong></p>
<p><strong>Input:</strong> nums1 = [1,2,2,1], nums2 = [2,2]<br>
<strong>Output:</strong> [2]</p>
<p><strong>Example 2:</strong></p>
<p><strong>Input:</strong> nums1 = [4,9,5], nums2 = [9,4,9,8,4]<br>
<strong>Output:</strong> [9,4]</p>
<p><strong>Note:</strong></p>
<ul>
<li>Each element in the result must be unique.</li>
<li>The result can be in any order.</li>
</ul>
<p>The main thing to note here is that this question is about intersecting elements and not if a portion of one array intersects another.<br>
The second thing to note is that we do not bother about the occurrence frequency. We just want to know the common array elements.</p>
<p>One way to do this is to store both arrays in HashSets so that we get rid of redundant elements. Then pick the smaller set and use brute force to check if each elements of that set is present in the other one. If it exits, we add it to the result array.</p>
<p>But instead of using brute force, we can make use of the in-built retainAll() function in Java.</p>
<p>class Solution {<br>
public int[] intersection(int[] nums1, int[] nums2) {<br>
HashSet h1 = new HashSet();<br>
HashSet h2 = new HashSet();</p>
<pre><code>    for(int i: nums1)
        h1.add(i);
    for(int j: nums2)
        h2.add(j);
    h1.retainAll(h2);
    int index=0;
    int [] res= new int[h1.size()];
    for(int k: h1)
    {
        res[index++]=k;
    }
    return Arrays.copyOf(res,index);
    
}
</code></pre>
<p>}</p>
<h4 id="time-complexity">Time Complexity:</h4>
<p>O(m): store nums1 to set<br>
O(n): store nums2 to set<br>
O(m+n): retainAll()<br>
Total- O(m+n)</p>
<h4 id="space-complexity">Space Complexity:</h4>
<p>import java.util.*;<br>
ArrayList l1= new ArrayList();<br>
ArrayList l2= new ArrayList();</p>
<p>int n1[]={1,2,3,4,4};<br>
int n2[]={2,4};</p>
<p>for(int i: n1)<br>
l1.add(i);<br>
for(int i:n2)<br>
l2.add(i);<br>
System.out.println(l1);<br>
System.out.println(l2);<br>
l1.retainAll(l2);</p>
<p>System.out.println(l1);</p>
<h3 id="the-new-thing-i-learnt-is-retainall">The new thing I learnt is retainAll()</h3>
<p>It can be applied to Lists (ArrayLists) and Sets.<br>
It is not the intersection. It simply tells the list/set to retain the elements specified. We will undestand it better in the next example.</p>
</div>
</body>

</html>
