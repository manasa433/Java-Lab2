1Q.
Create a Java program that identifies the top K numbers with the highest occurrences from a static array of integers. The program should:
    Use a static variable to store the input array.
    Implement a static method that accepts a positive integer K to determine the K most frequent numbers.
    Prioritize larger numbers in case of frequency ties.
    Output the results in descending order based on frequency.

import java.util.*;

public class TopKFrequentNumbers {
    // Static variable to hold the input array
    private static int[] numbers = {5, 6, 9, 6, 2, 3, 2, 1};

    // Static method to find top K frequent numbers
    public static void findTopKFrequent(int K) {
        // Map to store the frequency of each number
        Map<Integer, Integer> frequencyMap = new HashMap<>();

        // Calculate frequency of each number
        for (int num : numbers) {
            frequencyMap.put(num, frequencyMap.getOrDefault(num, 0) + 1);
        }

        // Create a list from the frequency map and sort it
        List<Map.Entry<Integer, Integer>> entryList = new ArrayList<>(frequencyMap.entrySet());
        
        // Sort the list first by frequency (descending) and then by number (descending)
        entryList.sort((a, b) -> {
            int freqComparison = b.getValue().compareTo(a.getValue());
            if (freqComparison == 0) {
                return b.getKey().compareTo(a.getKey()); // Compare by number if frequencies are equal
            }
            return freqComparison;
        });

        // Collect the top K numbers
        for (int i = 0; i < K; i++) {
            System.out.print(entryList.get(i).getKey() + " ");
        }
        System.out.println(); // Print a new line after output
    }

    public static void main(String[] args) {
        System.out.println("Top 2 frequent numbers:");
        findTopKFrequent(2); // Test case 1

        System.out.println("Top 4 frequent numbers:");
        numbers = new int[]{1, 3, 6, 1, 5, 5, 1, 8, 9, 10, 8, 9, 2, 1}; // Update array for second test case
        findTopKFrequent(4); // Test case 2
    }
}
