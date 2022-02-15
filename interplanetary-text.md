# Interplanetary text

`Interplanetary text` is one of the infinite constructs that are possible with `IPMM` and responds to:
> What does text look like under `IPMM` assumptions of `self-describing` `minformation`?


Within `IPMM`'s jargon, words are `abstraction-pointers`. They lead our minds into a pre-existing idea of what that the word conveys, different for each of us.
In a digital context though, the author could point the word to the exact `abstraction-projection` that is referring to. In other words... we can embed meaning and context within the word itself.

This enables:
- Transclusion: We can embed text inside text recursively without loosing meaning
- Single source of truth / non-duplication of information. There is no longer need for "copy-paste"
- Traceability: Each `note` has a `mind` behind, therefore each word or text element is "owned" by someone
- Progressively non-ambiguous: We can keep adding resolution to make the text less and less ambiguous over time as each word can carry context.
- Text history: We can navigate through time

## Example

Imagine I express the following:
```
The car is blue.
```

To add resolution for what I'm talking about I could generate `notes` that represent my `abstraction` of "car" and my `abstraction` of "blue".

In this case, the `notes` are made of two predicates that use the following `properties` (The properties live on their respective `notes` but to make it easier here we just use their `intent-identifier`):


### The "name" property
`IID`: 12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cqz3qlkca

Represents the idea of "name". A human-readable identifier that can be used as abstraction-reference in inline text.

### The "view" property
`IID`: 12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cnwyia5xq

Represents the idea of "view" or "perspective" about something.


### The "car" note

`IID`: 12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3civpeskra

```JSON
{
    "12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cqz3qlkca": "car",
    "12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cnwyia5xq": [
        "A Renault Scenic that my dad purchased.\nMy dad gave it to me. It was my first car\nIt learned to drive with that car."
  ],
}
```

### The "blue" note**
`IID`: 12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c4snxjotq
```json
{
  "12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cqz3qlkca": "Blue",
  "12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cnwyia5xq": [
    "A sky blue\n#0CE1F4"
  ],
}
```

### The `interplanetary-text` expression of "The car is blue.":

```JSON
[
    "The ",
    "[\"12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3civpeskra/12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cqz3qlkca\"]",
    " is ",
    "[\"12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3c4snxjotq/12D3KooWBSEYV1cK821KKdfVTHZc3gKaGkCQXjgoQotUDVYAxr3cqz3qlkca\"]",
    "."
]
```

## Implementation and execution

Currently `interplanetary-text` is represented as a JSON array that combines `abstraction-references` (`aref`) with normal text to make it easy to parse.
In the example, there are two `arefs`. The first one points to the "name" property of the "car" note. The second one points to the "name" property of the "blue" note.
The `view` property, where we give the extra context of what "car" and "blue" mean to me is not in "use" in the `interplanetary text` itself, but they are also none-separable from it. This means that the context is there and is up to the renderer and the user to decide how to "inspect" each note.

For the runtime to render the expression in the example it will go through the following steps:
1. Parse the `interplanetary-text` expression and obtain the `abstraction-references`
2. Parse the `abstraction-references` and obtain the `MID` and `LIID` of the transcluded notes ("car" and "blue") as well as for the transcluded properties ("name" and "view")
3. For each note reference; request to its respective `MID` the `CID` for the corresponding `IID`
4. Once the `CID`is received we can request its content to the IPFS network or to the MID itself
5. With the content received we can look up the `properties` that the `aref` is pointing at.
6. The runtime can now render the text by replacing each `abstraction-reference` with its respective transcluded text.
