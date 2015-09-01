
Pakistani Transmission Grid Model (PTGM)
########################################

Version: 1.0
Date: 01.09.2015


Introduction
============







Description of the data files
=============================

The data is contained in the files "nodes.csv" and "links.csv", in the "comma-separated values" (CSV) format.
They define a graph, which consists of a list of nodes, representing the substations and power plants of the transmission grid, and
a set of links (edges), which represent the transmission lines. Both nodes and links have a number of attributes, such as the geographical position of the nodes (latitude and longitude), and physical parameters of the transmission lines etc.

A detailed description of the content of the files follows below.


nodes.csv
---------

This file contains a list of the nodes of the graph. The following columns are given:

nid
    The node ID, an integer index used within this model to identify each node

osm_id
    If the node has a corresponding counterpart in OSM, we provide the OSM ID here.

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

fraction_of_population

fraction_of_total_consumed_power
    Unit: Watthours (Wh).



links.csv
---------

lid
    The link ID, an integer index used within this model to identify each link








Copyright information
=====================




List of data sources
--------------------

The OpenStreetMap project (OSM)
    The OpenStreetMap project, http://www.openstreetmap.org/. OpenStreetMap data is licensed under the Open Data Commons Open
    Database License (ODbL), see http://www.openstreetmap.org/copyright for more information. (c) OpenStreetMap contributors.

Google maps
    https://www.google.de/maps



Authors
=======

Talha Nisar (1)
Daniel Jung (1)
Stefan Kettemann (1)

(1) Department of Physics & Earth Sciences, Focus Area Health, Jacobs University Bremen, Germany.


Achnowledgements
================

We greatfully acknowledge support of the Federal Ministry of Education and Research (BMBF), CoNDyNet, FK. 03SF0472A.


Abbreviations
=============

OSM
    The OpenStreetMap project, http://www.openstreetmap.org/