# Conversão MARC para RDF

## Conversão de UNIMARC para MARC XML

Extrato de UNIMARC:

```
600  1^aPessoa^bFernando^f1888-1935
```

Correspondente MARC XML:

```
<datafield tag="600" ind1=" " ind2="1">
        <subfield code="a">Pessoa</subfield>
        <subfield code="b">Fernando</subfield>
        <subfield code="f">1888-1935</subfield>
</datafield>
```

## Conversão de MARX XML para RDF

### Validação do RDF

http://www.w3.org/RDF/Validator/

### Ontologia utilizada pela BNE

Ontologia definida pela BNE: http://datos.bne.es/def/ontology.html

Exemplo de RDF gerado pela BNE: [Miguel de Cervantes](http://datos.bne.es/autor/XX1718747.ttl)

Este recurso RDF (autor) é do tipo Person.

```
<?xml version="1.0"?>
<rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#" xmlns:bne="http://datos.bne.es/def/" xmlns:owl="http://www.w3.org/2002/07/owl#">
<rdf:Description rdf:about="http://datos.bne.es/resource/XX1718747"><bne:id>XX1718747</bne:id></rdf:Description>
<rdf:Description rdf:about="http://datos.bne.es/resource/XX1718747"><rdf:type rdf:resource="http://datos.bne.es/def/C1005"/></rdf:Description>
<rdf:Description rdf:about="http://datos.bne.es/resource/XX1718747"><owl:sameAs rdf:resource="http://dbpedia.org/resource/Miguel_de_Cervantes"/></rdf:Description>
</rdf:RDF>
```

### Ontologia da IFLA

Por exemplo, o conceito de [Person utilizado pela BNE](http://datos.bne.es/def/ontology.html#C1005) é o mesmo
que o conceito de [Person da IFLA](http://iflastandards.info/ns/fr/frbr/frbrer/C1005).

Ontologias/vocabulários definidos pela IFLA: http://iflastandards.info/ns/fr/

Este recurso RDF (autor) é do tipo Person.

```
<?xml version="1.0"?>
<rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#" xmlns:bmm="http://dados.cm-montalegre.pt/def/" xmlns:owl="http://www.w3.org/2002/07/owl#">
<rdf:Description rdf:about="http://datos.bne.es/resource/XX1718747"><bmm:id>XX1718747</bmm:id></rdf:Description>
<rdf:Description rdf:about="http://datos.bne.es/resource/XX1718747"><rdf:type rdf:resource="http://iflastandards.info/ns/fr/frbr/frbrer/C1005"/></rdf:Description>
<rdf:Description rdf:about="http://datos.bne.es/resource/XX1718747"><owl:sameAs rdf:resource="http://dbpedia.org/resource/Miguel_de_Cervantes"/></rdf:Description>
</rdf:RDF>
```

## Queries SPARQL sobre o RDF

http://docs.openlinksw.com/virtuoso/rdfinsertmethods.html#rdfinsertmethodwebdav

Ver print screens

SELECT *
from named <http://webgis.di.uminho.pt/~jgr/cervantes.rdf> option (get:soft "soft", get:method "GET")
WHERE { ?s ?p ?o }