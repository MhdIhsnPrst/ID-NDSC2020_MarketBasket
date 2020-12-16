# Market Basket Challenge - ID NDSC 2020
Hi, I am Muhammad Ihsan Prasetio. I and my friends participated Shopee ID NDSC 2020 in Beginner Category. There are two challenges in Beginner Category. One of them is Market Basket. This is how to solve Market Basket challenge in beginner way.

## Description
At Shopee, sellers list thousands of products for sale on our platform. A better understanding of users' tastes and preferences for products can help Shopee design better promotions and recommendations for our users. To do that, we conduct market basket analysis which allows us to identify the relationship between different combinations of products that users buy.

We are interested in finding association rules between combinations of different products. These association rules can help to uncover regularities in purchasing behaviors of our users.

For example, an association rule between 3 products, {Product A & Product B} → {Product C}, would indicate that a user buying both Product A & Product B would likely buy Product C as well.

*Confidence* is a measure that is used to indicate such tendencies and can be used to determine the association for varying numbers of products. For the purpose of this question, we will be using confidence to calculate the association for 2 products and 3 products.

Confidence for two products:

![A to B](https://user-images.githubusercontent.com/70465894/102372603-f0875000-3ff1-11eb-9e8d-cc3a0e643de9.png)

Confidence for three products:

![A to B&C](https://user-images.githubusercontent.com/70465894/102373095-6db2c500-3ff2-11eb-8512-449b06c1829b.png)

or

![A&B to C](https://user-images.githubusercontent.com/70465894/102373246-93d86500-3ff2-11eb-84ab-21b35699d0a3.png)

## Basic Concepts
**Confidence** is defined as the tendency that given product A is purchased, that product B will also be purchased.

Each orderid represents a distinct transaction that has occurred. Each itemid represents a unique product that is sold on Shopee.

A transaction can contain 1 or more itemid(s). If 2 or more itemid(s) share the same orderid, they are purchased together in a single transaction. An itemid can appear many times in different orderid(s), which means that the product was purchased many times in different transactions.

Task: Please calculate the confidence values for all the association rules provided in the rules.csv file.

Tips:
- A > B and B > A have different confidence and should be calculated separately
- A & B > C and B & A > C are identical association rules and will yield the same confidence

## Example
**Case 1: A > B;**

8 orderid have itemid 7917849 (31338643584868, 31364354557783, 31368958440199, 31369772179043, 31371954695064, 31375314731607, 31377601474289, 31379328498817)

6 orderid out of above have both itemid 7917849 and itemid 18642183 (31338643584868, 31368958440199, 31369772179043, 31371954695064, 31375314731607, 31377601474289)

Confidence (7917849 > 18642183) = 6 / 8 = 0.75

Please submit 750 (times by 1000 and round down to integer)

**Case 2: A&B > C;**

7 orderid have itemid 2363580843 and itemid 2002243261 (31342449702678, 31365563352719, 31366764361012, 31371701813987, 31372163437582, 31373610230585, 31381568386099)

6 orderid out of above have all itemid 2363580843, itemid 2002243261 and itemid 1993068031 (31342449702678, 31365563352719, 31366764361012, 31372163437582, 31373610230585, 31381568386099)

Confidence (2363580843 & 2002243261 > 1993068031) = 6 / 7 = 0.857143…

Please submit 857 (times by 1000 and round down to integer)

**Case 3: A > B&C;**

9 orderid have itemid 1089203645 (31351735245918, 31367488312991, 31372554805324, 31373458010259, 31373724807962, 31374927925523, 31375318612401, 31375354382289, 31384570619582)

7 orderid out of above have all itemid 1089203645, 431391770 and 1216842899 (31351735245918, 31372554805324, 31373458010259, 31373724807962, 31374927925523, 31375318612401, 31375354382289)

Confidence (1089203645 > 431391770 & 1216842899) = 7 / 9 = 0.777777…

Please submit 777 (times by 1000 and round down to integer)

Source: https://www.kaggle.com/c/market-basket-id-ndsc-2020
