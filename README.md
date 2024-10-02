# synapse_neuprint
retrieving synapse data from neuprint 

### TODO
🚩 What was the problem?
Neuronal synapses captured by electron microscopy (EM) are characterized by their dark appearance, a result of their protein-dense composition. Between two adjacent cells, the presynaptic site forms the T-bar, where clusters of neurotransmitter vesicles accumulate, while the postsynaptic density (PSD), recognizable by its "teeth-like" structure, reflects the output. In high-resolution images, synapses are often confused with other darkly stained organelles or with membrane shrinkage, leading to subjective classifications in ground truth annotations. To address this, an AI model is proposed to analyze visual cues and classify synapses in 3D EM image stacks. However, one of the challenges is the sparse distribution of synapses within the brain, making the development of a synapse detection machine learning model both time-consuming and computationally expensive.

- All solutions we explored and why?
The Janelia Hemibrain dataset is one of the readily available datasets consisting annotations of synapses, along with their respective connectivity partners and regions of interest (ROIs). It is also highly customizable for extracting the desired data. Through neuPrint+ project, the information of synapses can be retrieved. We demonstrated our ability to identify regions with the densest populations of synapses and curated this data to prepare it for machine learning models. Segmenting the data into smaller, denser regions could minimise the empty spaces an ulimately reducing computational costs.

- Logic behind finally choosing the regions in hemibrain  for the hulls.
- Exploration of synaptic counts
- Visualisation using navis and neuprint.
- Add mirror/flipping hack for navis template brains in here and in navis discussion boards.
- Embed the html graphs in the readme for quick visualisation
- Add hull generation after pulling data via pymaid.
