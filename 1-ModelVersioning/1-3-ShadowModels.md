# Shadow Models

Shadow models are a deployment strategy for machine learning models where a new model is deployed alongside an existing production model, but does not impact live traffic. It allows for real-world performance evaluation of a new model without risking disruption to the production system. 

Shadow models are often used during the testing and validation phase of the model lifecycle, providing a way to compare the performance of the new model against the existing production model under real-world conditions.

Often they are used to gather data on how the new model performs with live data, allowing for analysis of metrics such as latency, accuracy, and resource utilization. This information can be invaluable for making informed decisions about whether to fully deploy the new model or make further adjustments.

## Typical Metrics Monitored in Shadow Deployments

When deploying shadow models, several key metrics are typically monitored to evaluate their performance:

- **Latency:** The time it takes for the model to process a request and return a response. Monitoring latency helps ensure that the shadow model meets performance requirements.

- **Accuracy:** The correctness of the model's predictions compared to the ground truth. This metric is crucial for assessing the model's effectiveness.

- **Throughput:** The number of requests the model can handle in a given time period. This metric helps evaluate the model's scalability.

- **Resource Utilization:** The amount of computational resources (CPU, memory, etc.) the model consumes. Monitoring resource utilization helps ensure that the model operates efficiently.

- **Error Rates:** The frequency of errors or failures in the model's predictions. This metric helps identify potential issues with the model.

- **Cost:** The operational cost associated with running the shadow model. This includes infrastructure costs and any additional expenses incurred.

## Considerations for Implementing Shadow Models

When implementing shadow models, several considerations should be taken into account:

- **Percentage of Traffic:** Decide what percentage of live traffic will be routed to the shadow model. This can range from a small fraction to a significant portion, depending on the risk tolerance and testing needs.

- **Metric Collection:** Ensure that the necessary infrastructure is in place to collect and analyze metrics from both the shadow model and the production model.

- **Data Privacy:** Ensure that the deployment of shadow models complies with data privacy regulations and policies, especially when handling sensitive data.

- **Rollback Strategy:** Have a clear rollback strategy in place in case the shadow model exhibits unexpected behavior or performance issues.