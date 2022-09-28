# Interplanetary mind-map (IPMM)

- [Interplanetary mind-map (IPMM)](#interplanetary-mind-map-ipmm)
    - [Overview](#overview)
        - [Current stage](#current-stage)
    - [Meaning is subjective](#meaning-is-subjective)
        - [Meaning overview](#meaning-overview)
        - [Meaning in communication](#meaning-in-communication)
        - [Meaning in reasoning](#meaning-in-reasoning)
        - [Capturing meaning](#capturing-meaning)
    - [Everything is an abstraction](#everything-is-an-abstraction)
    - [Information should aim to be self-describing](#information-should-aim-to-be-self-describing)
        - [Self-describing data structure](#self-describing-data-structure)
        - [Instances of self-description](#instances-of-self-description)
    - [Technical mapping](#technical-mapping)
        - [Node](#node)
        - [MID - Mind identifier](#mid---mind-identifier)
        - [Note](#note)
        - [Property](#property)
        - [CID - Content identifier](#cid---content-identifier)
        - [IID - Intent identifier](#iid---intent-identifier)
        - [AREF - `Abstraction` reference](#aref---abstraction-reference)
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
- [Get in touch](#get-in-touch)

## Overview

The `Interplanetary mind-map` (`IPMM`) is a [long term project](history.md) that aims to build a system of information that deals with extremely large levels of complexity, unattainable with current software architectures, and consequently increase our reasoning and communication capacities at individual and collective levels.

`IPMM` endorses 3 fundamental assumptions:

1. [Meaning is subjective](#meaning-is-subjective)  
    The `meaning` given to specific `information` set is unique to each mind, as it is the product of an extremely complex cloud of associations. The word `minformation` is used to make this explicit. We need a system that aligns to each subject's `meaning`.
2. [Everything is an abstraction](#everything-is-an-abstraction)  
    The single most fundamental form to manage complexity are `abstractions`. `Abstraction malleability` (facilitating their access, creation, re-use, maintenance and evolution) is fundamental to maximize their quality (the signal-to-noise ratio they can capture for their specific purpose).
3. [Information should aim to be self-describing](#information-should-aim-to-be-self-describing)  
   To capture complexity and maximize interoperability, composability and understanding of information, there can't be external dependencies, `information` should not require external context to be used, computed or understood.

These assumptions force digital `information` to be structured connected and nested in a different new way. It enables a new paradigm of computation and communication that revolves around the particular ontologies and `abstractions` (language) of each mind allowing to adapt to each person needs, as opposed to subordinating people to the pre-assumptions, bias and incentives of software creators.

### Current stage

Currently, `Interplanetary mind-map` aims to create a conceptual framework that is representative of the nature of `meaning` and the flow of `minformation` to later map it into a technical implementation that can maximize its utility in most software domains.

[Pseudo-Interplanetary mind-map](#pseudo-interplanetary-mind-map-pipmm) is a prototype where the system fundamental assumptions and constructs are being explored.

On terminology:
> `IPMM` uses a lot of unique terminology and a particular narrowed meaning in certain words, this is necessary in order to make explicit certain subtleties within the framework. For a new reader, it may be confusing to read. In the future, likely, the terminology can be simplified, but at the current stage, while developing the conceptual, framework is necessary to optimize for the semantic-clarity of those who work with it.

> Many references of this documentation are pointing to [my personal instance](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22]]]&) (Xavi's) of `PIPMM`, where more up-to-date and extensive definitions can be found.

## Meaning is subjective

### Meaning overview

Each word carries `meaning`. While a dictionary may define a word based on its used within a culture, each of us gives a significant different meaning to them. Every experience that we have around an object/word/concept shapes its meaning.

While the grammar of a language allow us to represent it in a "standardized" way (information), its interpretation will always be subjective due to our differing associations (minformation).

- [information](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3czsjxwj5q%22]]]&): `Data` that is aimed to be interpreted.

- [minformation](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cxhm6fu5a%22]]]&): The product of `data` that has been interpreted by a particular subject. A completely subjective experience.

- [meaning](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3chp6gtfwq%22]]]&): Is all the `minformation` that a given subject needs to relate and to create certainty around a given object. Is complex and fuzzy, only exists inside a subject's body-mind system and can't be communicated in a lossless form, as its the product of its life experience.

Example:
> An article on a newspaper is `information`. It is `data` sitting there awaiting to be read.
> When someone reads the text, the `information` becomes subjective based on the subject's political views, preexisting knowledge, current emotional state, authorship of the article, all the associations with each word in the text... The `data` is now `minformation` instead. The product of the `minformation` with all the associations that had conditioned its interpretation conforms the `meaning` that subject gives to that article.

### Meaning in communication

Natural language requires to have a significant degree of [shared meaning](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cgwyycz5q%22]]]&) between its users, otherwise communication wouldn't be possible.

Reading the same words may have the effect of seeming that seem that two subjects will understand the same thing. This [fallacy of shared meaning](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cgpk6ijkq%22]]]&) is the root cause of most communication issues.

`Interplanetary mind-map` enables to make explicit the difference in `meaning` between subjects, minimizing miscommunication and conflict by providing tools to map each-other's `meaning`.

### Meaning in reasoning

Having `shared meaning` is a virtue for communication but its a huge drawback for thinking.

The quality of our reasoning is directly tight to the quality of our `abstractions`. The use of "common language" `abstractions` constrains the creation and evolution of our own unique `abstractions` that can better fullfil our particular needs.

With a system that supports us in expressing our particular `meaning` around a concept, we become in in full control of our own particular `abstractions`, better capturing our reality and enhancing our reasoning.

Similarly, any piece of software uses the same set of `abstractions` for all its user base (user interface, functions, options, visualizations...). This translates into only allowing its users to transform, compute, visualize and make sense of information based on the scenarios and needs that the software creators have considered.

`Interplanetary mind-map` recognizes that humans operate with `minformation` and not `information`, and to maximize our particular virtues, the system should be build around our particular `meaning`.

### Capturing meaning

`IPMM` can be understood as a "best effort" to maximize the digital caption of `meaning`.  The following are what `IPMM` considered its "primitives", and aims to recreate digitally.

- [meaning unit](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3chp6gtfwq%22]]]&): It is meaning of a given object at a given time by a given subject.
- [meaning unit projection](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdeplwy4q%22]]]&): Is a representation attempt of a `meaning unit`, it is inherently incomplete and distorted, usually expressed in the form of language.
- [intended meaning](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cz6zpqnbq%22]]]&): It is the `meaning unit` that a `meaning projection` aims to express.
- [meaning unit pointer](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c6ardl2ma%22]]]&): A sign, a word, a set of data that when interpreted makes the subject recall a specific `meaning-unit`.
- [meaning unit continuity essence](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cqkp7a4ja%22]]]&): The `minformation` set of a `meaning-unit` that does not change and allows for the `meaning-unit` to evolve while keep being referred by its `meaning unit pointers`.

Example:

> Each person has a different `meaning` for what car is. While a lot of this `meaning` is shared, there is a cloud of experiences, associations, emotions, knowledge, understandings... that conforms to our particular understanding of a car. This cloud, in a particular moment, for a particular mind is a `meaning unit`.
>
> If I try to explain what a car means to me, I will aim to express its `intended meaning` although I only will be able to express part of the cloud that I have in my head, there are things that I don't remember, there are associations of the car that I have that I'm not aware of, I'm limited on time for what I can express, and even if I could do the above the limits of the language will only be able to communicate part of it. That's why any expression of what a car means to me is just an `meaning unit projection`.
>
> Despite a `meaning unit` not being representable and constantly evolving we still can refer to a "car". There is an essential set of `minformation` of what constitutes a car that does not change, the `meaning unit continuity essence`.
>
> When we see a car or read the word "car", we recall the `meaning unit` of a car. Both, the image of a car and the word "car" are `meaning unit pointers`.

## Everything is an abstraction

We can't directly perceive reality. Our sensory receptors filter specific ranges of light, sound, touch... corresponding organs may do further processing, up until we can interpret information with our conscious and unconscious minds. At every step in that path, `minformation` is reduced and transformed in the form of `abstractions`.

- [Abstraction](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cnnjsotia%22]]]&): An `abstraction` is the expression of a pattern of information that captures the essence that allows it to better serve in the specific context where is used. An `abstraction` is the product of computation, where input information is reduced, transformed and re-grouped to increase the signal-to-noise enabling to to deal with greater complexity.

Example:
> We are constantly sensing light and sound, but not all of its is perceived equal. We ignore some signals and enhance others (improving signal-to-noise ratio). We can isolate the visual shape and the sound of a "car" within it surroundings recognizing it as a 3D object (improving signal-to-noise ratio). Each signal-to-noise ratio improvement produces an abstraction.

Humans are unique in their capacity to create abstractions that are not only perceptual and
natural language is its higher form.

A `word` is short and simple but its pointing to huge amounts of `meaning` without having to directly handle the complexity that they represent.

By composing clauses made of `words` we can capture even larger amount of complexity that better describe the meaningful elements of reality . We can wrap these clauses as new `abstractions` to further compress complexity (ideas, models, frameworks...). This nesting process can continue indefinitely,  creating higher level `abstractions` without no upper bound.

Language can be understood as a formal system of `abstraction` composition, that produces higher-level `abstractions` as a result.

Example:
> A "car" is a 3D object with specific shape and sound, composed of many parts, that uses complex physics and technology to function. By using the word "car" we can relate to it without having to relate to its complexity.
> A clause like "a Tesla", is in itself a higher level abstraction, representing more complexity than the word "car" on its own.

Language and words are not the only systems we have to generate `abstractions`. Anything that we can conceive and have some "boundaries" can be understood as an `abstraction`.

A computation is essentially the process of generating better `abstractions`, simplifying an aspect of reality to facilitate our relationship with it. But the  computation in itself can also be conceive as `abstraction` that transforms `abstractions`, making  code, functions, apps or machine learning models `abstractions` as well.

In `IPMM` anything that has `meaning` can be expressed as a `meaning unit projection` and understood as an `abstraction`, which means that everything can have its digital representation. The result is our personal language, a map of `meaning` of our particular mind.

Facilitating a coherent creation, evolution, re-use, and maintenance of `abstractions`, that map into how we think, is what enables better reasoning and communication, and the goal of `IPMM` is to support this process.

## Information should aim to be self-describing

`Self-describing` in `IPMM` is defined as not needing external information/context to be used or understood. This definition should not be read in absolute terms, but as a platonic attribute that any `abstraction` should aim for.

`Self-describing` can be understood as a spectrum, where the more `self-describing` an `abstraction` of a `meaning unit projection` is, the more capacity to be interoperable and understood is (does not have contextual dependencies).

`IPMM` architecture is designed so that the `meaning unit pointer` (mostly but not exclusively "words")  can't be separated from the `meaning` or `computation` given by the particular `mind` that created them. Every piece of `information` in the system carries all what is necessary to be computed or understood within itself.

### Self-describing data structure

An instance of a `meaning unit projection` within the IPMM framework is called a `note`.

The main mechanism used to achieve `self-description` is by nesting `notes` within `notes`. This means that any element of a `note` can in itself be a `note` allowing for extremely complex nested objects. [`IPLD`](https://ipld.io/docs/) is used to represent this data structures.

The reason the word "nesting" is used as opposed to "linking" is because the references in a `note` are assumed to be part of the `note` and not an outside thing. The nested `notes` are necessary to contribute to the `meaning` for the super-`note` to be understood . This is very different from the hyperlink pointing to a "web page".

> A simple analogy that may help to understand the data representation of the `self-describing` quality would be to imagine it as a "[Merkle Tree](https://en.wikipedia.org/wiki/Merkle_tree)" of `meaning`, where each node is a `meaning unit projection` made of other `meaning units projection`s

### Instances of self-description

The `self-describing` quality is manifested in multiple ways in the system:

- `Self-describing note`: This is a quality that the author of a `note` should aim for, and is what allows the overall ontology to grow and be coherent. It can't be enforced by the system, but it can be incentivized.
- `Self-describing type`: The "key" of each `note` `property` is nothing but an `meaning unit pointer` to the `type note`. A `type note` is a `note` that contains all the information to be processed by a computer (classic type system), but also the information to be semantically understood by a `mind`. The development of this type-system is one of the critical aspects of the development of the project.
- `Self-describing transforms`: `Transforms` are `notes` that can compute other `notes`. They can be filters, renders, parsers, functions... Being `self-describing` means that they don't have "dependencies". Any code they need must be within the `note`, either directly or as a nested `note`.
- `Self-describing text`: We can enable a system of [transclusions](https://en.wikipedia.org/wiki/Transclusion) where words, paragraphs and other text structures are nothing but the transcluded `properties` of a `note` and at the same time are pointers to that `note`. By having a semantic interface we can guarantee that the transclusion will still make sense in the future. This enables the capacity for each word to be `self-describing` which means that we do not need to rely on the ambiguous definitions of a global dictionary and instead we can create extremely explicit text where a resolution to its meaning can be added progressively. It also means that when writing (an article for example) the context required to make the point is extremely mitigated, as each concept/word can be self-explanatory. This type of text format is currently referred to as [interplanetary-text](interplanetary-text.md) and is one of the main focuses of exploration of the project as is where semantics meet the classical type system or where the `mind` meets the computer.

## Technical mapping

> While the main ideas are quite definitive, the specific details and namings still change constantly and should not be taken as specifications. They are for illustrative purposes only.

`IPMM` is fundamentally attempting to mimic the "analog" flow of `minformation` in a digital form. The following is a mapping of the previously described terminology to its digital counterparts.

### Node

- The origin of `minformation` is on each mind.
- A `mind` is represented in the system as `node` in a peer-to-peer network.
- A `mind` is the author of a `meaning unit projection`s, referred to as `notes`.
- Is not possible for a `note` to not have a `mind` behind.
- A `node` is the end-point to target in order to get updates of anything that is not our own `mind`.

### MID - Mind identifier

- The `MID` or `mind identifier` is a unique identifier derived from a private key and used to identify any given `mind`/`node`.
- Any request concerning a given `mind` will have to be handled by its respective `node` and to uniquely identify the `node` in the network we use the `MID`.
- `MID`s allow for global absolute references to any `note`
- A `MID` looks like this: `QmXPTSJee8a4uy61vhAs35tM5bXDomSmo1BbTMUVAVbAGJ`

### Note

- An instance of a `meaning unit projection`.
- A `note` is made of a list of arbitrary lengths of `predicates` . A `predicate` being another `meaning unit projection` representing quality or attribute of the `meaning unit`.
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

- While the `CID` allows us to reference a snapshot of a `meaning unit`, we still need a way to reference the current and evolving idea of the ever-changing `intended meaning`.
- The `IID`is the identifier of the current `intended meaning`.
- An `IID` is always mapped to the latest `CID` of a given `meaning unit`.
- An `IID`is composed of a `MID` and the `LIID` (`Local Intent identifier`)`.
- An  `IID` looks like this: `QmXPTSJee8a4uy61vhAs35tM5bXDomSmo1BbTMUVAVbAGJsdqwz4ea`, the 46 first characters representing the `MID` and the latest 8 representing the `LIID`  
![Intent identifier mapping timeline](images/abstraction_timeline.png)

### AREF - `Abstraction` reference

- The `AREF` is a text expression that allows us to point to any element of the system.
- Is the equivalent of what `hyperlink` is to the `hypertext`
- It can have several forms depending on if is pointing to an `IID`, a `CID`, a specific property or object within a `note`, or other more advance constructs:  `IID/PID/IPLD_path` or `CID/PID/IPLD_path`
- If the `AREF` is pointing to an `IID` the corresponding `node` will resolve it to latest `CID`, and then we can resolve to its matching `note`
- A `AREF`may look like that `QmXPTSJee8a4uy61vhAs35tM5bXDomSmo1BbTMUVAVbAGJz6zpqnbq/QmXPTSJee8a4uy61vhAs35tM5bXDomSmo1BbTMUVAVbAGJqz3qlkca`

## FAQ

### Semantic consensus

How to make any sense of anything if everything is in relation of the meaning of a particular `mind` as opposed to an agreed understanding of the meaning of something?

[Shared meaning](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cgwyycz5q%22]]]&
) is only partial and we should acknowledge it by being explicit on its representation, as opposed to embracing a [fallacy of shared meaning](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cgpk6ijkq%22]]]&).
If there is "shared meaning",  it is a partial overlap of fuzzy associations.

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

`Pseudo Interplanetary mind-map` is a proof of concept to play, understand and validate the current assumptions. While the technical part is complex, there are a lesser amount of unknowns than its conceptual counterpart. That means that currently the challenge does not reside in its implementation but understanding and generating a conceptual framework to help to operate with the aforementioned assumptions. `PIPMM` aims to help to generate this conceptual framework by providing a playground to play with.

A big handicap at the current stage is to be able to play with complex information without having to build a special editor for it. `PIPMM` makes use of existing tools to work around that.

`PIPMM` can be thought as a translator or compiler. It takes a set of markdown files with wikilinks as a source and converts them into interconnected [`IPLD`](https://ipld.io/docs/)  objects and `AREF`s

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
- Can't reference `Notes` via its `CID`, only `IID`, which means is not possible to point to old versions of an abstraction
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
- [docs](https://github.com/interplanetarymindmap/docs) (this repo): Current conceptual development its been done using PIPMM itself and partially accessible on the [prototype site](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cdzbeskxq%22]]]&). Since the system is currently too unstable to serve as documentation source, the purpose of [docs](https://github.com/interplanetarymindmap/docs) is to be a stable documentation reference (although highly incomplete) in the meantime.

## Installation

Pre-requirements:
- [Node.js](https://nodejs.dev/)
- [VSCodium](https://vscodium.com/) or [Visual Studio Code](https://code.visualstudio.com/) or [Obsidian](https://obsidian.md/)

Install:

1. `git clone git@github.com:interplanetarymindmap/abstractions-template.git`
2. Open `abstractions-template` in VSCode and install the recommended extensions ([Markdown Memo](https://marketplace.visualstudio.com/items?itemName=svsool.markdown-memo) and [Markdown Links](https://marketplace.visualstudio.com/items?itemName=tchayen.markdown-links) )
3. `cd`abstractions`-template`
4. `npm install pipmm -g`
5. `pipmm init`
6. `pipmm watch`
7. Open `http://localhost:56565/#?websocketsPort=34343&localServerPort=45454&expr=%5B%2212D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,%5B%5B%2212D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%2212D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cl5uz4zaq%22%5D%5D%5D`

## Exploration

The [Interplanetary-text](interplanetary-text.md) currently contains a detailed explanation of how all the above translates when applied to text

# Get in touch

`Interplanetary mind-map` is in constant evolution and growth and requires input from many disciplines. If you've got this far reading [I would love to talk to you](https://xavivives.com/#?expr=[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3clzfmhs7a%22,[[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cwx4lcc2a%22],[%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c2lf4dbua%22,%22i12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cbeeppy5a%22]]]&). :)
