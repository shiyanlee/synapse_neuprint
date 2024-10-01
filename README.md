# synapse_neuprint
retrieving synapse data from neuprint 

### TODO
- What was the problem?
Synapses have always posed a challenge for automatic detection due to their imperceptible features and sparse distribution within the brain. Ground truth annotations for synapses are limited and require multiple rounds of proofreading by professionals. These characteristics cause slow and resource-intensive development of machine learning models for synapse detection.

- All solutions we explored and why?
The Janelia Hemibrain dataset is one of the readily available datasets consisting annotations of synapses, along with their respective connectivity partners and regions of interest (ROIs). It is also highly customizable for extracting the desired data. Through neuPrint+ project, the information of synapses can be retrieved. We demonstrated our ability to identify regions with the densest populations of synapses and curated this data to prepare it for machine learning models. Segmenting the data into smaller, denser regions could minimise the empty spaces an ulimately reducing computational costs.

- Logic behind finally choosing the regions in hemibrain  for the hulls.
- Exploration of synaptic counts
- Visualisation using navis and neuprint.
- Add mirror/flipping hack for navis template brains in here and in navis discussion boards.
- Embed the html graphs in the readme for quick visualisation
- Add hull generation after pulling data via pymaid.
