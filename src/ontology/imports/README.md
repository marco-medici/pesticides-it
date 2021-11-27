To regenerate an owl file from a robot template, run this style of command:
NOTE: --input command ONLY ALLOWS ONE INPUT file; if you do multiple --input
only LAST one is used. Hence we need a merged version:

robot merge --input "../peston-edit.owl" --output peston-merged.owl

robot template --template robot_company.tsv \
  --input "peston-merged.owl" \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/company_import.owl" \
  --output company_import.owl


robot template --template robot_pesticide.tsv \
  --input "peston-merged.owl" \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/pesticide_import.owl" \
  --output pesticide_import.owl

robot template --template robot_address.tsv \
  --input "peston-merged.owl" \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/address_import.owl" \
  --output address_import.owl

  robot template --template robot_active_ingredient.tsv \
  --input "peston-merged.owl" \
  --prefix "PESTON:http://purl.obolibrary.org/obo/PESTON_" \
  --ontology-iri "http://purl.obolibrary.org/obo/peston/imports/active_ingredient_import.owl" \
  --output active_ingredient_import.owl