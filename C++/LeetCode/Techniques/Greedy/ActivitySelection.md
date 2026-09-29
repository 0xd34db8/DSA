```cpp
int activitySelection(vector<int> &start, vector<int> &finish) {
int n = start.size();
if (n == 0) return 0;

        // Pair activities as {finish_time, start_time}
        vector < pair < int, int > > activities(n);
        // fill them
        for (int i = 0; i < n; ++i) {
            activities[i] = {finish[i], start[i]};
        }

        // Sort by finish time in non-decreasing order
        sort(activities.begin(), activities.end());

        // (first activity has to be coutned in any case)
        int count = 1;
        int last_finish = activities[0].first;

        // Iterate through remaining activities
        for (int i = 1; i < n; ++i) {
            // Strictly greater because the next activity must start after finish time
            if (activities[i].second > last_finish) {
                count++;
                last_finish = activities[i].first;
            }
        }

        return count;
    }
```

The Activity Selection Problem is solved using a **Greedy Algorithm**. The objective is to maximize the total number of non-overlapping tasks a single resource (like a person or a machine) can complete.

The mathematically optimal strategy is to always pick the next available activity that ends the earliest. By sorting activities strictly by their **finish times** in ascending order, you ensure that each chosen activity consumes the absolute minimum amount of time from the schedule. This leaves the maximum possible remaining time open for subsequent activities. If you were to sort by start time or total duration instead, you risk selecting an activity that starts early but lasts all day, permanently blocking a dozen shorter tasks.

**Step-by-Step Example**

Imagine you are given the following 5 activities:

- **Start times:** `[3, 1, 5, 0, 8]`
- **Finish times:** `[4, 2, 7, 6, 9]`

**Step 1: Pair and Sort by Finish Time**
Bind each start time to its corresponding finish time, and sort the entire list from the earliest finish time to the latest.

- Activity 1: `(1, 2)`
- Activity 2: `(3, 4)`
- Activity 3: `(0, 6)`
- Activity 4: `(5, 7)`
- Activity 5: `(8, 9)`

**Step 2: Select the First Activity**
Because the list is sorted by finish time, the first item is mathematically guaranteed to be the best starting move.

- **Select Activity 1:** `(1, 2)`.
- **Total selected:** 1
- **Resource blocked until:** Time `2`.

**Step 3: Evaluate Remaining Activities Sequentially**
Move down the sorted list one by one. You can only select an activity if its start time is strictly greater than the time your resource finishes its current task.

- **Evaluate Activity 2 `(3, 4)`:** The start time is `3`. Since `3 > 2` (the current blocked time), you can perform it.
- _Action:_ Select it. Total selected becomes 2. Resource is now blocked until Time `4`.

- **Evaluate Activity 3 `(0, 6)`:** The start time is `0`. Since `0` is not greater than `4`, this task overlaps with your current schedule.
- _Action:_ Skip it.

- **Evaluate Activity 4 `(5, 7)`:** The start time is `5`. Since `5 > 4`, you can perform it.
- _Action:_ Select it. Total selected becomes 3. Resource is now blocked until Time `7`.

- **Evaluate Activity 5 `(8, 9)`:** The start time is `8`. Since `8 > 7`, you can perform it.
- _Action:_ Select it. Total selected becomes 4. Resource is now blocked until Time `9`.

The algorithm finishes evaluating the array and returns a maximum of 4 activities.
