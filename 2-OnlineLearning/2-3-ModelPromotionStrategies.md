# Model Promotion Strategies

When considering the deployment of a newly trained model in the online learning lifecycle, it is crucial to consider how you would like to promot the new model's assets into production. There are several strategies to consider when promoting models.

## Shadow Deployment

Shadow deployment is a strategy where the new model is deployed alongside the existing production model, but does not impact live traffic. This allows for real-world performance evaluation of the new model without risking disruption to the production system.

Deploying a model as a shadow model allows teams to gather real-world performance data and user feedback before making a full rollout decision. Key metrics such as latency, accuracy, error rates, and resource utilization are monitored to evaluate the shadow model's performance.

**Pros:**
- Low risk: Since the shadow model does not impact live traffic, there is minimal risk to the production system.
- Real-world testing: The shadow model is tested with live data, providing valuable insights into its performance.

**Cons:**
- No user feedback: Since the shadow model does not serve live traffic, it does not receive user feedback.
- Delayed deployment: If updates to the model are needed immediately, shadow deployment may delay the process.

## Champion/Challenger (A/B Testing)

In some scenarios, teams may choose to deploy multiple models simultaneously to compare their performance in a live environment. This approach, known as champion/challenger or A/B testing, involves routing a portion of live traffic to each model and comparing their performance based on predefined metrics.

An example of when this strategy may be useful is with an ad serving model. A company may want to test a new ad serving algorithm against the existing one to see which performs better in terms of click-through rates and revenue generation.

**Pros:**
- Direct comparison: Allows for direct comparison of multiple models in a live environment.
- Data-driven decisions: Provides empirical evidence to support model selection.

**Cons:**
- Increased complexity: Managing multiple models and routing traffic can add complexity to the deployment process.
- Resource intensive: Running multiple models simultaneously may require additional computational resources.

## Lower Environment Promotion (Automated Testing)

If the model is directly integrated into and application along with an environment that has automated testing, another strategy is to promote the model through lower environments (e.g., development, staging) before deploying to production. This approach allows for testing of application-level functionality and integration with the model in a controlled environment.

**Pros:**
- Controlled testing: Allows for thorough testing of the model's integration with the application.
- Early issue detection: Identifies potential issues before the model reaches production.

**Cons:**
- Environment differences: Lower environments may not fully replicate production conditions, potentially leading to undetected issues.
- Longer deployment time: The promotion process through multiple environments may extend the overall deployment timeline.

