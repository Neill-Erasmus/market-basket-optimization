# Market Basket Optimization (Apriori - Association Rule Learning)

Using the apriori association rule learning algorithm to identify goods commonly associated and purchased together.

## Apriori - Association Rule Learning

The Apriori algorithm is a classic algorithm used for association rule learning in data mining and machine learning. It's primarily used for mining frequent itemsets and generating association rules from transactional datasets. Here's an explanation of the Apriori algorithm and association rule learning:

1. Frequent Itemset Mining - The first step in the Apriori algorithm is to find all frequent itemsets in the dataset. A frequent itemset is a set of items that frequently appear together in transactions.
The algorithm works by iteratively generating candidate itemsets of increasing size and checking their support in the dataset.
A candidate itemset is considered frequent if its support (the proportion of transactions containing the itemset) is greater than or equal to a predefined minimum support threshold.

2. Association Rule Generation - Once frequent itemsets are discovered, association rules are generated from them.
An association rule is an implication of the form "if X then Y," where X and Y are sets of items.
The Apriori algorithm generates association rules by considering all possible combinations of items within each frequent itemset and calculating metrics such as confidence and lift to evaluate the strength of the rules.

3. Metrics - Support: The support of an itemset X is the proportion of transactions in the dataset that contain X.
Confidence: The confidence of an association rule X → Y is the proportion of transactions containing X that also contain Y.
Lift: Lift measures the strength of an association rule by comparing the observed support of the rule with the expected support if X and Y were independent.

4. Pruning - To improve efficiency, the Apriori algorithm uses a principle known as the "apriori property," which states that if an itemset is infrequent, then all its supersets must also be infrequent.
Based on this property, the algorithm prunes the search space by eliminating candidate itemsets that cannot be frequent based on the support of their subsets.

5. Iterative Process - The Apriori algorithm iterates through the dataset multiple times, gradually increasing the size of itemsets until no new frequent itemsets can be found.

Association rule learning, of which the Apriori algorithm is a prominent example, is a technique for discovering interesting relationships or associations between variables in large datasets. It's commonly used in market basket analysis, where the goal is to understand patterns of co-occurrence among items purchased by customers. Association rule learning can uncover valuable insights for businesses, such as product bundling opportunities, cross-selling strategies, and customer segmentation.

## Model Performance

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Left Hand Side</th>
      <th>Right Hand Side</th>
      <th>Support</th>
      <th>Confidence</th>
      <th>Lift</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3</th>
      <td>fromage blanc</td>
      <td>honey</td>
      <td>0.003333</td>
      <td>0.245098</td>
      <td>5.164271</td>
    </tr>
    <tr>
      <th>0</th>
      <td>light cream</td>
      <td>chicken</td>
      <td>0.004533</td>
      <td>0.290598</td>
      <td>4.843951</td>
    </tr>
    <tr>
      <th>2</th>
      <td>pasta</td>
      <td>escalope</td>
      <td>0.005866</td>
      <td>0.372881</td>
      <td>4.700812</td>
    </tr>
    <tr>
      <th>8</th>
      <td>pasta</td>
      <td>shrimp</td>
      <td>0.005066</td>
      <td>0.322034</td>
      <td>4.506672</td>
    </tr>
    <tr>
      <th>7</th>
      <td>whole wheat pasta</td>
      <td>olive oil</td>
      <td>0.007999</td>
      <td>0.271493</td>
      <td>4.122410</td>
    </tr>
    <tr>
      <th>5</th>
      <td>tomato sauce</td>
      <td>ground beef</td>
      <td>0.005333</td>
      <td>0.377358</td>
      <td>3.840659</td>
    </tr>
    <tr>
      <th>1</th>
      <td>mushroom cream sauce</td>
      <td>escalope</td>
      <td>0.005733</td>
      <td>0.300699</td>
      <td>3.790833</td>
    </tr>
    <tr>
      <th>4</th>
      <td>herb &amp; pepper</td>
      <td>ground beef</td>
      <td>0.015998</td>
      <td>0.323450</td>
      <td>3.291994</td>
    </tr>
    <tr>
      <th>6</th>
      <td>light cream</td>
      <td>olive oil</td>
      <td>0.003200</td>
      <td>0.205128</td>
      <td>3.114710</td>
    </tr>
  </tbody>
</table>
</div>

The results of the apriori model provide insights into associations between different items in a dataset, particularly in the context of market basket analysis. Here's a breakdown of the key metrics:

1. Support - This indicates the frequency with which an itemset appears in the dataset. For example, the association between 'light cream' and 'chicken' has a support of 0.004533, suggesting that these items appear together in approximately 0.45% of transactions.

2. Confidence - Confidence measures the reliability of the rule. It shows how often the rule has been found to be true. For instance, the association between 'light cream' and 'chicken' has a confidence of 0.290598, indicating that when 'light cream' is purchased, there's a 29.06% chance that 'chicken' will also be purchased.

3. Lift - Lift is a measure of how much more often the antecedent and consequent of a rule occur together than we would expect if they were statistically independent. A lift value greater than 1 indicates that the antecedent and consequent occur together more often than random, with higher values indicating stronger associations. For example, the association between 'fromage blanc' and 'honey' has a lift of 5.164271, suggesting a strong positive correlation between these items.

Based on these metrics, we can draw insights such as:

- There's a significant association between 'fromage blanc' and 'honey', with a high lift value of 5.164271, indicating that customers who purchase 'fromage blanc' are likely to buy 'honey' as well.

- 'Light cream' is often purchased with 'chicken' and 'olive oil', as indicated by their relatively high support and confidence values.

- Pasta seems to be associated with both 'escalope' and 'shrimp', with confidence values around 0.3, suggesting that customers who purchase pasta are moderately likely to buy either 'escalope' or 'shrimp'.

- 'Herb & pepper' and 'ground beef' also have a strong association with a lift value of 3.291994, indicating that customers who purchase 'herb & pepper' are likely to buy 'ground beef' as well.
These insights could be valuable for marketing strategies, store layout optimization, and product bundling decisions.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.