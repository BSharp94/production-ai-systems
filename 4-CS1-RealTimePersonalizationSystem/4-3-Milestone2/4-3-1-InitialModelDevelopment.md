# Initial Model Development

With the dataset infrastructure established, the data science team at ShopSmart can now focus on developing the initial recommendation model. They can use the dataset repository to establish a cloud hosted or local copy of the dataset for experimentation and model training.

## Model Experimentation

The team begins by exploring various recommendation algorithms, such as collaborative filtering, content-based filtering, and hybrid approaches. The experiments are tracked using the following:

- **Repository with spike folder:** A common practice is to create a folder within the main repository called "spike" or "experiments" where data scientists can create isolated experiments without affecting the main codebase. Experiments can be organized into subfolders or consolidated into a single notebook or script file.

- **MLflow for experiment tracking:** The team uses MLflow to log parameters, metrics, and artifacts for each experiment. This allows them to compare different model versions and configurations easily. Each experiment run is tagged with relevant information, such as the algorithm used, hyperparameters, and dataset version.

- **Experimentation Wiki:** The team maintains a wiki or documentation page to summarize the findings from each experiment. This includes insights on model performance, challenges faced, and next steps for further experimentation.

- **Weekly Sync-ups:** Regular meetings are held to discuss progress, share insights, and plan the next steps in model development. This collaborative approach ensures that the team stays aligned and can leverage each other's expertise.

## Model Selection

After conducting several experiments, the team settles on the following model architecture for the initial recommendation system:

- **User-Vector Embeddings:** A User-Vector Embedding model is chosen to capture user preferences based on their interaction history. This model generates dense vector representations of users, allowing for efficient similarity calculations.

- **Product-Vector Embeddings:** Similarly, a Product-Vector Embedding model is used to represent products in a dense vector space. This enables the system to recommend products that are similar to those a user has interacted with.

- **Dot Product for Similarity:** The recommendation score is calculated using the dot product of the user and product embeddings. This approach allows for efficient computation of recommendation scores for a large number of products.

- **Seasonal Features:** The model incorporates seasonal features, such as time of year and special events, to account for changes in user behavior during different periods.

- **Promoted Products:** Business rules are integrated into the recommendation logic to promote certain products based on marketing strategies.

## Model Hosting and Deployment Infrastructure

Since the recommendation system needs to operate in real-time, the team designs an infrastructure that supports low-latency recommendation serving. The key components of the infrastructure include:

- **Vector Database:** A vector database is used to store the user and product embeddings. This allows for efficient retrieval of similar products based on user preferences.

- **Kafka messages for triggering embedding updates:** The system uses Kafka to stream user interactions in real-time. When a user interacts with a product, a Kafka message is sent to trigger an update of the user's embedding in the vector database.

- **Model Serving API:** A RESTful API is developed to serve recommendations to the front-end application. The API retrieves user embeddings from the vector database and computes recommendation scores for products in real-time.

