# Regular-Expression-Matching-in-java
🧩 Problem Statement:

Given an input string s and a pattern p, implement regular expression matching with support for '.' and '*' where:

'.' matches any single character.

'*' matches zero or more of the preceding element.


The matching should cover the entire input string (not partial).


---

Examples:

Input	Output	Explanation

s = "aa", p = "a"	false	'a' does not match 'aa'
s = "aa", p = "a*"	true	'*' means zero or more of 'a'
s = "ab", p = ".*"	true	.* means any character repeated



---

💡 Approach:

We use Dynamic Programming (DP) to solve this efficiently.
Let dp[i][j] be whether s[0..i-1] matches p[0..j-1].

Transitions:

1. If characters match (or p[j-1] == '.'):
dp[i][j] = dp[i-1][j-1]


2. If p[j-1] == '*':

We can ignore the preceding element: dp[i][j] = dp[i][j-2]

Or, if the preceding character matches current one:
dp[i][j] = dp[i-1][j] (use one more occurrence)



🧩 Output:

false
true
true
false


---

⚙️ Complexity:

Type	Complexity

Time	O(m × n)
Space	O(m × n)



---

🔍 Explanation (Visual Example):

s	p	Meaning	Result

"aa"	"a*"	* repeats 'a' 0 or more times	✅ match
"ab"	".*"	. any char, * repeats any number of times	✅ match
"mississippi"	"mis*is*p*."	last pattern can’t match full string	❌ no match



---
