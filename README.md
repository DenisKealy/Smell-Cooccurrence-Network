This is a visualization of a co-occurrance network for smell percepts. The data was scraped from flavornet.org. For every molecule in the database there was a list of percieved smells. e.g = {honey, spice, rose, lilac}

In summary:

1. I scraped the data from flavornet.org using the scrapy libray and some python spiders. My spiders outputted a JSON file which has to be transformed to work with this visualisation.
2. Before transforming the data I performed data exploration to discover the properties such as how many unique mappings there were, how many duplicate. Discovering the number of unique percepts. Get a count of the frequency of each perceptual descriptor.
3. I then wrote a python class to transform the data into a JSON file that this program could read to construct a co-occurrance graph. Molecules with only a single percieved scent were ignored, apart from when counting the overall frequency (for weighted node sizes). All molecules with 2 percieved scents were used to create a mapping. 
4. Molecules which registered 2-4 percepts were considered and converted into binary groups of co-occurrance with each mapping only being added once. A frequency of each scent co-occurrence was stored and used to calculate the weighted links between the nodes.
5. In summary, each node is a smell. Each link is a co-occurrance of the two connected smells. The width and length of the link is proportional to the frequency of the co-occurrance in our dataset.

Playing with the visualisation:

* Hover over a node to see which smell it is
* Pull a node away from the cluster to see which nodes it drags along with it
* The connected nodes distance from the selected node is a measure of how often those smells occurred from the same stimulus.
