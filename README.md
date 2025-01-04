# Last-Sweet-Recipient

During the festive Diwali celebration, Neha received an abundance of sweets and decided to share them with the needy children in her community. There were N children, each numbered from 1 to N, and each child had a specific request for sweets - child i wanted at least cᵢ boxes. The children stood in a line according to their numbers, eagerly waiting for their turn.
Neha had a plan for distributing the sweets: she would give K boxes to the child at the front of the line. If that child hadn’t received enough boxes yet, they would go to the back of the line; if they had received enough, they would go home happily.
Neha repeated this process until all the children received their required sweets. Now, Neha is curious to find out which child will receive the last box of sweets. Can you help her determine the number of that child?

def last_sweet_recipient(N, K, c):
    last_child = -1
    max_rounds = 0

    for i in range(N):
        rounds = (c[i] + K - 1) // K  # Calculate rounds for each child
        if rounds >= max_rounds:
            max_rounds = rounds
            last_child = i + 1  # Store 1-based index

    return last_child

# Input
N, K = map(int, input().split())
c = list(map(int, input().split()))

# Output the result
print(last_sweet_recipient(N, K, c))
