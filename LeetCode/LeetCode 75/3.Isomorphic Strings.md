> Given two strings `s` and `t`, _determine if they are isomorphic_.
> 
> Two strings `s` and `t` are isomorphic if the characters in `s` can be replaced to get `t`.
> 
> All occurrences of a character must be replaced with another character while preserving the order of characters. No two characters may map to the same character, but a character may map to itself.
> 
> **Example 1:**
> 
> <pre>**Input:** s = "egg", t = "add"
> **Output:** true
> </pre>
> 
> **Example 2:**
> 
> <pre>**Input:** s = "foo", t = "bar"
> **Output:** false
> </pre>
> 
> **Example 3:**
> 
> <pre>**Input:** s = "paper", t = "title"
> **Output:** true
> </pre>
> 
> **Constraints:**
> 
> *   `1 <= s.length <= 5 * 104`
> *   `t.length == s.length`
> *   `s` and `t` consist of any valid ascii character.
>
> -- https://leetcode.com/problems/isomorphic-strings/description/?envType=study-plan&id=level-1#qd-content
```
class Solution:
    def isIsomorphic(self, s: str, t: str) -> bool:
        map_dict = {}
        for si,ti in zip(s,t):
            # Checking if there is a map in the dictionary
            if not si in map_dict.keys():
                # Checking if an entry in ti is already mapped to si
                if ti not in map_dict.values():
                    map_dict[si] = ti
                else:
                    return False
            else:
                # Checking if the current map of ti is working for next encounter
                if map_dict[si]!=ti:
                    return False
        return True


```
