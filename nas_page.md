## Master Thesis project

**Project description:** This is the result of my master thesis work.

### 1. Context

ML Classifiers are used in medical research for diverse tasks. In my thesis, the goal was to improve on an existing classifier of EEG signals that identifies in which sleep stage an EEG of a newborn corresponds to).


### 2. Problem

A [state-of-the-art EEG classifier](https://iopscience.iop.org/article/10.1088/1741-2552/ab5469/meta) already existed for this task, even though the model used was finely designed with different versions, it shows an accuracy of around 70%, some progress was to be made...
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

### 4. Provide a basis for further data collection through surveys or experiments

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. 

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
