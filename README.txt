
Pakistani Transmission Grid Model (PTGM)
########################################

Version: 1.0
Date: 01.09.2015


Description of the data files
=============================

All data is contained in the Excel file "ptgm.xlsx" which contains 5 sheets.
Each sheet is also provided in form of a CSV file (comma-separated values).

List of sheets / CSV files:

-   Nodes / ptgm_nodes.csv
-   Links / ptgm_links.csv
-   Cities / ptgm_cities.csv
-   Industries / ptgm_industries.csv
-   States / ptgm_states.csv

The list of nodes (vertices) and the list of links (edges) form a multigraph,
representing the substations as well as the transmission lines of the Pakistani
transmission grid. Some major power plants that are directly connected to the
transmission grid are also included.  Both nodes and links have certain
attributes, such as the geographical position of the nodes (latitude and
longitude), and physical parameters of the transmission lines etc.  The so
defined grid is visualized in the file "ptgm_plot.pdf". We also provide the
IPython Notebook "ptgm_plot.ipynb" with which this plot has been achieved.

A detailed description of the content of the Excel sheets / CSV files follows
below.


Nodes sheet / ptgm_nodes.csv
----------------------------

This sheet / CSV file contains the list of the nodes (vertices) of the graph.
The following columns are given:

nid
    The node ID, an integer index used within this model to identify each node.

osm_id
    If the node has a corresponding counterpart in OSM, we provide the OSM ID
    here.

name
    If given, contains the name of the substation or power plant.

type
    contains either "substation" or "plant", indicating the type of node.

lat
    Latitude, geographical position of the node.

lon
    Longitude, geographical position of the node.

nominal_power_output
    In case of a power plant, the nominal power output. Unit: Megawatt (MW).

population
    The estimated population supplied by this node. This estimate is obtained
    by a nearest-neighbor search for each city in the list of cities (see
    below) among the set of nodes.

fraction_of_population
    Fraction of the total population of Pakistan being supplied by this node
    according to the nearest-neighbor estimate.

fraction_of_total_consumed_power
    Fraction of the total Pakistani power consumption consumed at this node.
    Unit: Watthours (Wh).


Links sheet / ptgm_links.csv
----------------------------

This sheet / CSV file contains the list of the links (edges) of the graph. The
following columns are given:

lid
    The link ID, an integer index used within this model to identify each link.

osm_id
    If the link has a corresponding counterpart in OSM, we provide the OSM ID
    here.

nid1
    The ID of the node where the link starts.

nid2
    The ID of the node where the link ends.

voltage
    The voltage level of this link. Currently only the 220 kV and the 500 kV
    voltage levels are considered in the model. Unit: Volts (V).

cables
    The number of cables in the circuit. Typically a multiple of 3 due to
    3-phasic AC circuits.

wires
    The number of "wires" each cable is split into. Note that this information
    is so far missing from OSM data of Pakistan.

length_direct
    The direct distance between start and end nodes. In the current version of
    the grid model, we do not consider the actual path lengths of the
    transmission lines, but instead just the direct point-to-point distance
    between the two end points. Unit: Kilometers (km).


Cities sheet / ptgm_cities.csv
------------------------------

This sheet / CSV file contains the list of major Pakistani cities. This data
has been used to estimate which share of power is consumed by each node in this
model by exercising a simple nearest-neighbor search for each city among the
set of nodes. In other words, we make the crude approximation that every city
is provided with electrical energy by the nearest substation of the
transmission grid.

The following columns are given:

cid
    The city ID, an integer index used within this model to identify each city.

name
    The name of the city.

population
    The number of citizens.

province
    Name of the province in which this city is located.

lat
    Latitude, geographical position of the city.

lon
    Longitude, geographical position of the city.

closest_distance
    Distance to the nearest node. Unit: Kilometers (km).

closest_substation_index
    Index of the closest node.


Industries sheet / ptgm_industries.csv
--------------------------------------

This sheet / CSV file contains the list of major Pakistani industries. The
following columns are given:

iid
    The industry ID, an integer index used within this model to identify each
    industrial complex.

name
    Name of the industry.

city
    Name of the city at which the industry is located.

closest_substation_index
    Index of the nearest node.


States sheet / ptgm_states.csv
------------------------------

This sheet / CSV file contains the list of the Pakistani states (regions). The
following columns are given:

sid
    The state ID, an integer index used within this model to identify each
    state.

name
    The name of the state.

population
    The number of citizens of this state.


Copyright information
=====================

The Pakistani Transmission Grid Model (PTGM) is published under the terms of
the Open Database License (ODbL). A description of the ODbL license is
available at the webpage http://opendatacommons.org/licenses/odbl. The full
text of the license is contained in the file "LICENSE.txt", shipped with this
data package.


List of data sources
--------------------

The OpenStreetMap project (OSM)
    The OpenStreetMap project, http://www.openstreetmap.org/. OpenStreetMap
    data is licensed under the Open Data Commons Open Database License (ODbL),
    see http://www.openstreetmap.org/copyright for more information. (c)
    OpenStreetMap contributors. The alternative OSM inferface provided by
    http://www.flosm.de/ has also been used.

Google Maps
    Aerial photography provided by Google Maps has been used to correct and
    extend the data provided by the OpenStreetMap project, especially for
    "filling the gaps" in the OSM data. http://www.google.de/maps.

citypopulation.de
    The list of major Pakistani cities and their population have been taken
    from http://www.citypopulation.de/Pakistan-20T.html by Thomas Brinkhoff.
    The data is published under a Creative Commons Attribution 3.0 Unported
    license (CC BY 3.0).

scribd.com
    The list of major Pakistani industries has been taken from the book
    "List of 100 Companies of Pakistan" by Humayun Maqbool (2009),
    http://www.scribd.com/doc/12487960/List-of-100-Companies-of-Pakistan.
    scribd.com is an online publishing network. This book has been published
    under an "attribution non-commercial" license.


Authors
=======

Talha Nisar (1)
Daniel Jung (1)
Stefan Kettemann (1)

(1) Department of Physics & Earth Sciences, Focus Area Health, Jacobs
    University Bremen, Germany.


Achnowledgements
================

We greatfully acknowledge support of the Federal Ministry of Education and
Research (BMBF), CoNDyNet, FK. 03SF0472A.


Abbreviations
=============

OSM
    The OpenStreetMap project, http://www.openstreetmap.org/
