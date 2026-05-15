# parsley
Data-Driven Template Scaffolder with a Local Registry and High-Friction Schema Mutation.

Parsley: Data-Driven Catalog Scaffolding
Parsley prevents errors in catalog-info.yaml files by guiding users to choose from predefined, valid options.

Core Mechanics
Standard Input: A low-friction menu provides existing, valid values.

New Entries: Introducing freeform values requires deliberate intent. Users must bypass defaults via a command-line flag or menu option, then pass a high-friction confirmation prompt ("Type 'I am sure'").

Self-Updating Registry: Validated freeform entries are instantly appended to the local choices/ files, automatically updating the schema for future executions.

System Integration
The script outputs a completed catalog-info.yaml file. In the broader toolchain, an ingestion script scans the infrastructure directory, aggregates these artifacts, and compiles them into a downstream SQLite catalog.db for fast lookups and dependency graphing.

$ tree
.
├── catalog-info.template.yaml
├── catalog-info.yaml
├── choices
│   ├── __KIND__
│   ├── __LIFECYCLE__
│   └── __OWNER__
└── parsley.sh

