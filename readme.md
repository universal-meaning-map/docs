# Interplanetary mind-map (IPMM)
- [Interplanetary mind-map (IPMM)](#interplanetary-mind-map-ipmm)
  - [Overview](#overview)
  - [Communication efficiency](#communication-efficiency)
  - [Minformation terminology](#minformation-terminology)
  - [Self-describing](#self-describing)
  - [System Topology](#system-topology)
    - [Node](#node)
    - [MID - Mind identifier](#mid---mind-identifier)
    - [Note](#note)
    - [Property](#property)
    - [CID - Content identifier](#cid---content-identifier)
    - [IID - Intent identifier](#iid---intent-identifier)
    - [AREF - Abstraction reference](#aref---abstraction-reference)
  - [FAQ](#faq)
    - [Semantic consensus](#semantic-consensus)
    - [Comparison with the Semantic Web](#comparison-with-the-semantic-web)
    - [Project philosophy](#project-philosophy)
- [Pseudo Interplanetary mind-map (PIPMM)](#pseudo-interplanetary-mind-map-pipmm)
  - [Overview](#overview-1)
  - [Compromises](#compromises)
  - [Repositories](#repositories)
  - [Installation](#installation)

## Overview

The interplanetary mind map is a long term project that aims to explore and build tools and protocols to make digital human-to-human / human-to-self communication more efficient to minimize human conflict and maximize the capacity to understand complex information. It does it by building a protocol that endorses 2 fundamental assumptions:
1. The meaning or understanding of information is unique to each mind, as it is the product of an extremely complex cloud of associations. The word `minformation` is used to make this explicit.
2. To maximize interoperability and understanding of information, digital projections of `minformation` should aim to be `self-describing`. This means that information should not require external context to be understood.

These assumptions force digital information to be structured connected and nested in a different new way. It enables a new paradigm of computation and communication that revolves around the particular ontologies and `abstractions` of each mind allowing to adapt to each person needs, as opposed to subordinating people to the pre-assumptions, bias and incentives of software creators.

## Communication efficiency

Human conflict arises when there is miscommunication: when we lack context when we lack empathy when we misunderstand... If communication aims for a lossless transfer of information we miscommunicate all the time.

Digital protocols are very good at exchanging data in a lossless form, but not good at exchanging `minformation`. 

If we understand `minformation` like a cloud of associations in one person's mind it becomes clear why digital communication is so hard. We are forced to "marshall" this cloud into a "linear" medium (text, voice, video...), and the space and time and language are limited.

A similar thing happens when we try to understand complex information. The tools that we have to distil, transform, visualize and make sense of it do not map our cloud of associations. So, when we read, learn, study... we are constantly "marshalling" and "unmarshalling" information with tools creating an enormous mental overhead.

In both cases, a lot of noise is added and a lot of information is not even expressed due to the limitations of the mediums.

The approach of `Interplanetary mind-map` is to be able to recreate a map of the `mind` in a digital form. With this digital ontology, it becomes easier to make sense of digital information as we remove a lot of the "noise" that comes from using systems that are not adapted to our particular `mind`. While the system is still constrained and will never be able to represent what we have in our heads it can get much closer than the current tools. 

Now, we can share parts of this mind-map with others, so instead of simply using a word to refer to "car", we can share our entire cloud that a car represents, with all the associations that it has with it.

We are enhancing communication efficiency because what we communicate carries "context", as opposed to just exchanging a "sign" that may have a very different meaning by the receiver. 

Instead of being forced to a "linear" medium we now have graphs, and while the consumption of the graph may be linear, it is now possible to explore all its branches to make sense of the differences between the emitter `minformation` and the receiver `minformation`


## Minformation terminology

- `abstraction`: Is the atomic part of `minformation`. Anything that a `mind` can make sense of, can be encapsulated as an `abstraction`. It exists only in a particular `mind` at a given time. It can't ever be expressed nor represented fully. It is dynamic, constantly changing as we add more associations to it.
- `abstraction projection`: Is a representation attempt of an `abstraction`, it is inherently incomplete and distorted. 
- `abstraction intent`: A `abstraction` is dynamic, it can be understood as the state of a concept in a given time for a given mind. The `abstraction intent` is a static container where this concept lives, always pointing to its latest version. Is what we usually refer to in our daily communications.
- `abstraction pointer`: Is what we use to refer to an `abstraction intent`. We do that all the time with symbols and words (signs), these are `abstraction pointers`.

Example:

> Each of us has a different idea of what a car is. There is a cloud of experiences, associations and understandings that conforms to our understanding of a car. This cloud, in a particular moment, for a particular mind is an `abstraction`.
> 
> If I try to explain what a car is to you, I will only be able to express part of the cloud that I have in my head, there are things that I don't remember, there are associations of the car that I have that I'm not aware of, I'm limited on time for what I can express, and even if I could do the above the limits of the language will only be able to communicate part of it. That's why any expression of what a car means to me is just an `abstraction projection`. 
>
> Despite an `abstraction` being not representable and constantly evolving we still can refer to a "car". There is a "container" that we can point at, and therefore does not change, it holds the evolving idea of the car. This container is the `abstraction intent`.
> 
> When we communicate, we use the word "car". This is an `abstraction pointer` to the `abstraction intent` of a car. It doesn't point to the `abstraction` itself as it is only a snapshot in time. An `abstraction intent` can have many `abstraction pointers`, a picture of a car or even a memory can also be `abstraction pointers`


## Self-describing
> Some concepts referenced here are described below at [System Topology](#system-topology)

`Self-describing` in the system is defined as not needing external information/context to be used or understood. This definition should not be read in absolute terms, but as a platonic attribute that `abstraction-projections` should aim for.

`Self-describing` can be understood as a spectrum, where the more `self-describing` an `abstraction-projection` is the more capacity it has for interoperability and understanding (does not have contextual dependencies).

The main mechanism used to achieve that is by nesting `abstraction-projections` (`notes`) inside `abstraction-projections`. This means that any element of a `Note` can in itself be a `Note` allowing for extremely complex nested objects.  Luckily [`IPLD`](https://ipld.io/docs/) perfectly matches the requirements to build these structures.

The reason the word "nesting" is used as opposed to "linking" is because the references in a `note` are assumed to be part of the `note` and not an outside thing. The nested `notes` have a "function" in regards to its super-`note` and they are needed for the super-`note` to be understood. This is very different from the hyperlink pointing to a "web page".


The `self-describing` quality is manifested in multiple ways in the system:

- `Self-describing note`: This is a quality that the author of a `note` should aim for, and is what allows the overall ontology to grow and be coherent. It can't be enforced by the system, but it can be incentivized.
- `Self-describing type`: The "key" of each `note` `property` is nothing but an `abstraction-pointer` to the `type note`. A `type note` is a `note` that contains all the information to be processed by a computer (classic type system), but also the information to be semantically understood by a `mind`. The development of this type-system is one of the critical aspects of the development of the project.
- `Self-describing transforms`: `Transforms` are `notes` that can compute other `notes`. They can be filters, renders, parsers, functions... Being `self-describing` means that they don't have "dependencies". Any code they need must be in the `note`, either directly or in a nested `note`.
- `Self-describing text`: We can enable a system of [transclusions](https://en.wikipedia.org/wiki/Transclusion) where words, paragraphs and other text structures are nothing but the transcluded `properties` of a `note` and at the same time are pointers to that `note`. By having a semantic interface we can guarantee that the transclusion will still make sense in the future. This enables the capacity for each word to be `self-describing` which means that we do not need to rely on the ambiguous definitions of a global dictionary and instead we can create extremely explicit text where a resolution to its meaning can be added progressively. It also means that when writing /(an article for example) the context required to make the point is extremely mitigated, as each concept/word is self-explanatory. This type of text format is currently referred to as `interplanetary-text` and is one of the main focuses of exploration of the project.

## System Topology
> While the main ideas are quite definitive, the specific details and namings still change constantly and should not be taken as specifications. They are for illustrative purposes only.

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
- A `note` aims to represent an `abstraction` as accurately as possible, although is always a best effort.
- A `note` is made of a list of arbitrary lengths of `predicates`. A `predicate` being a quality or attribute of the `abstraction`.
- A `predicate` has the form of a key-value pair. The "key" is the `property` that can be understood as the how/verb/relationship/type...
- A `note` is an [`IPLD`](https://ipld.io/docs/) object that points at other `IPLD` objects.

### Property
- A `property` (key) defines "how" the `note` relates to any other information (value)
- The `property` in itself is a pointer to another `note`, that describes the semantic and type attributes of that `property`. This means that the meaning of how `notes` relate to other `notes` is always given by the users.
- This also means that `properties` can be understood as "global" variables, but the "global" scope is not within a project but truly global.
`Properties` are `self-describing` types that include a semantic and typing interface.

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


## FAQ
### Semantic consensus
How to make any sense of anything if everything is concerning the semantics of a particular `mind` as opposed to an agreed understanding of the meaning of something?

"Agreed understanding" is an illusion and we should acknowledge it by being explicit on its representation, as opposed to embracing a fallacy of shared meaning. 
If there is a "shared meaning" is a partial overlap of fuzzy associations. It is an emergent behaviour, as opposed to an explicit sought one.

### Comparison with the Semantic Web
Certain elements may seem similar to the `Semantic web` (and other similar protocols), but there are very significant differences:

- It does not assume that is possible to find a consensus on all the categories in which information can be related and instead gives the privilege to do so to the user.
- It does not want to be built on top of the existing web technologies, since for the end purpose of the project they are unsafe and inherit too much technical and conceptual debt.
- The system is fundamentally a peer-to-peer or mind-to-mind network, and by embracing it into its protocol design it expects to prevent the actual predominant client-server architecture of the web and generate very different dynamics, such as a strong reputation system, as each mind can be understood as an identity.
- The system has represented many more layers of `minformation` such as the `abstraction intent` or `time` which also create very different dynamics.

### Project philosophy
- The system should aim to serve the particular `minds` of each individual and to enable them to reach the maximum potential as opposed to subordinate people to the system.
- Because of its goals around recreating a fundamental information system, the project has an almost religious relationship around the use of information and therefore should be particularly aware of potentially misaligned incentives E.g., funding, corporate use, mindsets with "current web paradigm", token mechanisms, partnerships...
- Before to move forward to the "final" development is important to have conceptual framework and design. The current strategy is to go back and forth between...
  1. Conceptual design
  2. Proof of concept development
  3. Play, use, experiment
    ... until the conceptual design matches the desired intent. Then stablish a strategy for the development of the protocol.

# Pseudo Interplanetary mind-map (PIPMM)

## Overview
`Pseudo Interplanetary mind-map` is a proof of concept to play, understand and validate the previous assumptions. While the technical part is complex, there are a lesser amount of unknowns than its conceptual counterpart. That means that currently the challenge does not reside in its implementation but understanding and generating a conceptual framework to help to operate with the aforementioned assumptions. `PIPMM`aims to help to generate this conceptual framework by providing a playground to play with.

A big handicap at the current stage is to be able to play with complex information without having to build a special editor for it. To go around that `PIPMM` delegates this to existing tools and paradigmns.

`PIPMM` can be thought as a translator or compiler. It takes a bunch of "old-school" skeuomorphic documents and links as a source and converts them into interconnected [IPLD](https://obsidian.md/) objects and `AREF`s

The source files currently take the form of Markdowns with YAML Front Matter linked with wikilinks. This approach has been choosen in order to be as compatible as possible and therefore leverage the power of existing tools and personal knowledge repositories such as [Foam](https://foambubble.github.io/foam/) with VS Code  or [Obsidian](https://obsidian.md/) (not tested)

## Compromises
> This software is for experimental purposes and is not meant for production or a general audience but for people that already have a significant pre-understanding of the project and want to explore its possibilities.

`PIPMM` is optimized for:
- Replicating the desired information architecture
- Be able to demo and publish what can be done with it
- Experiment with fast iterations focusing on the biggest unknowns
- Live preview of the content produced, specially around `Interplanetary text` and `transclusions`

It is **NOT** optimized for:

- Performance
- Security
- Beauty

Therefore there are many compromizes:
- There are no security checks, the software is quite vulnerable, it is meant to be used in trusted circles.
- Can't reference `Notes` via its `CID`, only `IID`, which means is not possible to point to old versions of an `abstraction`
- Is not possible to reference other people's `notes` only your own (to change soon)
- `Transforms` or `Renders` are hard-coded as oppose to defined in their own abstractions.
- Many cryptographic operations are just emulated.
- Nothing is encrypted. The server stores the `notes` in plain text
- There is no server authentication
- The typing system is extremely simplified and just partially enforced with [IPLD Schemas](https://ipld.io/docs/schemas/) and  hard-coded references.
- No support for images or media
- Web stack is used for fast development


## Repositories
The following repositories compose the project:

- [abstractions-template](https://github.com/interplanetarymindmap/abstractions-template): This is a template that users can use to play around and generate content using VSCode or similar editor
- [pipmm-cli](https://github.com/interplanetarymindmap/pipmm-cli): An NPM package that helps to manipulate and compile the `abstractions` repo into the newly defined format, as well as to upload, serve and visualize them.
- [pipmm-client](https://github.com/interplanetarymindmap/pipmm-client): A Flutter web-app to render the contents. `pipmm-cli`  uses it
- [pipmm-server](https://github.com/interplanetarymindmap/pipmm-server): A simple Node server that plays the role of a node in the system. `pipmm-cli` uses it
- [docs](https://github.com/interplanetarymindmap/docs) (this repo): Most of the conceptual development is being dog fed in several users `abstractions` repositories, the system is currently too unstable to serve as documentation itself, although that is the ultimate goal. The purpose of [docs](https://github.com/interplanetarymindmap/docs) is therefore to be a stable reference for the project in the meantime.



## Installation

Pre-requirements:
- [Node.js](https://nodejs.dev/)
- [VSCodium](https://vscodium.com/) or [Visual Studio Code](https://code.visualstudio.com/)

Install:

1. `git clone git@github.com:interplanetarymindmap/abstractions-template.git`
2. Open `abstractions-template` in VSCode and install the recommended extensions
3. `cd abstractions-template`
4. `npm install pipmm -g`
5. `pipmm init`
6. `pipmm watch`
7. Open `http://localhost:56565/#?websocketsPort=34343&localServerPort=45454&expr=%5B%2212D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,%5B%5B%2212D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%2212D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cl5uz4zaq%22%5D%5D%5D`

