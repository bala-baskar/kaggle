We all know the benefit of using ensemble learning, which helps in averaging out the bias/variance present in the different models that we build.

Here are the two theorems from where the ensemble learning has arrived:

**Condorcet Jury Theorem**
Each of an odd number of people (models) classifies an unknown state of the world as either true or false. Each person (model) classifies correctly with a probability p > 0.5, and the probability that any person (model) classifies correctly is statistically independent of the correctness of any other person (model). The number of people (models) becomes large, the accuracy of the majority vote approaches 100%

**Diversity Prediction Theorem**

The squared error of the collective prediction equals the average squared error minus the predictive diversity. Therefore, when the diversity in a group is large, the error of the crowd is small.

- Average Individual Error: Average of the individual squared errors
- Collective Error: Squared error of the collective prediction
- Prediction Diversity: Average squared distance from the individual predictions to the collective prediction

**Collective Error = Average Individual Error - Prediction Diversity**

Eg: Two models predict the number of Oscars a film will be awarded. One model predicts 2 Oscars, and the other predicts 8 Oscars. The average of the 2 models' predictions = 5 Oscars (Collective Error). If, as it turns out the film wins 4 Oscars, the first model's error equals 4 ((2-4) squared) and second model's error equals 16 ((8-4) squared) and the Collective Error equals 1 ((4-5) squared). 

The prediction diversity equals 9 because each differs from the mean prediction by 3 (1st model = 2-5, 2nd model = 8-5).

Then, the diversity prediction theorem can then be expressed as follows: 
Collective Error (1) = Average Individual Error (10) - Prediction Diversity (9)

So, next time choose the group of models with maximum prediction diversity to the ensemble, which in turn reduces collective error.

**Reference: [The Model Thinker by Scott E. Page](<https://g.co/kgs/3hQcrD>)**