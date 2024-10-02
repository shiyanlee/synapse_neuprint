# synapse_neuprint
retrieving synapse data from neuprint 

### TODO
🚩 **What was the problem?**
Neuronal synapses captured by electron microscopy (EM) are characterized by their dark appearance due to their protein-dense composition. Between two adjacent cells, the presynaptic site forms the T-bar, where clusters of neurotransmitter vesicles accumulate, while the postsynaptic density (PSD), recognizable by its "teeth-like" structure, represents the output. In high-resolution 3D EM images, synapses are often confused with other darkly stained organelles or with artefacts produced by membrane shrinkages, leading to subjective classifications in ground truth annotations. Nevertheless, an AI model is proposed to analyse visual cues and classify synapses in EM images because manual annotation of synapse is both tedious and expensive.

💡**All solutions we explored and why?**
The Janelia Hemibrain dataset is a key resource because it a FIB-SEM volume at 8nm resolution, which contains annotations of pre- and post- synaptic partners. Through neuPrint+ project, users are given the flexibility to customize synapse properties and extract specific 3D locations for both pre- and post synapses. First, we identified combinations of traced ROIs and neurons with the densest populations of synapses, filtering the data to include only synapses with CL ≥ 0.95. These synapse points were then partitioned into limited-dimensional clusters using KMeans clustering (constrain the bounds). From these clusters, variations of convex hulls were generated to achieve the smallest volume containing the largest number of points. Once created and ranked, the optimal convex hull from each cluster were transformed into compact cuboids, with outliers removed based on their distance from the centroid. Ultimately, this process produced 3D cubes with smaller, denser regions, minimizing empty space in order to reduce AI computational costs.

🧠 **Logic behind finally choosing the regions in hemibrain for the hulls:**
In neuPrint, two dataframes, `neuron_df` and `roi_counts_df`, are returned when a NeuronCriteria is applied. The neuron_df return neuron types and their respective numbers of pre- and post-synapses. However, a single neuron can intersect with multiple ROIs, leading to synapse location being widely distributed across the brain, which is not ideal for cluster analysis. Conversely, the roi_counts_df provides synapse counts for each ROI but does not include information about the corresponding neuron types. Ranking the data solely by ROI or neuron type would result in incoherent analysis. To address this, we merged both dataframes using body IDs, creating a single dataframe that includes both neuron types and ROI information, ranked by per-ROI synapse counts. This approach allows overlapping of ROIs and neurons but ensuring unique combinations for coherent analysis.

- Exploration of synaptic counts
- Visualisation using navis and neuprint.
- Add mirror/flipping hack for navis template brains in here and in navis discussion boards.
- Embed the html graphs in the readme for quick visualisation
- Add hull generation after pulling data via pymaid.
