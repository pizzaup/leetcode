# [997. Find the Town Judge](https://leetcode.com/problems/find-the-town-judge)

[中文文档](/solution/0900-0999/0997.Find%20the%20Town%20Judge/README.md)

## Description

<p>In a town, there are <code>N</code> people labelled from&nbsp;<code>1</code> to <code>N</code>.&nbsp; There is a rumor that one of these people is secretly the town judge.</p>



<p>If the&nbsp;town judge exists, then:</p>



<ol>
	<li>The town judge trusts nobody.</li>
	<li>Everybody (except for the town judge) trusts the town judge.</li>
	<li>There is exactly one person that satisfies properties 1 and 2.</li>
</ol>



<p>You are given <code>trust</code>, an array of pairs <code>trust[i] = [a, b]</code> representing that the person labelled <code>a</code> trusts the person labelled <code>b</code>.</p>



<p>If the town judge exists and can be identified, return the label of the town judge.&nbsp; Otherwise, return <code>-1</code>.</p>



<p>&nbsp;</p>

<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> N = 2, trust = [[1,2]]

<strong>Output:</strong> 2

</pre><p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> N = 3, trust = [[1,3],[2,3]]

<strong>Output:</strong> 3

</pre><p><strong>Example 3:</strong></p>

<pre><strong>Input:</strong> N = 3, trust = [[1,3],[2,3],[3,1]]

<strong>Output:</strong> -1

</pre><p><strong>Example 4:</strong></p>

<pre><strong>Input:</strong> N = 3, trust = [[1,2],[2,3]]

<strong>Output:</strong> -1

</pre><p><strong>Example 5:</strong></p>

<pre><strong>Input:</strong> N = 4, trust = [[1,3],[1,4],[2,3],[2,4],[4,3]]

<strong>Output:</strong> 3

</pre>

<p>&nbsp;</p>

<p><strong>Constraints:</strong></p>



<ul>
	<li><code>1 &lt;= N &lt;= 1000</code></li>
	<li><code>0 &lt;= trust.length &lt;= 10^4</code></li>
	<li><code>trust[i].length == 2</code></li>
	<li><code>trust[i]</code> are all different</li>
	<li><code>trust[i][0] != trust[i][1]</code></li>
	<li><code>1 &lt;= trust[i][0], trust[i][1] &lt;= N</code></li>
</ul>

## Solutions

<!-- tabs:start -->

### **Python3**

```python
class Solution:
    def findJudge(self, n: int, trust: List[List[int]]) -> int:
        if n == 1 and len(trust) == 0:
            return 1
        dic = {}
        values = set()
        for i in trust:
            values.add(i[0])
            if i[1] in dic:
                dic[i[1]].append(i[0])
            else:
                dic[i[1]] = [i[0]]

        for key, value in dic.items():
            if len(dic[key]) == n-1 and key not in values:
                return k
```

### **Java**

```java

```

### **...**

```

```

<!-- tabs:end -->
