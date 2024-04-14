# $$⚛ \space Quantum \space K-Means\space Clustering $$

This project explores the application of quantum computing to k-means clustering, focusing on data with a single feature.
<hr>

## **Table of Contents**

* [Introduction](#intro):
    * What is K-Means Clustering?
    * Limitations of Classical K-Means
    * Quantum K-Means: A Potential Solution
* [Quantum K-Means for One Feature](#Qkmeans):
    * Data Representation and Encoding
    * Fidelity and Error Correction
    * Measurement and Cluster Assignment
* [Project Setup and Usage](#setup):
    * Dependencies
    * Running the Code
    * Visualizing Results (Optional)
* [Future Directions and Considerations](#future):
    * Multi-Feature Implementation
    * Hybrid Quantum-Classical Approaches
    * Error Mitigation Techniques

## <div id='intro'> Introduction </div>

### What is K-Means Clustering?

K-means clustering is a popular unsupervised machine learning technique for grouping data points into a predefined number of clusters (`k`). It works by iteratively minimizing the within-cluster sum of squared distances (WCSS), aiming to find clusters with high intra-cluster similarity and low inter-cluster similarity.

### Limitations of Classical K-Means

Classical k-means faces two main limitations:

* **Initialization Sensitivity:** The initial placement of centroids (cluster centers) can significantly impact the final results. A poor initial placement can lead to suboptimal clustering.
* **Scalability:** Classical k-means can become computationally expensive for large datasets, especially with high dimensionality. As the number of data points or features increases, the time and resources required for computation grow rapidly.

### Quantum K-Means: A Potential Solution

Quantum k-means leverages the principles of quantum computing to address some challenges of classical k-means. It utilizes quantum states to potentially achieve:

* **Improved Initialization:** Quantum superposition allows simultaneous exploration of multiple centroid positions, potentially leading to a better initial configuration.
* **Exponential Speedup:** Quantum algorithms have the theoretical potential to perform certain calculations, like distance computations, much faster than classical algorithms on quantum computers.

## <div id='Qkmeans'> Quantum K-Means for One Feature </div>

This project implements a single-feature version of quantum k-means. Here's a deeper look at its key aspects:

### Steps

- Determine the number of clusters `k`.
- Randomly initialize the centroids
- Measure distances between data points and the centroids using **`Fidelity`**
  - Initialize `k+1` separable states in the ground state. `One` is for the data point and the other `k` represent the centroid.
  - Choose your encoding scheme(Rotational Gates).
  - Encode the centroids using the encoding scheme.
  - Encode the data using the encoding scheme.
  - Calculate the fidelity between the two states (one state would represent the data point and the other would represent the centroid).
- Assign data points to the nearest centroid.
- Update the position of the centroid according to the mean of each cluster.

### Data Representation and Encoding

Data points are represented as quantum states (qubits) in the computational basis. For one feature, each data point is encoded as a single qubit using an encoding scheme(rotational gates).

### Fidelity and Error Correction
Fidelity is a measure of the "`closeness`" of two quantum states, and is the inner product between two states.

Quantum operations are susceptible to errors due to noise in the quantum system. Fidelity measures the accuracy of these operations, and error correction techniques are crucial to maintain reliable results.

### Measurement

Measurements are performed on the qubits to determine their state in the classical computer. Used to get the final value of the centroids.

## <div id='setup'> Project Setup and Usage </div>

### Dependencies

This project requires installation of specific quantum computing libraries (consult the documentation for each library for installation instructions). 

- qiskit
- numpy
- pandas
- seaborn
- matplotlib

### Running the Code

1. Clone the repository: `https://github.com/adelelwan24/Quantum-K-Means.git`
2. Install dependencies (refer to library documentation)
    ```bash
    pip install qiskit
    ```
3. Run the main notebook: `Quantum_K_Means.ipynb`

### Visualizing Results

Create plots of the clustered data and centroids. This can help you visualize the effectiveness of the clustering process.

## <div id='future'> Future Directions and Considerations </div>

### Multi-Feature Implementation

Extending the algorithm to handle data with multiple features is a significant research area. Techniques like quantum feature mapping or kernel methods would be necessary for higher-dimensional data.

### Hybrid Quantum-Classical Approaches

Combining the strengths of classical k-means with quantum capabilities in a hybrid approach could be beneficial. For example, classical k-means could be used for initialization or post-processing on classical computers.

### Error Mitigation Techniques

Research advancements in quantum error correction and noise mitigation are crucial for achieving practical quantum k-means applications. As these techniques improve, quantum k-means has the potential to become a more viable tool for real-world data clustering tasks.

This project provides a starting point for exploring quantum k-means for single-feature data. Continued research and development are needed to bring this approach to full fruition for high-dimensional data clustering.
