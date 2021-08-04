# sar

#Configuration

For each examined model, we used the publicly available implementations and tuned the hyperparameters following a grid-selection strategy on the validation set. In SSE-PT++ we set the dimensions of user and item embeddings to 100 and the sequence length to l=50. In SASRec-SAC and SASRec-SQN, we fix the user and item embeddings to 200, the state representation vector **s** of a user to 100 and the discount factor γ to 0.94. Moreover, the sequence length of SASRec-SAC and SASRec-SQN is set to l=100. MTAM uses 100-dimensional user and item embeddings and the sequence length is fixed to l=30. In TiSASRec the user and item embeddings are set to 150 and the sequence length to 100. AdaptiveSubSeq models the user-item interactions as a directed acyclic graph, thus user and item embeddings are not considered. Given that the sequence length is adaptive, we fix the maximum allowed sequence length to l=200. In the proposed SAR model, we set the user and item embeddings to 100, the state representation vector **s**<sub>t</sub> is fixed to 150 dimensions and the discount factor γ is set to 0.82. 


In addition, to train the RL based approaches, that is SASRec-SAC, SASRec-SQN and SAR, we employ an offline batch RL environment [1-3]. This means that the agent receives the sequential user interactions, ordered based on the interaction timestamp. To optimize the model parameters for each RL strategy, the agent is trained in an episodic manner [4]. For each episode the agent receives the user's $u$ sequential interactions x<sub>ut</sub> and predicts the next item i<sub>t+1</sub> [5]. The episode is completed when the agent has received all the users' interactions.


[References]
[1] Scott Fujimoto, David Meger, and Doina Precup. 2019. Off-Policy Deep Rein- forcement Learning without Exploration. In ICML. 2052–2062
[2] Aviral Kumar, Aurick Zhou, George Tucker, and Sergey Levine. 2020. Conservative Q-Learning for Offline Reinforcement Learning. In NeurIPS.
[3] Avi Singh, Albert Yu, Jonathan Yang, Jesse Zhang, Aviral Kumar, and Sergey Levine. 2020. COG: Connecting New Skills to Past Experience with Offline Reinforcement Learning. CoRR abs/2010.14500 (2020).
[4] Richard S Sutton and Andrew G Barto. 2018. Reinforcement learning: An intro- duction. MIT press.
[5] Xin Xin,Alexandros Karatzoglou,Ioannis Arapakis,and Joemon M.Jose.2020. Self-Supervised Reinforcement Learning for Recommender Systems. In SIGIR. 931–940.
