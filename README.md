# ERTMS Interlocking railML Implementation


This repository contains the sytems independent railML implementation specification for **ERTMS Interlocking**.  
It includes:
- The machine-readable CSV implementation specification.
- The Trafikverket-specific **railML extension schema** (`trvExtensions/`).
- Static and generated AsciiDoc documentation for Antora.
- A JSON configuration file for the railML Antora Doc Generator.

## Information Classification

All content in this repository is classified as “1 – Non-sensitive” according to the Swedish Transport Administration’s (Trafikverket’s) information classification model. This means that the material does not contain confidential, personal, security-related, or otherwise protected information, and its distribution poses no risk to operational, legal, or security interests. The repository may therefore be published, used, and shared publicly without restrictions.

## Repository Structure
```
railML-implementation-ertms-interlocking/
├── trv-ertms-interlocking.csv         # Implementation CSV specification
├── ertms-interlocking.json            # Generator configuration for CLI
├── AntoraAssets/                      # Static AsciiDoc pages and templates
│   ├── staticPages/                   # Reusable static documentation
│   └── templates/nav.adoc             # Navigation template (with insert marker)
├── trvExtensions/                     # Trafikverket-specific railML schema extensions validation
├── GeneratedDocs/                     # Generated AsciiDoc output
│   └── modules/ROOT/pages/            # Final documentation pages for Antora
└── README.md
```

## Workflow

1. Make required changes.
2. Verify that the implementation CSV (`trv-ertms-interlocking.csv`) and JSON config (`ertms-interlocking.json`) are correct.
3. Verify that the static Antora pages are correct.
4. Verify that the nav.adoc file is correct.
5. Run the **railML Antora Doc Generator** CLI targeting the JSON config file. See the railml-antora-doc-generator repo for details.
6. The Antora files are generated in the directory specified by the configuration file.
7. Review and commit the new files in the repo you targeted.
8. Build the Antora site based on the guide in the railML-docs repo.

## Developer Setup

There are no real requirements, all files are plain text.

### About the `trvExtensions` Folder

The `trvExtensions` directory contains **Trafikverket’s XML Schema extension** to the official [railML 3.2](https://www.railml.org/en/schema/) schema, introducing additional elements and attributes used in the ERTMS interlocking domain.  
This extension allows Trafikverket to represent infrastructure and interlocking data that are not part of the base railML specification.

## Learn More

* [Antora Quickstart](https://docs.antora.org/antora/latest/install-and-run-quickstart/)
* [AsciiDoc Reference](https://docs.asciidoctor.org/asciidoc/latest/)
* [railML 3.2 Schema Overview](https://www.railml.org/en/schema/)


