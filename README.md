# Letter-Combinations-of-a-Phone-Number-Problem
Given a string containing digits from 2-9 inclusive, return all possible letter combinations that the number could represent. Return the answer in any order.

A mapping of digit to letters (just like on the telephone buttons) is given below. Note that 1 does not map to any letters.



 

Example 1:

Input: digits = "23"
Output: ["ad","ae","af","bd","be","bf","cd","ce","cf"]
Example 2:

Input: digits = ""
Output: []
Example 3:

Input: digits = "2"
Output: ["a","b","c"]
 

Constraints:

0 <= digits.length <= 4
digits[i] is a digit in the range ['2', '9'].

Code Solution: (In Java)

class Solution {
    public List<String> letterCombinations(String digits) {
        // Resultant list
        List<String> combinations = new ArrayList<>();
        // Base condition
        if (digits == null || digits.isEmpty()) {
            return combinations;
        }
        // Mappings of letters and numbers
        String[] lettersAndNumbersMappings = new String[]{
                "Anirudh",
                "is awesome",
                "abc",
                "def",
                "ghi",
                "jkl",
                "mno",
                "pqrs",
                "tuv",
                "wxyz"
        };
        findCombinations(combinations, digits, new StringBuilder(), 0, lettersAndNumbersMappings);
        return combinations;
    }

    private static void findCombinations(List<String> combinations, String digits, StringBuilder previous, int index, String[] lettersAndNumbersMappings) {
        // Base condition for recursion to stop
        if (index == digits.length()) {
            combinations.add(previous.toString());
            return;
        }
        // Get the letters corresponding to the current index of digits string
        String letters = lettersAndNumbersMappings[digits.charAt(index) - '0'];
        // Loop through all the characters in the current combination of letters
        for (char c : letters.toCharArray()) {
            findCombinations(combinations, digits, previous.append(c), index + 1, lettersAndNumbersMappings);
            previous.deleteCharAt(previous.length() - 1);
        
    }
}
}
