## Master Thesis project

**Project description:** This is the result of my master thesis work.

### 1. Context

ML Classifiers are used in medical research for diverse tasks. In my thesis, the goal was to improve on an existing classifier of EEG signals that identifies in which sleep stage an EEG of a newborn corresponds to).


### 2. Problem

A [state-of-the-art EEG classifier](https://iopscience.iop.org/article/10.1088/1741-2552/ab5469/meta) already exists for this task, but even though the model used was finely designed, it shows an accuracy of around 70%. Some progress was to be made...
<p align="center">
<img src="images/ansari-network.jpg?raw=true" width=50% height=auto />
</p>

### 3. Technique used

Although the Deep Learning revolution made possible to solve really challenging and breathtaking tasks, it also involved designing more and more complex architectures, which becomes a bottleneck in term of manual effort.
Neural Architecture Search emerged as a solution to this problem by allowing the automated search for a best architecture.

The main idea is to use a neural network (i.e. LSTM) that samples, at each iteration, a new architecture, test it and compute a reward based on it, and updates its own weights according to the reward. It is basically, Reinforcement Learning used as a search strategy.

<p align="center">
<img src="images/NAS-paradigm.png?raw=true" width=50% height=auto />
</p>

### 4. Improvements on NAS

#### 1. A new version of the reward function (enhancement on the Performance Estimation Strategy)


Performance estimation in the context of a NAS consists of estimating the performance of the children as accurately as possible. For a NAS to be enough efficient and to learn fast, one must find ways to quickly estimate the accuracy of each child, one biggest challenge in this regard is to clearly separate between promising children and the others. Instead of using the accuracy directly as the reward, one can use the output of an exponential function of the
accuracy, thus amplifying the difference between low and high rewards.

$$Reward(x) = \frac{1}{(1 + exp(-x*A+B))}*C$$

If we know the accuracy value that separates bads and goods, we can set $\frac{A}{B} = threshold$ making the function changing its cavity at this value.


<p align="center">
<img src="images/concavity.png?raw=true" width=50% height=auto />
</p>


#### 2. Efficient Neural Architecture Search (ENAS) implementation

ENAS improves the training phase of the children networks by forcing them to share the
weights for the parts they have in common. This technique uses the principles of
transfer learning, leveraging the beneficial impact on the training phase by sharing
weights between similar (but different) architectures.
If one consider the two models below, represented by the red arrows linking the nodes of a DAG (each node is a computational layer, e.g. convolutional, pooling etc.), the thick edges represent the weights that are common to both model, and that ENAS will re-use during training.

<p align="middle">
<img src="images/ENAS-DAG-1.png?raw=true" width=40% height=auto />
<img src="images/ENAS-DAG-2.png?raw=true" width=40% height=auto />
</p>


### 5. Results


<p align="middle">
<img src="images/incre_norew.png?raw=true" width=40% height=auto />
<img src="images/incre_rew.png?raw=true" width=40% height=auto />
</p>


For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
