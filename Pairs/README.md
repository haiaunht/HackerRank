# [Count Pairs]

```
Given an array of integers and a target value, determine the number of pairs of array elements that have a difference equal to the target value.

Example


There are three values that differ by : , , and . Return .

Function Description

Complete the pairs function below.

pairs has the following parameter(s):

int k: an integer, the target difference
int arr[n]: an array of integers
Returns

int: the number of pairs that satisfy the criterion
Input Format

The first line contains two space-separated integers  and , the size of  and the target value.
The second line contains  space-separated integers of the array .


```

# Solution

```
public static int pairs(int k, List<Integer> arr) {
    // Write your code here
        int[] mem = new int[arr.size()];
        Map<Integer, Integer> map = new HashMap<>();
        for (int i:arr) {
            map.put(i, i);
        }
        int count = 0;
        for (int i:arr) {
            mem[count++] = i+k;
        }
        
        int result = 0;
        for (int i=0; i<mem.length; i++) {
            if (map.containsKey(mem[i])) {
                result++;
            }
        }
        
        return result;
    }
```
