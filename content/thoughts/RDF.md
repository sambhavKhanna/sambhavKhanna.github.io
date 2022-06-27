---
title: "RDF"
date: 2022-06-09
tags:
- seed
---

> RDF is a standard model for data interchange on the Web

RDF can be understood as a linking structure which forms a directed, labeled graph, where the edges represent the named link between two resources, represented by the graph nodes.

See also: [[thoughts/LDP|LDP]]

## RDF Triple
RDF extends the linking structure of the Web to use URIs to name the relationship between things as well as the two ends of the link (this is usually referred to as a “triple”)

## Turtle
[Source: W3](https://www.w3.org/TR/turtle/)

A textual syntax for RDF called Turtle that allows an RDF graph to be completely written in a compact and natural text form, with shorthands for common usage patterns and datatypes

```xml
@base <http://example.org/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix rel: <http://www.perceive.net/schemas/relationship/> .

<#green-goblin>
    rel:enemyOf <#spiderman> ;
    a foaf:Person ;    # in the context of the Marvel universe
    foaf:name "Green Goblin" .

<#spiderman>
    rel:enemyOf <#green-goblin> ;
    a foaf:Person ;
    foaf:name "Spiderman", "Человек-паук"@ru .
```

## JSON-LD
A **JSON-LD document is both an RDF document and a JSON document** and correspondingly represents an instance of an RDF data model

```json
{
  "@context": "[https://json-ld.org/contexts/person.jsonld](https://json-ld.org/contexts/person.jsonld)",
  "@id": "[http://dbpedia.org/resource/John_Lennon](http://dbpedia.org/resource/John_Lennon)",
  "name": "John Lennon",
  "born": "1940-10-09",
  "spouse": "[http://dbpedia.org/resource/Cynthia_Lennon](http://dbpedia.org/resource/Cynthia_Lennon)"
}
```