# Strengthening-the-Array

In a bustling town, a clever student named Maya received a challenge from her teacher. She was presented with an array of integers, A, containing N elements. Her task was to transform the array into a “strong” array, defined as one where the sum of its elements is odd.
However, Maya could only achieve this by performing a specific operation: she could remove the last element from the array as many times as necessary. Determined to rise to the occasion, Maya set off on her journey to find the minimum number of moves required to make her array strong. Yet, she was also aware that there might be a chance that making the array strong was impossible.
Can you help Maya determine the minimum moves needed to achieve her goal, or print -1 if it’s simply not possible?

Input
The first line of the input contains a single integer N.
The second line of the input contains N space-separated integers.

Constraints
1 ≤ N ≤ 105
1 ≤ Ai ≤ 109
Output
Print the minimum number of moves required to make the array strong. If it is not possible to make the array strong, print -1.

def main():
    import sys
    input = sys.stdin.read
    data = input().split()
    
    n = int(data[0])
    arr = list(map(int, data[1:]))
    
    total_sum = sum(arr)
    
    # If the total sum is already odd
    if total_sum % 2 != 0:
        print(0)
        return
    
    # Start removing elements from the end
    for i in range(n - 1, -1, -1):
        total_sum -= arr[i]
        if total_sum % 2 != 0:
            print(n - i)
            return
    
    # If no odd sum can be achieved
    print(-1)

if __name__ == "__main__":
    main()
