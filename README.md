# Review Score Analysis

This project implements methods to calculate different scoring techniques for user reviews based on upvotes and downvotes. The following scoring methods are included:

## Scoring Methods

### 1. **Up-Down Diff Score**
The Up-Down Diff Score calculates the difference between the number of upvotes and downvotes for a review.  
**Formula:**  
`Up-Down Diff Score = (up ratings) − (down ratings)`

### 2. **Average Rating Score**
This score calculates the average rating for a review based on the upvotes and downvotes.  
**Formula:**  
`Average Rating = (up votes) / (total votes)`

### 3. **Wilson Lower Bound Score**
The Wilson Lower Bound is a method used to calculate a lower confidence bound for the proportion of upvotes. It is particularly useful for cases where the number of votes is small, helping to provide a more reliable ranking of reviews.  
**Formula:**  
Wilson Score =  
`phat + z * z / (2 * n) - z * sqrt((phat * (1 - phat) + z * z / (4 * n)) / n) / (1 + z * z / n)`

## Features

- **Up-Down Diff Score**: Calculates the difference between upvotes and downvotes.
- **Average Rating**: Provides an average rating score.
- **Wilson Lower Bound**: Provides a confidence-based lower bound score for ranking reviews.

## Case Study

In the case study, a set of review data is provided where the `up` and `down` votes for each review are analyzed using the three scoring methods. The results are calculated and stored in a DataFrame, with columns representing each score type.

The following columns are created:

- `score_pos_neg_diff`: Difference between upvotes and downvotes.
- `score_average_rating`: Average rating score.
- `wilson_lower_bound`: Wilson Lower Bound score.

## Data Analysis

The data is sorted based on the Wilson Lower Bound score in descending order, so the most reliable reviews (based on the lower bound) are displayed first.

## Usage

1. Install the required libraries:

    ```bash
    pip install pandas scipy
    ```

2. Run the script to calculate and sort the review scores.

## Example Output

Here is an example of how the calculated scores would appear for a set of reviews:

| up  | down | score_pos_neg_diff | score_average_rating | wilson_lower_bound |
|-----|------|--------------------|----------------------|---------------------|
| 15  | 0    | 15                 | 1.00000              | 1.00000             |
| 70  | 2    | 68                 | 0.97403              | 0.97394             |
| 14  | 2    | 12                 | 0.87500              | 0.85657             |
| ... | ...  | ...                | ...                  | ...                 |

