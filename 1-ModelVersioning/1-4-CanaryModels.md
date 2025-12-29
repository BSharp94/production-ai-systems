# Canary Models

Canary models are a deployment strategy for machine learning models where a new model version is gradually rolled out to a small subset of users or traffic before being fully deployed to all users. This approach allows for monitoring and evaluation of the new model's performance in a production environment while minimizing risk.

Canary deployments are often used to test new features, improvements, or changes in the model without exposing the entire user base to potential issues. By directing a small percentage of traffic to the canary model, teams can gather real-world performance data and user feedback before making a full rollout decision.

## Gradual Rollout Process

The gradual rollout process for canary models typically involves the following steps:

1. **Initial Deployment:** Deploy the new model version as a canary alongside the existing production model. Initially, only a small percentage of traffic (e.g., 1-5%) is routed to the canary model.
The inital deployment may also be done as a shadow model where it does not impact live traffic at all.

2. **Monitoring:** Continuously monitor the performance of the canary model using key metrics such as latency, accuracy, error rates, and resource utilization. Compare these metrics against the existing production model to identify any discrepancies or issues.

3. **Incremental Traffic Increase:** If the canary model performs well and meets predefined success criteria, gradually increase the percentage of traffic routed to the canary model in increments (e.g., 5-10%) over time. Continue monitoring performance at each stage.

4. **Full Rollout:** Once the canary model has been validated and demonstrates stable performance, proceed with a full rollout by routing 100% of traffic to the new model.