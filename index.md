## CSE 5544 Final Project

Authors: 
Dantong Xue (xue.425), Alex Shearer (shearer.145), Pouya Kousha (kousha.2)

### Introduction

Recent advances in High Performance Computing (HPC) have provided the fast processing engine for HPC applications.

![HPC](supercomputer.jpeg)

With the recent advances in interconnect technology and increasing cost of communication, providing efficient data movement between nodes on the communication fabric is essential to guarantee optimized end-to-end solutions.

There is a need for interactive and straightforward visualization tool to better utilize and arrange the communication details happening on the network. The idea of this project is to give a clear visualization how the HPC infrastructure perform and how individual nodes in that network communicate with each other.

### problem statement

* How can we visualize the network topology along with link usage in an easy-to-interpret manner?
* How can we visualize the details of network topology in an easy manner?
* How can we present the network traffic of links in an interactive manner?

### Visualizations

With this in mind, we provide a suite of visualizations to meet the clients' need for understanding the HPC network.

#### Network
We started by visualizing the topological structure of all our computing nodes. The plot simply shows the connections between nodes with color indicating the node types (red->switches, white->normal nodes).

![Initial Network](InitNetwork.png)

As we move forward, we see the need of monitoring link usage visually. We add link color as the indicator for link usage. We intentionally choose hue instead of luminance to show different usage of the network as we think hue does a better job in categorizing the link usage circumstances.

![Colored Network](ColorNet.png)

 To compensate the need of accurate link usage data, we provided hovering to show the utilization number.

 ![Hover](OnHover.png)

#### Radar Plot

In order to show more detailed information about the node that we care, we implemented radar chart on top of the network design.

The initial design comes as a zoomed radar chart beside the network structure, as shown below.

![Radar1](Radar1.png)

We further improve this design by intergrating the radar plot directly to the network topology, as we believe the integration can help our clients to compare metrics between two nearby switches.

![RadarComp](RadarComp.png)

#### Integration

With all the elements above, we have a fully integrated suite of both network structure, link utilization rate, and detailed performance numbers for each node realized by integrating the radar plot with the network graph.

![NetworkFull](NetworkFull.png)

The interactive version of the network can be accessed [here](radar_network.html).

We also have a version support multiple edges in between two switches.

[NetworkMulti](radar_network_multi.html).

#### Timeseries Performance Plots

For network monitoring, having historical performance metrics visualized is also important. Clients may want to have analysis to historical data to find the **abnormal / extreme** points along the timeline.

We hear from our clients and implement the timeseries performance plots. The plots give information about sending/receiving package number and bits for a certain node in a period of time. Clients can easily drag the timeline to limit the timeframe shown on the plot.

Clients will first use the overall view to identify the abnormal point.

![Extreme](NoZoom.png)

Then, the client can zoom in to check detailed numbers for that region.

![Zoom](Zoom.png)

The interactive version of the timeseries performance plot can be accessed [here](data_line_plot.html).
