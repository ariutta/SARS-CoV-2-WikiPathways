# SARS-CoV-2-WikiPathways

Temporary repository of RDF of selected pathways from WikiPathways, supporting the Wikidata bot.

Both the source files are in this repository, as are the `.zip` files to be used by the bot.
These zip files are created/updated with these commands:

```shell
zip wikipathways-SARS-CoV-2-rdf-authors.zip authors/*
zip wikipathways-SARS-CoV-2-rdf-wp.zip wp/Human/*
```

The Turtle in the `wp/Human` folder is created with WPRDF from the
[SARS-CoV-2-WikiPathways](https://github.com/wikipathways/GPML2RDF/tree/SARS-CoV-2-WikiPathways)
branch. Generate the Turtle with these two Maven commands and manually copy/paste the content
into the `.ttl` files in this repository (GNU/Linux):

```shell
mkdir -p /tmp/OPSBRIDGEDB
echo "bridgefiles=/path/to/where/the/bridge/files/are" > /tmp/OPSBRIDGEDB/config.properties
mvn clean test -Dtest=org.wikipathways.wp2rdf.WP4846Test
mvn clean test -Dtest=org.wikipathways.wp2rdf.WP4853Test
mvn clean test -Dtest=org.wikipathways.wp2rdf.WP4860Test
```

To download the BridgeDb identifier mapping files, download them from
[here](https://bridgedb.github.io/data/gene_database/)
and save them in the `/path/to/where/the/bridge/files/are` folder, mathching what
you entered in the `config.properties` file above.


