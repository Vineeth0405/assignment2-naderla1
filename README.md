# assignment2-naderla1
# vineeth naderla
###### New York
New York is a state in the **Mid-Atlantic** and Northeastern regions of the United States.New York has a **diverse geography**.The southern part of the state is in the **Atlantic** coastal plain and includes Long Island and several smaller associated islands, as well as New York City and the lower **Hudson River** Valley. 

---

# Directions from Maryville to New York
1. Catch a directions of 1,251 miles from maryville to Jersey city via flight
2. Catch a cab and go to the kansas airport(MCI)
    1. Take a flight from kansas to Newark airport(EWR)
    2. It takes almost 20-25min newark airport to jersey city
3. Wait for your friends or cousins to pick you
    1. Share your experience of flight journey with your friends or cousins
5. We have reached  our destination before i complete saying about my experiences.


* Thing i would take with me
 * Drinks 
   * Water 
   * Redbull
   * Pepsi
 * food 
  * chocolates 
  * Chips
 * Accessories
  * Watch
  * Airpods
  * ipad
  * Powerbank

  **[AboutMe.md](AboutMe.md)**

  ---

  # food i loved and iwould love to suggest to others
  I am going to create a table with 4 food items that i would love to recommend someone try. i am a big fan of Indian cusine like chicken biryani, vegetable pulav, butter naan and gulab jamun.

  |Food Item|Location|Cost|
  |---|---|---|
  |chicken biryani|bawarchi|5$|
  |vegetable pulav|srikanya|4$|
  |butter naan|ratna|1$|
  |gulab jamun|paradise|2$|


  # Pithy Quote

  >"Be the change that you wish to see in the world"-*Mahatma gandhi*<br>
  >"Impossible is just an opinion"-*Nehru*

  ```
# Finding the rank of a matrix
> The rank of a matrix is the largest number of linearly independent rows/columns of the matrix. The rank is not only defined for square matrices.The rank of a matrix can also be defined as the largest order of any non-zero minor in the matrix.Let the matrix be rectangular and have size N×M. Note that if the matrix is square and its determinant is non-zero, then the rank is N (=M); otherwise it will be less. Generally, the rank of a matrix does not exceed min(N,M).
[click here to know more](https://en.wikipedia.org/wiki/Rank_(linear_algebra))

```
const double EPS = 1E-9;

int compute_rank(vector<vector<double>> A) {
    int n = A.size();
    int m = A[0].size();

    int rank = 0;
    vector<bool> row_selected(n, false);
    for (int i = 0; i < m; ++i) {
        int j;
        for (j = 0; j < n; ++j) {
            if (!row_selected[j] && abs(A[j][i]) > EPS)
                break;
        }

        if (j != n) {
            ++rank;
            row_selected[j] = true;
            for (int p = i + 1; p < m; ++p)
                A[j][p] /= A[j][i];
            for (int k = 0; k < n; ++k) {
                if (k != j && abs(A[k][i]) > EPS) {
                    for (int p = i + 1; p < m; ++p)
                        A[k][p] -= A[j][p] * A[k][i];
                }
            }
        }
    }
    return rank;
}

```
[code source](https://cp-algorithms.com/linear_algebra/rank-matrix.html)
