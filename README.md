# Shopee-Product-Matching

## Business Problem:
Shopee is a leading online e-commerce platform which enables users to buy and sell products online. It focuses on e-commerce and operates its business mainly in South Asian countries. Customers appreciate its easy, secure, and fast online shopping experience tailored to their region. The company also provides strong payment and logistical support along with a 'Lowest Price Guaranteed' feature on thousands of Shopee's listed products. In this competition they open sourced images of products with descriptions and expect Machine Learning practitioners to build models that identify similar products based on images and descriptions.

## Performance Metric:
The performance metric of this problem is F1-score averaged over postings. Which means the F1-score is computed on each product using its matches and the average of all products is taken.

## ArcFace Reference Paper: https://arxiv.org/pdf/1801.07698.pdf
1.  *ArcFace is a modification to Softmax to make loss depend only on Cosine Similarity(Dot Product) between feature vector and weight vector. Let's consider Sigmoid for example. We know that the Sigmoid Function is 1/(1+exp-(W.X+b)) where X is the feature vector, W is weight and b is the bias term. Let's consider the plane passes through origin i.e. bias=0 for simplicity. Now Sigmoid=1/(1+exp-(W.X)).*

2.   *We know that dot(W,X)=||W||.||X||.Cos(angle between them). We compute this and consider this as probability estimation and calculate loss with that. What if we make W and X unit vectors? The loss depends only on angle between those vectors. That is if angle is less(more cosine similar) the loss is less and during training the model updates weights in such a way that it decreases angle between W and X for particular class label.*

3.  *In addition to this, What if we add some angle to actual? Even if angle is less, as we are adding certain angle and making vector less cosine similar the model tries to reduce the added angle during training which in-turn update the weights through back propagation in such a way that the actual angle is reduced. We are just making training harder which results in better learning than actual.*

4.  *This process of making loss depend on Angle(Cosine Similarity) and adding additional angle to that to improve training efficiency is called* **ArcFace- Additive Angular Margin Loss**

### Go through 'Shopee Product Matching Abstract.pdf' for Data Exploration and ML problem solving approach.
