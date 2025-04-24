# relation_extend

**Overview**  
Transforms generic `dcterms:relation` in JSON-LD into specific RDF predicates based on your relationship nodes and role terms.

**Requirements**  
- **Role** taxonomy: add a **Text** field `field_rdf_property` to hold each term’s predicate IRI (e.g. `schema:translationOfWork`).  
- **Relationship** content types: include a `field_role` (to Role terms) and one or more `field_to_*` reference fields.  
- JSON-LD enabled for Node in REST (`?_format=jsonld` or `Accept: application/ld+json`).

**Setup**  
1. Add `field_rdf_property` to **Structure → Taxonomy → Role → Manage fields**.  
2. Copy the module to `modules/custom/relation_extend/` and ensure `relation_extend.info.yml` depends on `serialization` and `jsonld`.  
3. Enable modules:
   ```bash
   drush en serialization jsonld relation_extend -y
   drush cr
