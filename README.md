# Basic-DSA-Questions-Javascript

Basic DSA Questions and Solutions in JavaScript

1. Reverse a String
function reverseString(str) {
 return str.split('').reverse().join('');
}
// Example: reverseString("hello") -> "olleh"


3. Check if a String is a Palindrome
function isPalindrome(str) {
 const reversed = str.split('').reverse().join('');
 return str === reversed;
}
// Example: isPalindrome("madam") -> true


5. Find the Maximum Sum of a Subarray (Kadane's Algorithm)
function maxSubarraySum(arr) {
 let maxSum = arr[0];
 let currentSum = arr[0];
 for (let i = 1; i < arr.length; i++) {
 currentSum = Math.max(arr[i], currentSum + arr[i]);
 maxSum = Math.max(maxSum, currentSum);
 }
 return maxSum;
}
// Example: maxSubarraySum([-2, 1, -3, 4, -1, 2, 1, -5, 4]) -> 6


6. Find the First Non-Repeating Character in a String
function firstNonRepeatingChar(str) {
 const charCount = {};
 for (let char of str) {
 charCount[char] = (charCount[char] || 0) + 1;
 }
 for (let i = 0; i < str.length; i++) {
 if (charCount[str[i]] === 1) {
 return str[i];
 }
 }
 return null;
}
// Example: firstNonRepeatingChar("swiss") -> "w"


7. Rotate an Array to the Right by K Steps
function rotateArray(arr, k) {
 k = k % arr.length;
 return [...arr.slice(-k), ...arr.slice(0, -k)];
}
// Example: rotateArray([1, 2, 3, 4, 5], 2) -> [4, 5, 1, 2, 3]


8. Check if Two Strings are Anagrams
function areAnagrams(str1, str2) {
 const sorted1 = str1.split('').sort().join('');
 const sorted2 = str2.split('').sort().join('');
 return sorted1 === sorted2;
}
// Example: areAnagrams("listen", "silent") -> true


9. Find Duplicates in an Array
function findDuplicates(arr) {
 const seen = new Set();
 const duplicates = new Set();
 for (let num of arr) {
 if (seen.has(num)) {
 duplicates.add(num);
 } else {
 seen.add(num);
 }
 }
 return [...duplicates];
}
// Example: findDuplicates([1, 2, 3, 2, 4, 3]) -> [2, 3]


10. Merge Two Sorted Arrays
function mergeSortedArrays(arr1, arr2) {
 let i = 0, j = 0, merged = [];
 while (i < arr1.length && j < arr2.length) {
 if (arr1[i] < arr2[j]) {
 merged.push(arr1[i++]);
 } else {
 merged.push(arr2[j++]);
 }
 }
 return merged.concat(arr1.slice(i)).concat(arr2.slice(j));
}
// Example: mergeSortedArrays([1, 3, 5], [2, 4, 6]) -> [1, 2, 3, 4, 5, 6]


11. Find the Longest Common Prefix
function longestCommonPrefix(strs) {
 if (!strs.length) return "";
 let prefix = strs[0];
 for (let i = 1; i < strs.length; i++) {
 while (strs[i].indexOf(prefix) !== 0) {
 prefix = prefix.slice(0, -1);
 if (!prefix) return "";
 }
 }
 return prefix;
}
// Example: longestCommonPrefix(["flower", "flow", "flight"]) -> "fl"


12. Move Zeroes to End of Array
function moveZeroes(arr) {
 let index = 0;
 for (let i = 0; i < arr.length; i++) {
 if (arr[i] !== 0) {
 [arr[index], arr[i]] = [arr[i], arr[index]];
 index++;
 }
 }
 return arr;
}
// Example: moveZeroes([0, 1, 0, 3, 12]) -> [1, 3, 12, 0, 0]
