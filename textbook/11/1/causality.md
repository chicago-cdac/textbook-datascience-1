# Causality versus Association

As scientists, we are often looking for patterns or relations between variables. When there exists a pattern between two variables, we call this an *association*[^*]. For example, time of day is associated with the traffic on Chicago's Lake Shore Drive and temperature outside is associated with the number of people at Lake Michigan.

When we see that two variables *X* and *Y* are associated, we often wonder if one causes the other. There are 3 possible scenarios:

* **Causation**: change in *X* causes change in *Y* (or vice-versa)
* **Common response** (confounding): some other variable *Z* causes change in both *X* and *Y*
* **Common outcome** (colliding): changes in both *X* and *Y* cause change in some variable *Z*

Well-designed studies, which we will discuss further in the next section, can help distinguish between the three scenarios which are often depicted using causal graphs. A causal graph is a graph where each node depicts a variable and each edge is directed (an arrow) pointing in the direction of a cause. The figure below shows causal graphs as well as examples for all three scenarios.

```{figure} ./causality.png
---
align: center
---
Three Types of Association
```

The first panel above shows a *causal association*. When we see a causal association between *X* and *Y* we can depict it with an arrow from the cause to the effect. For example jumping in the lake is the direct cause of getting wet so the arrow is drawn from jumping in the lake to getting wet.

The second panel shows an association between *X* and *Y* (the dotted line) that is present due to a *confounding* variable, *Z*. *Conditioning on* a confounding variable is best practice to remove the false association between *X* and *Y*. Conditioning on a variable means looking at only one value of the conditioned variable. For example: suppose I have a dataset that contains information about things happening at the beach. I plot ice cream sales and shark attacks and see that there is a positive association such that as ice cream sales increase so do shark attacks. Should I conclude that ice cream attracts sharks? Thinking more deeply about the problem, I realize that shark attacks increase when the weather is warm because there are more people in the ocean. Ice cream sales also increase during warm weather, therfore both variables have a common cause, weather. When I condition on weather and only consider ice cream sales and shark attacks in the summer months, the association disappears.

In the last panel, we see that an association between *X* and *Y* is due to the *collider* variable, *Z*. We see false associations between two variables *X* and *Y* when both are causes of a third variable *Z* and we are conditioning on *Z*[^**]. For example: looking only at hospitalized patient data (conditioning on being hospitalized), we see a negative association between diabetes and heart disease such those who have diabetes are less likely to have heart disease. However, it is known that diabetes is a risk factor of heart disease – not a protective factor – so we should see the opposite effect. This reversal in association occurs because we are only looking at hospitalized patients and both heart disease and diabetes are causes of hospitalization. Diabetes increases likelihood of heart disease and likelihood of hospitalization. Heart disease increases likelihood of hospitalization as well. If you are hopitalized for diabetes, it is less likely you also have heart disease. Therefore, those with diabetes in this sample of hospitalized patients have lower incidence of heart disease than those with diabetes in the general population, reversing the association between diabetes and heart disease.

As colliding is a difficult concept to grasp, consider another example. Suppose your friend is complaining about a recent date. The person she went to dinner with was very good looking but had no sense of humor. Your friend comments that it seems all good-looking people have a bad sense of humor. You know that in reality looks and humor are not related. Your friend is conditioning on a collider by considering only people that she dates. She likely only dates people that meet a certain threshold of looks and humor. Those that are very good-looking don't need to have as good of a sense of humor to get a date whereas those who are less good-looking must have a better sense of humor, creating a negative association between looks and humor that does not exist outside of her dating pool.

[^*]: An association is often referred to as a correlation. Correlations are discussed in more detail in Chapter 17.
[^**]: A more thorough discussion of colliders is beyond the scope of this book, but interested readers are referred to *The Book of Why* by Judea Pearl and Dana Mackenzie.
