# No-ML-Just-Statistical-Analysis
No ML, Just Statistical Analysis
No ML, Just Statistical Analysis
# Introduction

Briefly, in this notebook I try to solve the Spaceship Titanic competition JUST by statistical methods and probability and not Machine Learning.

## Statistical Analysis
You may hear Bayesian Inference or probabily work with it. Here I used this method but in a slightly different way;
Defining Bayesian Score instead of Bayesian Probability.

## Bayes Theorem
This theorem describes the probability of an event, based on prior knowledge of conditions that might be related to the event.
### Simple Form:
${\displaystyle P(A\mid B)={\frac {P(B\mid A)P(A)}{P(B)}}}$
### Extended Form:
Often, for some partition ${A_j}$ of the sample space, the event space is given in terms of $P(A_j)$ and $P(B | A_j)$. It is then useful to compute P(B) using the law of total probability:

${\displaystyle P(B)={\sum _{j}P(B|A_{j})P(A_{j})}}$

Or equivalently:
${\displaystyle P(B)={\sum _{j}P(B 	\cap A_{j})}}$

## Bayesian Score
As in our case the event we want to predict (Transported) is not completely consists of the dataset's features, the bayesian theorem assumptions doesn't satisfy. Therefore, I use the idea behind this great theorem and define a new random variable, named Bayesian Score.

To understand the restriction of using this theorem, consider the $Ω$ as sample space, then we have:

$Columns = \big \{PassengerId, HomePlanet, CryoSleep, Cabin, Destination, Age,VIP, RoomService, FoodCourt, ShoppingMall, Spa, VRDeck,Name\big \}$


${\displaystyle Ω \neq \bigcup_{\alpha \in Columns} \alpha }$


Therefore:

${\displaystyle P(Transported=0 \,or\, 1) \neq {\sum _{\alpha \in Columns}P(Transported \cap \alpha)}}$

### BS: Bayesian Score

${\displaystyle BS(B)={\prod _{j}P(B|A_{j})P(A_{j})}}$

Or equivalently:
${\displaystyle BS(B)={\prod _{j}P(B 	\cap A_{j})}}$

### Finally

${\displaystyle BS\big (Transported = 0 \,or\, 1 \big )={\prod _{\alpha \in Columns}P \big ( (Transported = 0 \,or\, 1) \cap \alpha \big)}}$

## Advantage

As you can see in the following, one of the benefit of this type of statistical analysis is that, **You don't need to fill missing values** in the data which is almost one of the most time consuming and chanllenging task in data analysis.
