# How Machine Learning Works
{:.no_toc}

* TOC
{:toc}

## What is computer science?

* Computer science is fundamentally problem-solving, and programming alone or (more likely) collaboratively is one way to do that.
* Collaboration is an important aspect of problem solving. It can take on many forms, such as communication or consultation. Collaboration helps us see diverse perspectives, which can help us avoid bias in the development of computing innovations.
* We can think of problem-solving as the process of taking some input (details about our problem) and generate some output (the solution to our problem). The "black box" in the middle is what we'll gradually learn more and more about in this course.<br>
  ![word "input", arrow into box, arrow out of box, word "output"](input_output.png)
* We need a way to represent inputs in some standard way, and if our problem were to simply count the number of people in the lecture hall, we'd have many options. We could write tally marks on a board, or use our hands. In fact, with just one hand, we can use our fingers creatively: with just our thumb up, we could represent one; with our just index finger up, we could represent two; with both our thumb and index finger up, we could represent three. And by continuing to use a pattern of permutations, we could represent 32 different values with just five fingers!

## Machine Learning
Machine learning provides a computer with data, rather than explicit instructions. Using these data, the computer learns to recognize patterns and becomes able to execute tasks on its own.

## Supervised Learning
Supervised learning is a task where a computer learns a function that maps inputs to outputs based on a dataset of input-output pairs.

There are multiple tasks under supervised learning, and one of those is **Classification**. This is a task where the function maps an input to a discrete output. For example, given some information on humidity and air pressure for a particular day (input), the computer decides whether it will rain that day or not (output). The computer does this after training on a dataset with multiple days where humidity and air pressure are already mapped to whether it rained or not.

This task can be formalized as follows. We observe nature, where a function f(humidity, pressure) maps the input to a discrete value, either Rain or No Rain. This function is hidden from us, and it is probably affected by many other variables that we don’t have access to. Our goal is to create function h(humidity, pressure) that can approximate the behavior of function f. Such a task can be visualized by plotting days on the dimensions of humidity and rain (the input), coloring each data point in blue if it rained that day and in red if it didn’t rain that day (the output). The white data point has only the input, and the computer needs to figure out the output.

![classification](classification.png)

### Nearest-Neighbor Classification
One way of solving a task like the one described above is by assigning the variable in question the value of the closest observation. So, for example, the white dot on the graph above would be colored blue, because the nearest observed dot is blue as well. This might work well some times, but consider the graph below.

![Nearest Neighbor Classification](nearestneighbor.png)

Following the same strategy, the white dot should be colored red, because the nearest observation to it is red as well. However, looking at the bigger picture, it looks like most of the other observations around it are blue, which might give us the intuition that blue is a better prediction in this case, even though the closest observation is red.

One way to get around the limitations of nearest-neighbor classification is by using **k-nearest-neighbors classification**, where the dot is colored based on the most frequent color of the k nearest neighbors. It is up to the programmer to decide what k is. Using a 3-nearest neighbors classification, for example, the white dot above will be colored blue, which intuitively seems like a better decision.

A drawback of the k-nearest-neighbors classification is that, using a naive approach, the algorithm will have to measure the distance of every single point to the point in question, which is computationally expensive. This can be sped up by using data structures that enable finding neighbors more quickly or by pruning irrelevant observation.

### Perceptron Learning
Another way of going about a classification problem, as opposed to the nearest-neighbor strategy, is looking at the data as a whole and trying to create a decision boundary. In two-dimensional data, we can draw a line between the two types of observations. Every additional data point will be classified based on the side of the line on which it is plotted.

 ![Decision Boundary](decisionboundary.png)

The drawback to this approach is that data are messy, and it is rare that one can draw a line and neatly divide the classes into two observations without any mistakes. Often, we will compromise, drawing a boundary that separates the observations correctly more often than not, but still occasionally misclassifies them.

In this case, the input of

- ‌‌ $$x_1 = \text{Humidity}$$
- ‌‌ $$x_1 = \text{Pressure}$$

will be given to a hypothesis function $$h(x_1, x_2)$$, which will output its prediction of whether it is going to rain that day or not. It will do so by checking on which side of the decision boundary the observation falls. Formally, the function will weight each of the inputs with an addition of a constant, ending in a linear equation of the following form:

- Rain $$w_0 + w_1 \cdot x_1 + w_2 \cdot x_2 \geq 0$$
- No Rain otherwise

Often, the output variable will be coded as 1 and 0, where if the equation yields more than 0, the output is 1 (Rain), and 0 otherwise (No Rain).

The weights and values are represented by vectors, which are sequences of numbers (which can be stored in lists or tuples in Python). We produce a Weight Vector $$\textbf{w}: (w_0, w_1, w_2)$$, and getting to the best weight vector is the goal of the machine learning algorithm. We also produce an Input Vector $$\textbf{x}: (1, x_1, x_2)$$.

We take the dot product of the two vectors. That is, we multiply each value in one vector by the corresponding value in the second vector, arriving at the expression above: $$w_0 + w_1 x_1 + w_2 x_2$$. The first value in the input vector is 1 because, when multiplied by the weight vector $$w_0$$, we want to keep it a constant.

Thus, we can represent our hypothesis function the following way:

 ![Dot Product Equation](dotproduct.png)

Since the goal of the algorithm is to find the best weight vector, when the algorithm encounters new data it updates the current weights. It does so using the **perceptron learning rule**:

 ![Perceptron Learning Rule](perceptronlearning.png)

The important takeaway from this rule is that for each data point, we adjust the weights to make our function more accurate. The details, which are not as critical to our point, are that each weight is set to be equal to itself plus some value value in parentheses. Here, $$y$$ stands for the observed value while the hypothesis function stands for the estimate. If they are identical, this whole term is equal to zero, and thus the weight is not changed. If we underestimated (calling No Rain while Rain was observed), then the value in the parentheses will be 1 and the weight will increase by the value of $$x_i$$ scaled by $$\alpha$$ the learning coefficient. If we overestimated (calling Rain while No Rain was observed), then the value in the parentheses will be $$-1$$ and the weight will decrease by the value of x scaled by α. The higher $$\alpha$$, the stronger the influence each new event has on the weight.

The result of this process is a threshold function that switches from 0 to 1 once the estimated value crosses some threshold.

 ![Hard Threshold](hardthreshold.png)

The problem with this type of function is that it is unable to express uncertainty, since it can only be equal to 0 or to 1. It employs a **hard threshold**. A way to go around this is by using a logistic function, which employs a **soft threshold**. A logistic function can yield a real number between 0 and 1, which will express confidence in the estimate. The closer the value to 1, the more likely it is to rain.

 ![Soft Threshold](softthreshold.png)

### Support Vector Machines
In addition to nearest-neighbor and linear regression, another approach to classification is the Support Vector Machine. This approach uses an additional vector (support vector) near the decision boundary to make the best decision when separating the data. Consider the example below.

 ![Support Vector Machine](supportvector.png)

All the decision boundaries work in that they separate the data without any mistakes. However, are they equally as good? The two leftmost decision boundaries are very close to some of the observations. This means that a new data point that differs only slightly from one group can be wrongly classified as the other. As opposed to that, the rightmost decision boundary keeps the most distance from each of the groups, thus giving the most leeway for variation within it. This type of boundary, which is as far as possible from the two groups it separates, is called the **Maximum Margin Separator**.

Another benefit of support vector machines is that they can represent decision boundaries with more than two dimensions, as well as non-linear decision boundaries, such as below.

 ![Circle Decision Boundary](circleboundary.png)

To summarize, there are multiple ways to go about classification problems, with no one being always better than the other. Each has their drawbacks and might prove more useful than others in specific situations.

### Regression
Regression is a supervised learning task of a function that maps an input point to a continuous value, some real number. This differs from classification in that classification problems map an input to discrete values (Rain or No Rain).

For example, a company might use regression to answer the question of how money spent advertising predicts money earned in sales. In this case, an observed function $$f(\text{advertising})$$ represents the observed income following some money that was spent in advertising (note that the function can take more than one input variable). These are the data that we start with. With this data, we want to come up with a hypothesis function $$h(\text{advertising})$$ that will try to approximate the behavior of function $$f$$. $$h$$ will generate a line whose goal is not to separate between types of observations, but to predict, based on the input, what will be the value of the output.

 ![Regression](regression.png)

### Loss Functions
Loss functions are a way to quantify the utility lost by any of the decision rules above. The less accurate the prediction, the larger the loss.

For classification problems, we can use a **0-1 Loss Function**.

* $$L$$(actual, predicted):
  - 0 if actual = predicted
  - 1 otherwise

In words, this function gains value when the prediction isn’t correct and doesn’t gain value when it is correct (i.e. when the observed and predicted values match).

 ![0-1 Loss Function](01loss.png)

In the example above, the days that are valued at 0 are the ones where we predicted the weather correctly (rainy days are below the line and not rainy days are above the line). However, days when it didn’t rain below the line and days when it did rain above it are the ones that we failed to predict. We give each one the value of 1 and sum them up to get an empirical estimate of how lossy our decision boundary is.

$$L_1$$ and $$L_2$$ loss functions can be used when predicting a continuous value. In this case, we are interested in quantifying for each prediction *how much* it differed from the observed value. We do this by taking either the absolute value or the squared value of the observed value minus the predicted value (i.e. how far the prediction was from the observed value).

  - ‌‌ $$L_1: L(\text{actual, predicted}) = \ \mid \text{actual} - \text{predicted } \mid$$
  - ‌‌ $$L_2: L(\text{actual, predicted}) = (\text{actual} - \text{predicted})^2$$

One can choose the loss function that serves their goals best. $$L_2$$ penalizes outliers more harshly than L₁ because it squares the the difference. $$L_1$$ can be visualized by summing the distances from each observed point to the predicted point on the regression line:

 ![L1](l1.png)

## Overfitting
Overfitting is when a model fits the training data so well that it fails to generalize to other data sets. In this sense, loss functions are a double edged sword. In the two examples below, the loss function is minimized such that the loss is equal to 0. However, it is unlikely that it will fit new data well.

 ![Overfitting](overfitting.png)

For example, in the first graph, a dot next to the red one at the bottom of the screen is likely to be Rain (blue). However, with the overfitted model, it will be classified as No Rain (red).