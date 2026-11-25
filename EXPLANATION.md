# Explanation for Task 2


## Part 1 - Explanation of why the code was wrong
In line 62 of cluster_plot.py in a for loop which was iterating k from 2 to 5 this line was there `k = min(k, 3)`. As you can see from the code k would equal the smallest of the two options which are k or 3 meaning when in the loop k = 4 or 5 the line would change k to equal 3. This would mean when it was meant to test k = 4 or 5 it was just testing k = 3 again 2 more times. The fix used was to make `k=k` so that k could equal to 4 and 5.

In line 89 and 91 "silhouette_score" was used as shown below.
```python
if "silhouette_score" in metrics_df.columns:
    ...
    plt.bar(metrics_df["k"], metrics_df["silhouette_score"])
```

The problem with this is that the score returned by the function `run_clustering` is not called "silhouette_score". This meant that the plt.bar was never running because of the if statement.
The fix that was used to solve this was to change "silhouette_score" to the actual name of the key returned from `run_clustering` which is "silhouette"

After changing these fixes I checked the output of the code and saw the inertia changing and that demo_data_silhouette.png would now be created.

## Part 2 - Explaining what the corrected now does



