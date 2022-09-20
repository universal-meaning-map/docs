# Interplanetary mind-map (IPMM)

> This document aims to be a stable reference to the project. Its current development though its been developed using a prototype of the project itself. You can find some of the references here update at the [prototype site](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22]]]&)

- [Interplanetary mind-map (IPMM)](#interplanetary-mind-map-ipmm)
    - [Overview](#overview)
    - [Communication efficiency](#communication-efficiency)
    - [Terminology](#terminology)
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
    - [Exploration](#exploration)

## Overview

The interplanetary mind map is a [long term project](history.md) that aims to explore and build tools and protocols to make digital human-to-human / human-to-self communication more efficient to minimize human conflict and maximize the capacity to understand complex information. It does it by building a protocol that endorses 2 fundamental assumptions:

1. The meaning of any given information is unique to each mind, as it is the product of an extremely complex cloud of associations. The word `minformation` is used to make this explicit.
2. To maximize interoperability and understanding of information, digital projections of `minformation` should aim to be `self-describing`. This means that information should not require external context to be understood.

These assumptions force digital information to be structured connected and nested in a different new way. It enables a new paradigm of computation and communication that revolves around the particular ontologies and `abstractions` of each mind allowing to adapt to each person needs, as opposed to subordinating people to the pre-assumptions, bias and incentives of software creators.

The `Interplanetary mind-map` aims to create a conceptual framework that is representative of the natural flow of `minformation` to later be mapped into a technical implementation.

## Communication efficiency

Human conflict arises when there is miscommunication: when we lack context when we lack empathy when we misunderstand... If communication aims for a lossless transfer of information we miscommunicate all the time.

Digital protocols are very good at exchanging data in a lossless form, but not good at exchanging `minformation`.

If we understand `minformation` like a cloud of associations in one person's mind it becomes clear why digital communication is so hard. We are forced to "marshall" this cloud into a "linear" medium (text, voice, video...), and the space and time and language are limited.

A similar thing happens when we try to understand complex information. The tools that we have to distill, transform, visualize and make sense of it do not map our cloud of associations. So, when we read, learn, study... we are constantly "marshalling" and "unmarshalling" information with tools creating an enormous mental overhead.

In both cases, a lot of noise is added and a lot of information is not even expressed due to the limitations of the mediums.

The approach of `Interplanetary mind-map` is to be able to recreate a map of the `mind` in a digital form. With this digital ontology, it becomes easier to make sense of digital information as we remove a lot of the "noise" that comes from using systems that are not adapted to our particular `mind`. While the system is still constrained and will never be able to represent what we have in our heads it can get much closer than the current tools. With that, we can share parts of this mind-map with others, so instead of simply using a word to refer to "car", we can share the entire cloud of what a car represents us with its associations.

We are enhancing communication efficiency because what we communicate carries "context", as opposed to just exchanging a "sign" that may have a very different meaning by the receiver.

Instead of being forced to a "linear" medium we now have graphs, and while the consumption of the graph may be linear, it is now possible to explore all its branches to make sense of the differences between the emitter `minformation` and the receiver `minformation`

## Terminology

> IPMM uses a lot of unique terminology and a particular narrowed meaning in certain words, this is necessary in order to make explicit certain subtleties within the framework. For a new reader, it may be confusing to read. In the future likely the terminology can be simplified, but at the current stage, while developing the conceptual, framework is necessary to optimize for the semantic-clarity of those who work with it. Use to the links for an expanded and updated definitions.

- [information](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3czsjxwj5q%22]]]&): `data` that is aimed to be interpreted.

- [minformation](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cxhm6fu5a%22]]]&): The product of `data` that has been interpreted by a particular subject. A completely subjective experience.

Example:
> A text on a newspaper is `information`. It is `data` sitting there awaiting to be read.
> When someone reads the text, it will interpret it its own way, depending on its political views, its current emotional state, the current context it is in, and all its past associations with each word in the text. The product of the interpretation of this text is `minformation`


- [meaning](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3chp6gtfwq%22]]]&) : Is all the `minformation` that a given subject needs to relate and to create certainty around a given object. Is complex and fuzzy, only exists inside a subject's body-mind system and can't be communicated in a lossless form.
- [meaning unit](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3chp6gtfwq%22]]]&): It is meaning of a given object at a given time by a given subject.
- [meaning unit projection](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdeplwy4q%22]]]&): Is a representation attempt of an `meaning unit`, it is inherently incomplete and distorted, usually expressed in the form of language.
- [intended meaning](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cz6zpqnbq%22]]]&): It is the `meaning unit` that a `meaning projection` aims to express.
- [meaning unit pointer](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c6ardl2ma%22]]]&): A sign, a set of data that when interpreted makes the subject recall a specific `meaning-unit`
- [meaning unit continuity essence](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cqkp7a4ja%22]]]&): The `minformation` set of a `meaning-unit` that does not change and allows for the `meaning-unit` to evolve while keep being referred by its `meaning unit pointers`.

Example:

> Each person has a different `meaning` for what car is. While a lot of this `meaning` is shared, there is a cloud of experiences, associations, emotions, knowledge, understandings... that conforms to our particular understanding of a car. This cloud, in a particular moment, for a particular mind is a `meaning unit`.
>
> If I try to explain what a car means to you, I will aim to express its `intended meaning` although I only will be able to express part of the cloud that I have in my head, there are things that I don't remember, there are associations of the car that I have that I'm not aware of, I'm limited on time for what I can express, and even if I could do the above the limits of the language will only be able to communicate part of it. That's why any expression of what a car means to me is just an `meaning unit projection`.
>
> Despite a `meaning unit` not being representable and constantly evolving we still can refer to a "car". There is an essential set of `minformation` of what constitutes a car that does not change, the `meaning unit continuity essence`.
>
> When we see a car or read the word "car", we recall the `meaning unit` of a car. Both, the image of a car and the word "car" are `meaning unit pointers`.

## Self-describing

> Some concepts referenced here are described below at [System Topology](#system-topology)

`Self-describing` in the system is defined as not needing external information/context to be used or understood. This definition should not be read in absolute terms, but as a platonic attribute that `meaning unit projection`s should aim for.

`Self-describing` can be understood as a spectrum, where the more `self-describing` a `meaning unit projection` is the more capacity to be interoperable and understood is (does not have contextual dependencies).

An instance of a `meaning unit projection` within the IPMM framework is called a `note`.

The main mechanism used to achieve `self-description` is by nesting `note`s within `note`s. This means that any element of a `note` can in itself be a `note` allowing for extremely complex nested objects. [`IPLD`](https://ipld.io/docs/) is used to represent this data structures.

The reason the word "nesting" is used as opposed to "linking" is because the references in a `note` are assumed to be part of the `note` and not an outside thing. The nested `notes` have a "function" or a relationship with a quality in regards to its super-`note` and they are needed for the super-`note` to be understood. This is very different from the hyperlink pointing to a "web page".

The `self-describing` quality is manifested in multiple ways in the system:

- `Self-describing note`: This is a quality that the author of a `note` should aim for, and is what allows the overall ontology to grow and be coherent. It can't be enforced by the system, but it can be incentivized.
- `Self-describing type`: The "key" of each `note` `property` is nothing but an `meaning unit pointer` to the `type note`. A `type note` is a `note` that contains all the information to be processed by a computer (classic type system), but also the information to be semantically understood by a `mind`. The development of this type-system is one of the critical aspects of the development of the project.
- `Self-describing transforms`: `Transforms` are `notes` that can compute other `notes`. They can be filters, renders, parsers, functions... Being `self-describing` means that they don't have "dependencies". Any code they need must be within the `note`, either directly or in a nested `note`.
- `Self-describing text`: We can enable a system of [transclusions](https://en.wikipedia.org/wiki/Transclusion) where words, paragraphs and other text structures are nothing but the transcluded `properties` of a `note` and at the same time are pointers to that `note`. By having a semantic interface we can guarantee that the transclusion will still make sense in the future. This enables the capacity for each word to be `self-describing` which means that we do not need to rely on the ambiguous definitions of a global dictionary and instead we can create extremely explicit text where a resolution to its meaning can be added progressively. It also means that when writing (an article for example) the context required to make the point is extremely mitigated, as each concept/word can be self-explanatory. This type of text format is currently referred to as [interplanetary-text](interplanetary-text.md) and is one of the main focuses of exploration of the project as is where semantics meet the classical type system or where the `mind` meets the computer.

## System Topology

> While the main ideas are quite definitive, the specific details and namings still change constantly and should not be taken as specifications. They are for illustrative purposes only.

IPMM ins fundamentally attempting to mimic the "analog" flow of `minformation` in a digital form. The following is a mapping of the concepts described in [terminology](#terminology) to its digital counterparts.

### Node

- The origin of `minformation` is on each mind, a `mind` is represented in the system as `node` in a peer-to-peer network.
- A `mind` is the author of the `meaning unit projection`s, referred to as `notes`.
- A `node` is what we need to talk to if we want to know its latest updates.

### MID - Mind identifier

- The `MID` or `mind identifier` is a unique identifier derived from a private key and used to identify any given `mind`/`node`.
- Any request concerning a given `mind` will have to be handled by its respective `node` and to uniquely identify the `node` in the network we use the `MID`.
- A `MID` looks like this: `QmXPTSJee8a4uy61vhAs35tM5bXDomSmo1BbTMUVAVbAGJ`

### Note

- A set of `meaning unit projection`s attempting to represent a `meaning unit` as accurately as possible, although is always a best effort.
- A `note` is made of a list of arbitrary lengths of `predicates`. A `predicate` being a quality or attribute of the `meaning unit`.
- A `predicate` has the form of a key-value pair. The "key" is the `property` that can be understood as the how/verb/relationship/type...
- A `note` is an [`IPLD`](https://ipld.io/docs/) object.

### Property

- A `property` (key) defines "how" the `note` relates to any other information (value)
- The `property` in itself is a pointer to another `note`, that describes the semantic and type attributes of that `property`. This means that the meaning of how `notes` relate to other `notes` is always given by the users.
- This also means that `properties` can be understood as "global" variables, but the "global" scope is not within a project but truly global.
`Properties` are `self-describing` types that include a semantic and typing interface.

### CID - Content identifier

- At any given time, a `note` is represented by a [`CID`](https://github.com/multiformats/cid).
- A `CID` is a cryptographic hash of the `IPLD` object of a `note`.
- A `CID`is an immutable reference to an `meaning unit projection` as that `meaning unit projection` existed only in that particular moment in time.
- A CID looks like this: `baguqeeragkrzqs7df67d2qiwedqw56glsmwrssjhsp25mujxx5vdbu5yqbzq`

### IID - Intent identifier

- While the `CID` allows us to reference a snapshot of a `meaning unit`, we still need a way to reference the current and evolving idea, the `intended meaning`.
- The `IID`is the identifier of the current `intended meaning`.
- An `IID` is always mapped to the latest `CID` of a given `meaning unit`.
- An `IID`is composed of a `MID` and the `LIID` (`Local Intent identifier`)`.
- An  `IID` looks like this: `QmXPTSJee8a4uy61vhAs35tM5bXDomSmo1BbTMUVAVbAGJsdqwz4ea`, the 46 first characters representing the `MID` and the latest 8 representing the `LIID`  
![Intent identifier mapping timeline](images/abstraction_timeline.png)

### AREF - Abstraction reference

- The `AREF` is a text expression that allows us to point to any element of the system.
- Is the equivalent of what `hyperlink` is to the `hypertext`
- It can have several forms depending on if is pointing to an `IID`or a `CID`, or if we want to be more precise and point to a specific property or object within a `note`: `IID/PID/IPLD_path` or `CID/PID/IPLD_path`
- If the `AREF` is pointing to an `IID` the corresponding `node` will resolve it to latest `CID`, and then we can resolve to its matching `note`
- A `AREF`may look like that `QmXPTSJee8a4uy61vhAs35tM5bXDomSmo1BbTMUVAVbAGJz6zpqnbq/QmXPTSJee8a4uy61vhAs35tM5bXDomSmo1BbTMUVAVbAGJqz3qlkca`

## FAQ

### Semantic consensus

How to make any sense of anything if everything is in relation of the meaning of a particular `mind` as opposed to an agreed understanding of the meaning of something?

"[Shared meaning](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cgwyycz5q%22]]]&
)" is only partial and we should acknowledge it by being explicit on its representation, as opposed to embracing a [fallacy of shared meaning](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cgpk6ijkq%22]]]&).
If there is a "shared meaning" is a partial overlap of fuzzy associations. It is an emergent behavior, as opposed to an explicit sought one.

### Comparison with the Semantic Web

Certain elements may seem similar to the `Semantic web` (and other similar protocols), but there are very significant differences:

- It does not assume that is possible to find a consensus on all the categories in which information can be related and instead gives the privilege to do so to the user.
- It does not want to be built on top of the existing web technologies, since for the end purpose of the project they are unsafe and inherit too much technical and conceptual debt.
- The system is fundamentally a peer-to-peer or mind-to-mind network, and by embracing it into its protocol design it expects to prevent the actual predominant client-server architecture of the web and generate very different dynamics, such as a strong reputation system, as each mind can be understood as an identity.
- The system has represented many more layers of `minformation` such as the `intended meaning` or `time` which also create very different dynamics.

### Project philosophy

- The system should aim to serve the particular `minds` of each individual and to enable them to reach the maximum potential as opposed to subordinate people to the system.
- Because of its goals around recreating a fundamental information system, the project has an almost religious relationship around the use of information and therefore should be particularly aware of potentially misaligned incentives E.g. funding, corporate use, mindsets with "current web paradigm", token mechanisms, partnerships...
- Before moving forward towards a more "final" development is important to have conceptual framework and design. Most projects have a bias towards implementation, here the bias is towards its design. The current strategy is to go back and forth between...
  1. Conceptual design
  2. Proof of concept development
  3. Play, use, experiment
    ... until the conceptual design matches the desired intent. Then stablish a strategy for the development of the protocol.

# Pseudo Interplanetary mind-map (PIPMM)

## Overview

`Pseudo Interplanetary mind-map` is a proof of concept to play, understand and validate the previous assumptions. While the technical part is complex, there are a lesser amount of unknowns than its conceptual counterpart. That means that currently the challenge does not reside in its implementation but understanding and generating a conceptual framework to help to operate with the aforementioned assumptions. `PIPMM` aims to help to generate this conceptual framework by providing a playground to play with.

A big handicap at the current stage is to be able to play with complex information without having to build a special editor for it. To go around that `PIPMM` delegates this to existing tools and paradigms.

`PIPMM` can be thought as a translator or compiler. It takes a bunch of "old-school" skeuomorphic documents and links as a source and converts them into interconnected  [`IPLD`](https://ipld.io/docs/)  objects and `AREF`s

The source files currently take the form of Markdowns with YAML Front Matter linked with wikilinks. This approach has been chosen in order to be as compatible as possible and therefore leverage the power of existing tools and personal knowledge repositories such as VS Code or [Obsidian](https://obsidian.md/).

## Compromises

> This software is for experimental purposes and is not meant for production or a general audience but for people that already have a significant pre-understanding of the project and want to explore its possibilities.

`PIPMM` is optimized for:
- Replicating the desired information architecture
- Be able to demo and publish what can be done with it
- Experiment with fast iterations focusing on the biggest unknowns
- Live preview of the content produced, specially around [Interplanetary-text](interplanetary-text.md) and `transclusions`

It is **NOT** optimized for:

- Performance
- Security
- Beauty

Therefore there are many compromises:
- There are no security checks, the software is quite vulnerable, it is meant to be used in trusted circles.
- Can't reference `Notes` via its `CID`, only `IID`, which means is not possible to point to old versions of an `abstraction`
- Is not possible to reference other people's `notes` only your own (to change soon)
- `Transforms` or `Renders` are hard-coded as oppose to defined in their own `notes`.
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
- [VSCodium](https://vscodium.com/) or [Visual Studio Code](https://code.visualstudio.com/) or [Obsidian](https://obsidian.md/)

Install:

1. `git clone git@github.com:interplanetarymindmap/abstractions-template.git`
2. Open `abstractions-template` in VSCode and install the recommended extensions ([Markdown Memo](https://marketplace.visualstudio.com/items?itemName=svsool.markdown-memo) and [Markdown Links](https://marketplace.visualstudio.com/items?itemName=tchayen.markdown-links) )
3. `cd abstractions-template`
4. `npm install pipmm -g`
5. `pipmm init`
6. `pipmm watch`
7. Open `http://localhost:56565/#?websocketsPort=34343&localServerPort=45454&expr=%5B%2212D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,%5B%5B%2212D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%2212D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cl5uz4zaq%22%5D%5D%5D`

## Exploration

The [Interplanetary-text](interplanetary-text.md) currently contains a detailed explanation of how all the above translates when applied to text
