# synapse_neuprint
retrieving synapse data from neuprint 

### TODO
🚩 What was the problem?
Neuronal synapses captured by electron microscopy (EM) are characterized by their dark appearance, a result of their protein-dense composition. Between two adjacent cells, the presynaptic site forms the T-bar, where clusters of neurotransmitter vesicles accumulate, while the postsynaptic density (PSD), recognizable by its "teeth-like" structure, reflects the output. In high-resolution images, synapses are often confused with other darkly stained organelles or with membrane shrinkage, leading to subjective classifications in ground truth annotations. To address this, an AI model is proposed to analyze visual cues and classify synapses in 3D EM image stacks. However, one of the challenges is the sparse distribution of synapses within the brain, making the development of a synapse detection machine learning model both time-consuming and computationally expensive.

💡All solutions we explored and why?
The Janelia Hemibrain dataset, which includes annotations of synapses along with their respective connectivity partners and regions of interest (ROIs), served as a key resource. Through the neuPrint+ project, we customized the dataset to selectively filter information, such as synapse confidence levels (CL), and extract specific 3D locations for each synapse. First, we identified combinations of ROIs and neurons with the densest populations of synapses, filtering the data to include only synapses with CL ≥ 0.95. These synapse points were then partitioned into limited-dimensional clusters using KMeans clustering. From these clusters, variations of convex hulls were generated to achieve the smallest volume containing the largest number of points. Once created and ranked, the optimal convex hull from each cluster were transformed into cuboids, with outliers removed based on their distance from the centroid. Ultimately, this process produced 3D cubes with smaller, denser regions, minimizing empty space and reducing computational costs.

- Logic behind finally choosing the regions in hemibrain  for the hulls.
- Exploration of synaptic counts
- Visualisation using navis and neuprint.
- Add mirror/flipping hack for navis template brains in here and in navis discussion boards.
- Embed the html graphs in the readme for quick visualisation
- Add hull generation after pulling data via pymaid.
