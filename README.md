# Model-free-solutions-using-Deep-Reinforcement-Learning-and-Function-Approximations

Name - Akshit Shishodia

## Motivation?
The motivation for this project is closely linked to my B.Tech thesis, where I focused on developing adaptive, model-free solutions for general physical systems, particularly in the context of civil engineering. This current project builds on that foundation by exploring reinforcement learning as a tool to derive optimal and adaptive control strategies. Reinforcement learning is especially appealing because it enables learning from data through a wide spectrum of mathematical techniques—from basic methods like linear regression to advanced frameworks such as deep Q-networks or policy gradient algorithms. Despite the variation in tools and complexity, the core challenge remains consistent: finding optimal solutions under constraints using data-driven, adaptive approaches.
## Multimodal Learning
This algorithm aligns closely with current advancements in multimodal reinforcement learning by aiming to stabilize general physical systems using only state feedback, without requiring explicit knowledge of system dynamics. In complex real-world environments, sensors such as cameras, IMUs, force sensors, and others provide diverse streams of data. Multimodal learning leverages this diversity by integrating multiple sensory modalities to create a rich representation of the system state. This algorithm can adopt this strategy by feeding these combined inputs into modular neural networks that approximate the actor and critic, enabling robust decision-making in systems that are otherwise difficult to model.

Recent work in multimodal RL often uses separate encoders for each modality and fuses the outputs either early or late in the network, often through attention or learned gating mechanisms. This algorithm naturally fits into this framework and extends it by focusing on policy learning through direct interaction with the environment. This allows it to adapt across different systems and sensor configurations, providing robustness to noise, partial observability, or missing data. By combining model-free RL with multimodal state representations, this algorithm contributes to the growing field of adaptive, generalizable control systems that learn directly from experience, making it well-suited for real-world stabilization tasks. 

For example, in the CartPole task, the state can be derived from multiple modalities—like vision (camera for pole angle), encoders (cart position), and IMUs (angular velocity). This algorithm can fuse these inputs into a unified representation and learn to balance the pole using actor-critic networks trained purely from interaction. Without relying on known dynamics, it updates its policy based on feedback, making it robust to sensor noise and adaptable to real-world conditions.

## Takes from the project
This project allowed me to apply and deepen several core concepts from the course in a practical and integrated way. Starting with linear algebra, I used norms and vector operations to measure distances between state vectors, which were essential for clustering and identifying similar states—key to localized learning and control.

I also strengthened my understanding of deep learning by implementing neural networks as function approximators for the actor, critic, and value functions. This helped me grasp how neural architectures can learn complex, nonlinear relationships through iterative gradient-based updates. Additionally, working with similarity metrics and feature vector representations made abstract concepts like distance and geometric intuition in high-dimensional spaces more tangible.

Finally, integrating these ideas into a reinforcement learning framework taught me how model-free algorithms can learn to stabilize dynamic systems using only state feedback, without any prior knowledge of system dynamics. Overall, this project tied together mathematical foundations, learning theory, and practical algorithm design in a meaningful way.

## Scope for Improvement
## Addressing Steady-State Response and Oscillatory Behavior

A significant improvement is required to address the steady-state response and oscillatory behavior observed in the system. These issues may stem from instability in the model, potentially caused by inappropriate batch sizes leading to unstable training dynamics and persistent (non-vanishing) gradients.

### Potential Causes

- **Model Instability:** The choice of batch size can impact the stability of training, resulting in oscillations or divergence.
- **Gradient Issues:** Non-vanishing gradients can further exacerbate instability, preventing the model from converging to a steady state.

### Proposed Next Steps

To mitigate these issues, the following hyperparameters should be carefully tuned:

- **Norm Distance for Clusters:** Adjusting this can improve the quality of clustering and overall model stability.
- **Number of Training Epochs:** Finding the optimal number of epochs can help prevent overfitting or undertraining.
- **Learning Rate:** Fine-tuning the learning rate is crucial for achieving stable and efficient convergence.

### Ideal Solution

The ultimate goal is to stabilize the system using feedback mechanisms that require minimal training time (ensuring fast adaptation) while achieving optimal performance as defined by the cost function. This approach will ensure both efficiency and effectiveness in the system’s operation.
