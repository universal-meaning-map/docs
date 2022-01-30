# Interplanetary mind-map (IPMM)
- [Interplanetary mind-map (IPMM)](#interplanetary-mind-map-ipmm)
  - [Overview](#overview)
  - [Minformation terminology](#minformation-terminology)
  - [Self-describing](#self-describing)
  - [System Topology](#system-topology)
    - [Node](#node)
    - [MID - Mind identifier](#mid---mind-identifier)
    - [Note](#note)
    - [CID - Content identifier](#cid---content-identifier)
    - [IID - Intent identifier](#iid---intent-identifier)
    - [AREF - Abstraction reference](#aref---abstraction-reference)
    - [Property](#property)
  - [FAQ](#faq)
    - [Semantic consensus](#semantic-consensus)
    - [Comparison with the Semantic Web](#comparison-with-the-semantic-web)
    - [Project philosophy](#project-philosophy)
- [Pseudo Interplanetary mind-map (Pipmm)](#pseudo-interplanetary-mind-map-pipmm)
  - [Overview](#overview-1)
  - [Installation (WIP)](#installation-wip)

## Overview

The interplanetary mind map is a long term project that aims to explore and build tools and protocols to make digital human-to-human / human-to-self communication more efficient to minimize human conflict and maximize the capacity to understand complex information. It does it by building a protocol that endorses 2 fundamental assumptions:
1. The meaning or understanding of information is unique to each mind, as it is the product of an extremely complex cloud of associations. The word `minformation`is used to make this explicit.
2. To maximize interoperability and understanding of information, digital projections of `minformation` should aim to be `self-describing`. This means that information should not require external context to be understood.

These assumptions force digital information to be structured connected and nested in a different new way. It enables a new paradigm of computation and communication that revolves around the particular ontologies of each mind allowing to adapt to each person needs, as opposed to subordinating people to the pre-assumptions, bias and incentives of software creators.


## Minformation terminology
- `abstraction`: Is the atomic part of `minformation`. Anything that a `mind` can make sense of, can be encapsulated as an `abstraction`. It exists only in a particular `mind` at a given time. It can't ever be expressed nor represented fully. It is constantly changing as we add more associations to it.
- `abstraction projection`: Is a representation attempt of an `abstraction`, it is inherently incomplete and distorted. 
- `abstraction intent`: A `abstraction` is ephemeral, it can be understood as the state of a concept in a given time for a given mind. The `abstraction intent` is an immutable container where this concept lives and is what we usually refer to in our daily communications.
- `abstraction pointer`: Is what we use to refer to an `abstraction intent`. We do that all the time with symbols and words (signs), these are `abstraction pointers`.

Example:

```md
Each of us has a different idea of what a car is. There is a cloud of experiences, associations and understandings that conforms to our understanding of a car. This cloud, in a particular moment, for a particular mind is an `abstraction`.

If I try to explain what a car is to you, I will only be able to express part of the cloud that I have in my head, there are things that I don't remember, there are associations of the car that I have that I'm not aware of, I'm limited on time for what I can express, and even if I could do the above the limits of the language will only be able to communicate part of it. That's why any expression of what a car means to me is just an `abstraction projection`.

Despite an `abstraction` being not representable and constantly evolving we still can refer to a "car". There is a "container" that we can point at, and therefore does not change, it holds the evolving idea of the car. This container is the `abstraction intent`.

When we communicate, we use the word "car". This is an `abstraction pointer` to the `abstraction intent` of a car. It doesn't point to the `abstraction` itself as it is only a snapshot in time. An `abstraction intent` can have many `abstraction pointers`, a picture of a car or even a memory can also be `abstraction pointers`
```

## Self-describing
The `self-describing` quality is manifested in many ways in the system:

1. `self-describing note`: This is a quality that the author of a `note` should aim for, and is what allows the overall ontology to grow and be coherent. It can't be enforced by the system, but it can be incentivized.
2. `self-describing type`: The "key" of each `note` `property` is nothing but an `abstraction-pointer` to the `type note`. A `type note` is a `note` that contains all the information to be processed by a computer (classic type system), but also the information to be semantically understood by a `mind`. The development of this type-system is one of the critical aspects of the development of the project.
3. `self-describing text`: We have the capacity now to make `transclusions` by making words, paragraphs and other text structures to be pointers to particular `notes` `properties` and having a semantic interface that guarantees that the transclusion will still make sense in the future. This enables the capacity for each word to be `self-describing` which means that we do not need to rely on the ambiguous definitions of a global dictionary and instead we can create extremely explicit text where a resolution to its meaning can be added progressively. This type of text format is currently referred to as `interplanetary-text` and is one of the main focuses of exploration of the project.

## System Topology
> While the main ideas are quite definitive, the specific details still change constantly and should not be taken as specifications. They are for illustrative purposes only.

### Node
- The system tries to mimic the behaviour of `minformation` in the analogue world. Because the origin of `minformation` is on each mind, a `mind` is represented in the system.
- A `mind` is the source of the `abstraction projections`, currently referred to as `notes`.
- A `mind` takes the form of a `node` in a peer-to-peer network. Is the element we need to refer to if we want to know its latest updates.

### MID - Mind identifier
- The `MID` or `Mind Identifier` is a unique identifier derived from a private key and used to identify any given `mind`/`node`.
- Any request concerning a given `mind` will have to be handled by its respective `node` and to uniquely identify the `node` in the network we use the `MID`.
- A `MID`looks like this: `QmXPTSJee8a4uy61vhAs35tM5bXDomSmo1BbTMUVAVbAGJ`

### Note
- An instance of an `abstraction-projection` in the system is currently referred to as `note`.

- A `note` aims to represent an `abstraction` as accurately as possible, although is always the best effort.
- A `note` is made of a list of arbitrary lengths of `predicates`. A `predicate` is a quality or attribute of the `abstraction`.
- A `predicate` has the form of a key-value pair. The "key" is the `property` that can be understood as the how/verb/relationship/type...
- A `note` is an [`IPLD`](https://ipld.io/docs/) object that points at other `IPLD` objects.

### CID - Content identifier
- At any given time, a `note` is represented by a [`CID`](https://github.com/multiformats/cid).
- A `CID` is a cryptographic hash of the `IPLD` object of a `note`.
- A `CID`is an immutable reference to an `abstraction-projection`.
- A CID looks like this: `baguqeeragkrzqs7df67d2qiwedqw56glsmwrssjhsp25mujxx5vdbu5yqbzq`

### IID - Intent identifier
- While the `CID`allows us to reference a snapshot of an `abstraction`, we still need a way to reference the evolving idea of an `abstraction`, the `abstraction-intent`.
- The `IID`is the identifier of the container of an `abstraction`.
- An `IID` is always mapped to the latest `CID`of a given `abstraction`.
- An `IID`is composed of a `MID`and the `LIID`(`Local Intent identifier`)`.
- An  `IID` looks like this: `QmXPTSJee8a4uy61vhAs35tM5bXDomSmo1BbTMUVAVbAGJsdqwz4ea`, the 46 first characters representing the `MID` and the latest 8 representing the `LIID`
![Intent identifier mapping timeline](images/abstraction_timeline.png)

### AREF - Abstraction reference

- The `AREF` is a text expression that allows us to point to any element of the system. 
- Is the equivalent of what `hyperlink` is to the `hypertext`
- It can have several forms depending on if is pointing to an `IID`or a `CID`, or if we want to be more precise and point to a specific property or object within a `note`: `IID/PID/IPLD_path` or `CID/PID/IPLD_path`
- If the `AREF` is pointing to an `IID`it will resolve to the `CID`, and then will resolve the `CID`
- A `AREF`may look like that `QmXPTSJee8a4uy61vhAs35tM5bXDomSmo1BbTMUVAVbAGJz6zpqnbq/QmXPTSJee8a4uy61vhAs35tM5bXDomSmo1BbTMUVAVbAGJqz3qlkca`

### Property
- A `property` (key) defines "how" the `note` relates to any other information (value)
- The `property` in itself is a pointer to another `note`, that describes the semantic and type attributes of that `property`. This means that the meaning of how `notes` relate to other `notes` is always given by the users.
- This also means that `properties` can be understood as "global" variables, but the "global" scope is not within a project but truly global.
`Properties` are `self-describing` types that include a semantic and typing interface.


## FAQ
### Semantic consensus
A common question about the system is...
> How to make any sense of anything if everything is concerning the semantics of a particular `mind` as opposed to an agreed understanding of the meaning of something?
>
The view in this regard is that an "agreed understanding" is an illusion and we should acknowledge it by being explicit on its representation, as opposed to embracing a fallacy of shared meaning. 
If there is a "shared meaning" is a fuzzy one and emergent behaviour, as opposed to a, seek one.

### Comparison with the Semantic Web
Certain elements may seem similar to the `Semantic web` (and other similar protocols), but there are very significant differences:

- It does not assume that is possible to find a consensus on all the categories in which information can be related and instead gives the privilege to do so to the user.
- It does not want to be built on top of the existing web technologies, since for the end purpose of the project they are unsafe and inherit too much technical and conceptual debt.
- The system is fundamentally a peer-to-peer or mind-to-mind network, and by embracing it into its protocol design it expects to prevent the actual predominant client-server architecture of the web and generate very different dynamics, such as a strong reputation system, as each mind can be understood as an identity.
- The system has represented many more layers of `minformation` such as the `abstraction intent` or `time` which also create very different dynamics.

### Project philosophy
- The system should aim to serve the particular `minds` of each individual and to enable them to reach the maximum potential as opposed to subordinate people to the system.
- Because of its goals around recreating a fundamental information system, the project should be particularly aware of potentially misaligned incentives E.g., Funding, corporate use, mindsets with "current web paradigm"
- The take on its design is at the very least singular and it does not fit within the established development paradigms as it requires first a conceptual understanding. The current strategy is to go back and forth between...
  1. Conceptual design
  2. Proof of concept development
  3. Play, use, experimental
    ... until the conceptual design matches the desired intent. Then start a solid development of the protocol.

# Pseudo Interplanetary mind-map (Pipmm)

`Pseudo Interplanetary mind-map` is a proof a concept to play, understand and validate the previous assumptions. While the technical part is complex, there are a lesser amount of unknowns than its conceptual counterpart. That means that the challenge does not reside in its implementation but understanding and generating a conceptual framework to help to operate with the aforementioned assumptions.


## Overview
> This software is mostly for experimental purposes and is not meant for production or a general audience but for people that already have a significant pre-understanding of the project and want to explore its possibilities.

The following repositories compose the project:

- `abstractions-template`: This is a template that users can use to play around and generate content. To be able to play with complex information without having to build a special editor for it the `abstractions` repo is built around `VS Code` in combination with `Foam` and a set of `Snippets` and guidelines to help to format and manage the content in a particular way.
- `pipmm-cli`: An NPM package that helps to manipulate and compile the `abstractions` repo into the newly defined format, as well as to upload, serve and visualize them.
- `pipmm-client`: A Flutter project to render the contents. `pipmm-cli`  uses it
- `pipmm-server`: A simple Node server that plays the role of a node in the system. `pipmm-cli` uses it
- `docs` (this repo): Most of the conceptual development is being dog fed in several users `abstractions` repositories, the system is currently too unstable serve as documentation itself, although that is the ultimate goal. The purpose of `pipmm-docs` is therefore to be a stable reference for the project in the meantime.


## Installation (WIP)
0. Install base tooling
   1. `Node`(v.) and `NPM`
   2. VSCode
   3. Foam ()
1. `npm install pipmm-cli -g`
2. `git clone ...abstractions`
3. `cd abstractions`
4. `pipmm-cli init`
5. `pipmm-cli watch`
6. Go to `http://localhost:56565/#?localServerPort=45454&websocketsPort=34343&expr=[%22QmXPTSJee8a4uy61vhAs35tM5bXDomSmo1BbTMUVAVbAGJlzfmhs7a%22,[[%22QmXPTSJee8a4uy61vhAs35tM5bXDomSmo1BbTMUVAVbAGJ2lf4dbua%22,%22QmXPTSJee8a4uy61vhAs35tM5bXDomSmo1BbTMUVAVbAGJwf5rbuta%22]]]`