
# Knapsack Algorithm

## Description
The Knapsack Problem is a classic combinatorial optimization problem commonly encountered in resource allocation scenarios. Decision-makers are tasked with selecting from a set of indivisible items or tasks within fixed budget or time constraints. The objective is to optimize by choosing the best combination to maximize a specific goal, such as profit, efficiency, or meeting particular requirements, within the confines of limited resources.

![Image Title](knapsack2.png)
![Image Title](knapsack1.png)

## Gold
There is a backpack with a fixed capacity and a series of items, each with its own weight and value. The capacity of a backpack limits the total weight of items that can be placed, and each item has a specific value. The goal is to select a group of items to be placed in the backpack without exceeding its capacity, in order to maximize the total value of these items.

## The two different types of Knapsack
### 0-1 Knapsack Problem
Each item can either be fully included in the knapsack or not included at all. This means that for each item, there are only two choices: either to place it in the knapsack or to exclude it.
### Fractional Knapsack Problem
Each item can be partially included in the knapsack; it does not have to be fully included or excluded. This implies that it is possible to select a fraction of an item to place in the knapsack rather than committing to the whole item or excluding it entirely.
## Solution

### False Start

#### Pseudocode
```
function knapsack_false_start(n, weights[], values[], W):
    M = array[n+1][W+1]
    for w from 0 to W:
        M[0][w] = 0
    for i from 1 to n:
        for w from 0 to W:
            if weights[i] > w:
                M[i][w] = M[i-1][w]
            else:
                with_i = values[i] + M[i-1][w - weights[i]]
                without_i = M[i-1][w]
                M[i][w] = max(with_i, without_i)
    return M[n][W]
```
#### Algorithmic principle
This method emphasizes the consideration of more subproblems to account for different scenarios. It involves defining a function to represent the optimal solution of the problem and considering two possibilities: selecting the current item or not selecting it. If the current item is chosen, it might require considering previously selected items, but it doesn't necessarily imply that selecting the current item will lead to the exclusion of other items. By addressing these scenarios and subproblems, this approach aims for a more comprehensive solution to the problem.



#### Algorithm implement
The Implementation of Algorithms in C++
```
int knapsack_false_start(int n, vector<int>& weights, vector<int>& values, int W) {
    // Create a 2D array to store the maximum values for subproblems
    vector<vector<int>> M(n + 1, vector<int>(W + 1, 0));

    // Iterate over each item
    for (int i = 1; i <= n; ++i) {
        // Iterate over each possible weight capacity
        for (int w = 0; w <= W; ++w) {
            // If the current item's weight exceeds the current capacity, don't select it
            if (weights[i] > w) {
                M[i][w] = M[i - 1][w];
            } else {
                // Consider two possibilities: including the current item or not
                // If including the current item, calculate the value
                int with_i = values[i] + M[i - 1][w - weights[i]];
                // If not including the current item, the value remains the same as for the previous item
                int without_i = M[i - 1][w];
                // Choose the maximum value between including and not including the current item
                M[i][w] = max(with_i, without_i);
            }
        }
    }

    // Return the maximum value after considering all items and weight capacities
    return M[n][W];
}

```

#### Time complexity
The time complexity of the False Start method is O(n W), where n is the number of items and W is the capacity of the knapsack. In the False Start method, we need to fill in an n×W 2D array to store intermediate results, and for each item, we need to consider every possible knapsack capacity.

## Results
