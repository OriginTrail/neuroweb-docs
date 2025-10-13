# JSON-LD tutorial

In this tutorial, you will learn how to prepare JSON-LD for Knowledge Assets creation, a data format that enables you to express Linked Data in JSON. _Knowledge Assets_ are self-contained and structured pieces of knowledge that can be used across Web3 applications and linked to other Knowledge Assets in a decentralized knowledge graph. You will also learn how to use various tools to work with JSON-LD data, such as OpenRefine, JSON-LD Playground, jsonld.js, and Schema Markup Validator.

## Knowledge Assets

As a developer, you can create Knowledge Assets tailored to your specific use case, which can be used across Web3 applications. Knowledge Assets are self-contained and structured pieces of knowledge that can be linked to other Knowledge Assets and bring great value to your organization. You can apply standardized technologies such as GS1 EPCIS, RDF/SPARQL, JSON-LD, and other W3C and GS1 standards out of the box.

JSON-LDs are used to create Knowledge Assets. A Knowledge Asset is an ownable container for your valuable information that can describe any physical thing, document, abstract concept, number, or string. Your data is stored in a Decentralized Knowledge Graph, which makes it easily discoverable. The underlying blockchain safeguards the integrity of your information and the ownership of your Knowledge Asset. More on Knowledge Assets can be found [here](https://docs.origintrail.io/key-concepts/dkg-key-concepts) and [here](https://origintrail.io/technology/decentralized-knowledge-graph).

### JSON-LD

JSON-LD stands for JavaScript Object Notation for Linked Data. It is a lightweight JSON-based data format for encoding Linked Data. JSON-LD is easy to read and understand for humans and a powerful format for creating structured data.

**JSON and JSON-LD** are both data formats based on JavaScript Object Notation. The main difference is that JSON-LD adds a context to link the data to well-defined vocabularies, such as Schema.org. Adding context to link the data to well-defined vocabularies, such as Schema.org, and JSON-LD makes the data more semantic and machine-understandable. It is also compatible with Linked Data principles.

**Linked Data** is a powerful concept that allows data to be interlinked and become more valuable through semantic queries. Linked Data allows structured data to be published and interlinked, making it more useful through semantic queries.

In the context of knowledge graphs, Linked Data principles are used to create a network of data that can be easily queried and analyzed. **Knowledge graphs** are databases that use graph structures to represent data and its relationships. Using Linked Data principles, knowledge graphs can be created that are interoperable with other data sources from the knowledge graph, making it possible to combine data from multiple sources by connecting them to create a complete picture of a particular domain.

For further exploration of Linked Data and the concept of a knowledge graph, you can delve into additional resources available [here](https://docs.origintrail.io/general/kg).

**JSON-LD allows you to structure your data to align with Linked Data principles.** It achieves this through its unique features:

* **Context:** JSON-LD allows you to define a context for your data. This context provides a way to map JSON keys to specific meanings or vocabularies. By using a context, you can semantically enrich your data, defining how JSON keys relate to terms in an ontology or schema.
* **Compact and Expanded Syntax:** JSON-LD supports both a compact and an expanded syntax. The compact syntax is more human-readable and concise, while the expanded syntax is more verbose and suitable for machine processing. Both syntaxes represent the same data model but offer different levels of readability.
* **Linked Data Principles:** JSON-LD is designed to adhere to the principles of Linked Data. These principles include using URIs as resource identifiers, providing links to other resources, and using standard vocabularies or ontologies to define the meaning of terms. By following these principles, JSON-LD enables data to be easily linked and queried semantically.

Here is an example of JSON-LD code that describes a person:

```
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "John Doe",
 "@id": "https://www.example.com/person/john-doe",
  "jobTitle": "Software Engineer",
  "telephone": "(123) 456-7890",
  "url": "https://www.example.com",
  "sameAs": [
    "https://www.facebook.com/johndoe",
    "https://www.linkedin.com/in/johndoe",
    "https://twitter.com/johndoe"
  ]
}
```

This JSON-LD describes a person named John Doe, who is a software engineer.&#x20;

If you use the `“@ID”` attribute in JSON-LD datasets, it must have a non-null value and be set to an Internationalized Resource Identifier (IRI). For more information on IRIs and their use in JSON-LDs, refer to this [resource](https://www.w3.org/TR/json-ld11/#iris).

In this example, the `"@context"` and `"@type"` fields are crucial in enriching the data by utilizing established schemas from Schema.org. These fields provide the necessary context to understand the structured data and specify that the information pertains to a person (identified by the `"@type"` field) within the context of Schema.org's vocabulary.

`@context` is a field in JSON-LD that defines the context for the data. It provides additional information about the meaning of the data, such as the vocabulary used to define the terms in the data. The context can be a URL that points to a JSON-LD context document, or it can be an object that defines the context directly in the JSON-LD document.

`@type` is a field in JSON-LD that specifies the type of the data. It is used to indicate the type of the object being described in the JSON-LD document. For example, in the JSON-LD code provided earlier, the `@type` field specifies that the data is describing a person.

Other fields are standard parts of the Person schema, additionally, more fields could be added to better describe the person, as can be seen [here](https://schema.org/Person). And more schemas can be found [here](https://schema.org/).&#x20;

A detailed explanation of how to build and use JSON-LD can be found [here](https://www.w3.org/TR/json-ld11/).

### JSON-LD and Knowledge Assets

When crafting JSON-LD, it's important to consider how it will translate into a Knowledge Asset (KA), especially regarding the handling of private and public fields. By defining these fields in the JSON-LD format, you can maintain control over sensitive data within your Knowledge Asset, ensuring that it remains private while still allowing for the publication of relevant public information. Additionally, connecting your Knowledge Asset to existing knowledge within the Decentralized Knowledge Graph (DKG) through Universal Asset Locators (UALs) can significantly enhance its value and discoverability. These UALs serve as unique identifiers, similar to URLs on the traditional web, enabling seamless navigation and linking within the DKG.

#### Private and public fields

If you have sensitive data in your Knowledge Asset that you want to keep private, you can define private and public fields using JSON-LD. This allows you to control access to the private segment of the data, ensuring it is only accessible to you. To do this, you need to split the data into two JSON-LD properties: one that becomes public and one that becomes private.&#x20;

By doing so, you can ensure that the private segment of the data is only accessible to you. The public part of your data is replicated to other nodes and is accessible to others, while the private part is stored only on your node and is accessible only to you.

Example of JSON-LD with public and private parts:

```
{
    "public": {
        "@context": "https://schema.org",
        "@id": "https://tesla.modelX/2321",
        "@type": "Car",
        "name": "Tesla Model X",
        "brand": {
            "@type": "Brand",
            "name": "Tesla"
        },
        "model": "Model X",
        "manufacturer": {
            "@type": "Organization",
            "name": "Tesla, Inc."
        }
    },
    "private": {
        "@context": "https://schema.org",
        "@id": "https://tesla.modelX/2321",
        "productionDate": "2015-09-29",
        "mileageFromOdometer": {
            "@type": "QuantitativeValue",
            "value": "25672",
            "unitCode": "KMT"
        }
    }
}
```

#### Connecting data

To unlock the full potential of the Knowledge Assets,  they should be connected to existing knowledge in the DKG.&#x20;

For your Knowledge Asset to be connected to other Knowledge Assets, it needs to include the Universal Asset Locator of the asset you want to point to. The Universal Asset Locator (UAL) is a unique identifier used to locate and identify a specific Knowledge Asset within the OriginTrail Decentralized Knowledge Graph (DKG). It is similar to a URL in the traditional web and follows the DID URL specification. More on UAL can be found [here](https://docs.origintrail.io/decentralized-knowledge-graph-layer-2/dkg-basic-concepts#what-is-a-ual).

Example of JSON-LD connected to Knowledge Asset with UAL "did:dkg:otp/0x5cac41237127f94c2d21dae0b14bfefa99880630/1962724"

```
{
  "public": {
    "@context": "http://schema.org",
    "@type": "ScholarlyArticle",
    "@id": "https://alphasigma.docsend.com/view/vsm7pa46bzsf75mv",
    "headline": "OriginTrail (TRAC) - The End of AI Hallucinations",
    "publisher": {
      "@id": "https://www.alphatransform.io/",
      "isPartOf": "did:dkg:otp/0x5cac41237127f94c2d21dae0b14bfefa99880630/1962724"
    }
  }
}
```

By incorporating references to other knowledge assets through Unique Asset Locators (UALs) in your JSON-LD, you enhance the discoverability and context of your Knowledge Asset. This interconnected web of information contributes to a richer decentralized knowledge graph, where relationships between different assets are more easily understood. By participating in this ecosystem, your Knowledge Assets not only become more discoverable but also gain depth and relevance through the context provided by other assets. This interconnectedness ultimately enhances the value of your Knowledge Assets within the broader knowledge graph, contributing to a more comprehensive and valuable resource for all participants in the decentralized knowledge network.

### Tools

In this chapter, you will learn about some of the tools that can assist you in working with JSON-LD data. These tools can help you with various tasks, such as creating JSON-LD data from different sources, such as CSV, XML, or existing JSON data; validating JSON-LD data to ensure that it conforms to the JSON-LD specification and the Schema.org vocabulary; or transforming JSON to JSON-LD, by adding context and semantics to your JSON data. These tools can make your work with JSON-LD data easier and more efficient, and help you produce high-quality and standards-compliant data.

#### OpenRefine

OpenRefine is a free and open-source tool that lets you clean, transform, and extend your data from various sources. You can use facets, heuristics, reconciliation, and web services to work with large datasets and external databases. OpenRefine supports a wide range of file formats, including CSV, JSON, XML, ODS, XLS, and more. OpenRefine also supports extensions that add more functionality and features to the tool.

One of the extensions that OpenRefine supports is JSON-LD. You can use OpenRefine to create JSON-LD data from your existing data by adding a context column that links your data to well-defined vocabularies, such as Schema.org. You can also use OpenRefine to validate, export, and import JSON-LD data, as well as reconcile it with external sources.

You can find OpenRefine documentation [here](https://openrefine.org/docs).

#### JSON-LD Playground

JSON-LD Playground is a web-based JSON-LD viewer and debugger that allows you to explore and edit your JSON-LD data. You can also use it to visualize the data graph, expand or compact the data, and convert it to other formats, such as RDF or N-Quads2. JSON-LD Playground can be accessed [here](https://json-ld.org/playground/).

### Jsonld.js

jsonld.js is a JavaScript library that implements the JSON-LD specification, which is a standard for expressing Linked Data in JSON. JSON-LD allows you to add context and semantics to your JSON data, making it more machine-understandable and compatible with the Web of Knowledge. You can use jsonld.js to manipulate, expand, compact, frame, and normalize JSON-LD data, as well as convert it to other formats, such as RDF. You can also use jsonld.js to create and verify digital signatures for JSON-LD data, using various cryptographic algorithms and proof purposes. jsonld.js works in both Node.js and browser environments. You can see the jsonld.js repository on GitHub [here](https://github.com/digitalbazaar/jsonld.js).

#### Schema Markup Validator

Schema Markup Validator is a tool that lets you test your structured data using the Schema.org vocabulary, which is a widely used and supported vocabulary for describing various types of entities on the web. You can paste your JSON-LD code or enter a URL and see the results in a graphical or raw format. Schema Markup Validator can be accessed [here](https://validator.schema.org/).
