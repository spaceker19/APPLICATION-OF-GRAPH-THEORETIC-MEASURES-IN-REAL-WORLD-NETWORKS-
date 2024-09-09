# APPLICATION-OF-GRAPH-THEORETIC-MEASURES-IN-REAL-WORLD-NETWORKS-
Btech project


---

# Reddit Network Analysis using Graph Theory

This project analyzes the network of subreddits on the Reddit platform to identify influential subreddits and to discover communities using graph-theoretic metrics like centrality and modularity. The primary goal is to analyze how subreddits are connected based on shared users and determine which subreddits have the potential to make content viral.

## Table of Contents
1. [Introduction](#introduction)
2. [Project Overview](#project-overview)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Centrality Measures](#centrality-measures)
6. [Modularity and Community Detection](#modularity-and-community-detection)
7. [Results](#results)
8. [References](#references)

## Introduction

The Reddit platform is composed of thousands of subreddits, each representing a community of users discussing various topics. The goal of this project is to analyze how subreddits are interconnected based on user activity and to identify influential subreddits, as well as find subreddit communities, using graph theory.

### Key Concepts
- **Centrality**: Measures the importance of a node (subreddit) in the network.
- **Modularity**: Measures the strength of division of a network into communities.

## Project Overview

The analysis uses Python’s Reddit API Wrapper (PRAW) to scrape data from Reddit and the NetworkX package to construct and analyze the network of subreddits. The network is formed by linking subreddits that share common users. Centrality measures such as PageRank, Betweenness Centrality, and Current Flow Betweenness are used to identify key subreddits. Modularity is used to discover communities within the network.

### Data Collection
- Data is collected using Reddit’s API through PRAW.
- Top posts from popular subreddits are retrieved, and based on user activity, a network is constructed.
  
### Analysis
- **Centrality Measures**: Identify subreddits with the highest influence.
- **Modularity**: Discover clusters of related subreddits.

## Installation

### Prerequisites
- Python 3.x
- Reddit API credentials (Client ID and Secret) for using PRAW

### Install Required Packages
```bash
pip install praw networkx matplotlib
```

### Setting Up Reddit API Credentials
To use PRAW, you’ll need to create a Reddit app to get your API credentials. You can do this by following these steps:
1. Go to [Reddit Apps](https://www.reddit.com/prefs/apps).
2. Create a new app, and note down the `client_id`, `client_secret`, and `user_agent`.

## Usage

1. Clone this repository.
   ```bash
   git clone https://github.com/yourusername/reddit-network-analysis.git
   cd reddit-network-analysis
   ```

2. Update the `config.py` file with your Reddit API credentials:
   ```python
   reddit = praw.Reddit(client_id='YOUR_CLIENT_ID',
                        client_secret='YOUR_CLIENT_SECRET',
                        user_agent='YOUR_USER_AGENT')
   ```

3. Run the script to scrape data from Reddit and build the network:
   ```bash
   python reddit_network.py
   ```

4. Visualize the network and results:
   ```bash
   python visualize.py
   ```

## Centrality Measures

### 1. **PageRank**
- **Definition**: PageRank centrality identifies the most important subreddits based on the number of incoming connections and their importance.
- **Usage**: This helps determine which subreddits have the highest potential for virality.

### 2. **Betweenness Centrality**
- **Definition**: Betweenness centrality identifies subreddits that act as bridges in the network, connecting various communities.
- **Usage**: Subreddits with high betweenness are key for content exposure across multiple communities.

### 3. **Current Flow Betweenness**
- **Definition**: Models the flow of information through the network considering multiple paths.
- **Usage**: Provides a broader view of subreddit influence beyond just shortest paths.

## Modularity and Community Detection

### Modularity
- **Definition**: Measures how well the network can be divided into distinct communities.
- **Usage**: Detects communities of subreddits with similar users, which helps understand the structure of Reddit's user base and possible echo chambers.

## Results

After analyzing the network, we:
1. Identified key subreddits using centrality measures.
2. Detected communities of subreddits with strong user overlap using modularity.
3. Determined the subreddits with the highest potential for spreading content across the network.

### Example Visualization:
- Subreddits are represented as nodes.
- Communities are color-coded.
- The size of each node corresponds to its centrality value.

## References

1. Newman, M. E. J. "Networks: An Introduction." Oxford University Press, 2010.
2. Blondel, Vincent D., et al. "Fast unfolding of communities in large networks." Journal of Statistical Mechanics: Theory and Experiment 2008.10 (2008): P10008.
3. Brin, Sergey, and Page, Lawrence. "The anatomy of a large-scale hypertextual web search engine." Computer networks and ISDN systems 30.1-7 (1998): 107-117.
4. Brandes, Ulrik. "A faster algorithm for betweenness centrality." Journal of mathematical sociology 25.2 (2001): 163-177.

---
