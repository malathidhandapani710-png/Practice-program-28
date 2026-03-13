class Solution:
    def getSecondLargest(self, arr):
        # Initialize both variables to -1 as per problem requirements
        largest = -1
        second_largest = -1
        
        for num in arr:
            # Case 1: Found a new maximum
            if num > largest:
                # The old largest is demoted to second largest
                second_largest = largest
                largest = num
            
            # Case 2: Found a number smaller than the max but larger than the current second
            # We check (num != largest) to handle duplicate values of the maximum
            elif num > second_largest and num != largest:
                second_largest = num
                
        return second_largest
