# [Sparse Arrays]

```
There is a collection of input strings and a collection of query strings. For each query string, determine how many times it occurs in the list of input strings. Return an array of the results.

Example



There are  instances of ',  of '' and  of ''. For each query, add an element to the return array, .

Function Description

Complete the function matchingStrings in the editor below. The function must return an array of integers representing the frequency of occurrence of each query string in strings.

matchingStrings has the following parameters:

string strings[n] - an array of strings to search
string queries[q] - an array of query strings
Returns

int[q]: an array of results for each query
Input Format

The first line contains and integer , the size of .
Each of the next  lines contains a string .
The next line contains , the size of .
Each of the next  lines contains a string .



```

# Solutions - Java

```
  public static List<Integer> matchingStrings(List<String> strings, List<String> queries) {
      // Write your code here
          List<Integer> result = new ArrayList<>();

          Map<String, Integer> freq = new HashMap<>();
          for (String s : strings) {
              if (!freq.containsKey(s)) {
                  freq.put(s, 1);
              } else {
                  freq.put(s, freq.get(s)+1);
              }
          }

          for (String s : queries) {
              if (freq.containsKey(s)) {
                  result.add(freq.get(s));
              } else {
                  result.add(0);
              }
          }
          return result;
      }

```
