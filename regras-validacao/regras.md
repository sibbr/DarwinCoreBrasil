# Testes de qualidade de dados

Este documento é um espelho das especificações para testes de validação de dados em Darwin Core definidos pelo TDWG em https://github.com/tdwg/bdq/projects/2. As especificações foram extraídas do link anterior por um processo automatizado permitindo acompanhar a evolução e a proposição de novas especificações, quando disponíveis. Atualmente, um total de 104 testes estão disponíveis, distribuídos em **quatro tipos**: 

- _Validation_: indica teste do tipo de validação dos dados; 

- _Amendment_: propõem mudanças e/ou melhoria dos dados; 

- _Issue_: aponta problemas com o dado informado e necessita de intervenção do usuário para determinar se o dado é adequado para uso; 

- _Measure_: sumarização dos testes anteriores (por exemplo, quantos testes do tipo _Validation_ apresentaram algum problema)
O vocabulário completo para os termos utilizados neste documento pode ser encontrado no link a seguir: https://github.com/tdwg/bdq/issues/152#issue-354943638 

**Notas sobre o desenvolvimento dos testes**: os cabeçalhos a seguir indicam os nomes oficiais definidos para cada teste. É importante que essa mesma nomenclatura seja utilizada durante a fase de desenvolvimento e de homologação dos testes. Isso garante a adequação ao padrão oficial sugerido pelo [TDWG](https://www.tdwg.org/). Assim, por exemplo, o nome do teste **VALIDATION_DAY_INRANGE** deve ser **VALIDATION_DAY_INRANGE**. Além disso, cada cabeçalho contém um hiperlink que aponta para sua respectiva _issue_ no repositório de proposição dos testes (https://github.com/tdwg/bdq/projects/2), onde atualizações e discussões podem ser verificadas. Para a maioria dos testes, os valores de exemplo dos dados de entrada (um ou mais valores para cada termo/coluna testado) e as respostas esperadas são exibidos em tabelas que também podem ser encontradas em CSV no link a seguir: https://github.com/sibbr/DarwinCoreBrasil/blob/regras-validacao/regras-validacao/exemplos-testes. 

## Teste 001: [`VALIDATION_COUNTRYCODE_STANDARD`](https://github.com/tdwg/bdq/issues/20) 

**Nome do teste**: `VALIDATION_COUNTRYCODE_STANDARD` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/20 

**ID oficial do teste**: `0493bcfb-652e-4d17-815b-b0cce0742fbe` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `countryCode` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is the value of dwc:countryCode a valid ISO 3166-1-alpha-2 country code?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if the dwc:countryCode was EMPTY; COMPLIANT if dwc:countryCode can be unambiguously interpreted as a valid ISO 3166-1-alpha-2 country code; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "ISO 3166 Country Codes" {[https://www.iso.org/iso-3166-country-codes.html]} {ISO 3166-1-alpha-2 Country Code search [https://www.iso.org/obp/ui/#search]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Locations outside of a jurisdiction covered by a country code should not have a value in the field dwc:countryCode. This test must return NOT_COMPLIANT if there is leading or trailing whitespace or there are leading or trailing non-printing characters._ 



<table>
<caption>Tabela 1: Termos testados e os resultados esperados para o teste VALIDATION_COUNTRYCODE_STANDARD.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> countryCode </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 001_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:countryCode is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 001_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc countryCode is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 001_3 </td>
   <td style="text-align:left;"> GL </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:countryCode is a valid ISO (ISO 3166-1-alpha-2 country codes) value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 001_4 </td>
   <td style="text-align:left;"> GRL </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:countryCode is NOT a valid ISO (ISO 3166-1-alpha-2 country codes) value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 001_5 </td>
   <td style="text-align:left;"> XX </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:countryCode is NOT a valid ISO (ISO 3166-1-alpha-2 country codes) value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 001_6 </td>
   <td style="text-align:left;"> Austria </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:countryCode is NOT a valid ISO (ISO 3166-1-alpha-2 country codes) value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 001_7 </td>
   <td style="text-align:left;"> US </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc countryCode is a valid ISO (ISO 3166-1-alpha-2 country codes) value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 001_8 </td>
   <td style="text-align:left;"> CL </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc countryCode is a valid ISO (ISO 3166-1-alpha-2 country codes) value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 001_9 </td>
   <td style="text-align:left;"> AR </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc countryCode is a valid ISO (ISO 3166-1-alpha-2 country codes) value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 001_10 </td>
   <td style="text-align:left;"> MX </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc countryCode is a valid ISO (ISO 3166-1-alpha-2 country codes) value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 001_11 </td>
   <td style="text-align:left;"> MX </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> The bdq:sourceAuthority was not available or unreachable </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:countryCode="GL": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Result.comment="	dwc:countryCode is a valid ISO (ISO 3166-1-alpha-2 country codes) value"],[dwc:countryCode="GRL": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:countryCode is NOT a valid ISO (ISO 3166-1-alpha-2 country codes) value"]

## Teste 002: [`VALIDATION_COUNTRY_FOUND`](https://github.com/tdwg/bdq/issues/21) 

**Nome do teste**: `VALIDATION_COUNTRY_FOUND` 

**Última atualização**: `2022-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/21 

**ID oficial do teste**: `69b2efdc-6269-45a4-aecb-4cb99c2ae134` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `country` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Does the value of dwc:country occur in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:country was EMPTY; COMPLIANT if value of dwc:country is a place type equivalent to "nation" by the bdq:sourceAuthority; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "The Getty Thesaurus of Geographic Names (TGN)" {[https://www.getty.edu/research/tools/vocabularies/tgn/index.html]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Non-country information such "high seas" will fail this test. Multiple values in the dwc:country field (whether to signify on a border or in a list of possibilities) will fail this test. Locations outside of a jurisdiction covered by a country code should not have a value in the field dwc:countryCode. This test must return NOT_COMPLIANT if there is leading or trailing whitespace or there are leading or trailing non-printing characters._ 



<table>
<caption>Tabela 2: Termos testados e os resultados esperados para o teste VALIDATION_COUNTRY_FOUND.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> country </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 002_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:country is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 002_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:country is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 002_3 </td>
   <td style="text-align:left;"> Eswatini </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country is a valid country name according to The Getty Thesaurus of Geographic Names (2021-03-30). </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 002_4 </td>
   <td style="text-align:left;"> Swaziland </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> Eswatini is the preferred name according to The Getty Thesaurus of Geographic Names (2021-03-30). </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 002_5 </td>
   <td style="text-align:left;"> Yugoslavia </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Yugoslavia is the preferred name according to The Getty Thesaurus of Geographic Names (2021-03-30). </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 002_6 </td>
   <td style="text-align:left;"> Congo </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> Congo could be Republic of the Congo or Democratic Republic of the Congo. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 002_7 </td>
   <td style="text-align:left;"> United States Minor Outlying Islands </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> &quot;United States Minor Outlying Islands&quot; is not a valid COUNTRY in The Getty Thesaurus of Geographic Names (2021-03-30). </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 002_8 </td>
   <td style="text-align:left;"> México </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country is a valid country name according to The Getty Thesaurus of Geographic Names (2021-03-30). </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 002_9 </td>
   <td style="text-align:left;"> México </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> The bdq:sourceAuthority was not available or unreachable </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:country="Eswatini": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:country is a valid country name according to The Getty Thesaurus of Geographic Names (2021-03-30)."],[dwc:country="Swaziland": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="Eswatini is the preferred name according to The Getty Thesaurus of Geographic Names (2021-03-30)."]

## Teste 003: [`VALIDATION_PHYLUM_FOUND`](https://github.com/tdwg/bdq/issues/22) 

**Nome do teste**: `VALIDATION_PHYLUM_FOUND` 

**Última atualização**: `2022-03-25` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/22 

**ID oficial do teste**: `eaad41c5-1d46-4917-a08b-4fd1d7ff5c0f` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `phylum` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Does the value of dwc:phylum occur at rank of Phylum in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:phylum is EMPTY; COMPLIANT if the value of dwc:phylum was found as a value at the rank of Phylum by the bdq:sourceAuthority; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "GBIF Backbone Taxonomy" {[https://doi.org/10.15468/39omei]} {API endpoint [https://api.gbif.org/v1/species?datasetKey=d7dddbf4-2cf0-4f39-9b2a-bb099caae36c&name=]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The purpose of this test is to check whether the value is a name that is a result of a nomenclatural act at this rank. This excludes unpublished names, misspellings and vernacular names. It is expected that the test will designate the source authority against to check. The same test might return distinct results when using distinct source authorities._ 



<table>
<caption>Tabela 3: Termos testados e os resultados esperados para o teste VALIDATION_PHYLUM_FOUND.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> phylum </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 003_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:phylum is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 003_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:phylum consists of white space </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 003_3 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:phylum does not have an equivalent at the rank of Phylum in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 003_4 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:phylum does not have an equivalent at the rank of Phylum in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 003_5 </td>
   <td style="text-align:left;"> Tracheophyta </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:phylum has an equivalent at the rank of Phylum in the bdq:sourceAuthority. GBIF.org uses Trachyophyta for the Phylum including ferns </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 003_6 </td>
   <td style="text-align:left;"> Trachyophyta </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:phylum does not have an equivalent at the rank of Phylum in the bdq:sourceAuthority. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 003_7 </td>
   <td style="text-align:left;"> Chareophyta </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:phylum does not have an equivalent at the rank of Phylum in the bdq:sourceAuthority. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 003_8 </td>
   <td style="text-align:left;"> Charophyta </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:phylum has an equivalent at the rank of Phylum in the bdq:sourceAuthority. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 003_9 </td>
   <td style="text-align:left;"> Chordata </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:phylum has an equivalent at the rank of Phylum in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 003_10 </td>
   <td style="text-align:left;"> chordate </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:phylumdoes not have an equivalent at the rank of Phylum in the bdq:sourceAuthority. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 003_11 </td>
   <td style="text-align:left;"> dwc:phylum </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:phylumdoes not have an equivalent at the rank of Phylum in the bdq:sourceAuthority. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 003_12 </td>
   <td style="text-align:left;"> AnyPhylum </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> The bdq:sourceAuthority was not available or unreachable </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:phylum="Tracheophyta": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:phylum has an equivalent at the rank of Phylum in the bdq:sourceAuthority. GBIF.org uses Trachyophyta for the Phylum including ferns"],[dwc:phylum="Trachyophyta": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:phylum does not have an equivalent at the rank of Phylum in the bdq:sourceAuthority."]

## Teste 004: [`VALIDATION_OCCURRENCEID_STANDARD`](https://github.com/tdwg/bdq/issues/23) 

**Nome do teste**: `VALIDATION_OCCURRENCEID_STANDARD` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/23 

**ID oficial do teste**: `3cfe9ab4-79f8-4afd-8da5-723183ef16a3` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Occurrence` 

**Termos (colunas) testados**: `occurrenceID` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Does the value of dwc:occurrenceID occur in bdq:SourceAuthority?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:occurrenceID is EMPTY; COMPLIANT if the value of dwc:occurrenceID follows a format commonly associated with globally unique identifiers (GUIDs); otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 4: Termos testados e os resultados esperados para o teste VALIDATION_OCCURRENCEID_STANDARD.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> occurrenceID </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 004_1 </td>
   <td style="text-align:left;"> https://www.inaturalist.org/observations/43047701 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceID conforms to GUID structure </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 004_2 </td>
   <td style="text-align:left;"> 42 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceID does not conform to GUID structure </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 004_3 </td>
   <td style="text-align:left;"> anyOldTerm </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceID does not conform to GUID structure </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 004_4 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceID does not conform to a GUID structure </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 004_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:occurrenceID is EMPTY or missing </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 004_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:occurrenceID is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 004_7 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceID does not conform to a GUID structure </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:occurrenceID="https://www.inaturalist.org/observations/43047701": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:occurrenceID conforms to GUID structure"],[dwc:occurrenceID="42": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:occurrenceID does not conform to GUID structure"]

## Teste 005: [`VALIDATION_MINDEPTH_GREATERTHAN_MAXDEPTH`](https://github.com/tdwg/bdq/issues/24) 

**Nome do teste**: `VALIDATION_MINDEPTH_GREATERTHAN_MAXDEPTH` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/24 

**ID oficial do teste**: `8f1e6e58-544b-4365-a569-fb781341644e` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `minimumDepthInMeters, maximumDepthInMeters` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is the value of dwc:minimumDepthInMeters a number that is less than or equal to the value of dwc:maximumDepthInMeters?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:minimumDepthInMeters or dwc:maximumDepthInMeters is EMPTY, or if either are interpretable as not zero or a positive number; COMPLIANT if the value of dwc:minimumDepthInMeters is less than or equal to the value of dwc:maximumDepthInMeters; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 5: Termos testados e os resultados esperados para o teste VALIDATION_MINDEPTH_GREATERTHAN_MAXDEPTH.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> minimumDepthInMeters </th>
   <th style="text-align:left;"> maximumDepthInMeters </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 005_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Input fields are EMPTY. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 005_2 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:minimumDepthInMeters = dwc:maximumDepthInMeters </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 005_3 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:minimumDepthInMeters &gt; dwc:maximumDepthInMeters </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 005_4 </td>
   <td style="text-align:left;"> -1 </td>
   <td style="text-align:left;"> -1 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> The values of dwc:minimumDepthInMeters or dwc:maximumDepthInMeters are not zero or a positive number </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 005_5 </td>
   <td style="text-align:left;"> 1200 </td>
   <td style="text-align:left;"> 1200 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:minimumDepthInMeters = dwc:maximumDepthInMeters </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 005_6 </td>
   <td style="text-align:left;"> 100 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:maximumDepthInMeters is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 005_7 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> 1200 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:minimumDepthInMeters is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 005_8 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1200 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:minimumDepthInMeters is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 005_9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1200 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:minimumDepthInMeters is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 005_10 </td>
   <td style="text-align:left;"> 100 </td>
   <td style="text-align:left;"> 50 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:minimumDepthInMeters &gt; maximumDepthInMeters </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:minimumDepthInMeters="0", dwc:maximumDepthInMeters="0": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:minimumDepthInMeters = dwc:maximumDepthInMeters"],[dwc:minimumDepthInMeters="1", dwc:maximumDepthInMeters="0": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:minimumDepthInMeters > dwc:maximumDepthInMeters"]

## Teste 006: [`AMENDMENT_DATEIDENTIFIED_STANDARDIZED `](https://github.com/tdwg/bdq/issues/26) 

**Nome do teste**: `AMENDMENT_DATEIDENTIFIED_STANDARDIZED ` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/26 

**ID oficial do teste**: `39bb2280-1215-447b-9221-fd13bc990641` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Identification` 

**Termos (colunas) testados**: `dateIdentified` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Propose amendment to the value of dwc:dateIdentified to a valid ISO date._ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:dateIdentified is EMPTY; AMENDED if the value of dwc:dateIdentified was not a properly formatted ISO 8601-1 date but was unambiguous and was altered to be a valid ISO 8601-1 date; otherwise NOT_AMENDED. bdq:sourceAuthority = "ISO 8601-1:2019" {[https://www.iso.org/iso-8601-date-and-time-format.html]}_ 

**Código fonte de exemplo**: _https://github.com/FilteredPush/event_date_qc/blob/1abbd3f02eb6c28129764defab78f72156972864/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L489_ 

**Notas**: _We reference Wikipedia for the ISO standard because the standard documents are not free._ 



<table>
<caption>Tabela 6: Termos testados e os resultados esperados para o teste AMENDMENT_DATEIDENTIFIED_STANDARDIZED .</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> dateIdentified </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 006_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:dateIdentified is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 006_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:dateIdentified is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 006_3 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:dateIdentified contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 006_4 </td>
   <td style="text-align:left;"> 10-28 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:dateIdentified contains an ambiguous value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 006_5 </td>
   <td style="text-align:left;"> 2021-28-10 </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:dateIdentified&quot;:&quot;2021-10-28&quot;} </td>
   <td style="text-align:left;"> dwc:dateIdentified assuming dwc:year, dwc:day and dwc:month </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 006_6 </td>
   <td style="text-align:left;"> 21-10-28 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:dateIdentified contains ambiguous values. It could be dd-mm-yy or yy-mm-dd </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 006_7 </td>
   <td style="text-align:left;"> 2021/10/28 </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:dateIdentified&quot;:&quot;2021-10-28&quot;} </td>
   <td style="text-align:left;"> dwc:dateIdentified contains an interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 006_8 </td>
   <td style="text-align:left;"> 2021/04/03 </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:dateIdentified&quot;:&quot;2021-04-03&quot;} </td>
   <td style="text-align:left;"> dwc:dateIdentified contains an unambiguous values (at least by Paul :) </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:dateIdentified="2021-28-10": Response.status=AMENDED, Response.result=dwc:dateIdentified="2021-10-28", Response.comment="dwc:dateIdentified assuming dwc:year, dwc:day and dwc:month"],[dwc:dateIdentified="21-10-28": Response.status=NOT_AMENDED, Response.result="", Response.comment="dwc:dateIdentified contains ambiguous values. It could be dd-mm-yy or yy-mm-dd"]

## Teste 007: [`VALIDATION_FAMILY_FOUND`](https://github.com/tdwg/bdq/issues/28) 

**Nome do teste**: `VALIDATION_FAMILY_FOUND` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/28 

**ID oficial do teste**: `3667556d-d8f5-454c-922b-af8af38f613c` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `family` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Does the value of dwc:family occur at rank of Family in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:family is EMPTY; COMPLIANT if the value of dwc:family was found as a value at the rank of Family by the bdq:sourceAuthority; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "GBIF Backbone Taxonomy" {[https://doi.org/10.15468/39omei]} {API endpoint [https://api.gbif.org/v1/species?datasetKey=d7dddbf4-2cf0-4f39-9b2a-bb099caae36c&name=]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The purpose of this test is to check whether the value is a name that is a result of a nomenclatural act at this rank. This excludes unpublished names, misspellings and vernacular names. It is expected that the test will designate the source authority against to check. The same test might return distinct results when using distinct source authorities._ 



<table>
<caption>Tabela 7: Termos testados e os resultados esperados para o teste VALIDATION_FAMILY_FOUND.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> family </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 007_1 </td>
   <td style="text-align:left;"> anyfamily </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> The bdq:sourceAuthority was unavailable or unreachable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 007_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:family is EMPTY or MISSING </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 007_3 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:family is EMPTY or white space </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 007_4 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> bdq:family does not have an equivalent at the rank of Family in the bdq:sourceAuthority, string serializations of null are not empty. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 007_5 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> bdq:family does not have an equivalent at the rank of Family in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 007_6 </td>
   <td style="text-align:left;"> Agaricaceae </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> bdq:family has an equivalent at the rank of Family in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 007_7 </td>
   <td style="text-align:left;"> Agaricacae </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> bdq:family does not have an equivalent at the rank of Family in the Parameterized Source Authority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 007_8 </td>
   <td style="text-align:left;"> Macropodidae </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> bdq:family has an equivalent at the rank of Family in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 007_9 </td>
   <td style="text-align:left;"> kangaroos </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> bdq:family does not have an equivalent at the rank of Family in the Parameterized Source Authority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 007_10 </td>
   <td style="text-align:left;"> Macropods </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> bdq:family does not have an equivalent at the rank of Family in the Parameterized Source Authority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 007_11 </td>
   <td style="text-align:left;"> dwc:family </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> bdq:family does not have an equivalent at the rank of Family in the bdq:sourceAuthority </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:family="Agaricaceae": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="bdq:family has an equivalent at the rank of Family in the bdq:sourceAuthority"],[dwc:family="Agaricacae": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="bdq:family does not have an equivalent at the rank of Family in the Parameterized Source Authority"]

## Teste 008: [`VALIDATION_DECIMALLONGITUDE_INRANGE`](https://github.com/tdwg/bdq/issues/30) 

**Nome do teste**: `VALIDATION_DECIMALLONGITUDE_INRANGE` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/30 

**ID oficial do teste**: `0949110d-c06b-450e-9649-7c1374d940d1` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `decimalLongitude` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is the value of dwc:decimalLongitude a number between -180 and 180 inclusive?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:decimalLongitude is EMPTY or the value is not a number; COMPLIANT if the value of dwc:decimalLongitude is between -180 and 180 degrees, inclusive; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 8: Termos testados e os resultados esperados para o teste VALIDATION_DECIMALLONGITUDE_INRANGE.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> decimalLongitude </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 008_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLongitude is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 008_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLongitude is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 008_3 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLongitude does not contain a numerical value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 008_4 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLongitude is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 008_5 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLongitude is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 008_6 </td>
   <td style="text-align:left;"> 121.0534 W </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLongitude is NOT a number </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 008_7 </td>
   <td style="text-align:left;"> 181.0554 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLongitude &gt;180 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 008_8 </td>
   <td style="text-align:left;"> -189.5674 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLongitude &lt;-180 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 008_9 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLongitude is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 008_10 </td>
   <td style="text-align:left;"> -94.4805934 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLongitude is in range </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:decimalLongitude="0": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:decimalLongitude is in range"],[dwc:decimalLongitude="181.0554": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:decimalLongitude >180"]

## Teste 009: [`AMENDMENT_COORDINATES_FROM_VERBATIM`](https://github.com/tdwg/bdq/issues/32) 

**Nome do teste**: `AMENDMENT_COORDINATES_FROM_VERBATIM` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/32 

**ID oficial do teste**: `3c2590c7-af8a-4eb4-af57-5f73ba9d1f8e` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `decimalLatitude, decimalLongitude, verbatimCoordinates, verbatimLatitude, verbatimLongitude, verbatimCoordinateSystem, verbatimSRS` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Propose amendment to the values of dwc:decimalLatitude and dwc:decimalLongitude from information in the verbatim coordinates terms._ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if either dwc:decimalLatitude or dwc:decimalLongitude were not EMPTY, or either dwc:verbatimLatitude and dwc:verbatimLongitude, or dwc:verbatimCoordinates were not unambiguously interpretable into valid coordinates; FILLED_IN the values of dwc:decimalLatitude and dwc:decimalLongitude if unambiguous values can be interpreted from  dwc:verbatimCoordinates or dwc:verbatimLatitude and dwc:verbatimLongitude, plus dwc:verbatimCoordinateSystem and dwc:verbatimSRS; otherwise NOT_AMENDED_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 9: Termos testados e os resultados esperados para o teste AMENDMENT_COORDINATES_FROM_VERBATIM.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> decimalLatitude </th>
   <th style="text-align:left;"> decimalLongitude </th>
   <th style="text-align:left;"> verbatimCoordinates </th>
   <th style="text-align:left;"> verbatimLatitude </th>
   <th style="text-align:left;"> verbatimLongitude </th>
   <th style="text-align:left;"> verbatimCoordinateSystem </th>
   <th style="text-align:left;"> verbatimSRS </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 009_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> All input fields are EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 009_2 </td>
   <td style="text-align:left;"> -23.712 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatutide is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 009_3 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 139.923 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLongitude is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 009_4 </td>
   <td style="text-align:left;"> -23.712 </td>
   <td style="text-align:left;"> 139.923 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatutide and dwc:decimalLongitude are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 009_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 23 degrees 42.72 minutes south </td>
   <td style="text-align:left;"> -23.712 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimLatitude and dwc:verbatimLongitude and dwc:verbatimCoordinates were not interpretable into coordinates as decimal degrees </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 009_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> -23.712 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimLatitude and dwc:verbatimLongitude were not interpretable into coordinates as decimal degrees </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 009_7 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 23 degrees south 185 degrees east </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimCoordinates were not interpretable into coordinates as decimal degrees </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 009_8 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimCoordinates were not interpretable into coordinates as decimal degrees </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 009_9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 139 degrees 55.38 minutes east </td>
   <td style="text-align:left;"> -23.712 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> EPSG:4326 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimCoordinateSystem is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 009_10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 139 degrees 55.38 minutes east </td>
   <td style="text-align:left;"> -23.712 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> decimal degrees </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimCoordinateSRS is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 009_11 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 139 degrees 55.38 minutes east </td>
   <td style="text-align:left;"> -23.712 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> decimal degrees </td>
   <td style="text-align:left;"> WDGB21 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimSRS contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 009_12 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> -23.712 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> decimal degrees </td>
   <td style="text-align:left;"> EPSG:4326 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimLongitude is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 009_13 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 139.92 </td>
   <td style="text-align:left;"> -23.712 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> decimal degrees </td>
   <td style="text-align:left;"> EPSG:4326 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:decimalLatitude&quot;:&quot;-23.712&quot;,&quot;dwc:decimalLongitude&quot;:&quot;139.923&quot;,&quot;dwc:geodeticDatum&quot;:&quot;EPSG:4326&quot;} </td>
   <td style="text-align:left;"> Input fields contain interpretable values </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 009_14 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 139.92. -23.712 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> decimal degrees </td>
   <td style="text-align:left;"> EPSG:4326 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:decimalLatitude&quot;:&quot;-23.712&quot;,&quot;dwc:decimalLongitude&quot;:&quot;139.923&quot;,&quot;dwc:geodeticDatum&quot;:&quot;EPSG:4326&quot;} </td>
   <td style="text-align:left;"> Input fields contain interpretable values </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 009_15 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> -23.712 </td>
   <td style="text-align:left;"> 139.92 </td>
   <td style="text-align:left;"> decimal degrees </td>
   <td style="text-align:left;"> EPSG:4326 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:decimalLatitude&quot;:&quot;-23.712&quot;,&quot;dwc:decimalLongitude&quot;:&quot;139.923&quot;,&quot;dwc:geodeticDatum&quot;:&quot;EPSG:4326&quot;} </td>
   <td style="text-align:left;"> Input fields contain interpretable values </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:verbatimLatitude="-23.712", dwc:verbatimLongitude="", dwc:verbatimCoordinates="139.92", dwc:verbatimSRS="EPSG:4326", dwc:verbatimCoordinateSystem="decimal degrees": Response.status=FILLED_IN, Response.result=dwc:decimalLatitude="-23.712", dwc:decimalLongitude="139.923", dwc:geodeticDatum="EPSG:4326", Response.comment="Input fields contain interpretable values"],[dwc:verbatimLatitude="-23.712", dwc:verbatimLongitude="", dwc:verbatimCoordinates="", dwc:verbatimSRS="EPSG:4326", dwc:verbatimCoordinateSystem="decimal degrees",  dwc:decimalLatitude="", dwc:decimalLongitude="": Response.status=NOT_AMENDED, Response.result="", Response.comment="dwc:verbatimLongitude is EMPTY"],[dwc:verbatimLatitude="", dwc:verbatimLongitude="", dwc:verbatimCoordinates="54K 0390210 7377243", dwc:verbatimSRS="EPSG:32754", dwc:verbatimCoordinateSystem="decimal degrees",  dwc:decimalLatitude="", dwc:decimalLongitude="": Response.status=AMENDED, Response.result={dwc:decimalLatitude="-23.712", dwc:decimalLongitude="139.923", dwc:geodeticDatum="EPSG:4326"}, Response.comment="dwc:verbatimLongitude is EMPTY"]

## Teste 010: [`VALIDATION_EVENTDATE_NOTEMPTY`](https://github.com/tdwg/bdq/issues/33) 

**Nome do teste**: `VALIDATION_EVENTDATE_NOTEMPTY` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/33 

**ID oficial do teste**: `f51e15a6-a67d-4729-9c28-3766299d2985` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `eventDate` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:eventDate?_ 

**Especificação**: 
> _COMPLIANT if dwc:eventDate is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _event_date_qc v3.0.0 [DwCEventDQ.validationEventdateNotEmpty()](https://github.com/FilteredPush/event_date_qc/blob/v3.0.0/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L182)_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 10: Termos testados e os resultados esperados para o teste VALIDATION_EVENTDATE_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> eventDate </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 010_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_2 </td>
   <td style="text-align:left;"> 1964-11-01T10:00-0600 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_3 </td>
   <td style="text-align:left;"> 1949-09-15T12:34 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_4 </td>
   <td style="text-align:left;"> 1949-09-16T12:34 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_5 </td>
   <td style="text-align:left;"> 1949-12-09T12:34 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_6 </td>
   <td style="text-align:left;"> 1963-03-08T14:07-0600 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_7 </td>
   <td style="text-align:left;"> 1963-03-08T14:07 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_8 </td>
   <td style="text-align:left;"> 1963-03-08T14 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_9 </td>
   <td style="text-align:left;"> 1963-03-08T14:67-0600 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_10 </td>
   <td style="text-align:left;"> 1963-03-08T14:07Z </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_11 </td>
   <td style="text-align:left;"> 1963-03-08T4 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_12 </td>
   <td style="text-align:left;"> 1963-03-08T14:0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_13 </td>
   <td style="text-align:left;"> 1963-03-08T14:07 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_14 </td>
   <td style="text-align:left;"> 1963-03-08 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_15 </td>
   <td style="text-align:left;"> 1963-03 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_16 </td>
   <td style="text-align:left;"> 1963 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_17 </td>
   <td style="text-align:left;"> 1962-11-01T10:00 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_18 </td>
   <td style="text-align:left;"> 1964-11-01T10:00 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_19 </td>
   <td style="text-align:left;"> 1963-11-01T10:00 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_20 </td>
   <td style="text-align:left;"> 63 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_21 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_22 </td>
   <td style="text-align:left;"> 1949-01-01 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_23 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_24 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 010_25 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventdate is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:eventDate="1962-11-01T10:00-0600": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:eventdate is not EMPTY"],[dwc:eventDate="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:eventDate is EMPTY"]

## Teste 011: [`VALIDATION_EVENTDATE_INRANGE`](https://github.com/tdwg/bdq/issues/36) 

**Nome do teste**: `VALIDATION_EVENTDATE_INRANGE` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/36 

**ID oficial do teste**: `3cff4dc4-72e9-4abe-9bf3-8a30f1618432` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `eventDate` 

**Pré-requisitos externos (parâmetros)**: `bdq:earliestValidDate,bdq:latestValidDate` 

**Descrição**: 
> _Is the value of dwc:eventDate entirely with the Parameter Range?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:eventDate is EMPTY or if the value of dwc:eventDate is not a valid ISO 8601-1 date; COMPLIANT if the range of dwc:eventDate is entirely within the range bdq:earliestValidDate to bdq:latestValidDate, inclusive, otherwise NOT_COMPLIANT bdq:earliestValidDate default ="1582-11-15",bdq:latestValidDate default = current year_ 

**Código fonte de exemplo**: _FilteredPush event_date_qc [DwCEventDQ.validationEventdateInrange()](https://github.com/FilteredPush/event_date_qc/blob/c17d6e8340f7dd5dfa63a761d4e1cb66c126980a/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L2229)_ 

**Notas**: _This test provides for a default earliest date, which is 1582-11-15 by convention. That date was chosen because ISO 8601-1 asserts that "the use of proleptic Gregorian calendar dates prior are not allowed in ISO 8601-1 without prior agreement of the parties exchanging data", and Darwin Core does not comment on this.  Different calendars have been used at different times in different places, and the transcription of an original date in one calendar into dwc:eventDate, where a Gregorian Calendar is assumed, may or may not have been done with the correct translation of the date, and metadata may or not be present to even identify such records. Given the complexity, and ongoing nature of transitions between calendars, we do not advocate using this test for quality assurance by selecting a transition date and using it as a threshold._ 



<table>
<caption>Tabela 11: Termos testados e os resultados esperados para o teste VALIDATION_EVENTDATE_INRANGE.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> eventDate </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 011_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_2 </td>
   <td style="text-align:left;"> 1962-11-01T10:00-0600 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is IN_RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_3 </td>
   <td style="text-align:left;"> 1964-11-01T10:00-0600 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is IN_RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_4 </td>
   <td style="text-align:left;"> 1949-09-15T12:34 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is IN_RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_5 </td>
   <td style="text-align:left;"> 1949-09-16T12:34 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is IN_RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_6 </td>
   <td style="text-align:left;"> 1949-12-09T12:34 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is IN_RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_7 </td>
   <td style="text-align:left;"> 1949-01-15T12:34/1949-01-20T17:00 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is IN_RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_8 </td>
   <td style="text-align:left;"> 1963-03-08T14:07-0600 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is IN_RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_9 </td>
   <td style="text-align:left;"> 1963-03-08T14:07 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is IN_RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_10 </td>
   <td style="text-align:left;"> 1963-03-08T14 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is IN_RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_11 </td>
   <td style="text-align:left;"> 1963-03-08 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is IN_RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_12 </td>
   <td style="text-align:left;"> 1963-03 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is IN_RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_13 </td>
   <td style="text-align:left;"> 1499 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is NOT_IN_RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_14 </td>
   <td style="text-align:left;"> 2300-11-01T10:00 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is NOT_IN_RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_15 </td>
   <td style="text-align:left;"> 0032-11-01T10:00 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is NOT_IN_RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_16 </td>
   <td style="text-align:left;"> 1963-03-08T14:67-0600 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is not a valid ISO 8601 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_17 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is not a valid ISO 8601 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_18 </td>
   <td style="text-align:left;"> 1963-03-08T4 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is not a valid ISO 8601 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_19 </td>
   <td style="text-align:left;"> 1963-03-08T14:0 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is not a valid ISO 8601 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_20 </td>
   <td style="text-align:left;"> 63 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is not a valid ISO 8601 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_21 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is not a valid ISO 8601 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_22 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 011_23 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is not interpretable as a valid ISO date </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:eventDate="1962-11-01T10:00-0600": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:eventDate is IN_RANGE"],[dwc:eventDate="2300-11-01T10:00": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:eventDate is NOT_IN_RANGE"]

## Teste 012: [`VALIDATION_LICENCE_STANDARD`](https://github.com/tdwg/bdq/issues/38) 

**Nome do teste**: `VALIDATION_LICENCE_STANDARD` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/38 

**ID oficial do teste**: `3136236e-04b6-49ea-8b34-a65f25e3aba1` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Record-level` 

**Termos (colunas) testados**: `license` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Does the value of dcterms:license occur in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dcterms:license is EMPTY; COMPLIANT if the value of the term dcterms:license is in the bdq:sourceAuthority; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "Creative Commons" {[https://creativecommons.org/]} {Creative Commons licenses [https://creativecommons.org/about/cclicenses/]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The license at the record level might be derived from the license of the data set from which the record is retrieved. This test must return NOT_COMPLIANT if there is leading or trailing whitespace or there are leading or trailing non-printing characters._ 



<table>
<caption>Tabela 12: Termos testados e os resultados esperados para o teste VALIDATION_LICENCE_STANDARD.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> license </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 012_1 </td>
   <td style="text-align:left;"> CC BY </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dcterms:license matches a term in bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 012_2 </td>
   <td style="text-align:left;"> GPL </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dcterms:license does not match a term in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 012_3 </td>
   <td style="text-align:left;"> anyOldTerm </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dcterms:license does not match a term in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 012_4 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dcterms:license does not match a term in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 012_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dcterms:license is EMPTY or missing </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 012_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dcterms:license is EMPTY or missing </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 012_7 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dcterms:license does not match a term in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 012_8 </td>
   <td style="text-align:left;"> Anylicence </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority was not available or was unreachable </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dcterms:license="CC BY": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dcterms:license matches a term in bdq:sourceAuthority"],[dcterms:license="GPL": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dcterms:license does not match a term in the bdq:sourceAuthority"]

## Teste 013: [`VALIDATION_MINELEVATION_INRANGE`](https://github.com/tdwg/bdq/issues/39) 

**Nome do teste**: `VALIDATION_MINELEVATION_INRANGE` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/39 

**ID oficial do teste**: `0bb8297d-8f8a-42d2-80c1-558f29efe798` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `minimumElevationInMeters` 

**Pré-requisitos externos (parâmetros)**: `bdq:minimumValidElevationInMeters,bdq:maximumValidElevationInMeters` 

**Descrição**: 
> _Is the value of dwc:minimumElevationInMeters within the Parameter range?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:minimumElevationInMeters is EMPTY or the value is not a number; COMPLIANT if the value of dwc:minimumElevationInMeters is within the range of bdq:minimumValidElevationInMeters to bdq:maximumValidElevationInMeters inclusive; otherwise NOT_COMPLIANT bdq:minimumValidElevationInMeters default = "-430",bdq:maximumValidElevationInMeters default = "8850"_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _We have rounded up the Parameter values. We are aware of sub-ice elevations in Antarctica to -3,500m and possible sampling in the atmosphere above the elevation of the top of Mt Everest that would fail this test but we support the odd false positive._ 



<table>
<caption>Tabela 13: Termos testados e os resultados esperados para o teste VALIDATION_MINELEVATION_INRANGE.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> minimumElevationInMeters </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 013_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters is EMPTY&quot; </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 013_2 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters is IN_RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 013_3 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters is IN_RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 013_4 </td>
   <td style="text-align:left;"> -500 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters is NOT_IN_RANGE (&lt;-430) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 013_5 </td>
   <td style="text-align:left;"> 8860 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters is NOT_IN_RANGE (&gt;8850) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 013_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters is EMPTY&quot; </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 013_7 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters is not a NUMBER </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 013_8 </td>
   <td style="text-align:left;"> [non-prininting characters] </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters is not a NUMBER </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:minimumElevationInMeters="0": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:minimumElevationInMeters is IN_RANGE"],[dwc:minimumElevationInMeters="-500": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:minimumElevationInMeters is NOT_IN_RANGE (<-430)"]

## Teste 014: [`VALIDATION_LOCATION_NOTEMPTY`](https://github.com/tdwg/bdq/issues/40) 

**Nome do teste**: `VALIDATION_LOCATION_NOTEMPTY` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/40 

**ID oficial do teste**: `58486cb6-1114-4a8a-ba1e-bd89cfe887e9` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `locationID, higherGeographyID, continent, waterBody, islandGroup, island, country, countryCode, stateProvince, decimalLatitude, decimalLongitude, geodeticDatum, footprintWKT` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in any of the Darwin Core spatial terms that could specify a location?_ 

**Especificação**: 
> _COMPLIANT if at least one term needed to determine the location of the entity exists and is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Only fails if all of the relevant fields of the Darwin Core Location class are EMPTY or do not exist.  Relevant Darwin Core fields include dwc:locationID, dwc:higherGeographyID, dwc:higherGeography, dwc:continent, dwc:waterBody, dwc:islandGroup, dwc:island, dwc:country, dwc:countryCode, dwc:stateProvince, dwc:county, dwc:municipality, dwc:locality, dwc:verbatimLocality, dwc:decimalLatitude, dwc:decimalLongitude, dwc:verbatimCoordinates, dwc:verbatimLatitude, dwc:verbatimLongitude, dwc:footprintWKT. Elevation and/or depth alone are deemed insufficient to meaningfully locate a position on the earth._ 



<table>
<caption>Tabela 14: Termos testados e os resultados esperados para o teste VALIDATION_LOCATION_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> locationID </th>
   <th style="text-align:left;"> higherGeographyID </th>
   <th style="text-align:left;"> continent </th>
   <th style="text-align:left;"> waterBody </th>
   <th style="text-align:left;"> islandGroup </th>
   <th style="text-align:left;"> island </th>
   <th style="text-align:left;"> country </th>
   <th style="text-align:left;"> countryCode </th>
   <th style="text-align:left;"> stateProvince </th>
   <th style="text-align:left;"> decimalLatitude </th>
   <th style="text-align:left;"> decimalLongitude </th>
   <th style="text-align:left;"> geodeticDatum </th>
   <th style="text-align:left;"> footprintWKT </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 014_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> All location fields are EMPTY. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_2 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Some location field have content </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_3 </td>
   <td style="text-align:left;"> https://opencontext.org/subjects/768A875F-E205-4D0B-DE55-BAB7598D0FD19 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY as there is a value in dwc:locationID </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> http://vocab.getty.edu/tgn/1002020 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Africa </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Southern Ocean </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_7 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Antipodes Islands </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_8 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Robinson Crusoe Island </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Eswatini </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Swaziland </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_11 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Yugoslavia </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_12 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Congo </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_13 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> GL </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_14 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> GRL </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_15 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> XX </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_16 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Austria </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_17 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> POLYGON ((10 20, 11 20, 11 21, 10 21, 10 20)) </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY: the one-degree bounding box with opposite corners at longitude=10, latitude=20 and longitude=11, latitude=21 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_18 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> San Isidro </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_19 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_20 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_21 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 41.0554 N </td>
   <td style="text-align:left;"> 121.0534 W </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_22 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 121.0534 </td>
   <td style="text-align:left;"> 181.0554 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_23 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> -99.2314 </td>
   <td style="text-align:left;"> -189.5674 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_24 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> -41.0525925872862 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_25 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> CL </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> -41.0525925872862 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_26 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> AR </td>
   <td style="text-align:left;"> Rio Negro </td>
   <td style="text-align:left;"> -41.0525925872862 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_27 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> AR </td>
   <td style="text-align:left;"> Neuquén </td>
   <td style="text-align:left;"> -41.0525925872862 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_28 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> México </td>
   <td style="text-align:left;"> MX </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 18.835941 </td>
   <td style="text-align:left;"> -94.4805934 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_29 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> -41.0525925872862 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;"> 4326 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_30 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 41.0525925872862 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;"> 4326 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 014_31 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> -41.0525925872862 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;"> 4326 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Location not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:locationID="https://opencontext.org/subjects/768A875F-E205-4D0B-DE55-BAB7598D0FD19", dwc:higherGeographyID="", dwc:higherGeography="",  dwc:continent="", dwc:waterBody="", dwc:islandGroup="", dwc:island="", dwc:country="", dwc:countryCode="", dwc:stateProvince="", dwc:county="", dwc:municipality="", dwc:locality="", dwc:verbatimLocality="", dwc:decimalLatitude="", dwc:decimalLongitude="", dwc:coordinateUncertaintyInMeters="", dwc:geodeticDatum="", dwc:verbatimCoordinates="", dwc:verbatimLatitude="", dwc:verbatimLongitude="": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="Location not EMPTY as there is a value in dwc:locationID"],[dwc:locationID="", dwc:higherGeographyID="", dwc:higherGeography="", dwc:continent="", dwc:waterBody="", dwc:islandGroup="", dwc:island="", dwc:country="", dwc:countryCode="", dwc:stateProvince="", dwc:county="", dwc:municipality="", dwc:locality="", dwc:verbatimLocality="", dwc:decimalLatitude="", dwc:decimalLongitude="", dwc:coordinateUncertaintyInMeters="", dwc:geodeticDatum="", dwc:verbatimCoordinates="", dwc:verbatimLatitude="", dwc:verbatimLongitude="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="All location fields are EMPTY."]

## Teste 015: [`AMENDMENT_DCTYPE_STANDARDIZED`](https://github.com/tdwg/bdq/issues/41) 

**Nome do teste**: `AMENDMENT_DCTYPE_STANDARDIZED` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/41 

**ID oficial do teste**: `bd385eeb-44a2-464b-a503-7abe407ef904` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Record-level` 

**Termos (colunas) testados**: `type` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Propose amendment to the value of dc:type using the DCMI type vocabulary._ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if the value of dc:type is EMPTY; AMENDED the value of dc:type if it can be unambiguously interpreted as a value in bdq:sourceAuthority; otherwise NOT_AMENDED bdq:sourceAuthority is "Dublin Core Metadata Initiative (DCMI)" {[https://www.dublincore.org/]} {DCMI Type Vocabulary" [https://www.dublincore.org/specifications/dublin-core/dcmi-type-vocabulary/]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 15: Termos testados e os resultados esperados para o teste AMENDMENT_DCTYPE_STANDARDIZED.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> type </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 015_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dc:type is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 015_2 </td>
   <td style="text-align:left;"> Event </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> The bdq:sourceAuthority was not available or was unreachable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 015_3 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dc:type contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 015_4 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dc:type contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 015_5 </td>
   <td style="text-align:left;"> evnt </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dc:type&quot;:&quot;Event&quot;} </td>
   <td style="text-align:left;"> dc:type contains an interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 015_6 </td>
   <td style="text-align:left;"> image </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dc:type&quot;:&quot;StillImage&quot;} </td>
   <td style="text-align:left;"> dc:type contains an interpretable value </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dc:type="evnt": Response.status=AMENDED, Response.result=dc:type="Event", Response.comment="dc:type contains an interpretable value"],[dc:type="X": Response.status=NOT_AMENDED, Response.result="", Response.comment="dc:type contains an uninterpretable value"]

## Teste 016: [`VALIDATION_COUNTRY_NOTEMPTY`](https://github.com/tdwg/bdq/issues/42) 

**Nome do teste**: `VALIDATION_COUNTRY_NOTEMPTY` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/42 

**ID oficial do teste**: `6ce2b2b4-6afe-4d13-82a0-390d31ade01c` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `country` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:country?_ 

**Especificação**: 
> _COMPLIANT if dwc:country is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _[geo_ref_qc DwCGeoRefDQ.validationCountryNotEmpty](https://github.com/FilteredPush/geo_ref_qc/blob/fcad4a3757db9bd6ba36fe41064ce015eeede2e3/src/main/java/org/filteredpush/qc/georeference/DwCGeoRefDQ.java#L478)_ 

**Notas**: _Country is expected to be empty if material comes from the high seas, or from those portions of Antartica outside of any sovereign nation._ 



<table>
<caption>Tabela 16: Termos testados e os resultados esperados para o teste VALIDATION_COUNTRY_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> country </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 016_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:country is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 016_2 </td>
   <td style="text-align:left;"> Eswatini </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 016_3 </td>
   <td style="text-align:left;"> Swaziland </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 016_4 </td>
   <td style="text-align:left;"> Yugoslavia </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 016_5 </td>
   <td style="text-align:left;"> Congo </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 016_6 </td>
   <td style="text-align:left;"> United States Minor Outlying Islands </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 016_7 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country is not EMPTY, string serializations of null are not empty. </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:country="Eswatini": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:country is not EMPTY"],[dwc:country="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:country is EMPTY"]

## Teste 017: [`AMENDMENT_COORDINATES_CONVERTED`](https://github.com/tdwg/bdq/issues/43) 

**Nome do teste**: `AMENDMENT_COORDINATES_CONVERTED` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/43 

**ID oficial do teste**: `620749b9-7d9c-4890-97d2-be3d1cde6da8` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `decimalLatitude, decimalLongitude, geodeticDatum, coordinateUncertaintyInMeters` 

**Pré-requisitos externos (parâmetros)**: `bdq:targetCRS` 

**Descrição**: 
> _Propose amendment to the value of dwc:geodeticDatum and potentially to dwc:decimalLatitude and/or dwc:decimalLongitude based on a conversion between coordinate reference systems._ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:decimalLatitude is EMPTY or does not have a valid value, or dwc:decimalLongitude is EMPTY or does not have a valid value, or dwc:geodeticDatum is EMPTY or does not contain an interpretable value; AMENDED if the values of dwc:decimalLatitude, dwc:decimalLongitude and dwc:geodeticDatum are changed based on a conversion between the coordinate reference systems as specified by dwc:geodeticDatum and bdq:targetCRS, and, if dwc:coordinateUncertaintyInMeters was an interpretable value, the uncertainty from the conversion is added to it, and the value of dwc:coordinatePrecision is provided from the conversion result; otherwise NOT_AMENDED. bdq:targetCRS default = "EPSG:4326" {[https://epsg.org]} {EPSG Endpoint for translations  [https://epsg.io/transform]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _This test relates only to EPSG codes applying to coordinate reference systems where the coordinate system is EPSG:6422 (Ellipsoidal 2D CS. Axes: latitude, longitude. Orientations: north, east. UoM: degree), or EPSG:6423 (Ellipsoidal 3D CS. Axes: latitude, longitude, ellipsoidal height. Orientations: north, east, up. UoM: degree, degree, metre.). Any amendment has implications for dwc:coordinateUncertaintyInMeters and dwc:coordinatePrecision. If the dwc:coordinateUncertaintyInMeters is EMPTY or is not interpretable, this amendment should not provide a dwc:coordinateUncertaintyInMeters. If the dwc:coordinateUncertaintyInMeters is not EMPTY and is valid, this amendment should add the uncertainty contributed by the conversion to the value of dwc:coordinateUncertaintyInMeters. The amended dwc:coordinatePrecision should be the precision of coordinates as provided after the conversion, ideally this should be 0.0000001, reflecting the seven digits of precision required to reverse a coordinate transformation without loss of information at the scale of one meter. If dwc:geodeticDatum specifies the same CRS for dwc:decimalLatitude and dwc:decimalLongitude as bdq:targetCRS (e.g., if dwc:geodeticDatum has either the value "WGS84" or "EPSG:4326" and the bdq:targetCRS is "EPSG:4326"), then the coordinates are assumed to be in the target CRS and the Response.status is NOT_AMENDED._ 



<table>
<caption>Tabela 17: Termos testados e os resultados esperados para o teste AMENDMENT_COORDINATES_CONVERTED.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> decimalLatitude </th>
   <th style="text-align:left;"> decimalLongitude </th>
   <th style="text-align:left;"> geodeticDatum </th>
   <th style="text-align:left;"> coordinateUncertaintyInMeters </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 017_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude, dwc:decimalLongitude, dwc:geodeticDatum are EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 017_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 139.923 </td>
   <td style="text-align:left;"> GDA94 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 017_3 </td>
   <td style="text-align:left;"> -23.721 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> GDA94 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLongitude is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 017_4 </td>
   <td style="text-align:left;"> -23.712 </td>
   <td style="text-align:left;"> 139.923 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:geodeticDatum is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 017_5 </td>
   <td style="text-align:left;"> -23.712 </td>
   <td style="text-align:left;"> 139.923 </td>
   <td style="text-align:left;"> GDX93 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:geodeticDatum does not have a match in bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 017_6 </td>
   <td style="text-align:left;"> -23.712 </td>
   <td style="text-align:left;"> 139.923 </td>
   <td style="text-align:left;"> AGD66 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:decimalLatitude&quot;:&quot;-23.7105001&quot;,&quot;dwc:decimalLongitude&quot;:&quot;139.924185&quot;,&quot;dwc:coordinateUncertaintyInMeters&quot;:&quot;&quot;,&quot;dwc:geodeticDatum&quot;:&quot;EPSG:4326&quot;,&quot;dwc:coordinatePrecision&quot;:&quot;6&quot;} </td>
   <td style="text-align:left;"> Input fields contain interpretable values: xform using &quot;https://epsg.io/transform#s_srs=4202&amp;t_srs=4326&amp;x=139.9230000&amp;y=-23.7120000&quot; </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 017_7 </td>
   <td style="text-align:left;"> -93.712 </td>
   <td style="text-align:left;"> 139.923 </td>
   <td style="text-align:left;"> GDA94 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude was out of range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 017_8 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> 139.923 </td>
   <td style="text-align:left;"> GDA94 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitide contains uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 017_9 </td>
   <td style="text-align:left;"> -23.712 </td>
   <td style="text-align:left;"> 139.923 </td>
   <td style="text-align:left;"> GDA94 </td>
   <td style="text-align:left;"> 50 </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:decimalLatitude&quot;:&quot;--23.7119864&quot;,&quot;dwc:decimalLongitude&quot;:&quot;139.9230077&quot;,&quot;dwc:coordinateUncertaintyInMeters&quot;:&quot;50&quot;,&quot;dwc:geodeticDatum&quot;:&quot;EPSG:4326&quot;,&quot;dwc:coordinatePrecision&quot;:&quot;7&quot;} </td>
   <td style="text-align:left;"> Input fields contain interpretable values: Xform from https://epsg.io/transform#s_srs=4939&amp;t_srs=4326&amp;x=139.9230000&amp;y=-23.7120000 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 017_10 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> 139.923 </td>
   <td style="text-align:left;"> GDA94 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Input fields contain interpretable values </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 017_11 </td>
   <td style="text-align:left;"> -10.671867 </td>
   <td style="text-align:left;"> 150.207555 </td>
   <td style="text-align:left;"> EPSG:5546 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:decimalLatitude&quot;:&quot;-10.671867&quot;,&quot;dwc:decimalLongitude&quot;:&quot;150.207555&quot;,&quot;dwc:coordinateUncertaintyInMeters&quot;:&quot;&quot;,&quot;dwc:geodeticDatum&quot;:&quot;EPSG:4326&quot;,&quot;dwc:coordinatePrecision&quot;:&quot;&quot;} </td>
   <td style="text-align:left;"> Input fields contain interpretable values: Xform from https://epsg.io/transform#s_srs=5546&amp;t_srs=4326&amp;x=150.2075550&amp;y=-10.6718670 </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:decimalLatitude="-23.712", dwc:decimalLongitude="139.923", dwc:geodeticDatum="AGD66", dwc:coordinateUncertaintyInMeters="", dwc:coordinatePrecision="": Response.status=AMENDED, Response.result=dwc:decimalLatitude="-23.7105001", dwc:decimalLongitude="139.924185", dwc:geodeticDatum="EPSG:4326", dwc:coordinateUncertaintyInMeters="", dwc:coordinatePrecision="6", Response.comment="Input fields contain interpretable values: xform using "https://epsg.io/transform#s_srs=4202&t_srs=4326&x=139.9230000&y=-23.7120000" "],[dwc:decimalLatitude="-93.712", dwc:decimalLongitude="139.923", dwc:geodeticDatum="GDA94", dwc:coordinateUncertaintyInMeters="", dwc:coordinatePrecision="": Response.status=NOT_AMENDED, Response.result=, Response.comment="dwc:decimalLatitude was out of range"]

## Teste 018: [`VALIDATION_SCIENTIFICNAME_FOUND`](https://github.com/tdwg/bdq/issues/46) 

**Nome do teste**: `VALIDATION_SCIENTIFICNAME_FOUND` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/46 

**ID oficial do teste**: `3f335517-f442-4b98-b149-1e87ff16de45` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `scientificName` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Is there a match of the contents of dwc:scientificName with bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:scientificName is EMPTY; COMPLIANT if there is a match of the contents of dwc:scientificName with the bdq:sourceAuthority; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "GBIF Backbone Taxonomy" {[https://doi.org/10.15468/39omei]} {API endpoint [https://api.gbif.org/v1/species?datasetKey=d7dddbf4-2cf0-4f39-9b2a-bb099caae36c&name=]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The purpose of this test is to detect errors in the scientific name but is dependent on the abilities of the parsing of the bdq:sourceAuthority. For research users of biodiversity data doing quality assurance, VALIDATION_TAXON_UNAMBIGUOUS (4c09f127-737b-4686-82a0-7c8e30841590) handles their needs, but for curators of data sets doing quality control, this test provides a specific subset of targeted data cleaning, making it a valuable test to include for the quality control case._ 



<table>
<caption>Tabela 18: Termos testados e os resultados esperados para o teste VALIDATION_SCIENTIFICNAME_FOUND.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> scientificName </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 018_1 </td>
   <td style="text-align:left;"> Eucalyptus gunnii </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> The bdq:sourceAuthority was not available or was unreachable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 018_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificName is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 018_3 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName was not found in bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 018_4 </td>
   <td style="text-align:left;"> Eucalyptus camaldulensis </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName found in bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 018_5 </td>
   <td style="text-align:left;"> Capulus intort </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName was not found in bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 018_6 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName was not found in bdq:sourceAuthority </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:scientificName="Eucalyptus camaldulensis": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:scientificName found in bdq:sourceAuthority"],[dwc:scientificName="Capulus intort": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:scientificName was not found in bdq:sourceAuthority"]

## Teste 019: [`VALIDATION_OCCURRENCEID_NOTEMPTY`](https://github.com/tdwg/bdq/issues/47) 

**Nome do teste**: `VALIDATION_OCCURRENCEID_NOTEMPTY` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/47 

**ID oficial do teste**: `c486546c-e6e5-48a7-b286-eba7f5ca56c4` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Occurrence` 

**Termos (colunas) testados**: `occurrenceID` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:occurrenceID?_ 

**Especificação**: 
> _COMPLIANT if dwc:occurrenceID is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 19: Termos testados e os resultados esperados para o teste VALIDATION_OCCURRENCEID_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> occurrenceID </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 019_1 </td>
   <td style="text-align:left;"> https://www.inaturalist.org/observations/43047701 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceID conforms to GUID structure </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 019_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceID is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 019_3 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceID is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 019_4 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceID is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 019_5 </td>
   <td style="text-align:left;"> --- </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceID is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 019_6 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceID is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:occurrenceID="https://www.inaturalist.org/observations/43047701": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:occurrenceID conforms to GUID structure"],[dwc:occurrenceID="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:occurrenceID is EMPTY"]

## Teste 020: [`AMENDMENT_COUNTRYCODE_STANDARDIZED`](https://github.com/tdwg/bdq/issues/48) 

**Nome do teste**: `AMENDMENT_COUNTRYCODE_STANDARDIZED` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/48 

**ID oficial do teste**: `fec5ffe6-3958-4312-82d9-ebcca0efb350` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `countryCode` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Propose amendment to the value of dwc:countryCode if it can be interpreted as an ISO country code._ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISTITES_NOT_MET if the value of dwc:countryCode is EMPTY; AMENDED the value of dwc:countryCode if it can be unambiguously interpreted from bdq:sourceAuthority; otherwise NOT_AMENDED bdq:sourceAuthority default = "ISO 3166 Country Codes" {[https://www.iso.org/iso-3166-country-codes.html]} {ISO 3166-1-alpha-2 Country Code search [https://www.iso.org/obp/ui/#search]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 20: Termos testados e os resultados esperados para o teste AMENDMENT_COUNTRYCODE_STANDARDIZED.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> countryCode </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 020_1 </td>
   <td style="text-align:left;"> 004 </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> The bdq:sourceAuthority was not available or was unreachable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 020_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:countryCode is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 020_3 </td>
   <td style="text-align:left;"> Australia </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:countryCode&quot;:&quot;AU&quot;} </td>
   <td style="text-align:left;"> dwc:countryCode contains an interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 020_4 </td>
   <td style="text-align:left;"> Aust. </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:countryCode contains an ambiguous value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 020_5 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:countryCode contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 020_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:countryCode is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 020_7 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:countryCode contains an uninterpretable value </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:countryCode="Australia": Response.status=AMENDED, Response.result=dwc:countryCode="AU", Response.comment="dwc:countryCode contains an interpretable value"],[dwc:countryCode="Aust.": Response.status=NOT_AMENDED, Response.result=, Response.comment="dwc:countryCode contains an ambiguous value"]

## Teste 021: [`VALIDATION_YEAR_NOTEMPTY`](https://github.com/tdwg/bdq/issues/49) 

**Nome do teste**: `VALIDATION_YEAR_NOTEMPTY` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/49 

**ID oficial do teste**: `c09ecbf9-34e3-4f3e-b74a-8796af15e59f` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `year` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:year?_ 

**Especificação**: 
> _COMPLIANT if dwc:year is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _event_date_qc v3.0.0 [DwCEventDQ.validationYearNotEmpty()](https://github.com/FilteredPush/event_date_qc/blob/v3.0.0/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L217)_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 21: Termos testados e os resultados esperados para o teste VALIDATION_YEAR_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> year </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 021_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 021_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 021_3 </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 021_4 </td>
   <td style="text-align:left;"> 194x </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 021_5 </td>
   <td style="text-align:left;"> 1952 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 021_6 </td>
   <td style="text-align:left;"> 9999 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 021_7 </td>
   <td style="text-align:left;"> 1599 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 021_8 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 021_9 </td>
   <td style="text-align:left;"> XXXX </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 021_10 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is not EMPTY, string serializations of null are not empty </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:year="1949": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:year is not EMPTY"],[dwc:year="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:year is EMPTY"]

## Teste 022: [`VALIDATION_COORDINATES_COUNTRYCODE_CONSISTENT`](https://github.com/tdwg/bdq/issues/50) 

**Nome do teste**: `VALIDATION_COORDINATES_COUNTRYCODE_CONSISTENT` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/50 

**ID oficial do teste**: `adb27d29-9f0d-4d52-b760-a77ba57a69c9` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `countryCode, decimalLatitude, decimalLongitude` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority,bdq:spatialBufferInMeters` 

**Descrição**: 
> _Do the geographic coordinates fall on or within the boundaries of the territory given in dwc:countryCode or its Exclusive Economic Zone?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if one or more of dwc:decimalLatitude, dwc:decimalLongitude, or dwc:countryCode are EMPTY or invalid; COMPLIANT if the geographic coordinates fall on or within the boundary defined by the union of the boundary of the country from dwc:countryCode plus it's Exclusive Economic Zone as found in the bdq:sourceAuthority, if any, plus an exterior buffer given by bdq:spatialBufferInMeters; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "ADM1 boundaries UNION with Exclusive Economic Zones" {[https://gadm.org] spatial UNION [https://marineregions.org]},bdq:spatialBufferInMeters default = "3000"_ 

**Código fonte de exemplo**: _https://github.com/FilteredPush/geo_ref_qc/blob/master/src/main/java/org/filteredpush/qc/georeference/DwCGeoRefDQ.java#L80_ 

**Notas**: _dwc:coordinatePrecicision and dwc:coordinateUncertaintyInMeters (if present) imply a potential displacement of the provided coordinates. These two terms can be considered spatial buffers. Likewise, country polygons cannot be 100% accurate at all scales (Dooley 2005), so a spatial buffer of the country boundaries is justified. Taking the spatial buffers into account does however greatly complicate both the logic and the implementation of such tests. The same applies to potential conversion of the Spatial Reference System (SRS) of dwc:decimalLatitude and dwc:decimalLongitude to the SRS used in the bdq:sourceAuthority._ 



<table>
<caption>Tabela 22: Termos testados e os resultados esperados para o teste VALIDATION_COORDINATES_COUNTRYCODE_CONSISTENT.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> countryCode </th>
   <th style="text-align:left;"> decimalLatitude </th>
   <th style="text-align:left;"> decimalLongitude </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 022_1 </td>
   <td style="text-align:left;"> AU </td>
   <td style="text-align:left;"> -30.0 </td>
   <td style="text-align:left;"> 130.0 </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> The bdq:sourceAuthority was not available or was unreachable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 022_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> All input fields EMPTY. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 022_3 </td>
   <td style="text-align:left;"> GL </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude and dwc:decimalLongitude EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 022_4 </td>
   <td style="text-align:left;"> GRL </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude and dwc:decimalLongitude EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 022_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:countryCode is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 022_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:countryCode is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 022_7 </td>
   <td style="text-align:left;"> CL </td>
   <td style="text-align:left;"> -41.0525925872862 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> Coordinates are in Argentina, not Chile </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 022_8 </td>
   <td style="text-align:left;"> AR </td>
   <td style="text-align:left;"> -41.0525925872862 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Coordinates match dwc:countryCode </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 022_9 </td>
   <td style="text-align:left;"> MX </td>
   <td style="text-align:left;"> 18.835941 </td>
   <td style="text-align:left;"> -94.4805934 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Coordinates match dwc:countryCode </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 022_10 </td>
   <td style="text-align:left;"> MX </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> -94.4805934 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude is not a valid numeric value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 022_11 </td>
   <td style="text-align:left;"> MX </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> -94.4805934 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 022_12 </td>
   <td style="text-align:left;"> MX </td>
   <td style="text-align:left;"> 18.835941 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLongitude is not a valid numeric value </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:countryCode="AR", dwc:decimalLatitude="-41.0525925872862", dwc:decimalLongitude="-71.5310546742521": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="Coordinates match dwc:countryCode"],[dwc:countryCode="CL", dwc:decimalLatitude="-41.0525925872862", dwc:decimalLongitude="-71.5310546742521": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="Coordinates are in Argentina, not Chile"],[dwc:countryCode="ZX", dwc:decimalLatitude="-41.0525925872862", dwc:decimalLongitude="-71.5310546742521": Response.status=INTERNAL_PREREQUISTES_NOT_MET, Response.comment="Input field contains invalid values - ZX is not a valid ISO 3166-1-alpha-2 country code"]

## Teste 023: [`VALIDATION_COORDINATES_TERRESTRIALMARINE`](https://github.com/tdwg/bdq/issues/51) 

**Nome do teste**: `VALIDATION_COORDINATES_TERRESTRIALMARINE` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/51 

**ID oficial do teste**: `b9c184ce-a859-410c-9d12-71a338200380` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `decimalLatitude, decimalLongitude, scientificName` 

**Pré-requisitos externos (parâmetros)**: `bdq:taxonIsMarine,bdq:geospatialLand,bdq:spatialBufferInMeters` 

**Descrição**: 
> _Does the marine/non-marine biome of a taxon from the bdq:sourceAuthority match the biome at the location given by the coordinates?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if either bdq:taxonomyIsMarine or bdq:geospatialLand are not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:dcientificName was EMPTY or the marine/non-marine status of the taxon is not interpretable from bdq:taxonomyIsMarine or the values of dwc:decimalLatitude or dwc:decimalLongitude are EMPTY; COMPLIANT if the taxon marine/non-marine status from bdq:taxonomyIsMarine matches the marine/non-marine status of dwc:decimalLatitude and dwc:decimalLongitude on the boundaries given by bdq:geospatialLand plus an exterior buffer given by bdq:spatialBufferInMeters; otherwise NOT_COMPLIANT bdq:taxonIsMarine default = "World Register of Marine Species (WoRMS") {[https://www.marinespecies.org/]} {Web service [https://www.marinespecies.org/aphia.php?p=webservice]},{bdq:geospatialLand default = The spatial union of "NaturalEarth 10m-physical-vectors for Land" [https://www.naturalearthdata.com/http//www.naturalearthdata.com/download/10m/physical/ne_10m_land.zip] and "NaturalEarth Minor Islands" [https://www.naturalearthdata.com/http//www.naturalearthdata.com/download/10m/physical/ne_10m_minor_islands.zip]},bdq:spatialBufferInMeters default = "3000"_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _dwc:coordinatePrecicision and dwc:coordinateUncertaintyInMeters (if present) imply a potential displacement of the provided coordinates. These two terms can be considered spatial buffers. Likewise, country polygons cannot be 100% accurate at all scales (Dooley 2005), so a spatial buffer of the country boundaries is justified. Taking the spatial buffers into account does however greatly complicate both the logic and the implementation of such tests. The same applies to potential conversion of the Spatial Reference System (SRS) of dwc:decimalLatitude and dwc:decimalLongitude to the SRS used in the bdq:sourceAuthority._ 



<table>
<caption>Tabela 23: Termos testados e os resultados esperados para o teste VALIDATION_COORDINATES_TERRESTRIALMARINE.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> decimalLatitude </th>
   <th style="text-align:left;"> decimalLongitude </th>
   <th style="text-align:left;"> scientificName </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 023_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> The bdq:sourceAuthority was not available or was unreachable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 023_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> All input fields EMPTY. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 023_3 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificName is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 023_4 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificName is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 023_5 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificName is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 023_6 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> The terrestrial/marine status of the value of dwc:scientificName is not intrerpretable from bdq:sourceAuthority[taxonomyismarine] </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 023_7 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;"> Brown ant </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> The terrestrial/marine status of the value of dwc:scientificName is not intrerpretable from bdq:sourceAuthority[taxonomyismarine] </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 023_8 </td>
   <td style="text-align:left;"> -42.8747 </td>
   <td style="text-align:left;"> 147.6489 </td>
   <td style="text-align:left;"> Choerocoris paganus </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is terrestrial and coordinates are on land </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 023_9 </td>
   <td style="text-align:left;"> 41.0554 N </td>
   <td style="text-align:left;"> 121.0534 W </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude cannot be interpreted as a number </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 023_10 </td>
   <td style="text-align:left;"> -41.0525925872862 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;"> Orcinus orca </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> The species is marine and the location is an inland lake. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 023_11 </td>
   <td style="text-align:left;"> 41.0525925872862 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;"> Puma concolor </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is terrestrial but coordinates are marine </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 023_12 </td>
   <td style="text-align:left;"> -41.0525925872862 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;"> Aegla neuquensis </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> The species is freshwater aquatic and the coordinates fall in a lake and thus COMPLIANT </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:decimalLatitude="-41.0525925872862", dwc:decimalLongitude="-71.5310546742521", dwc:scientificName="Aegla neuquensis": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="The species is freshwater aquatic and the coordinates fall in a lake and thus COMPLIANT"],[dwc:decimalLatitude="41.0525925872862", dwc:decimalLongitude="-71.5310546742521",  dwc:scientificName="Puma concolor": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:scientificName is terrestrial but coordinates are marine"]

## Teste 024: [`AMENDMENT_EVENT_FROM_EVENTDATE`](https://github.com/tdwg/bdq/issues/52) 

**Nome do teste**: `AMENDMENT_EVENT_FROM_EVENTDATE` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/52 

**ID oficial do teste**: `710fe118-17e1-440f-b428-88ba3f547d6d` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `eventDate, year, month, day` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Propose amendment to values in any of dwc:year, dwc:month, dwc:day, dwc:startDayOfYear or dwc:endDayOfYear from the content of dwc:eventDate._ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:eventDate is EMPTY or contains an invalid value according to ISO 8601-1; FILLED_IN (1) dwc:day from dwc:eventDate if dwc:day is EMPTY and dwc:eventDate has a precision of a day or finer and is within a single day, (2) dwc:month from dwc:eventDate if dwc:month is EMPTY and dwc:eventDate has a precision of a single month or finer and is within a single month, (3) dwc:year from dwc:eventDate if dwc:year is EMPTY and dwc:eventDate has a precision of a single year or finer and is within a single year, (4) dwc:startDayOfYear and dwc:endDayOfYear if they are EMPTY and dwc:eventDate has a precision of a day or better; otherwise NOT_AMENDED._ 

**Código fonte de exemplo**: _FilteredPush event_date_qc [DwCEventDQ.amendmentEventFromEventdate()](https://github.com/FilteredPush/event_date_qc/blob/89436b476975fb40ab2883c4e48717bdf957c0a8/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L2010) unit test in [DwcEventDQTest](https://github.com/FilteredPush/event_date_qc/blob/89436b476975fb40ab2883c4e48717bdf957c0a8/src/test/java/org/filteredpush/qc/date/DwcEventDQTest.java#L1569)_ 

**Notas**: _Only fields that are empty will be have changes proposed, and only if dwc:eventDate has a valid ISO 8601-1 date. The dwc:eventDate is the canonical form of the event date (it is the first trusted form). If event date does not contain a range,  dwc:startDayOfYear = dwc:endDayOfYear. Time (as compared to date) is not deemed a CORE component.  Note, see sequencing tests section of standards document, run this amendment after any other amendment which may affect dwc:eventDate_ 



<table>
<caption>Tabela 24: Termos testados e os resultados esperados para o teste AMENDMENT_EVENT_FROM_EVENTDATE.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> eventDate </th>
   <th style="text-align:left;"> year </th>
   <th style="text-align:left;"> month </th>
   <th style="text-align:left;"> day </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 024_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 024_2 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> eventDate contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 024_3 </td>
   <td style="text-align:left;"> 2023 </td>
   <td style="text-align:left;"> 2023 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> No amendments possible </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 024_4 </td>
   <td style="text-align:left;"> 2023-01-26 </td>
   <td style="text-align:left;"> 2023 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:startDayOfYear&quot;:&quot;26&quot;,&quot;dwc:month&quot;:&quot;1&quot;,&quot;dwc:day&quot;:&quot;26&quot;,&quot;dwc:endDayOfYear&quot;:&quot;26&quot;} </td>
   <td style="text-align:left;"> dwc:month, dwc:day, dwc:startDayOfyear and dwc:endDayOfYear filled in from dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 024_5 </td>
   <td style="text-align:left;"> 2023-01-26 </td>
   <td style="text-align:left;"> 2023 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> 26 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:startDayOfYear&quot;:&quot;26&quot;,&quot;dwc:endDayOfYear&quot;:&quot;26&quot;} </td>
   <td style="text-align:left;"> dwc:startDayOfyear and dwc:endDayOfYear filled in from dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 024_6 </td>
   <td style="text-align:left;"> 2007-03-01T13:00:00Z/2008-05-11T15:30:00Z </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:startDayOfYear&quot;:&quot;60&quot;,&quot;dwc:endDayOfYear&quot;:&quot;132&quot;} </td>
   <td style="text-align:left;"> filled in dwc:startDayOfYear and endDayOfYear. Dwc:eventDate spans more than one day, month and year </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 024_7 </td>
   <td style="text-align:left;"> 2007-03 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:year&quot;:&quot;2007&quot;,&quot;dwc:month&quot;:&quot;3&quot;} </td>
   <td style="text-align:left;"> dwc:eventDate contains interpretable values, assuming we treat dwc:eventDate as year-month </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 024_8 </td>
   <td style="text-align:left;"> 2021-10-29 </td>
   <td style="text-align:left;"> 2021 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:startDayOfYear&quot;:&quot;302&quot;,&quot;dwc:month&quot;:&quot;10&quot;,&quot;dwc:day&quot;:&quot;29&quot;,&quot;dwc:endDayOfYear&quot;:&quot;302&quot;} </td>
   <td style="text-align:left;"> dwc:eventDate contains an interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 024_9 </td>
   <td style="text-align:left;"> 2021-01-15/2021-02-02 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:startDayOfYear&quot;:&quot;15&quot;,&quot;dwc:year&quot;:&quot;2021&quot;,&quot;dwc:endDayOfYear&quot;:&quot;33&quot;} </td>
   <td style="text-align:left;"> Provided dwc:eventDate [2021-01-15/2021-02-02] represents a range of more than one day or has precision coarser than a day, can't fill in day.|Provided dwc:eventDate [2021-01-15/2021-02-02] spans more than one month, can't fill in dwc:month.|Added year [2021] from start month of eventDate [2021-01-15/2021-02-02].|Added startDayOfYear [15] from start day of eventDate [2021-01-15/2021-02-02].|Added endDayOfYear [33] from end day of eventDate [2021-01-15/2021-02-02]. </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:eventDate="2023-01-26",  dwc:year="2023", dwc:month="", dwc:day="", dwc:startDayOfYear="", dwc:endDayOfYear="": Response.status=FILLED_IN, Response.result= dwc:startDayOfYear="26", dwc:month="1", dwc:day="26",dwc:endDayOfYear="26", Response.comment="dwc:month, dwc:day, dwc:startDayOfyear and dwc:endDayOfYear filled in from dwc:eventDate"],[dwc:eventDate="2023",  dwc:year="2023", dwc:month="", dwc:day="", dwc:startDayOfYear="", dwc:endDayOfYear="": Response.status=NOT_AMENDED, Response.result=, Response.comment="No amendments possible"]

## Teste 025: [`AMENDMENT_COORDINATES_TRANSPOSED`](https://github.com/tdwg/bdq/issues/54) 

**Nome do teste**: `AMENDMENT_COORDINATES_TRANSPOSED` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/54 

**ID oficial do teste**: `f2b4a50a-6b2f-4930-b9df-da87b6a21082` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `countryCode, decimalLatitude, decimalLongitude` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Propose amendment of the signs of dwc:decimalLatitude and/or dwc:decimalLongitude to align the location with the dwc:countryCode._ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if any of dwc:decimalLatitude or dwc:decimalLongitude or dwc:countryCode are EMPTY; AMENDED dwc:decimalLatitude and dwc:decimalLongitude if the coordinates were transposed or one or more of the signs of the coordinates were reversed to align the location with dwc:countryCode; otherwise NOT_AMENDED_ 

**Código fonte de exemplo**: _https://github.com/FilteredPush/geo_ref_qc/blob/master/src/main/java/org/filteredpush/qc/georeference/DwCGeoRefDQ.java#L324_ 

**Notas**: _The dwc:geodeticDatum is not necessary for this test. The maximum positional shift between any geographic coordinate reference system and WGS84 is less than 6 km, so any hemisphere test that relies on a country code for consistency would not be affected by the potential shift.  The prior VALIDATION for this test is VALIDATION_COORDINATE_COUNTRYCODE_CONSISTENT (adb27d29-9f0d-4d52-b760-a77ba57a69c9)._ 



<table>
<caption>Tabela 25: Termos testados e os resultados esperados para o teste AMENDMENT_COORDINATES_TRANSPOSED.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> countryCode </th>
   <th style="text-align:left;"> decimalLatitude </th>
   <th style="text-align:left;"> decimalLongitude </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 025_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude, dwc:decimalLongitude and dwc:countryCode are EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 025_2 </td>
   <td style="text-align:left;"> ARB </td>
   <td style="text-align:left;"> 12.5 </td>
   <td style="text-align:left;"> 70 </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:decimalLongitude&quot;:&quot;-70.0&quot;} </td>
   <td style="text-align:left;"> dwc:decimalLongitude sign reversed to align with dwc:countryCode Aruba </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 025_3 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 25.46 </td>
   <td style="text-align:left;"> 135.87 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:countryCode is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 025_4 </td>
   <td style="text-align:left;"> AU </td>
   <td style="text-align:left;"> 25.46 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLongitude is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 025_5 </td>
   <td style="text-align:left;"> AU </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 135.87 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 025_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 25.46 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLongitude and dwc:countryCode are EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 025_7 </td>
   <td style="text-align:left;"> AX </td>
   <td style="text-align:left;"> 25.46 </td>
   <td style="text-align:left;"> 135.87 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:countryCode is uninterpretable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 025_8 </td>
   <td style="text-align:left;"> AU </td>
   <td style="text-align:left;"> 25.46 </td>
   <td style="text-align:left;"> 185.87 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLongitude is out of range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 025_9 </td>
   <td style="text-align:left;"> AU </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> 135.87 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 025_10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 25.46 </td>
   <td style="text-align:left;"> 135.87 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:countryCode is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 025_11 </td>
   <td style="text-align:left;"> AU </td>
   <td style="text-align:left;"> 25.46 </td>
   <td style="text-align:left;"> 135.87 </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:decimalLatitude&quot;:&quot;-25.46&quot;} </td>
   <td style="text-align:left;"> Input fields contain interpretable values </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:decimalLatitude="25.46", dwc:decimalLongitude="135.87", dwc:countryCode="AU": Response.status=AMENDED, Response.result=dwc:decimalLatitude="-25.46", Response.comment="Input fields contain interpretable values"],[dwc:decimalLatitude="25.46", dwc:decimalLongitude="135.87", dwc:countryCode="": Response.status=NOT_AMENDED, Response.result="", Response.comment="dwc:countryCode is EMPTY"]

## Teste 026: [`AMENDMENT_MINDEPTH-MAXDEPTH_FROM_VERBATIM`](https://github.com/tdwg/bdq/issues/55) 

**Nome do teste**: `AMENDMENT_MINDEPTH-MAXDEPTH_FROM_VERBATIM` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/55 

**ID oficial do teste**: `c5658b83-4471-4f57-9d94-bf7d0a96900c` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `minimumDepthInMeters, maximumDepthInMeters, verbatimDepth` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Propose amendments of the values of dwc:minimumDepthInMeters and/or dwc:maximumDepthInMeters if they can be interpreted from dwc:verbatimDepth._ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:verbatimDepth is EMPTY or the value is not unambiguously interpretable or dwc:minimumDepthInMeters and dwc:maximumDepthInMeters are not EMPTY; FILLED_IN the value of dwc:minimumDepthInMeters and/or dwc:maximumDepthInMeters if they could be unambiguously determined from dwc:verbatimDepth; otherwise NOT_AMENDED_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _If the dwc:verbatimDepth has a single value rather than a range, the minimum and maximum values should be amended with the same value._ 



<table>
<caption>Tabela 26: Termos testados e os resultados esperados para o teste AMENDMENT_MINDEPTH-MAXDEPTH_FROM_VERBATIM.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> minimumDepthInMeters </th>
   <th style="text-align:left;"> maximumDepthInMeters </th>
   <th style="text-align:left;"> verbatimDepth </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 026_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimDepth is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 026_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimDepth does not conatin an interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 026_3 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimDepth contains an uninterpretable value. &quot;x&quot; is ambiguous as either &quot;10&quot; or &quot;No&quot; or &quot;unknown&quot; </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 026_4 </td>
   <td style="text-align:left;"> 25 </td>
   <td style="text-align:left;"> 100 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Output fields are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 026_5 </td>
   <td style="text-align:left;"> 11 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Min depth 10m </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Input and output fields are conflicting </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 026_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 11 </td>
   <td style="text-align:left;"> Max depth 100m </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Input and output fields are conflicting </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 026_7 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 11 </td>
   <td style="text-align:left;"> Min depth 10m </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:minimumDepthInMeters&quot;:&quot;10&quot;} </td>
   <td style="text-align:left;"> dwc:verbatimDepth contains an interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 026_8 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 10feet </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:maximumDepthInMeters&quot;:&quot;3.048&quot;,&quot;dwc:minimumDepthInMeters&quot;:&quot;3.048&quot;} </td>
   <td style="text-align:left;"> dwc:verbatimDepth contains interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 026_9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Mindepth 10m, maxdepth=100 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:maximumDepthInMeters&quot;:&quot;100&quot;,&quot;dwc:minimumDepthInMeters&quot;:&quot;10&quot;} </td>
   <td style="text-align:left;"> dwc:verbatimDepth contains interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 026_10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 25.8-34.9m </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:maximumDepthInMeters&quot;:&quot;34.9&quot;,&quot;dwc:minimumDepthInMeters&quot;:&quot;25.8&quot;} </td>
   <td style="text-align:left;"> dwc:verbatimDepth contains interpretable values </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:minimumDepthInMeters="", dwc:maximumDepthInMeters="11", dwc:verbatimDepth="Min depth 10m": Response.status=FILLED_IN, Response.result=dwc:minimumDepthInMeters="10", Response.comment="dwc:verbatimDepth contains an interpretable value"],[dwc:minimumDepthInMeters="",  dwc:maximumDepthInMeters="11", dwc:verbatimDepth="Max depth 100m": Response.status=NOT_AMENDED, Response.result="", Response.comment="Input and output fields are conflicting"]

## Teste 027: [`VALIDATION_COORDINATES_STATE-PROVINCE_CONSISTENT`](https://github.com/tdwg/bdq/issues/56) 

**Nome do teste**: `VALIDATION_COORDINATES_STATE-PROVINCE_CONSISTENT` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/56 

**ID oficial do teste**: `f18a470b-3fe1-4aae-9c65-a6d3db6b550c` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `stateProvince, decimalLatitude, decimalLongitude, geodeticDatum` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority,bdq:spatialBufferInMeters` 

**Descrição**: 
> _Do the geographic coordinates fall on or within the boundary from the bdq:sourceAuthority for the given dwc:stateProvince or within the distance given by bdq:spatialBufferInMeters outside that boundary?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority was not available; INTERNAL_PREREQUISITES_NOT_MET if the values of dwc:decimalLatitude, dwc:decimalLongitude, or dwc:stateProvince are EMPTY or invalid; COMPLIANT if the geographic coordinates fall on or within the boundary from the bdq:sourceAuthority for the given dwc:stateProvince (after coordinate reference system transformations, if any, have been accounted for), or within the distance given by bdq:spatialBufferInMeters outside that boundary; otherwise NOT_COMPLIANT. bdq:sourceAuthority default = "ADM1 boundaries" {[https://gadm.org]},bdq:spatialBufferInMeters default = "3000"_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The geographic determination service is expected to return a list of names of first-level administrative divisions for geometries that the geographic point falls on or within, including a 3 km buffer around the administrative geometry. A match on any of those names should constitute a consistency, and dwc:countryCode should not be needed to make this determination, that is, this test does not attempt to disambiguate potential duplicate first-level administrative division names. The level of buffering may be related to the scale of the underlying GIS layer being used. At a global scale, typical map scales used for borders and coastal areas are either 1:3M or 1:1M (Dooley 2005, Chapter 4). Horizontal accuracy at those scales is around 1.5-2.5km and 0.5-0.85 km respectively (Chapman & Wieczorek 2020)._ 



<table>
<caption>Tabela 27: Termos testados e os resultados esperados para o teste VALIDATION_COORDINATES_STATE-PROVINCE_CONSISTENT.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> stateProvince </th>
   <th style="text-align:left;"> decimalLatitude </th>
   <th style="text-align:left;"> decimalLongitude </th>
   <th style="text-align:left;"> geodeticDatum </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 027_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority was not available or was unreachable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 027_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> All input fields EMPTY. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 027_3 </td>
   <td style="text-align:left;"> San Isidro </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude, dwc:decimalLongitude and dwc:geodeticDatum are EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 027_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:stateProvince is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 027_5 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:stateProvince is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 027_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:stateProvince is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 027_7 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:stateProvince is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 027_8 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:stateProvince is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 027_9 </td>
   <td style="text-align:left;"> Tasmania </td>
   <td style="text-align:left;"> -42.85 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLongitude is not an interpretable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 027_10 </td>
   <td style="text-align:left;"> Tasmania </td>
   <td style="text-align:left;"> -42.85 </td>
   <td style="text-align:left;"> -147.645 </td>
   <td style="text-align:left;"> GDA94 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Input fields contain interpretable values </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 027_11 </td>
   <td style="text-align:left;"> Rio Negro </td>
   <td style="text-align:left;"> -41.0525925872862 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> Input fields contain interpretable values </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 027_12 </td>
   <td style="text-align:left;"> Taswegion </td>
   <td style="text-align:left;"> -42.85 </td>
   <td style="text-align:left;"> -147.645 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:stateProvince is not a valid value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 027_13 </td>
   <td style="text-align:left;"> Neuquén </td>
   <td style="text-align:left;"> -41.0525925872862 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> Input fields contain interpretable values but coordinates don't match dwc:stateProvince </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:stateProvince="Rio Negro", dwc:decimalLatitude="-41.0525925872862", dwc:decimalLongitude="-71.5310546742521", dwc:geodeticDatum="": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="Input fields contain interpretable values"],[dwc:stateProvince="Neuquén", dwc:decimalLatitude="-41.0525925872862", dwc:decimalLongitude="-71.5310546742521", dwc:geodeticDatum="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="Input fields contain interpretable values but coordinates don't match dwc:stateProvince"],[dwc:stateProvince="Neuquén", dwc:decimalLatitude="-141.0525925872862", dwc:decimalLongitude="-71.5310546742521", dwc:geodeticDatum="": Response.status=INTERNAL_PREREQUISTES_NOT_MET, Response.comment="Input field contain invalid value"]

## Teste 028: [`AMENDMENT_SCIENTIFICNAMEID_FROM_TAXON`](https://github.com/tdwg/bdq/issues/57) 

**Nome do teste**: `AMENDMENT_SCIENTIFICNAMEID_FROM_TAXON` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/57 

**ID oficial do teste**: `431467d6-9b4b-48fa-a197-cd5379f5e889` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `scientificNameID, scientificName, kingdom, phylum, class, family, genus, genericName, specificEpithet, taxonRank, scientificNameAuthorship, vernacularName` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Propose amendment to the value of dwc:scientificNameID if it can be unambiguously resolved from bdq:sourceAuthority using the available taxon terms._ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available;  INTERNAL_PREREQUISITES_NOT_MET if dwc:scientificNameID is not EMPTY or if all of dwc:scientificName, dwc:genericName, dwc:specificEpithet, dwc:infraspecificEpithet, dwc:scientificNameAuthorship, and dwc:cultivarEpithet are EMPTY, FILLED_IN the value of dwc:scientificNameID for an unambiguously resolved single taxon record in the bdq:sourceAuthority through (1) the value of dwc:scientificName or (2) if dwc:scientificName is EMPTY through values of the terms dwc:genericName, dwc:specificEpithet, dwc:infraspecificEpithet, dwc:scientificNameAuthorship and dwc:cultivarEpithet, or (3) if ambiguity produced by multiple matches in (1) or (2) can be disambiguated to a single Taxon using the values of dwc:subtribe, dwc:tribe, dwc:subgenus, dwc:genus, dwc:subfamily, dwc:family, dwc:superfamily, dwc:order, dwc:class, dwc:phylum, dwc:kingdom, dwc:higherClassification, dwc:taxonID, dwc:acceptedNameUsageID, dwc:originalNameUsageID, dwc:taxonConceptID, dwc:taxonomicRank, and dwc:vernacularName; otherwise NOT_AMENDED bdq:sourceAuthority default = "GBIF Backbone Taxonomy" {[https://doi.org/10.15468/39omei]} {API endpoint [https://api.gbif.org/v1/species?datasetKey=d7dddbf4-2cf0-4f39-9b2a-bb099caae36c&name=]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Return a result with no value and a Result.status of NOT_AMENDED with a Response.comment of ambiguous if the information provided does not resolve to a unique result (e.g. if homonyms exist and there is insufficient information in the provided data, for example using the lowest ranking taxa in conjunction with dwc:dwc:scientificNameAuthorship, to resolve them).  When referencing a GBIF taxon by GBIF's identifier for that taxon, use the the pseudo-namespace "gbif:" and the form "gbif:{integer}" as the value for dwc:scientificNameID._ 



<table>
<caption>Tabela 28: Termos testados e os resultados esperados para o teste AMENDMENT_SCIENTIFICNAMEID_FROM_TAXON.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> scientificNameID </th>
   <th style="text-align:left;"> scientificName </th>
   <th style="text-align:left;"> kingdom </th>
   <th style="text-align:left;"> phylum </th>
   <th style="text-align:left;"> class </th>
   <th style="text-align:left;"> family </th>
   <th style="text-align:left;"> genus </th>
   <th style="text-align:left;"> genericName </th>
   <th style="text-align:left;"> specificEpithet </th>
   <th style="text-align:left;"> taxonRank </th>
   <th style="text-align:left;"> scientificNameAuthorship </th>
   <th style="text-align:left;"> vernacularName </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 028_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificName, dwc:genericName, dwc:specificEpithet, dwc:infraspecificEpithet, dwc:scientificNameAuthorship, and dwc:cultivarEpithet are EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> All relevant taxon fields are EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_3 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificNameID is NOT_EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_4 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> Eucalyptus camaldulensis </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Red River Gum </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificNameID is NOT_EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_5 </td>
   <td style="text-align:left;"> https://api.gbif.org/v1/species?name=Puma%20concord </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificNameID is NOT_EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Chicoreus palmarosae (Lamarck, 1822) </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Mollusca </td>
   <td style="text-align:left;"> Gastropoda </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> palmarosae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> (Lamarck, 1822) </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority unavailable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_7 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Chicoreus palmarosae (Lamarck, 1822) </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Mollusca </td>
   <td style="text-align:left;"> Gastropoda </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> palmarosae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> (Lamarck, 1822) </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:scientificNameID&quot;:&quot;urn:lsid:marinespecies.org:taxname:208134&quot;} </td>
   <td style="text-align:left;"> dwc:scientificName matched to unique taxon record in WoRMS, exact match on name and authorship.  Resolvable at https://marinespecies.org/aphia.php?p=taxdetails&amp;id=208134 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_8 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Chicoreus palmarosae (Lamarck) </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Mollusca </td>
   <td style="text-align:left;"> Gastropoda </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> palmarosae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> (Lamarck) </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:scientificNameID&quot;:&quot;urn:lsid:marinespecies.org:taxname:208134&quot;} </td>
   <td style="text-align:left;"> dwc:scientificName matched to unique taxon record in WoRMS, exact match on name and partial match on authorship.  Resolvable at https://marinespecies.org/aphia.php?p=taxdetails&amp;id=208134 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Chicoreus palmarosae (L., 1822) </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Mollusca </td>
   <td style="text-align:left;"> Gastropoda </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> palmarosae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> (L., 1822) </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:scientificNameID&quot;:&quot;urn:lsid:marinespecies.org:taxname:208134&quot;} </td>
   <td style="text-align:left;"> dwc:scientificName matched to unique taxon record in WoRMS, exact match on name and match on authorship with common abbreviation.  Resolvable at https://marinespecies.org/aphia.php?p=taxdetails&amp;id=208134 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Triplex rosaria Perry, 1811 </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Mollusca </td>
   <td style="text-align:left;"> Gastropoda </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> Triplex </td>
   <td style="text-align:left;"> rosarium </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Perry, 1811 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:scientificNameID&quot;:&quot;urn:lsid:marinespecies.org:taxname:406078&quot;} </td>
   <td style="text-align:left;"> dwc:scientificName matched to unique taxon record in WoRMS, unique fuzzy match on name and exact match on authorship.  Resolvable at https://marinespecies.org/aphia.php?p=taxdetails&amp;id=406078 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_11 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Graphis </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificName=&quot;Graphis&quot; is ambiguous as could be either a lichen or a gastropod. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_12 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Graphis </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Adanson, 1763 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:scientificNameID&quot;:&quot;urn:lsid:irmng.org:taxname:1361721&quot;} </td>
   <td style="text-align:left;"> dwc:scientificName=&quot;Graphis&quot; is ambigous but can be disambiguated to a single taxon by the value in dwc:scientificNameAuthorship=&quot;Adanson, 1763&quot; identifying the taxon as a lichen </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_13 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Eucalyptus Cam. </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Species </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificName is ambiguous. The &quot;cam&quot; specific epithet could refer to Eucalyptus cambageana, Eucalyptus cameronii, Eucalyptus camfieldii, Eucalyptus campanulata, Eucalyptus campaspe or Eucalyptus camphora </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_14 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Graphis </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Jeffreys, 1867 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:scientificNameID&quot;:&quot;urn:lsid:irmng.org:taxname:1361722&quot;} </td>
   <td style="text-align:left;"> dwc:scientificName=&quot;Graphis&quot; is ambigous but can be disambiguated to a single taxon by the value in dwc:scientificNameAuthorship=&quot;Jeffreys, 1867&quot; identifying the taxon as a gastropod </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_15 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Graphis </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:scientificNameID&quot;:&quot;urn:lsid:marinespecies.org:taxname:137787&quot;} </td>
   <td style="text-align:left;"> dwc:scientificName=&quot;Graphis&quot; is ambigous but can be disambiguated to a single taxon by the value in dwc:kingdom=Animalia&quot; identifying the taxon as a gastropod </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_16 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Graphis </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Lecanoromycetes </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:scientificNameID&quot;:&quot;gbif:2602041&quot;} </td>
   <td style="text-align:left;"> dwc:scientificName=&quot;Graphis&quot; is ambigous but can be disambiguated to a single taxon by the value in dwc:class=Lecanoromycetes&quot; identifying the taxon as a lichen. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_17 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Chicoreus palmarosae (Lamarck, 1822) </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Mollusca </td>
   <td style="text-align:left;"> Gastropoda </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> palmarosae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> (Lamarck, 1822) </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:scientificNameID&quot;:&quot;gbif:4365662&quot;} </td>
   <td style="text-align:left;"> dwc:scientificName matched to unique taxon record in GBIF Backbone, exact match on name and authorship.  Resolvable at https://marinespecies.org/aphia.php?p=taxdetails&amp;id=208134 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_18 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Triplex rosarium Perry, 1811 </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Mollusca </td>
   <td style="text-align:left;"> Gastropoda </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> Triplex </td>
   <td style="text-align:left;"> rosarium </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Perry, 1811 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificName matched to unique taxon record in GBIF, unique fuzzy match on name (Triplex Rosaria) and exact match on authorship. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_19 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Graphis Jeffreys, 1867 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Jeffreys, 1867 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:scientificNameID&quot;:&quot;gbif:2300979&quot;} </td>
   <td style="text-align:left;"> dwc:scientificName=&quot;Graphis&quot; is ambigous but can be disambiguated to a single taxon by the value in dwc:scientificNameAuthorship=&quot;Jeffreys, 1867&quot; identifying the taxon as a gastropod </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 028_20 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Graphis Adans., 1763 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Adans., 1763 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:scientificNameID&quot;:&quot;gbif:2602041&quot;} </td>
   <td style="text-align:left;"> dwc:scientificName=&quot;Graphis&quot; is ambigous but can be disambiguated to a single taxon by the value in dwc:scientificNameAuthorship=&quot;Adans., 1763&quot; identifying the taxon as a lichen </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:taxonID="", dwc:scientificNameID="", dwc:acceptedNameUsageID="", dwc:originalNameUsageID="", dwc:taxonConceptID="", dwc:scientificName="Chicoreus palmarosae (Lamarck, 1822)", dwc:higherClassification="", dwc:kingdom="Animalia", dwc:phylum="Mollusca", dwc:class="Gastropoda", dwc:order="", dwc:family="Muricidae", dwc:subfamily="", dwc:genus="Chicoreus", dwc:genericName="Chicoreus", dwc:subgenus="", dwc:infragenericEpithet="", dwc:specificEpithet="palmarosae", dwc:infraspecificEpithet="", dwc:cultivarEpithet="", dwc:vernacularName="", dwc:scientificNameAuthorship="(Lamarck, 1822)", dwc:taxonRank="", bdq:sourceAuthority=”marinespecies.org”: Response.status=FILLED_IN, Response.result=dwc:scientificNameID="urn:lsid:marinespecies.org:taxname:208134", Response.comment="dwc:scientificName matched to unique taxon record in WoRMS, exact match on name and authorship.  Resolvable at https://marinespecies.org/aphia.php?p=taxdetails&id=208134"],[dwc:taxonID="", dwc:scientificNameID="", dwc:acceptedNameUsageID="", dwc:originalNameUsageID="", dwc:taxonConceptID="", dwc:scientificName="Graphis", dwc:higherClassification="", dwc:kingdom="", dwc:phylum="", dwc:class="", dwc:order="", dwc:family="", dwc:subfamily="", dwc:genus="", dwc:genericName="", dwc:subgenus="", dwc:infragenericEpithet="", dwc:specificEpithet="", dwc:infraspecificEpithet="", dwc:cultivarEpithet="", dwc:vernacularName="", dwc:scientificNameAuthorship="", dwc:taxonRank="": Response.status=NOT_AMENDED, Response.result="", Response.comment="dwc:scientificName="Graphis" is ambiguous as could be either a lichen or a gastropod."]

## Teste 029: [`VALIDATION_BASISOFRECORD_NOTEMPTY`](https://github.com/tdwg/bdq/issues/58) 

**Nome do teste**: `VALIDATION_BASISOFRECORD_NOTEMPTY` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/58 

**ID oficial do teste**: `ac2b7648-d5f9-48ca-9b07-8ad5879a2536` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Record-level` 

**Termos (colunas) testados**: `basisOfRecord` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:basisOfRecord?_ 

**Especificação**: 
> _COMPLIANT if dwc:basisOfRecord is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 29: Termos testados e os resultados esperados para o teste VALIDATION_BASISOFRECORD_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> basisOfRecord </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 029_1 </td>
   <td style="text-align:left;"> PreservedSpecimen </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 029_2 </td>
   <td style="text-align:left;"> PreservedSpec </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 029_3 </td>
   <td style="text-align:left;"> anyOldTerm </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 029_4 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 029_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 029_6 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 029_7 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord is EMPTY or Missing </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 029_8 </td>
   <td style="text-align:left;"> dwc:basisOfRecord </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:basisOfRecord="PreservedSpecimen": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:basisOfRecord is not EMPTY"],[dwc:basisOfRecord="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:basisOfRecord is EMPTY"]

## Teste 030: [`VALIDATION_GEODETICDATUM_STANDARD`](https://github.com/tdwg/bdq/issues/59) 

**Nome do teste**: `VALIDATION_GEODETICDATUM_STANDARD` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/59 

**ID oficial do teste**: `7e0c0418-fe16-4a39-98bd-80e19d95b9d1` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `geodeticDatum` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Does the value of dwc:geodeticDatum occur as a valid geographic CRS, Datum or ellipsoid in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available, INTERNAL_PREREQUISITES_NOT_MET if dwc:geodeticDatum is EMPTY; COMPLIANT if the value of dwc:geodeticDatum is (1) "not recorded" or (2) a valid geographic EPSG code for a CRS, Datum, or ellipsoid; otherwise NOT_COMPLIANT bdq:sourceAuthority = "EPSG" {[https://epsg.org]} {API for EPSG codes [https://apps.epsg.org/api/swagger/ui/index#/Datum]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Darwin Core recommends best practice is to a controlled vocabulary. Chapman and Wieczorek (2020) recommend the use the EPSG code for the Coordinate Reference System as the controlled vocabulary, if known. If the EPSG code is not known, use the value "not recorded".  This test must return NOT_COMPLIANT if there is leading or trailing whitespace or there are leading or trailing non-printing characters.  Chapman and Wieczorek (2020) recommend best practice is to use EPSG geographic CRS or Datum codes (https://epsg.io/) as a controlled vocabulary. Ideally, amend to the EPSG code for the geographic coordinate reference system (CRS), if known. Otherwise use the EPSG code for the geodetic datum, if known. Otherwise use the EPSG code of the ellipsoid, if known. If none of these is known, use the explicit value "not recorded". The reference vocabularies of values for geodetic datums and ellipsoids needs to be made available should map alternative representations of dwc:geodeticDatum strings to EPSG codes, such as "WGS84", "WGS_84", "WGS:84", "WGS 84" all with standard value "epsg:4326"._ 



<table>
<caption>Tabela 30: Termos testados e os resultados esperados para o teste VALIDATION_GEODETICDATUM_STANDARD.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> geodeticDatum </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 030_1 </td>
   <td style="text-align:left;"> GDA94 </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority is unavailable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 030_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:geodeticDatum is EMPTY. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 030_3 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum doesn't match values in bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 030_4 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum doesn't match values in bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 030_5 </td>
   <td style="text-align:left;"> UTM </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum doesn't match values in bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 030_6 </td>
   <td style="text-align:left;"> WGS84 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum matches an unambiguous alphanumeric CRS or datum code value in bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 030_7 </td>
   <td style="text-align:left;"> EPSG:4326 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum matches an unambiguous alphanumeric CRS or datum code value in bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 030_8 </td>
   <td style="text-align:left;"> 6326 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum matches an unambiguous alphanumeric CRS or datum code value in bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 030_9 </td>
   <td style="text-align:left;"> 7030 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum doesn't match values in bdq:sourceAuthority, 1730 (EPSG:1730) is an ellipsoid not a datum </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 030_10 </td>
   <td style="text-align:left;"> EPSG:23032 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum matches an unambiguous alphanumeric CRS or datum code value in bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 030_11 </td>
   <td style="text-align:left;"> ED50 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum matches an unambiguous alphanumeric CRS or datum code value in bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 030_12 </td>
   <td style="text-align:left;"> International 1924 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum doesn't match values in bdq:sourceAuthority. International 1924 is an Ellipsoid not a Datum </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 030_13 </td>
   <td style="text-align:left;"> 4326 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum matches an unambiguous alphanumeric CRS or datum code value in bdq:sourceAuthority </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:geodeticDatum="6326": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:geodeticDatum matches an unambiguous alphanumeric CRS or datum code value in bdq:sourceAuthority"],[dwc:geodeticDatum="7030": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:geodeticDatum doesn't match values in bdq:sourceAuthority, 1730 (EPSG:1730) is an ellipsoid not a datum"]

## Teste 031: [`AMENDMENT_GEODETICDATUM_STANDARDIZED`](https://github.com/tdwg/bdq/issues/60) 

**Nome do teste**: `AMENDMENT_GEODETICDATUM_STANDARDIZED` 

**Última atualização**: `2023-09-17` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/60 

**ID oficial do teste**: `0345b325-836d-4235-96d0-3b5caf150fc0` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `geodeticDatum` 

**Pré-requisitos externos (parâmetros)**: `dwc:geodeticDatum vocabulary` 

**Descrição**: 
> _Propose amendment to the value of dwc:geodeticDatum using bdq:sourceAuthority._ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority was not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:geodeticDatum is EMPTY; AMENDED the value of dwc:geodeticDatum if it could be unambiguously interpreted as a value in bdq:sourceAuthority; otherwise NOT_AMENDED bdq:sourceAuthority = "EPSG" {[https://epsg.org]} {dwc:geodeticDatum vocabulary [https://media.githubusercontent.com/media/VertNet/DwCVocabs/master/vocabs/geodeticDatum.csv]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Chapman and Wieczorek (2020) recommend best practice is to use EPSG codes (https://epsg.io) as a controlled vocabulary. Ideally, amend to the EPSG code for the geographic coordinate reference system (CRS), if known. Otherwise use the EPSG code for the geodetic datum, if known. Otherwise use the EPSG code of the ellipsoid, if known. If none of these is known, use the explicit value "not recorded". The reference vocabularies of values for geodetic datums and ellipsoids needs to be made available should map alternative representations of dwc:geodeticDatum strings to EPSG codes, such as "WGS84", "WGS_84", "WGS:84", "WGS 84" all with standard value "epsg:4326"._ 



<table>
<caption>Tabela 31: Termos testados e os resultados esperados para o teste AMENDMENT_GEODETICDATUM_STANDARDIZED.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> geodeticDatum </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 031_1 </td>
   <td style="text-align:left;"> AnyDatum </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority unavailable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 031_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:geodeticDatum is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 031_3 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:geodeticDatum contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 031_4 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:geodeticDatum contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 031_5 </td>
   <td style="text-align:left;"> WGS8 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:geodeticDatum contains an ambiguous value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 031_6 </td>
   <td style="text-align:left;"> WGS84 </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:geodeticDatum&quot;:&quot;EPSG:4326&quot;} </td>
   <td style="text-align:left;"> dwc:geodeticDatum contains a valid code in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 031_7 </td>
   <td style="text-align:left;"> EPSG:4326 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:geodeticDatum contains a valid code in the bdq:sourceAuthority </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:geodeticDatum="WGS84": Response.status=AMENDED, Response.result=dwc:geodeticDatum="EPSG:4326", Response.comment="dwc:geodeticDatum contains a valid code in the bdq:sourceAuthority"],[dwc:geodeticDatum="WGS8": Response.status=NOT_AMENDED, Response.result="", Response.comment="dwc:geodeticDatum contains an ambiguous value"]

## Teste 032: [`AMENDMENT_EVENTDATE_STANDARDIZED`](https://github.com/tdwg/bdq/issues/61) 

**Nome do teste**: `AMENDMENT_EVENTDATE_STANDARDIZED` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/61 

**ID oficial do teste**: `718dfc3c-cb52-4fca-b8e2-0e722f375da7` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `eventDate` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Propose amendment of the value of dwc:eventDate to a valid ISO date._ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:eventDate is EMPTY; AMENDED if the value of dwc:eventDate was not a properly formatted ISO 8601-1 date but was unambiguous, and was altered to be a valid ISO 8601-1 date; otherwise NOT_AMENDED_ 

**Código fonte de exemplo**: _event_date_qc [DwCEventDQ.amendmentEventdateStandardized()](https://github.com/FilteredPush/event_date_qc/blob/v3.0.0/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L545) A minimal set of unit tests is in [DwCEventDQTestDefinitions](https://github.com/FilteredPush/event_date_qc/blob/v3.0.0/src/test/java/org/filteredpush/qc/date/DwCEventDQTestDefinitions.java#L338)  unit tests for the underlying verbatim date extraction code are in [DateUtilsTest](https://github.com/FilteredPush/event_date_qc/blob/v3.0.0/src/test/java/org/filteredpush/qc/date/DateUtilsTest.java#L632) and [DateUtilsTest](https://github.com/FilteredPush/event_date_qc/blob/v3.0.0/src/test/java/org/filteredpush/qc/date/DateUtilsTest.java#L788)_ 

**Notas**: _The intent of the amended range is to capture the original uncertainty where possible. As in the example, we amend "1999-11" instead of "1999-11-01/1999-11-31".  An AMBIGUOUS response is possible._ 



<table>
<caption>Tabela 32: Termos testados e os resultados esperados para o teste AMENDMENT_EVENTDATE_STANDARDIZED.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> eventDate </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 032_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 032_2 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 032_3 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 032_4 </td>
   <td style="text-align:left;"> 10-28 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate contains an ambiguous value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 032_5 </td>
   <td style="text-align:left;"> 2021-28-10 </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;2021-10-28&quot;} </td>
   <td style="text-align:left;"> dwc:eventDate contains an interpretable value. Assuming year-day-month input format </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 032_6 </td>
   <td style="text-align:left;"> 21-10-28 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate contains an ambiguous value for year. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 032_7 </td>
   <td style="text-align:left;"> 2021/10/28 </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;2021-10-28&quot;} </td>
   <td style="text-align:left;"> dwc:eventDate contains an interpretable value </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:eventDate="2021-28-10": Response.status=AMENDED, Response.result=dwc:eventDate="2021-10-28", Response.comment="dwc:eventDate contains an interpretable value. Assuming year-day-month input format"],[dwc:eventDate="10-28": Response.status=NOT_AMENDED, Response.result=, Response.comment="dwc:eventDate contains an ambiguous value"]

## Teste 033: [`VALIDATION_COUNTRY_COUNTRYCODE_CONSISTENT`](https://github.com/tdwg/bdq/issues/62) 

**Nome do teste**: `VALIDATION_COUNTRY_COUNTRYCODE_CONSISTENT` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/62 

**ID oficial do teste**: `b23110e7-1be7-444a-a677-cdee0cf4330c` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `country, countryCode` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Does the ISO country code determined from the value of dwc:country equal the value of dwc:countryCode?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if either of the terms dwc:country or dwc:countryCode are EMPTY; COMPLIANT if the value of the country code determined from the value of dwc:country from the bdq:sourceAuthority is equal to the value of dwc:countryCode; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "ISO 3166 Country Codes" {[https://www.iso.org/iso-3166-country-codes.html]} {ISO 3166-1-alpha-2 Country Code search [https://www.iso.org/obp/ui/#search]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The country code determination service should be able to match the name of a country in the original language. This test must return NOT_COMPLIANT if there is leading or trailing whitespace or there are leading or trailing non-printing characters._ 



<table>
<caption>Tabela 33: Termos testados e os resultados esperados para o teste VALIDATION_COUNTRY_COUNTRYCODE_CONSISTENT.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> country </th>
   <th style="text-align:left;"> countryCode </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 033_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> All input fields EMPTY. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 033_2 </td>
   <td style="text-align:left;"> Austria </td>
   <td style="text-align:left;"> AUS </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority unavailable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 033_3 </td>
   <td style="text-align:left;"> Eswatini </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:countryCode is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 033_4 </td>
   <td style="text-align:left;"> Swaziland </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:countryCode is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 033_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> GL </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:country EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 033_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Austria </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:country EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 033_7 </td>
   <td style="text-align:left;"> United States Minor Outlying Islands </td>
   <td style="text-align:left;"> US </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:country does not match dwc:countryCode </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 033_8 </td>
   <td style="text-align:left;"> Australia </td>
   <td style="text-align:left;"> USA </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:country does not match dwc:countryCode </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 033_9 </td>
   <td style="text-align:left;"> México </td>
   <td style="text-align:left;"> MX </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country matches dwc:countryCode </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 033_10 </td>
   <td style="text-align:left;"> Australia </td>
   <td style="text-align:left;"> AU </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country matches dwc:countryCode </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:country="Australia", dwc:countryCode="AU": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:country matches dwc:countryCode"],[dwc:country="United States Minor Outlying Islands", dwc:countryCode="US": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:country does not match dwc:countryCode"]

## Teste 034: [`AMENDMENT_BASISOFRECORD_STANDARDIZED`](https://github.com/tdwg/bdq/issues/63) 

**Nome do teste**: `AMENDMENT_BASISOFRECORD_STANDARDIZED` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/63 

**ID oficial do teste**: `07c28ace-561a-476e-a9b9-3d5ad6e35933` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Record-level` 

**Termos (colunas) testados**: `basisOfRecord` 

**Pré-requisitos externos (parâmetros)**: `dwc:basisOfRecord vocabulary` 

**Descrição**: 
> _Propose amendment to the value of dwc:basisOfRecord using bdq:sourceAuthority._ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:basisOfRecord is EMPTY; AMENDED the value of dwc:basisOfRecord if it could be unambiguously interpreted as a value in bdq:sourceAuthority; otherwise NOT_AMENDED bdq:sourceAuthority default = "Darwin Core basisOfRecord" {[https://dwc.tdwg.org/terms/#dwc:basisOfRecord]} {dwc:basisOfRecord vocabulary [https://rs.gbif.org/vocabulary/dwc/basis_of_record.xml]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The term dwc:basisOfRecord has the comment "Recommended best practice is to use the standard label of one of the Darwin Core classes." The list of these values can be determined by searching https://github.com/tdwg/dwc/blob/master/vocabulary/term_versions.csv for rows with status="recommended" and rdf_type="http://www.w3.org/2000/01/rdf-schema#Class". For tests against a dwc:Occurrence record, the set of valid terms is more limited and embodied in the resource found at https://rs.gbif.org/vocabulary/dwc/basis_of_record.xml, which contains both preferred labels and alternate labels from which to standardize values._ 



<table>
<caption>Tabela 34: Termos testados e os resultados esperados para o teste AMENDMENT_BASISOFRECORD_STANDARDIZED.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> basisOfRecord </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 034_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:basisOfRecord is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 034_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:basisOfRecord is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 034_3 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:basisOfRecord contains uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 034_4 </td>
   <td style="text-align:left;"> Pres.spec </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:basisOfRecord&quot;:&quot;PreservedSpecimen&quot;} </td>
   <td style="text-align:left;"> dwc:basisOfRecord contains interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 034_5 </td>
   <td style="text-align:left;"> Human obs </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:basisOfRecord&quot;:&quot;HumanObservation&quot;} </td>
   <td style="text-align:left;"> dwc:basisOfRecord contains interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 034_6 </td>
   <td style="text-align:left;"> FossilSpecimen </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:basisOfRecord contains match in bdq:sourceAuthority so NOT_AMENDED </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 034_7 </td>
   <td style="text-align:left;"> Machine </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority unavailable </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:basisOfRecord="Human obs": Response.status=AMENDED, Response.result=dwc:basisOfRecord="HumanObservation", Response.comment="dwc:basisOfRecord contains interpretable value"],[dwc:basisOfRecord="FossilSpecimen": Response.status=NOT_AMENDED, Response.result="", Response.comment="dwc:basisOfRecord contains match in bdq:sourceAuthority so NOT_AMENDED"]

## Teste 035: [`VALIDATION_EVENTDATE_STANDARD`](https://github.com/tdwg/bdq/issues/66) 

**Nome do teste**: `VALIDATION_EVENTDATE_STANDARD` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/66 

**ID oficial do teste**: `4f2bf8fd-fc5c-493f-a44c-e7b16153c803` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `eventDate` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is the value of dwc:eventDate a valid ISO date?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:eventDate is EMPTY; COMPLIANT if the value of dwc:eventDate is a valid ISO 8601-1 date; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _event_date_qc [DwCEventDQ.validationEventdateStandard() ](https://github.com/FilteredPush/event_date_qc/blob/v3.0.0/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L494)_ 

**Notas**: _This test should also pick up issues such as 29 Feb in a non leap year._ 



<table>
<caption>Tabela 35: Termos testados e os resultados esperados para o teste VALIDATION_EVENTDATE_STANDARD.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> eventDate </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 035_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 035_2 </td>
   <td style="text-align:left;"> 1962-11-01T10:00-0600 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate contains a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 035_3 </td>
   <td style="text-align:left;"> 1949-09-15T12:34 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate contains a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 035_4 </td>
   <td style="text-align:left;"> 1949-01-15T12:34/1949-01-20T17:00 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate contains a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 035_5 </td>
   <td style="text-align:left;"> 1963-03-08T14:07-0600 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate contains a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 035_6 </td>
   <td style="text-align:left;"> 1963-03-08T14 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate contains a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 035_7 </td>
   <td style="text-align:left;"> 1963-03-08T14:67-0600 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate doesnot  contain a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 035_8 </td>
   <td style="text-align:left;"> 1963-03-08T14:07Z </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate contains a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 035_9 </td>
   <td style="text-align:left;"> 1963-03-08T4 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate does not contain a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 035_10 </td>
   <td style="text-align:left;"> 1963-03-08T14:0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate does not contain a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 035_11 </td>
   <td style="text-align:left;"> 1963-03-08 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate contains a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 035_12 </td>
   <td style="text-align:left;"> 1963-03 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate contains a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 035_13 </td>
   <td style="text-align:left;"> 1963 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate contains a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 035_14 </td>
   <td style="text-align:left;"> 63 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate does not contain a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 035_15 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate does not contain a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 035_16 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate does not contain a valid ISO 8601-1:2019 date </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:eventDate="1963-03-08T14": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:eventDate contains a valid ISO 8601-1:2019 date"],[dwc:eventDate="1963-03-08T14:67-0600": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:eventDate does not contain a valid ISO 8601-1:2019 date"]

## Teste 036: [`VALIDATION_EVENTDATE_CONSISTENT`](https://github.com/tdwg/bdq/issues/67) 

**Nome do teste**: `VALIDATION_EVENTDATE_CONSISTENT` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/67 

**ID oficial do teste**: `5618f083-d55a-4ac2-92b5-b9fb227b832f` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `eventDate, startDayOfYear, endDayOfYear, year, month, day` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Are the values in dwc:eventDate consistent with the values in dwc:year, dwc:month, dwc:day, dwc:startDayOfYear and dwc:endDayOfYear?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:eventDate is EMPTY, or all of dwc:year, dwc:month, dwc:day, dwc:startDayOfYear and dwc:endDayOfYear are EMPTY; COMPLIANT if all of the following conditions are met (1) dwc:year is EMPTY or dwc:eventDate has a precision of one year or finer and and is within a single year and the provided value of dwc:year matches the year expressed in dwc:eventDate, and (2) dwc:month is EMPTY or dwc:eventDate has a precision of one month or finer and is within a single month and the provided value in dwc:month matches the month represented by dwc:eventDate, and (3) dwc:day is EMPTY or dwc:eventDate has a precision of a day or less and is within a single day and the provided value in dwc:day matches the day represented by dwc:eventDate, and (4) dwc:startDayOfYear is empty or dwc:eventDate has a precision of one day or finer and the provided value in dwc:startDayOfYear matches the start day of the year of the range represented by dwc:eventDate, and (5) dwc:endDayOfYear is empty or dwc:eventDate has a precision of one day or finer and the provided value in dwc:endDayOfYear matches the end day of the year of the range represented by dwc:eventDate; otherwise NOT_COMPLIANT._ 

**Código fonte de exemplo**: _https://github.com/FilteredPush/event_date_qc/blob/029466e0dc5ef649e7768ab19f75c86094023fce/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L1179 minimal set of unit tests at https://github.com/FilteredPush/event_date_qc/blob/029466e0dc5ef649e7768ab19f75c86094023fce/src/test/java/org/filteredpush/qc/date/DwcEventDQTest.java#L1149_ 

**Notas**: _This test does not take a position on whether the value in dwc:eventDate, or the values in the atomic terms are correct, it simply points out the presence of inconsistencies.  For this test, dwc:eventTime is explicitly ignored. It may be useful to consider an additional test that does evaluate dwc:eventTime and dwc:eventDate. In that case, but not in this test, if the time is present in both dwc:eventDate and dwc:eventTime, and it is inconsistent, it may indicate an error in the dwc:eventDate, thus making it a problem that someone needs to evaluate.   This test will only assert consistency if the data are both internally consistent and are compliant with the term definitions, for example dwc:day, by its definition, can only be the day  of an dwc:eventDate that has a precision of a day or better and is not a range that spans more than a single day.   A dwc:day that was internally consistent with the first day of the year (that is, 1) of an dwc:eventDate that only had precision to a year would be consistent internally, but not consistent with the Darwin Core term definitions, and would not return COMPLIANT from this test._ 



<table>
<caption>Tabela 36: Termos testados e os resultados esperados para o teste VALIDATION_EVENTDATE_CONSISTENT.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> eventDate </th>
   <th style="text-align:left;"> startDayOfYear </th>
   <th style="text-align:left;"> endDayOfYear </th>
   <th style="text-align:left;"> year </th>
   <th style="text-align:left;"> month </th>
   <th style="text-align:left;"> day </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 036_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> All input fields EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_2 </td>
   <td style="text-align:left;"> 1962-11-01T10:00-0600 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:day, dwc:month, dwc:year, dwc:startDayOfYear and dwc:endDayOfYear are EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_3 </td>
   <td style="text-align:left;"> 1964-11-01T10:00-0600 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:day, dwc:month, dwc:year, dwc:startDayOfYear and dwc:endDayOfYear are EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_6 </td>
   <td style="text-align:left;"> 1949-09-15T12:34 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;"> 9 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day, dwc:month and dwc:year match dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_7 </td>
   <td style="text-align:left;"> 1949-09-16T12:34 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;"> 9 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:day does not match dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_8 </td>
   <td style="text-align:left;"> 1949-09-15T12:34 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;"> 9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:month and dwc:year match dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_9 </td>
   <td style="text-align:left;"> 1949-12-09T12:34 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1948 </td>
   <td style="text-align:left;"> 12 </td>
   <td style="text-align:left;"> 9 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:year does not match dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_10 </td>
   <td style="text-align:left;"> 1949-01-15T12:34/1949-01-20T17:00 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> 20 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:startDayOfYear and dwc:endDayOfYear match dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_11 </td>
   <td style="text-align:left;"> 1949-01-15T12:34/1949-01-20T17:00 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> 21 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:endDayOfYear does not match dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_12 </td>
   <td style="text-align:left;"> 1949-09-15T12:34 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year matches dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_13 </td>
   <td style="text-align:left;"> 1949-09-16T12:34 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;"> 8 </td>
   <td style="text-align:left;"> 16 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:month does not match dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_14 </td>
   <td style="text-align:left;"> 1949-09-16T12:34 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1948 </td>
   <td style="text-align:left;"> 9 </td>
   <td style="text-align:left;"> 16 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:year does not match dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_15 </td>
   <td style="text-align:left;"> 1981-01-03 </td>
   <td style="text-align:left;"> 3 </td>
   <td style="text-align:left;"> 3 </td>
   <td style="text-align:left;"> 1981 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> 3 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate, dwc:day, dwc:month, dwc:year, dwc:startDayOfYear and dwc:endDayOfYear are consistent </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_16 </td>
   <td style="text-align:left;"> 1981-01 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1981 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate, dwc:day, dwc:month, dwc:year, dwc:startDayOfYear and dwc:endDayOfYear are consistent </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_17 </td>
   <td style="text-align:left;"> 1981-01 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1981 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate, dwc:day, dwc:month, dwc:year, dwc:startDayOfYear and dwc:endDayOfYear are consistent </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_18 </td>
   <td style="text-align:left;"> 1981-01/1981-12 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1981 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate, dwc:day, dwc:month, dwc:year, dwc:startDayOfYear and dwc:endDayOfYear are consistent </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_19 </td>
   <td style="text-align:left;"> 1981-01-01/1981-12-31 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> 365 </td>
   <td style="text-align:left;"> 1981 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate, dwc:day, dwc:month, dwc:year, dwc:startDayOfYear and dwc:endDayOfYear are consistent </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_20 </td>
   <td style="text-align:left;"> 1980/1981 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:day, dwc:month, dwc:year, dwc:startDayOfYear and dwc:endDayOfYear are EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_21 </td>
   <td style="text-align:left;"> 1981-01-10/1981-01-15 </td>
   <td style="text-align:left;"> 10 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> 1980 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate doesn't match dwc:year </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_22 </td>
   <td style="text-align:left;"> 1981-12-30/1982-01-03 </td>
   <td style="text-align:left;"> 364 </td>
   <td style="text-align:left;"> 3 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate, dwc:day, dwc:month, dwc:year, dwc:startDayOfYear and dwc:endDayOfYear are consistent </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_23 </td>
   <td style="text-align:left;"> 1981-01 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> 31 </td>
   <td style="text-align:left;"> 1981 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:endDayOfYear is populated for a date with a precision less than a day </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_24 </td>
   <td style="text-align:left;"> 1981-01 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1980 </td>
   <td style="text-align:left;"> 2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:month is inconsistent with dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_25 </td>
   <td style="text-align:left;"> 1981 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> 365 </td>
   <td style="text-align:left;"> 1981 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:day and dwc:month do not match dwc:startDayOfYear and dwc:endDayOfYear </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_26 </td>
   <td style="text-align:left;"> 1981-01/1981-12 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1981 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is consistent with dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_27 </td>
   <td style="text-align:left;"> 1981-01-01/1981-12-31 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> 365 </td>
   <td style="text-align:left;"> 1981 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:day and dwc:month do not match dwc:startDayOfYear and dwc:endDayOfYear </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_28 </td>
   <td style="text-align:left;"> 1981-01-01/1981-12-31 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> 366 </td>
   <td style="text-align:left;"> 1981 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:endDayOfYear does not match dwc:eventDate. 1981 is not a leap year, so &quot;366&quot; is not compliant. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_29 </td>
   <td style="text-align:left;"> 1980/1981 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1980 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:year does not match dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_30 </td>
   <td style="text-align:left;"> 1980-01-10/1980-01-15 </td>
   <td style="text-align:left;"> 10 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> 1980 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> 10 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:day does not match dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_31 </td>
   <td style="text-align:left;"> 1981-12-30/1982-01-03 </td>
   <td style="text-align:left;"> 364 </td>
   <td style="text-align:left;"> 3 </td>
   <td style="text-align:left;"> 1981 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:year does not match dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 036_32 </td>
   <td style="text-align:left;"> 1981-12-30/1982-01-03 </td>
   <td style="text-align:left;"> 3 </td>
   <td style="text-align:left;"> 364 </td>
   <td style="text-align:left;"> 1981 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:startDayOfYear and dwc:endDayOfYear do not match dwc:eventDate </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:day="15", dwc:month="9", dwc:year="1949", dwc:eventDate="1949-09-15T12:34", dwc:startDayOfYear="", dwc:endDayOfYear="": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:day, dwc:month and dwc:year match dwc:eventDate"],[dwc:day="15", dwc:month="9", dwc:year="1949", dwc:eventDate="1949-09-16T12:34", dwc:startDayOfYear="", dwc:endDayOfYear="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:day does not match dwc:eventDate"]

## Teste 037: [`AMENDMENT_MINELEVATION-MAXELEVATION_FROM_VERBATIM`](https://github.com/tdwg/bdq/issues/68) 

**Nome do teste**: `AMENDMENT_MINELEVATION-MAXELEVATION_FROM_VERBATIM` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/68 

**ID oficial do teste**: `2d638c8b-4c62-44a0-a14d-fa147bf9823d` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `minimumElevationInMeters, maximumElevationInMeters, verbatimElevation` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Propose amendment(s) to the values of dwc:minimumElevationInMeters and/or dwc:maximumElevationInMeters if they can be interpreted from dwc:verbatimElevation._ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:verbatimElevation is EMPTY or dwc:minimumElevationInMeters and/or dwc:maximumElevationInMeters are not EMPTY; FILLED_IN the values of dwc:minimumElevationInMeters and/or dwc:maximumElevationInMeters that could be unambiguously interpreted from dwc:verbatimElevation; otherwise NOT_AMENDED"_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _If the field dwc:verbatimElevation has a single value rather than a range, the minimum and maximum values should be amended with the same value._ 



<table>
<caption>Tabela 37: Termos testados e os resultados esperados para o teste AMENDMENT_MINELEVATION-MAXELEVATION_FROM_VERBATIM.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> minimumElevationInMeters </th>
   <th style="text-align:left;"> maximumElevationInMeters </th>
   <th style="text-align:left;"> verbatimElevation </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 037_1 </td>
   <td style="text-align:left;"> 25 </td>
   <td style="text-align:left;"> 100 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimElevation is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 037_2 </td>
   <td style="text-align:left;"> 25 </td>
   <td style="text-align:left;"> 100 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters and dwc:maximumElevationInMeters are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 037_3 </td>
   <td style="text-align:left;"> 11 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Min Elevation 10m </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 037_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 110 </td>
   <td style="text-align:left;"> Max Elevation 100m </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:maximumElevationInMeters is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 037_5 </td>
   <td style="text-align:left;"> 11 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Min Elevation 10m </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 037_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 10feet </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:minimumElevationInMeters&quot;:&quot;3.048&quot;,&quot;dwc:maximumElevationInMeters&quot;:&quot;3.048&quot;} </td>
   <td style="text-align:left;"> dwc:verbatimElevation contains an interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 037_7 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 250-300 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimElevation contains ambiguous values (feet or meters or cms?) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 037_8 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> L30 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimElevation contains ambiguous values </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 037_9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> MinElevation 10m, maxElevation=100 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:minimumElevationInMeters&quot;:&quot;10&quot;,&quot;dwc:maximumElevationInMeters&quot;:&quot;100&quot;} </td>
   <td style="text-align:left;"> dwc:verbatimElevation contains an interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 037_10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 356-369m </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:minimumElevationInMeters&quot;:&quot;356&quot;,&quot;dwc:maximumElevationInMeters&quot;:&quot;369&quot;} </td>
   <td style="text-align:left;"> dwc:verbatimElevation contains an interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 037_11 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 19375 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:minimumElevationInMeters&quot;:&quot;5905.5&quot;,&quot;dwc:maximumElevationInMeters&quot;:&quot;5905.5&quot;} </td>
   <td style="text-align:left;"> dwc:verbatimElevation contains an interpretable value as is assumed to be in feet </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:verbatimElevation="10feet", dwc:minimumElevationInMeters="", dwc:maximumElevationInMeters="": Response.status=FILLED_IN, Response.result=dwc:minimumElevationInMeters="3.048", dwc:maximumElevationInMeters="3.048", Response.comment="dwc:verbatimElevation contains an interpretable value"],[dwc:verbatimElevation="x", dwc:minimumElevationInMeters="", dwc:maximumElevationInMeters="": Response.status=NOT_AMENDED, Response.result="", Response.comment="dwc:verbatimElevation contains an uninterpretable value"]

## Teste 038: [`VALIDATION_DATEIDENTIFIED_STANDARD`](https://github.com/tdwg/bdq/issues/69) 

**Nome do teste**: `VALIDATION_DATEIDENTIFIED_STANDARD` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/69 

**ID oficial do teste**: `66269bdd-9271-4e76-b25c-7ab81eebe1d8` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Identification` 

**Termos (colunas) testados**: `dateIdentified` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is the value of dwc:dateIdentified a valid ISO date?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:dateIdentified is EMPTY; COMPLIANT if the value of dwc:dateIdentified contains a valid ISO 8601-1 date; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _[event_date_qc  DwCOtherDateDQ.validationDateidentifiedStandard()](https://github.com/FilteredPush/event_date_qc/blob/be60f348609363d560fe16552bca4cc2975c0766/src/main/java/org/filteredpush/qc/date/DwCOtherDateDQ.java#L58)_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 38: Termos testados e os resultados esperados para o teste VALIDATION_DATEIDENTIFIED_STANDARD.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> dateIdentified </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 038_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:dateIdentified is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 038_2 </td>
   <td style="text-align:left;"> 1963-03-08X14:07-0600 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is not a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 038_3 </td>
   <td style="text-align:left;"> 1963-03-08T14:07 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 038_4 </td>
   <td style="text-align:left;"> 1963-03-08T14 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 038_5 </td>
   <td style="text-align:left;"> 1963-03-08T14:67-0600 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is not a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 038_6 </td>
   <td style="text-align:left;"> 1963-03-08T14:07Z </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 038_7 </td>
   <td style="text-align:left;"> 1963-03-08T4 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is not a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 038_8 </td>
   <td style="text-align:left;"> 1963-03-08T14:0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is not a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 038_9 </td>
   <td style="text-align:left;"> 1963-03-08 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 038_10 </td>
   <td style="text-align:left;"> 1963-03 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 038_11 </td>
   <td style="text-align:left;"> 1963 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 038_12 </td>
   <td style="text-align:left;"> 63 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is not a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 038_13 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is not a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 038_14 </td>
   <td style="text-align:left;"> 2021_06_03T24:00 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is not a valid ISO 8601-1:2019 date. 24 no longer allowed in the hours position. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 038_15 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is not a valid ISO 8601-1:2019 date </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:dateIdentified="1963-03-08T14:07": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:dateIdentified is a valid ISO 8601-1:2019 date"],[dwc:dateIdentified="1963-03-08X14:07-0600": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:dateIdentified is not a valid ISO 8601-1:2019 date"]

## Teste 039: [`VALIDATION_TAXON_UNAMBIGUOUS`](https://github.com/tdwg/bdq/issues/70) 

**Nome do teste**: `VALIDATION_TAXON_UNAMBIGUOUS` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/70 

**ID oficial do teste**: `4c09f127-737b-4686-82a0-7c8e30841590` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `taxonID, scientificName, kingdom, phylum, class, family, genus, genericName, specificEpithet, cultivarEpithet, taxonRank, scientificNameAuthorship` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Can the taxon be unambiguously resolved from bdq:sourceAuthority using the available taxon terms?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if all of dwc:scientificNameID, dwc:scientificName, dwc:genericName, dwc:specificEpithet, dwc:infraspecificEpithet, dwc:scientificNameAuthorship, dwc:cultivarEpithet are EMPTY; COMPLIANT if (1) dwc:scientificNameID references a single taxon record in the bdq:sourceAuthority, or (2) dwc:scientificNameID is empty and dwc:scientificName references a single taxon record in the bdq:sourceAuthority, or (3) if dwc:scientificName and dwc:scientificNameID are EMPTY and if a combination of the values of the terms dwc:genericName, dwc:specificEpithet, dwc:infraspecificEpithet, dwc:cultivarEpithet, dwc:taxonRank, and dwc:scientificNameAuthorship can be unambiguously resolved to a unique taxon in the bdq:sourceAuthority, or (4) if ambiguity produced by multiple matches in (2) or (3) can be disambiguated to a unique Taxon using the values of dwc:tribe, dwc:subtribe, dwc:subgenus, dwc:genus, dwc:subfamily, dwc:family, dwc:superfamily, dwc:order, dwc:class, dwc:phylum, dwc:kingdom, dwc:higherClassification, dwc:taxonID, dwc:acceptedNameUsageID, dwc:originalNameUsageID, dwc:taxonConceptID and dwc:vernacularName; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "GBIF Backbone Taxonomy" {[https://doi.org/10.15468/39omei]} {API endpoint [https://api.gbif.org/v1/species?datasetKey=d7dddbf4-2cf0-4f39-9b2a-bb099caae36c&name=]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _There are any number of potential controlled vocabularies that might be used for this test, including local vocabularies and taxon specific vocabularies. If dwc:scientificNameID is empty, use dwc:scientificName and dwc:CultivarEpithet to search for a unique taxon.  If dwc:scientificName is empty, check with the terms that form atomic parts of it (dwc:genericName, dwc:specificEpithet, dwc:infraspecificEpithet, dwc:taxonRank, dwc:scientificNameAuthorship), and if more than one match is found, use the remaining terms to try to disambiguate to a single Taxon record.   The terms dwc:subgenus, dwc:genus, dwc:family, dwc:order, dwc:class, dwc:phylum, dwc:kingdom, dwc:higherClassification, dwc:scientificNameID,, dwc:acceptedNameUsageID, dwc:originalNameUsageID, dwc:taxonConceptID should not be used to make a match if dwc:scientificNameID and dwc:scientificName or dwc:genericName, dwc:specificEpithet, dwc:infraspecificEpithet, dwc:taxonRank, dwc:scientificNameAuthorship are empty.  Note that test VALIDATION_SCIENTIFICNAME_FOUND (4c09f127-737b-4686-82a0-7c8e30841590) is a more specific test for a subset of Information Elements from this test._ 



<table>
<caption>Tabela 39: Termos testados e os resultados esperados para o teste VALIDATION_TAXON_UNAMBIGUOUS.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> taxonID </th>
   <th style="text-align:left;"> scientificName </th>
   <th style="text-align:left;"> kingdom </th>
   <th style="text-align:left;"> phylum </th>
   <th style="text-align:left;"> class </th>
   <th style="text-align:left;"> family </th>
   <th style="text-align:left;"> genus </th>
   <th style="text-align:left;"> genericName </th>
   <th style="text-align:left;"> specificEpithet </th>
   <th style="text-align:left;"> cultivarEpithet </th>
   <th style="text-align:left;"> taxonRank </th>
   <th style="text-align:left;"> scientificNameAuthorship </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 039_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> All relevant fields are empty </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_2 </td>
   <td style="text-align:left;"> urn:lsid:irmng.org:taxname:1361721 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonID references a single taxon record in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_3 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Chicoreus palmarosae (Lamarck, 1822) </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Mollusca </td>
   <td style="text-align:left;"> Gastropoda </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> palmarosae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> (Lamarck, 1822) </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority unavailable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_4 </td>
   <td style="text-align:left;"> https://api.gbif.org/v1/species </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonID contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Chicoreus palmarosae (Lamarck, 1822) </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Mollusca </td>
   <td style="text-align:left;"> Gastropoda </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> palmarosae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> (Lamarck, 1822) </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName matched to unique taxon record in WoRMS, exact match on name and authorship. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Chicoreus palmarosae (Lamarck) </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Mollusca </td>
   <td style="text-align:left;"> Gastropoda </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> palmarosae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> (Lamarck) </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName matched to unique taxon record in WoRMS, exact match on name and partial match on authorship. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_7 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Chicoreus palmarosae (L., 1822) </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Mollusca </td>
   <td style="text-align:left;"> Gastropoda </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> palmarosae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> (L., 1822) </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName matched to unique taxon record in WoRMS, exact match on name and match on authorship with common abbreviation. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_8 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Triplex rosaria Perry, 1811 </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> mollusca </td>
   <td style="text-align:left;"> Gastropoda </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> Triplex </td>
   <td style="text-align:left;"> rosarium </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Perry, 1811 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName matched taxon record in WoRMS - (Triplex rosaria Perry, 1811) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Graphis </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName=&quot;Graphis&quot; is ambiguous as could be either a lichen or a gastropod. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Graphis Adans., 1763 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Adans., 1763 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName=&quot;Graphis&quot; is ambigous but can be disambiguated to a single taxon by the value in dwc:scientificNameAuthorship=&quot;Adanson, 1863&quot; identifying the taxon as a lichen </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_11 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Graphis Jeffreys, 1867 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Jeffreys, 1867 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName=&quot;Graphis&quot; is ambigous but can be disambiguated to a single taxon by the value in dwc:scientificNameAuthorship=&quot;Jeffreys, 1867&quot; identifying the taxon as a gastropod </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_12 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Graphis </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName=&quot;Graphis&quot; is ambigous but can be disambiguated to a single taxon by the value in dwc:kingdom=Animalia&quot; identifying the taxon as a gastropod </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_13 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Graphis </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Lecanoromycetes </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName=&quot;Graphis&quot; is ambigous but can be disambiguated to a single taxon by the value in dwc:class=Lecanoromycetes&quot; identifying the taxon as a lichen. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_14 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Solanum </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> centrale </td>
   <td style="text-align:left;"> 'Desert tang' </td>
   <td style="text-align:left;"> cultivar </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is EMPTY, but an unambiguous taxon can be identified through the combination of dwc: genus, dwc:specificEpithet, dwc:taxonRank and dwc:cultivarEpithet. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_15 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Chicoreus palmarosae (Lamarck, 1822) </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Mollusca </td>
   <td style="text-align:left;"> Gastropoda </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> palmarosae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> (Lamarck, 1822) </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName matched to taxon record in GBIF Backbone, exact match on name and authorship. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_16 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Chicoreus palmarosae (Lamarck) </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Mollusca </td>
   <td style="text-align:left;"> Gastropoda </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> palmarosae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> (Lamarck) </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName matched to taxon record in GBIF Backbone, exact match on name and partial match on authorship. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_17 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Chicoreus palmarosae (L., 1822) </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Mollusca </td>
   <td style="text-align:left;"> Gastropoda </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> palmarosae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> (L., 1822) </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName matched to taxon record in GBIF Backbone, exact match on name and match on authorship with common abbreviation. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 039_18 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Triplex rosarium Perry, 1811 </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> mollusca </td>
   <td style="text-align:left;"> Gastropoda </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;"> Chicoreus </td>
   <td style="text-align:left;"> Triplex </td>
   <td style="text-align:left;"> rosarium </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Perry, 1811 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName did not match taxon record in GBIF Backbone (default source authority) </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:taxonID="", dwc:scientificNameID="", dwc:acceptedNameUsageID="", dwc:originalNameUsageID="", dwc:taxonConceptID="", dwc:scientificName="Triplex rosaria Perry, 1811", dwc:higherClassification="", dwc:kingdom="Animalia", dwc:phylum="mollusca", dwc:class="Gastropoda", dwc:order="", dwc:family="Muricidae", dwc:subfamily="", dwc:genus="Chicoreus", dwc:genericName="Triplex", dwc:subgenus="", dwc:infragenericEpithet="", dwc:specificEpithet="rosarium", dwc:infraspecificEpithet="", dwc:cultivarEpithet="", dwc:vernacularName="", dwc:scientificNameAuthorship="Perry, 1811", dwc:taxonRank="",bdq:sourceAuthority=”marinespecies.org”: Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:scientificName matched to unique taxon record in WoRMS, unique fuzzy match on name and exact match on authorship.  "],[dwc:taxonID="", dwc:scientificNameID="", dwc:acceptedNameUsageID="", dwc:originalNameUsageID="", dwc:taxonConceptID="", dwc:scientificName="Graphis", dwc:higherClassification="", dwc:kingdom="", dwc:phylum="", dwc:class="", dwc:order="", dwc:family="", dwc:subfamily="", dwc:genus="", dwc:genericName="", dwc:subgenus="", dwc:infragenericEpithet="", dwc:specificEpithet="", dwc:infraspecificEpithet="", dwc:cultivarEpithet="", dwc:vernacularName="", dwc:scientificNameAuthorship="", dwc:taxonRank="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:scientificName="Graphis" is ambiguous as could be either a lichen or a gastropod."]

## Teste 040: [`AMENDMENT_SCIENTIFICNAME_FROM_SCIENTIFICNAMEID`](https://github.com/tdwg/bdq/issues/71) 

**Nome do teste**: `AMENDMENT_SCIENTIFICNAME_FROM_SCIENTIFICNAMEID` 

**Última atualização**: `2022-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/71 

**ID oficial do teste**: `f01fb3f9-2f7e-418b-9f51-adf50f202aea` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `scientificNameID, scientificName` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Propose an amendment to the value of dwc:scientificName using the dwc:scientificNameID value from bdq:sourceAuthority._ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:scientificNameID is EMPTY, the value of dwc:scientificNameID is ambiguous or dwc:scientificName was not EMPTY; FILLED_IN the value of dwc:scientificName if the value of scientificNameID could be unambiguously interpreted as a value in bdq:sourceAuthority; otherwise NOT_AMENDED bdq:sourceAuthority default = "GBIF Backbone Taxonomy" {[https://doi.org/10.15468/39omei]} {API endpoint [https://api.gbif.org/v1/species?datasetKey=d7dddbf4-2cf0-4f39-9b2a-bb099caae36c&name=]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The value of dwc:scientificNameID is unambiguous if dwc:scientificNameID references a single taxon record in the bdq:sourceAuthority.   When referencing a GBIF taxon by GBIF's identifier for that taxon, use the the pseudo-namespace "gbif:" and the form "gbif:{integer}" as the value for dwc:scientificNameID.   Implementors can be aware of the current  GBIF api endpoint that can replace the pseduo-namespace gbif: when looking up the dwc:scientificNameID (taxonID in the gbif document), e.g. `s/gbif:/https:\/\/api.gbif.org\/v1\/species\// ` will transform the value taxonID=gbif:8102122 to the resolvable endpoint https://api.gbif.org/v1/species/8102122  The pseudo-namespace "gbif:" is recommended by GBIF to reference GBIF taxon records.   Where resolvable persistent identifiers exist for dwc:scientificNameID values, they should be used in full, but implementors will need to support at least the "gbif:" pseudo-namespace._ 



<table>
<caption>Tabela 40: Termos testados e os resultados esperados para o teste AMENDMENT_SCIENTIFICNAME_FROM_SCIENTIFICNAMEID.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> scientificNameID </th>
   <th style="text-align:left;"> scientificName </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 040_1 </td>
   <td style="text-align:left;"> gbif:8102122 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:scientificName&quot;:&quot;Harpullia pendula F.Muell.&quot;} </td>
   <td style="text-align:left;"> dwc:scientificNameID contains an interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 040_2 </td>
   <td style="text-align:left;"> gbif:8a </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificNameID does not contain an interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 040_3 </td>
   <td style="text-align:left;"> http://api.gbif.org/v1/species/8102122 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority is unavailable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 040_4 </td>
   <td style="text-align:left;"> http://api.gbif.org/v1/species/ </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificNameID does not contain an interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 040_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Harpullia pendula F.Muell. </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificNameID is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 040_6 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificNameID is uninterpretable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 040_7 </td>
   <td style="text-align:left;"> https://id.biodiversity.org.au/112570 </td>
   <td style="text-align:left;"> Eucalyptus citriodora </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificName is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 040_8 </td>
   <td style="text-align:left;"> https://id.biodiversity.org.au/112570 </td>
   <td style="text-align:left;"> Eucalyptus </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificName is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 040_9 </td>
   <td style="text-align:left;"> https://data.aad.gov.au/aadc/biodiversity/taxon_profile.cfm?taxon_id=62947 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificName is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:scientificNameID="gbif:8102122", dwc:scientificName="": Response.status=FILLED_IN, Response.result=dwc:scientificName="Harpullia pendula F.Muell.", Response.comment="dwc:scientificNameID contains an interpretable value"],[dwc:scientificNameID="gbif:8a", dwc:scientificName="": Response.status=NOT_AMENDED, Response.result="", Response.comment="dwc:scientificNameID does not contain an interpretable value"]

## Teste 041: [`ISSUE_DATAGENERALIZATIONS_NOTNOTEMPTY`](https://github.com/tdwg/bdq/issues/72) 

**Nome do teste**: `ISSUE_DATAGENERALIZATIONS_NOTNOTEMPTY` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/72 

**ID oficial do teste**: `13d5a10e-188e-40fd-a22c-dbaa87b91df2` 

**Tipo de teste**: `Issue` 

**Contexto dos termos testados**: `Record-level` 

**Termos (colunas) testados**: `dataGeneralizations` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:dataGeneralizations?_ 

**Especificação**: 
> _POTENTIAL_ISSUE if dwc:dataGeneralizations is not EMPTY; otherwise NOT_ISSUE_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _This is not specific to spatial data, any value in the dwc:dataGeneralizations field will cause this flag to be raised, but the primary use case is expected to be that dwc:dataGeneralizations demonstrates obfuscated locations._ 



<table>
<caption>Tabela 41: Termos testados e os resultados esperados para o teste ISSUE_DATAGENERALIZATIONS_NOTNOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> dataGeneralizations </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 041_1 </td>
   <td style="text-align:left;"> placed on quarter degree grid </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> POTENTIAL_ISSUE </td>
   <td style="text-align:left;"> dwc:dataGeneralizations is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 041_2 </td>
   <td style="text-align:left;"> blah </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> POTENTIAL_ISSUE </td>
   <td style="text-align:left;"> dwc:dataGeneralizations is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 041_3 </td>
   <td style="text-align:left;"> anyOldTerm </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> POTENTIAL_ISSUE </td>
   <td style="text-align:left;"> dwc:dataGeneralizations is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 041_4 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> POTENTIAL_ISSUE </td>
   <td style="text-align:left;"> dwc:dataGeneralizations is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 041_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_ISSUE </td>
   <td style="text-align:left;"> dwc:dataGeneralizations is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 041_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_ISSUE </td>
   <td style="text-align:left;"> dwc:dataGeneralizations is EMPTY or Missing </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 041_7 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> POTENTIAL_ISSUE </td>
   <td style="text-align:left;"> dwc:dataGeneralizations is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 041_8 </td>
   <td style="text-align:left;"> dwc:dataGeneralizations </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> POTENTIAL_ISSUE </td>
   <td style="text-align:left;"> dwc:dataGeneralizations is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:dataGeneralizations="placed on quarter degree grid": Response.status=RUN_HAS_RESULT, Response.result=POTENTIAL_ISSUE, Response.comment="dwc:dataGeneralizations is not EMPTY"],[dwc:dataGeneralizations="": Response.status=RUN_HAS_RESULT, Response.result=NOT_ISSUE, Response.comment="dwc:dataGeneralizations is EMPTY"]

## Teste 042: [`AMENDMENT_COUNTRYCODE_FROM_COORDINATES`](https://github.com/tdwg/bdq/issues/73) 

**Nome do teste**: `AMENDMENT_COUNTRYCODE_FROM_COORDINATES` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/73 

**ID oficial do teste**: `8c5fe9c9-4ba9-49ef-b15a-9ccd0424e6ae` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `countryCode, decimalLatitude, decimalLongitude` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Propose amendment to the value of dwc:countryCode if dwc:decimalLatitude and dwc:decimalLongitude fall within a boundary from the bdq:countryShapes that is attributable to a single valid country code._ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:countryShapes is not available; INTERNAL_PREREQUISITES_NOT_MET if either dwc:decimalLatitude or dwc:decimalLongitude is EMPTY or uninterpretable, or if dwc:countryCode is NOT_EMPTY; FILLED_IN dwc:countryCode if dwc:decimalLatitude and dwc:decimalLongitude fall within a boundary from the bdq:countryShapes that is attributable to a single valid country code; otherwise NOT_AMENDED. bdq:sourceAuthority default = "ADM1 boundaries spatial UNION with Exclusive Economic Zones" {[https://gadm.org] spatial UNION [https://marineregions.org]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _This amendment simply fills dwc:countryCode from a lookup of dwc:decimalLatitude and dwc:decimalLongitude. dwc:coordinateUncertaintyInMeters and dwc:coordinatePrecicision (if present) imply a buffer around the provided coordinates. Likewise, country polygons cannot be 100% accurate at all scales (Dooley 2005), so a spatial buffer of the country boundaries is also justified. Taking spatial buffers into account does however greatly complicate the logic and the implementation of this and related tests. In this test, a detection of multiple country codes by sampling within the buffer while possible, is not considered._ 



<table>
<caption>Tabela 42: Termos testados e os resultados esperados para o teste AMENDMENT_COUNTRYCODE_FROM_COORDINATES.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> countryCode </th>
   <th style="text-align:left;"> decimalLatitude </th>
   <th style="text-align:left;"> decimalLongitude </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 042_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> -25.23 </td>
   <td style="text-align:left;"> 135.43 </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority not available </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 042_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude and dwc:decimalLongitude are EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 042_3 </td>
   <td style="text-align:left;"> AX </td>
   <td style="text-align:left;"> -25.23 </td>
   <td style="text-align:left;"> 135.43 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:countryCode is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 042_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> -25.23 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 042_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 145.0 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 042_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> -25.23 </td>
   <td style="text-align:left;"> 185.43 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLongitude is out of range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 042_7 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> -38.280937 </td>
   <td style="text-align:left;"> 72.047790 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Coordinates do not fall in the boundary of any country </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 042_8 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> -42.280937 </td>
   <td style="text-align:left;"> 145.047790 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:countryCode is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 042_9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> 135.87 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 042_10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> -25.23 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLongitude contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 042_11 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> -25.23 </td>
   <td style="text-align:left;"> 135.43 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:countryCode&quot;:&quot;AU&quot;} </td>
   <td style="text-align:left;"> dwc:decimalLatitude and dwc:decimalLongitude contain interpretable values </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 042_12 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> -41.195924 </td>
   <td style="text-align:left;"> -71.253562 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:countryCode&quot;:&quot;AR&quot;} </td>
   <td style="text-align:left;"> dwc:decimalLatitude and dwc:decimalLongitude contain interpretable values </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:decimalLatitude="-25.23", dwc:decimalLongitude="135.43", dwc:countryCode="": Response.status=FILLED_IN, Response.result=dwc:countryCode="AU", Response.comment="dwc:decimalLatitude and dwc:decimalLongitude contain interpretable values"],[dwc:decimalLatitude="-38.280937", dwc:decimalLongitude="72.047790", dwc:countryCode="": Response.status=NOT_AMENDED, Response.result="", Response.comment="Coordinates do not fall in the boundary of any country"]

## Teste 043: [`AMENDMENT_OCCURRENCESTATUS_ASSUMEDDEFAULT`](https://github.com/tdwg/bdq/issues/75) 

**Nome do teste**: `AMENDMENT_OCCURRENCESTATUS_ASSUMEDDEFAULT` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/75 

**ID oficial do teste**: `96667a0a-ae59-446a-bbb0-b7f2b0ca6cf5` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Occurrence` 

**Termos (colunas) testados**: `individualCount, occurrenceStatus` 

**Pré-requisitos externos (parâmetros)**: `dwc:occurrenceStatus` 

**Descrição**: 
> _Propose an amendment of the value of dwc:occurrenceStatus to the default parameter value if dwc:occurrenceStatus, dwc:individualCount and dwc:organismQuantity are empty._ 

**Especificação**: 
> _FILLED_IN the value of dwc:occurrenceStatus using the Parameter value if dwc:occurrence.Status,  dwc:individualCount and dwc:organismQuantity are EMPTY; otherwise NOT_AMENDED dwc:occurrenceStatus default = "present"_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 43: Termos testados e os resultados esperados para o teste AMENDMENT_OCCURRENCESTATUS_ASSUMEDDEFAULT.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> individualCount </th>
   <th style="text-align:left;"> occurrenceStatus </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 043_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:occurrenceStatus&quot;:&quot;present&quot;} </td>
   <td style="text-align:left;"> dwc:occurrenceStatus is EMPTY; assumed &quot;present&quot; </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 043_2 </td>
   <td style="text-align:left;"> 10 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:occurrenceStatus is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 043_3 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:occurrenceStatus is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 043_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> absent </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:occurrenceStatus is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:occurrenceStatus="", dwc:individualCount="", dwc:organismQuantity="": Response.status=FILLED_IN, Response.result=dwc:occurrenceStatus="present", Response.comment="dwc:occurrenceStatus is EMPTY; assumed "present""],[dwc:occurrenceStatus="X", dwc:individualCount="10", dwc:organismQuantity="": Response.status=NOT_AMENDED, Response.result="", Response.comment="dwc:occurrenceStatus is not EMPTY"]

## Teste 044: [`VALIDATION_DATEIDENTIFIED_INRANGE`](https://github.com/tdwg/bdq/issues/76) 

**Nome do teste**: `VALIDATION_DATEIDENTIFIED_INRANGE` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/76 

**ID oficial do teste**: `dc8aae4b-134f-4d75-8a71-c4186239178e` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Identification` 

**Termos (colunas) testados**: `eventDate, dateIdentified` 

**Pré-requisitos externos (parâmetros)**: `bdq:earliestValidDate,bdq:latestValidDate,bdq:includeEventDate` 

**Descrição**: 
> _Is the value of dwc:dateIdentified within Parameter ranges and either overlap or is later than dwc:eventDate?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if (1) dwc:dateIdentified is EMPTY, or (2) dwc:dateIdentified contains an invalid value according to ISO 8601-1, or (3) bdq:includeEventDate=true and dwc:eventDate is not a valid ISO 8601-1 date; COMPLIANT if the value of dwc:dateIdentified is between bdq:earliestValidDate and bdq:latestValidDate inclusive and either (1) dwc:eventDate is EMPTY or bdq:includeEventDate=false, or (2) if dwc:eventDate is a valid ISO 8601-1 date and dwc:dateIdentified overlaps or is later than the dwc:eventDate; otherwise NOT_COMPLIANT bdq:sourceAuthority = "ISO 8601-1:2019" {[https://www.iso.org/iso-8601-date-and-time-format.html]},bdq:earliestValidDate default="1753-01-01",bdq:latestValidDate default=[current day],bdq:includeEventDate default=true_ 

**Código fonte de exemplo**: _https://github.com/FilteredPush/event_date_qc/blob/37d349b79f05a76eeb264bafe2315ce88493ecb7/src/main/java/org/filteredpush/qc/date/DwCOtherDateDQ.java#L181_ 

**Notas**: _There may be valid identifications prior to Linnaeus, but this test will flag these under the default value of bdq:earliestValidDate, as for most biodiversity data, pre-linnaean identification dates are likely to be errors. If a parameter is not set, then the default is 1753-01-01. This test will, by design, flag as problematic cases (such as LTER plots and marine mammal sightings) where a known individual organism is identified by a specialist and then subsequently observed without new taxonomic identifications being made._ 



<table>
<caption>Tabela 44: Termos testados e os resultados esperados para o teste VALIDATION_DATEIDENTIFIED_INRANGE.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> eventDate </th>
   <th style="text-align:left;"> dateIdentified </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 044_1 </td>
   <td style="text-align:left;"> 1949_0915T11:34 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:dateIdentified is EMPTY or Missing </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1963-03-08T14:07-0600 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_3 </td>
   <td style="text-align:left;"> 1962-11-01T10:00-0600 </td>
   <td style="text-align:left;"> 1963-03-08T14:07-0600 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_4 </td>
   <td style="text-align:left;"> 1964-11-01T10:00-0600 </td>
   <td style="text-align:left;"> 1963-03-08T14:07-0600 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified before dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> All input fields are EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_6 </td>
   <td style="text-align:left;"> 1949-09-15 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:dateIdentified is invalid </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_7 </td>
   <td style="text-align:left;"> 1963-03-08T14:07-0600 </td>
   <td style="text-align:left;"> 1963-03-08T14:07-0600 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_8 </td>
   <td style="text-align:left;"> 1963-03-08T14:07 </td>
   <td style="text-align:left;"> 1963-03-08T14:07 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_9 </td>
   <td style="text-align:left;"> 1963-03-08T14:67-0600 </td>
   <td style="text-align:left;"> 1963-03-08T14:67-0600 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:dateIdentified is not a valid ISO 8601 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_10 </td>
   <td style="text-align:left;"> 1963-03-08T14:07Z </td>
   <td style="text-align:left;"> 1963-03-08T14:07Z </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_11 </td>
   <td style="text-align:left;"> 1963-03-08T4 </td>
   <td style="text-align:left;"> 1963-03-08T4 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:dateIdentified is not a valid ISO 8601 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_12 </td>
   <td style="text-align:left;"> 1963-03-08T14:0 </td>
   <td style="text-align:left;"> 1963-03-08T14:0 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:dateIdentified is not a valid ISO 8601 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_13 </td>
   <td style="text-align:left;"> 1963-03-08T14:07 </td>
   <td style="text-align:left;"> 1963-03-08T14:07 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_14 </td>
   <td style="text-align:left;"> 1963-03-08 </td>
   <td style="text-align:left;"> 1963-03-08 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_15 </td>
   <td style="text-align:left;"> 1963-03 </td>
   <td style="text-align:left;"> 1963-03 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_16 </td>
   <td style="text-align:left;"> 1963 </td>
   <td style="text-align:left;"> 1963 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_17 </td>
   <td style="text-align:left;"> 1962-11-01T10:00 </td>
   <td style="text-align:left;"> 1963 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_18 </td>
   <td style="text-align:left;"> 1964-11-01T10:00 </td>
   <td style="text-align:left;"> 1963 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified before dwc:eventDate </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_19 </td>
   <td style="text-align:left;"> 1963-11-01T10:00 </td>
   <td style="text-align:left;"> 1963 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:dateIdentified is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_20 </td>
   <td style="text-align:left;"> 63 </td>
   <td style="text-align:left;"> 63 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:dateIdentified is not a valid ISO 8601 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_21 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:dateIdentified is not a valid ISO 8601 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_22 </td>
   <td style="text-align:left;"> 1949-09-16T12:34 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:dateIdentified is EMPTY or Missing </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 044_23 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 2021_06_03T24:00 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is EMPTY. </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:dateIdentified="1963-03-08T14:07-0600", dwc:eventDate="1962-11-01T10:00-0600": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:dateIdentified is in range"],[dwc:dateIdentified="1963-03-08T14:07-0600", dwc:eventDate="1964-11-01T10:00-0600": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:dateIdentified before dwc:eventDate"]

## Teste 045: [`VALIDATION_CLASS_FOUND`](https://github.com/tdwg/bdq/issues/77) 

**Nome do teste**: `VALIDATION_CLASS_FOUND` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/77 

**ID oficial do teste**: `2cd6884e-3d14-4476-94f7-1191cfff309b` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `class` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Does the value of dwc:class occur at rank of Class in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:class is EMPTY; COMPLIANT if the value of dwc:class was found as a value at the rank of Class in the bdq:sourceAuthority; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "GBIF Backbone Taxonomy" {[https://doi.org/10.15468/39omei]} {API endpoint [https://api.gbif.org/v1/species?datasetKey=d7dddbf4-2cf0-4f39-9b2a-bb099caae36c&name=]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The purpose of this test is to check whether the value is a name that is a result of a nomenclatural act at this rank. This excludes unpublished names, misspellings and vernacular names. It is expected that the test will designate the source authority against to check. The same test might return distinct results when using distinct source authorities._ 



<table>
<caption>Tabela 45: Termos testados e os resultados esperados para o teste VALIDATION_CLASS_FOUND.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> class </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 045_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:class is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 045_2 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:class does not have an equivalent at the rank of Class in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 045_3 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:class does not have an equivalent at the rank of Class in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 045_4 </td>
   <td style="text-align:left;"> Insecta </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:class has an equivalent at the rank of Class in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 045_5 </td>
   <td style="text-align:left;"> Insetca </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:class does not have an equivalent at the rank of Class in the paramaterized bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 045_6 </td>
   <td style="text-align:left;"> Magnoliopsida </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:class has an equivalent at the rank of Class in the parameterized bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 045_7 </td>
   <td style="text-align:left;"> Magnoleopsida </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:class does not have an equivalent at the rank of Class in the parameterized bdq:sourceAuthority. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 045_8 </td>
   <td style="text-align:left;"> Magnoliophyta </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:class does not have an equivalent at the rank of Class in the bdq:sourceAuthority. Magnoliophyta is a Phylum - not a Class </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 045_9 </td>
   <td style="text-align:left;"> herps </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:class does not have an equivalent at the rank of Class in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 045_10 </td>
   <td style="text-align:left;"> Dicotyledoneae </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:class does not have an equivalent at the rank of Class in the bdq:sourceAuthority. Parameterized Source Authority has Dicotyledonae instead of Magnoliopsida </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 045_11 </td>
   <td style="text-align:left;"> Dicotyledonae </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:class not have an equivalent at the rank of Class in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 045_12 </td>
   <td style="text-align:left;"> AnyClass </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> the bdq:sourceAuthority was not available or was unreachable </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:class="Insecta": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:class has an equivalent at the rank of Class in the paramaterized bdq:sourceAuthority"],[dwc:class="Magnoleopsida": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT,  Response.comment="dwc:class does not have an equivalent at the rank of Class in the parameterized bdq:sourceAuthority."]

## Teste 046: [`VALIDATION_GEODETICDATUM_NOTEMPTY`](https://github.com/tdwg/bdq/issues/78) 

**Nome do teste**: `VALIDATION_GEODETICDATUM_NOTEMPTY` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/78 

**ID oficial do teste**: `239ec40e-a729-4a8e-ba69-e0bf03ac1c44` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `geodeticDatum` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:geodeticDatum?_ 

**Especificação**: 
> _COMPLIANT if dwc:geodeticDatum is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 46: Termos testados e os resultados esperados para o teste VALIDATION_GEODETICDATUM_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> geodeticDatum </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 046_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum is EMPTY. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 046_2 </td>
   <td style="text-align:left;"> UTM </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum is NOT EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 046_3 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum is NOT EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 046_4 </td>
   <td style="text-align:left;"> WGS84 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum is NOT EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 046_5 </td>
   <td style="text-align:left;"> ED50 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum is NOT EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 046_6 </td>
   <td style="text-align:left;"> International 1924 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum is NOT EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 046_7 </td>
   <td style="text-align:left;"> 4326 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum is NOT EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 046_8 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:geodeticDatum is NOT EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:geodeticDatum="UTM": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:geodeticDatum is NOT EMPTY"],[dwc:geodeticDatum="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:geodeticDatum is EMPTY."]

## Teste 047: [`VALIDATION_DECIMALLATITUDE_INRANGE`](https://github.com/tdwg/bdq/issues/79) 

**Nome do teste**: `VALIDATION_DECIMALLATITUDE_INRANGE` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/79 

**ID oficial do teste**: `b6ecda2a-ce36-437a-b515-3ae94948fe83` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `decimalLatitude` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is the value of dwc:decimalLatitude a number between -90 and 90 inclusive?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:decimalLatitude is EMPTY or the value is not interpretable as a number; COMPLIANT if the value of dwc:decimalLatitude is between -90 and 90, inclusive; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 47: Termos testados e os resultados esperados para o teste VALIDATION_DECIMALLATITUDE_INRANGE.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> decimalLatitude </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 047_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 047_2 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude is not interpretable as a number </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 047_3 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatitude is in RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 047_4 </td>
   <td style="text-align:left;"> 41.0554 N </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude is not interpretable as a number </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 047_5 </td>
   <td style="text-align:left;"> 121.0534 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatitude is in not in RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 047_6 </td>
   <td style="text-align:left;"> -99.2314 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatitude is in not in RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 047_7 </td>
   <td style="text-align:left;"> -41.0525925872862 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatitude is in RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 047_8 </td>
   <td style="text-align:left;"> 18.835941 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatitude is in RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 047_9 </td>
   <td style="text-align:left;"> 41.0525925872862 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatitude is in RANGE </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:decimalLatitude="0.0": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:decimalLatitude is in RANGE"],[dwc:decimalLatitude="121.0534": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:decimalLatitude is in not in RANGE"]

## Teste 048: [`VALIDATION_KINGDOM_FOUND`](https://github.com/tdwg/bdq/issues/81) 

**Nome do teste**: `VALIDATION_KINGDOM_FOUND` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/81 

**ID oficial do teste**: `125b5493-052d-4a0d-a3e1-ed5bf792689e` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `kingdom` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Does the value of dwc:kingdom occur at rank of Kingdom in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:kingdom is EMPTY; COMPLIANT if the value of dwc:kingdom was found as a value at the rank of kingdom by the bdq:sourceAuthority; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "GBIF Backbone Taxonomy" {[https://doi.org/10.15468/39omei]} {API endpoint [https://api.gbif.org/v1/species?datasetKey=d7dddbf4-2cf0-4f39-9b2a-bb099caae36c&name=]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The purpose of this test is to check whether the value is a name that is a result of a nomenclatural act at this rank. This excludes unpublished names, misspellings and vernacular names. It is expected that the test will designate the source authority against to check. The same test might return distinct results when using distinct source authorities._ 



<table>
<caption>Tabela 48: Termos testados e os resultados esperados para o teste VALIDATION_KINGDOM_FOUND.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> kingdom </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 048_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:kingdom is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 048_2 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:kingdom does not have an equivalent at the rank of Kingdom in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 048_3 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:kingdom does not have an equivalent at the rank of Kingdom in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 048_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:kingdom is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 048_5 </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:kingdom has an equivalent at the rank of Kingdom in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 048_6 </td>
   <td style="text-align:left;"> Metazoa </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:kingdom does not strictly have an equivalent at the rank of Kingdom in the Parameterized Source Authority (Metazoa is synonym of Animalia) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 048_7 </td>
   <td style="text-align:left;"> Metazoo </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:kingdom does not have an equivalent at the rank of Kingdom in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 048_8 </td>
   <td style="text-align:left;"> animals </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:kingdom does not have an equivalent at the rank of Kingdom in the bdq:sourceAuthority. This may be fixed using fuzzy matching at the AMENDMENT stage </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 048_9 </td>
   <td style="text-align:left;"> Fungi </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:kingdom has an equivalent at the rank of Kingdom in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 048_10 </td>
   <td style="text-align:left;"> fungus </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:kingdom does not have an equivalent at the rank of Kingdom in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 048_11 </td>
   <td style="text-align:left;"> dwc:kingdom </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:kingdom does not have an equivalent at the rank of Kingdom in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 048_12 </td>
   <td style="text-align:left;"> AnyKindom </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> the bdq:sourceAuthority was unavailable or unreachable </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:kingdom="Animalia": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:kingdom has an equivalent at the rank of Kingdom in the bdq:sourceAuthority"],[dwc:kingdom="Metazoa": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:kingdom does not strictly have an equivalent at the rank of Kingdom in the Parameterized Source Authority (Metazoa is synonym of Animalia)"]

## Teste 049: [`VALIDATION_SCIENTIFICNAME_NOTEMPTY`](https://github.com/tdwg/bdq/issues/82) 

**Nome do teste**: `VALIDATION_SCIENTIFICNAME_NOTEMPTY` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/82 

**ID oficial do teste**: `7c4b9498-a8d9-4ebb-85f1-9f200c788595` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `scientificName, genus` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:scientificName?_ 

**Especificação**: 
> _COMPLIANT if dwc:scientificName is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 49: Termos testados e os resultados esperados para o teste VALIDATION_SCIENTIFICNAME_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> scientificName </th>
   <th style="text-align:left;"> genus </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 049_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 049_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 049_3 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 049_4 </td>
   <td style="text-align:left;"> --- </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 049_5 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 049_6 </td>
   <td style="text-align:left;"> Hakea decurrens ssp. Physocarpa </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 049_7 </td>
   <td style="text-align:left;"> Hakea </td>
   <td style="text-align:left;"> Hakea </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 049_8 </td>
   <td style="text-align:left;"> Hakea decurrens </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 049_9 </td>
   <td style="text-align:left;"> Hakea decurrens subsp. physocarpa W.R.Barker </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 049_10 </td>
   <td style="text-align:left;"> dwc:scientificName </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:scientificName="?": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:scientificName is not EMPTY"],[dwc:scientificName="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:scientificName is EMPTY"]

## Teste 050: [`VALIDATION_ORDER_FOUND`](https://github.com/tdwg/bdq/issues/83) 

**Nome do teste**: `VALIDATION_ORDER_FOUND` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/83 

**ID oficial do teste**: `81cc974d-43cc-4c0f-a5e0-afa23b455aa3` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `order` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Does the value of dwc:order occur at rank of Order in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:order is EMPTY; COMPLIANT if the value of dwc:order was found as a value at the rank of Order by the bdq:sourceAuthority; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "GBIF Backbone Taxonomy" {[https://doi.org/10.15468/39omei]} {API endpoint [https://api.gbif.org/v1/species?datasetKey=d7dddbf4-2cf0-4f39-9b2a-bb099caae36c&name=]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The purpose of this test is to check whether the value is a name that is a result of a nomenclatural act at this rank. This excludes unpublished names, misspellings and vernacular names. It is expected that the test will designate the source authority against to check. The same test might return distinct results when using distinct source authorities._ 



<table>
<caption>Tabela 50: Termos testados e os resultados esperados para o teste VALIDATION_ORDER_FOUND.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> order </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 050_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:order is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 050_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:order is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 050_3 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:order does not have an equivalent at the rank of Order in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 050_4 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:order does not have an equivalent at the rank of Order in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 050_5 </td>
   <td style="text-align:left;"> Myrtales </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:order has an equivalent at the rank of Order in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 050_6 </td>
   <td style="text-align:left;"> Lepidoptera </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:order has an equivalent at the rank of Order in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 050_7 </td>
   <td style="text-align:left;"> Nymphalidae </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:order does not have an equivalent at the rank of Order in the bdq:sourceAuthority. Nymphalidae is a family, not an order </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 050_8 </td>
   <td style="text-align:left;"> butterflies </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:order does not have an equivalent at the rank of Order in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 050_9 </td>
   <td style="text-align:left;"> dwc:order </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:order does not have an equivalent at the rank of Order in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 050_10 </td>
   <td style="text-align:left;"> AnyOrder </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> the bdq:sourceAuthority was not available or unreachable </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:order="Lepidoptera": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:order has an equivalent at the rank of Order in the bdq:sourceAuthority"],[dwc:order="Nymphalidae": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:order does not have an equivalent at the rank of Order in the bdq:sourceAuthority. Nymphalidae is a family, not an order"]

## Teste 051: [`VALIDATION_YEAR_INRANGE`](https://github.com/tdwg/bdq/issues/84) 

**Nome do teste**: `VALIDATION_YEAR_INRANGE` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/84 

**ID oficial do teste**: `ad0c8855-de69-4843-a80c-a5387d20fbc8` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `year` 

**Pré-requisitos externos (parâmetros)**: `bdq:earliestValidDate,bdq:latestValidDate` 

**Descrição**: 
> _Is the value of dwc:year within the Parameter range?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:year is not present, or is EMPTY or cannot be interpreted as an integer; COMPLIANT if the value of dwc:year is within the range bdq:earliestValidDate to bdq:latestValidDate inclusive; otherwise NOT_COMPLIANT bdq:earliestValidDate="1582",bdq:latestValidDate=current year_ 

**Código fonte de exemplo**: _event_date_qc [DwCEventDQ.validationYearInrange()]( https://github.com/FilteredPush/event_date_qc/blob/07f5a338c595c345cd6a0243df511cc752386d99/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L2163)  [unit test](https://github.com/FilteredPush/event_date_qc/blob/07f5a338c595c345cd6a0243df511cc752386d99/src/test/java/org/filteredpush/qc/date/DwcEventDQTest.java#L1945)_ 

**Notas**: _The results of this test are time-dependent. Next year is not valid now. Next year it will be. This test provides the option to designate lower and upper limits to the year. The upper limit, if not provided, should default to the year when the test is run. This test provides for a default earliest date (year), of 1582 by convention. That value was chosen because ISO 8601-1 asserts that "the use of proleptic Gregorian calendar dates prior are not allowed in ISO 8601-1 without prior agreement of the parties exchanging data", and Darwin Core provides no such prior agreement._ 



<table>
<caption>Tabela 51: Termos testados e os resultados esperados para o teste VALIDATION_YEAR_INRANGE.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> year </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 051_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:year is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 051_2 </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is in RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 051_3 </td>
   <td style="text-align:left;"> 194x </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:year is not an interpretable as an integer </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 051_4 </td>
   <td style="text-align:left;"> 1952 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is in RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 051_5 </td>
   <td style="text-align:left;"> 9999 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is not in RANGE. The value in year has not yet come to pass. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 051_6 </td>
   <td style="text-align:left;"> 1599 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is in RANGE 1585-present.  This result assumes the bdq:earliestDate default value of 1585 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 051_7 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is not in RANGE.  This result assumes the bdq:earliestDate default value of 1600. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 051_8 </td>
   <td style="text-align:left;"> XXXX </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:year is not an interpretable as an integer </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 051_9 </td>
   <td style="text-align:left;"> 2000 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is in RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 051_10 </td>
   <td style="text-align:left;"> 1900 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is in RANGE </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 051_11 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:year is not an interpretable as an integer </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:year="1952": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:year is in RANGE"],[dwc:year="9999": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:year is not in RANGE. The value in year has not yet come to pass."]

## Teste 052: [`AMENDMENT_EVENTDATE_FROM_VERBATIM`](https://github.com/tdwg/bdq/issues/86) 

**Nome do teste**: `AMENDMENT_EVENTDATE_FROM_VERBATIM` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/86 

**ID oficial do teste**: `6d0a0c10-5e4a-4759-b448-88932f399812` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `eventDate, verbatimEventDate` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Propose amendment to the value of dwc:eventDate from the content of dwc:verbatimEventDate._ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:eventDate is not EMPTY or the value of dwc:verbatimEventDate is EMPTY or not unambiguously interpretable as an ISO 8601-1 date; FILLED_IN the value of dwc:eventDate if an unambiguous ISO 8601-1 date was interpreted from dwc:verbatimEventDate; otherwise NOT_AMENDED_ 

**Código fonte de exemplo**: _event_date_qc [DwCEventDQ.amendmentEventdateFromVerbatim()](https://github.com/FilteredPush/event_date_qc/blob/v3.0.0/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L320) For a minimum set of unit tests see: [DwcEventDQTest](https://github.com/FilteredPush/event_date_qc/blob/v3.0.0/src/test/java/org/filteredpush/qc/date/DwcEventDQTest.java#L441), see also unit tests for underlying implementation in [DateUtilsTest](https://github.com/FilteredPush/event_date_qc/blob/v3.0.0/src/test/java/org/filteredpush/qc/date/DateUtilsTest.java#L632) and [DateUtilsTest](https://github.com/FilteredPush/event_date_qc/blob/v3.0.0/src/test/java/org/filteredpush/qc/date/DateUtilsTest.java#L788)_ 

**Notas**: _If the proposed eventDate is prior to 1918-02-14, the Response.comment will include a note that the "verbatimDate was assumed to be in the Gregorian calendar". When running the test, the original precision, e.g. year=1980, month=1 should be retained, e.g. dwc:eventDate should become 1980-01, not 1980-01-01/1980-01-31._ 



<table>
<caption>Tabela 52: Termos testados e os resultados esperados para o teste AMENDMENT_EVENTDATE_FROM_VERBATIM.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> eventDate </th>
   <th style="text-align:left;"> verbatimEventDate </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 052_1 </td>
   <td style="text-align:left;"> 2021_10_29 </td>
   <td style="text-align:left;"> February 2022 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimEventDate is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_3 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimEventDate is cannot be interpreted as a valid ISO 8601 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_4 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> 1980-08-09 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_5 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> 1980-08-09 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_6 </td>
   <td style="text-align:left;"> 1980 </td>
   <td style="text-align:left;"> 1980-08-09 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_7 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Friday 29th Oct. 2021 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;2021-10-29&quot;} </td>
   <td style="text-align:left;"> dwc:verbatimEventDate contains an interpretable value (assuming some external lookup thesauri) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_8 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 03/04/2020 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimEventDate is ambiguous - could be either 3rd April or 4th March </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 0377 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:verbatimEventDate cannot be unabiguously interpreted as a valid ISO date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 18/V/1981 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;1981-05-18&quot;} </td>
   <td style="text-align:left;"> dwc:verbatimEventDate with Roman numerals as used in some disciplines (suggested by Paul Morris) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_11 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> xi.1996 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;1996-11&quot;} </td>
   <td style="text-align:left;"> dwc:verbatimEventDate with Roman numerals as used in some disciplines (suggested by Paul Morris). From Vernet example </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_12 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1932.10.6 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;1932-10-06&quot;} </td>
   <td style="text-align:left;"> dwc:eventDate interpreted from dwc:verbatimEventDate with period separators [found in the wild in VertNet data] </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_13 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 15.10.1932 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;1932-10-15&quot;} </td>
   <td style="text-align:left;"> dwc:eventDate interpreted from dwc:verbatimEventDate with period separators in soviet/post-soviet dd.mm.yyyy form </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_14 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1932年3月5日 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;1932-03-05&quot;} </td>
   <td style="text-align:left;"> dwc:eventDate interpreted from dwc:verbatimEventDate in yyyy mm dd format with Chinese characters for year, month, and day included. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_15 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 31 August 1932 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;1932-08-31&quot;} </td>
   <td style="text-align:left;"> dwc:eventDate interpreted from dwc:verbatimEventDate in dd Month yyyy form </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_16 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> XX DEC 1932 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;1932-12&quot;} </td>
   <td style="text-align:left;"> dwc:eventDate interpreted as yyyy-mm from dwc:verbatimEventDate in dd MMM yyyy form with XX interpreted as a no-data placeholder for day </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_17 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 5. juni 1932 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;1932-06-05&quot;} </td>
   <td style="text-align:left;"> dwc:eventDate interpreted from dwc:verbatimEventDate in dd month yyyy form for localization da_DK </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_18 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 9.ii-10.iii.2000 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;2000-02-09/2000-03-10&quot;} </td>
   <td style="text-align:left;"> dwc:eventDate interpreted from dwc:verbatimEventDate in dd.mm-dd.mm.yyyy form with Roman numeral months [found in the wild in VertNet data] </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_19 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Aug. 1987 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;1987-08&quot;} </td>
   <td style="text-align:left;"> dwc:eventDate interpreted from dwc:verbatimEventDate in  MMM. yyyy form for localization en_US [found in the wild in VertNet data] </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_20 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 11-VII-1885 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;1885-07-11&quot;} </td>
   <td style="text-align:left;"> dwc:eventDate interpreted from dwc:verbatimEventDate in dd-mm-yyyy form with Roman numeral months [found in the wild in MCZ data] </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 052_21 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1980s </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;1980-01-01/1989-12-31&quot;} </td>
   <td style="text-align:left;"> dwc:eventDate interpreted from dwc:verbatimEventDate expressed as a decade [found in the wild in VertNet data] </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:eventDate="", dwc:verbatimEventDate="Friday 29th Oct. 2021": Response.status=FILLED_IN, Response.result=dwc:eventDate="2021-10-29", Response.comment="dwc:verbatimEventDate contains an interpretable value (assuming some external lookup thesauri)"],[dwc:eventDate="", dwc:verbatimEventDate="03/04/2020": Response.status=NOT_AMENDED, Response.result="", Response.comment="dwc:verbatimEventDate is ambiguous - could be either 3rd April or 4th March"]

## Teste 053: [`VALIDATION_COORDINATES_ZERO`](https://github.com/tdwg/bdq/issues/87) 

**Nome do teste**: `VALIDATION_COORDINATES_ZERO` 

**Última atualização**: `2023-06-20` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/87 

**ID oficial do teste**: `1bf0e210-6792-4128-b8cc-ab6828aa4871` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `decimalLatitude, decimalLongitude` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Are the values of either dwc:decimalLatitude or dwc:decimalLongitude numbers that are not equal to 0?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:decimalLatitude is EMPTY or is not interpretable as a number, or dwc:decimalLongitude is EMPTY or is not interpretable as a number; COMPLIANT if either the value of dwc:decimalLatitude is not = 0 or the value of dwc:decimalLongitude is not = 0; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _A record with 0.0 is interpreted as the string "0"_ 



<table>
<caption>Tabela 53: Termos testados e os resultados esperados para o teste VALIDATION_COORDINATES_ZERO.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> decimalLatitude </th>
   <th style="text-align:left;"> decimalLongitude </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 053_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> All input fields EMPTY. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 053_2 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> 140.45 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude is not interpretable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 053_3 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatitude and dwc:decimalLongitude are zero </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 053_4 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatitude and dwc:decimalLongitude are zero </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 053_5 </td>
   <td style="text-align:left;"> 41.0554 N </td>
   <td style="text-align:left;"> 121.0534 W </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:decimalLatitude and dwc:decimalLongitude are not numeric </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 053_6 </td>
   <td style="text-align:left;"> 21.0534 </td>
   <td style="text-align:left;"> 81.0554 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatitude and dwc:decimalLongitude are not zero </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 053_7 </td>
   <td style="text-align:left;"> -99.2314 </td>
   <td style="text-align:left;"> -189.5674 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatitude and dwc:decimalLongitude are not zero </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 053_8 </td>
   <td style="text-align:left;"> -41.0525925872862 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatitude and dwc:decimalLongitude are not zero </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 053_9 </td>
   <td style="text-align:left;"> 18.835941 </td>
   <td style="text-align:left;"> -94.4805934 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatitude and dwc:decimalLongitude are not zero </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 053_10 </td>
   <td style="text-align:left;"> 41.0525925872862 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatitude and dwc:decimalLongitude are not zero </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 053_11 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> -71.5310546742521 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLongitude is not zero </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 053_12 </td>
   <td style="text-align:left;"> -41.0525925872862 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatitude is not zero </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:decimalLatitude="21.0534", dwc:decimalLongitude="81.0554": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:decimalLatitude and dwc:decimalLongitude are not zero"],[dwc:decimalLatitude="0", dwc:decimalLongitude="0",: Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:decimalLatitude and dwc:decimalLongitude are zero"]

## Teste 054: [`VALIDATION_EVENT_TEMPORAL_NOTEMPTY`](https://github.com/tdwg/bdq/issues/88) 

**Nome do teste**: `VALIDATION_EVENT_TEMPORAL_NOTEMPTY` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/88 

**ID oficial do teste**: `41267642-60ff-4116-90eb-499fee2cd83f` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `eventDate, startDayOfYear, endDayOfYear, year, month, day, verbatimEventDate` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in any of the terms dwc:eventDate, dwc:year, dwc:month, dwc:day, dwc:startDayOfYear, dwc:endDayOfYear, dwc:verbatimEventDate?_ 

**Especificação**: 
> _COMPLIANT if any of dwc:eventDate, dwc:year, dwc:month, dwc:day, dwc:startDayOfYear, dwc:endDayOfYear, dwc:verbatimEventDate are NOT EMPTY; otherwise NOT_COMPLIANT._ 

**Código fonte de exemplo**: _https://github.com/FilteredPush/event_date_qc/blob/8740a00b52ef41cdda5fc7fa1689e5d95a23a94b/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L1207 Unit test at  https://github.com/FilteredPush/event_date_qc/blob/8740a00b52ef41cdda5fc7fa1689e5d95a23a94b/src/test/java/org/filteredpush/qc/date/DwcEventDQTest.java#L881_ 

**Notas**: _Only fails if all of the relevant fields of the Darwin Core Event class are EMPTY or do not exist. Relevant Darwin Core fields include dwc:eventDate, dwc:verbatimEventDate, dwc:year, dwc:month, dwc:day, dwc:startDayOfYear, dwc:endDayOfYear.  The terms dwc:eventID (if populated may or may not point to temporal information accessible to user of the data) and dwc:eventTime (uses of dwc:eventTime are rare and put it out of scope of the CORE tests) are not included._ 



<table>
<caption>Tabela 54: Termos testados e os resultados esperados para o teste VALIDATION_EVENT_TEMPORAL_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> eventDate </th>
   <th style="text-align:left;"> startDayOfYear </th>
   <th style="text-align:left;"> endDayOfYear </th>
   <th style="text-align:left;"> year </th>
   <th style="text-align:left;"> month </th>
   <th style="text-align:left;"> day </th>
   <th style="text-align:left;"> verbatimEventDate </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 054_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> All input fields EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_2 </td>
   <td style="text-align:left;"> 1962-11-01T10:00-0600 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_3 </td>
   <td style="text-align:left;"> 1964-11-01T10:00-0600 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 32 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_7 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_8 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 194x </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day and dwc:year are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1952 </td>
   <td style="text-align:left;"> 2 </td>
   <td style="text-align:left;"> 30 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day, dwc:month and dwc:year are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_11 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1952 </td>
   <td style="text-align:left;"> 2 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day, dwc:month and dwc:year are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_12 </td>
   <td style="text-align:left;"> 1949-09-15T12:34 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;"> 9 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day, dwc:month, dwc:year and dwc:evendate are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_13 </td>
   <td style="text-align:left;"> 1949-09-16T12:34 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;"> 9 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day, dwc:month, dwc:year and dwc:evendate are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_14 </td>
   <td style="text-align:left;"> 1949-09-15T12:34 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;"> 9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:month, dwc:year and dwc:evendate are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_15 </td>
   <td style="text-align:left;"> 1949-12-09T12:34 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 9/12/1949 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:evendate and dwc:verbatimEventDate are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_16 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 9/15/1949 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:verbatimEventDate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_17 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> 20 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:startDayOfYear and dwc:endDayOfYear are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_18 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> 20 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:startDayOfYear and dwc:endDayOfYear are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_19 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> 20 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:startDayOfYear and dwc:endDayOfYear are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_20 </td>
   <td style="text-align:left;"> 1949-01-15T12:34/1949-01-20T17:00 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> 20 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:eventDate, dwc:startDayOfYear and dwc:endDayOfYear are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_21 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> 20 </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day, dwc:month, dwc:year, dwc:startDayOfYear and dwc:endDayOfYear are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_22 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> 20 </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;"> 9 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day, dwc:month, dwc:year, dwc:startDayOfYear and dwc:endDayOfYear are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_23 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 10 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day and dwc:month are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_24 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:month is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_25 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> v </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:month is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_26 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 366 </td>
   <td style="text-align:left;"> 366 </td>
   <td style="text-align:left;"> 2004 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:year, dwc:startDayOfYear and dwc:endDayOfYear are not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_27 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 2021-06-03T24:00 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:verbatimEventDate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 054_28 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1949-01-15T12:34/ </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:verbatimEventDate is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:day="", dwc:month="", dwc:year="", dwc:eventDate="1962-11-01T10:00-0600", dwc:verbatimEventDate="", dwc:startDayOfYear="", dwc:endDayOfYear="": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:eventDate is not EMPTY"],[dwc:dateIdentified="", dwc:day="", dwc:month="", dwc:year="", dwc:eventDate="", dwc:verbatimEventDate="", dwc:startDayOfYear="", dwc:endDayOfYear="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="All input fields EMPTY"]

## Teste 055: [`VALIDATION_DCTYPE_STANDARD`](https://github.com/tdwg/bdq/issues/91) 

**Nome do teste**: `VALIDATION_DCTYPE_STANDARD` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/91 

**ID oficial do teste**: `cdaabb0d-a863-49d0-bc0f-738d771acba5` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Record-level` 

**Termos (colunas) testados**: `type` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Does the value in dc:type occur as a value in the DCMI type vocabulary?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if the value of dc:type is EMPTY; COMPLIANT if the value of dc:type is found in  bdq:sourceAuthority; otherwise NOT_COMPLIANT bdq:sourceAuthority is "Dublin Core Metadata Initiative (DCMI)" {[https://www.dublincore.org/]} {DCMI Type Vocabulary" [https://www.dublincore.org/specifications/dublin-core/dcmi-type-vocabulary/]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _This test must return NOT_COMPLIANT if there is leading or trailing whitespace or there are leading or trailing non-printing characters._ 



<table>
<caption>Tabela 55: Termos testados e os resultados esperados para o teste VALIDATION_DCTYPE_STANDARD.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> type </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 055_1 </td>
   <td style="text-align:left;"> Event </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dc:type matches a term in DCMI Vocabulary </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 055_2 </td>
   <td style="text-align:left;"> StillerImage </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dc:type does not match terms in DCMI Vocabulary </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 055_3 </td>
   <td style="text-align:left;"> anyOldTerm </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dc:type does not match terms in DCMI Vocabulary </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 055_4 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dc:type does not match terms in DCMI Vocabulary </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 055_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dc:type is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 055_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dc:type is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 055_7 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dc:type does not match terms in DCMI Vocabulary </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 055_8 </td>
   <td style="text-align:left;"> AnyType </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority not available or unreachable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 055_9 </td>
   <td style="text-align:left;"> dc:type </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dc:type does not match terms in DCMI Vocabulary </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dc:type="Event": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dc:type matches a term in DCMI Vocabulary"],[dc:type="StillerImage": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dc:type does not match terms in DCMI Vocabulary"]

## Teste 056: [`AMENDMENT_EVENTDATE_FROM_YEARMONTHDAY`](https://github.com/tdwg/bdq/issues/93) 

**Nome do teste**: `AMENDMENT_EVENTDATE_FROM_YEARMONTHDAY` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/93 

**ID oficial do teste**: `3892f432-ddd0-4a0a-b713-f2e2ecbd879d` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `eventDate, year, month, day` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Propose amendment to the value of dwc:eventDate from values in dwc:year, dwc:month and dwc:day._ 

**Especificação**: 
> _INTERNAL _PREREQUISITES_NOT_MET if dwc:eventDate is not EMPTY or dwc:year is EMPTY or is not interpretable as a valid year; FILLED_IN the value of dwc:eventDate if an ISO 8601-1 date was interpreted from the values in dwc:year, dwc:month and dwc:day; otherwise NOT_AMENDED._ 

**Código fonte de exemplo**: _https://github.com/FilteredPush/event_date_qc/blob/5f2e7b30f8a8076977b2a609e0318068db80599a/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L1003 unit tests at https://github.com/FilteredPush/event_date_qc/blob/5f2e7b30f8a8076977b2a609e0318068db80599a/src/test/java/org/filteredpush/qc/date/DwcEventDQTest.java#L493_ 

**Notas**: _An attempt to populate dwc:eventDate from dwc:verbatimEventDate and from dwc:startDayOfYear and dwc:endDayOfYear should be made before this test is run. If dwc:year and dwc:day are present and interpretable, but dwc:month is not supplied or is not interpretable, then just the year should be given as the proposed amendment.   This test assumes that that dwc:year, dwc:month, dwc:day are in a Gregorian calendar, and that only those three pieces of information are needed to produce a dwc:eventDate (explicitly in ISO 8601-1 format, and thus using the Gregorian calendar). When running the test, the original precision, e.g. dwc:year=1980, dwc:month=1 should be retained, e.g. dwc:eventDate should become 1980-01, not 1980-01-01/1980-01-3._ 



<table>
<caption>Tabela 56: Termos testados e os resultados esperados para o teste AMENDMENT_EVENTDATE_FROM_YEARMONTHDAY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> eventDate </th>
   <th style="text-align:left;"> year </th>
   <th style="text-align:left;"> month </th>
   <th style="text-align:left;"> day </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 056_1 </td>
   <td style="text-align:left;"> 2021-10-29 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 056_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:year EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 056_3 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:year is an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 056_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 2021 </td>
   <td style="text-align:left;"> 10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;2021-10&quot;} </td>
   <td style="text-align:left;"> dwc:year and dwc:month are interpretable values </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 056_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 2021 </td>
   <td style="text-align:left;"> 10 </td>
   <td style="text-align:left;"> 29 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;2021-10-29&quot;} </td>
   <td style="text-align:left;"> dwc:year, dwc:month and dwc:day are interpretable values </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 056_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 2021 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 29 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;2021&quot;} </td>
   <td style="text-align:left;"> dwc:year and dwc:day are interpretable values but as dwc:month is missing we resolve only to dwc:year </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 056_7 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 2021 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> 29 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;2021-10-29&quot;} </td>
   <td style="text-align:left;"> dwc:year and dwc:day in range and dwc:month is interpretable as an integer between 1-12. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 056_8 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> 10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:year is uninterpretable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 056_9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 197 </td>
   <td style="text-align:left;"> 10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:year is uninterpretable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 056_10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 2021 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;2021&quot;} </td>
   <td style="text-align:left;"> dwc:year is an interpretable value </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:eventDate="", dwc:year="2021", dwc:month="X", dwc:day="29": Response.status=FILLED_IN, Response.result=dwc:eventDate="2021-10-29", Response.comment="dwc:year and dwc:day in range and dwc:month is interpretable as an integer between 1-12."],[dwc:eventDate="", dwc:year="x", dwc:month="10", dwc:day="": Response.status=NOT_AMENDED, Response.result=, Response.comment="dwc:year is uninterpretable as a valid year and dwc:day are EMPTY so dwc:eventDate is not FILLED_IN"]

## Teste 057: [`ISSUE_ESTABLISHMENTMEANS_NOTEMPTY`](https://github.com/tdwg/bdq/issues/94) 

**Nome do teste**: `ISSUE_ESTABLISHMENTMEANS_NOTEMPTY` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/94 

**ID oficial do teste**: `acc8dff2-d8d1-483a-946d-65a02a452700` 

**Tipo de teste**: `Issue` 

**Contexto dos termos testados**: `Occurrence` 

**Termos (colunas) testados**: `establishmentMeans` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:establishmentMeans?_ 

**Especificação**: 
> _POTENTIAL_ISSUE if dwc:establishmentMeans is not EMPTY; otherwise NOT_ISSUE_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 57: Termos testados e os resultados esperados para o teste ISSUE_ESTABLISHMENTMEANS_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> establishmentMeans </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 057_1 </td>
   <td style="text-align:left;"> native </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> POTENTIAL_ISSUE </td>
   <td style="text-align:left;"> dwc:establishmentMeans is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 057_2 </td>
   <td style="text-align:left;"> anyOldTerm </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> POTENTIAL_ISSUE </td>
   <td style="text-align:left;"> dwc:establishmentMeans is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 057_3 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> POTENTIAL_ISSUE </td>
   <td style="text-align:left;"> dwc:establishmentMeans is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 057_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_ISSUE </td>
   <td style="text-align:left;"> dwc:establishmentMeans is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 057_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_ISSUE </td>
   <td style="text-align:left;"> dwc:establishmentMeans is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 057_6 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> POTENTIAL_ISSUE </td>
   <td style="text-align:left;"> dwc:establishmentMeans is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 057_7 </td>
   <td style="text-align:left;"> cultivated specimen </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> POTENTIAL_ISSUE </td>
   <td style="text-align:left;"> dwc:establishmentMeans is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:establishmentMeans="?": Response.status=RUN_HAS_RESULT, Response.result=POTENTIAL_ISSUE, Response.comment="dwc:establishmentMeans is not EMPTY"],[dwc:establishmentMeans="": Response.status=RUN_HAS_RESULT, Response.result=NOT_ISSUE, Response.comment="dwc:establishmentMeans is EMPTY"]

## Teste 058: [`VALIDATION_DECIMALLONGITUDE_NOTEMPTY`](https://github.com/tdwg/bdq/issues/96) 

**Nome do teste**: `VALIDATION_DECIMALLONGITUDE_NOTEMPTY` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/96 

**ID oficial do teste**: `9beb9442-d942-4f42-8b6a-fcea01ee086a` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `decimalLongitude` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:decimalLongitude?_ 

**Especificação**: 
> _COMPLIANT if dwc:decimalLongitude is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 58: Termos testados e os resultados esperados para o teste VALIDATION_DECIMALLONGITUDE_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> decimalLongitude </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 058_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLongitude is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 058_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLongitude is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 058_3 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLongitude is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 058_4 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLongitude is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 058_5 </td>
   <td style="text-align:left;"> 121.0534 W </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLongitude is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 058_6 </td>
   <td style="text-align:left;"> 181.0554 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLongitude is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 058_7 </td>
   <td style="text-align:left;"> -189.5674 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLongitude is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:decimalLongitude="0": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:decimalLongitude is not EMPTY"],[dwc:decimalLongitude="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:decimalLongitude is EMPTY"]

## Teste 059: [`VALIDATION_COUNTRYCODE_NOTEMPTY`](https://github.com/tdwg/bdq/issues/98) 

**Nome do teste**: `VALIDATION_COUNTRYCODE_NOTEMPTY` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/98 

**ID oficial do teste**: `853b79a2-b314-44a2-ae46-34a1e7ed85e4` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `countryCode` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:countryCode?_ 

**Especificação**: 
> _COMPLIANT if dwc:countryCode is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _[geo_ref_qc DwCGeoRefDQ,validationCountrycodeNotempty()](https://github.com/FilteredPush/geo_ref_qc/blob/78afb5f2c8b8e2ebede1de48cb7a40fd1503748f/src/main/java/org/filteredpush/qc/georeference/DwCGeoRefDQ.java#L1060)_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 59: Termos testados e os resultados esperados para o teste VALIDATION_COUNTRYCODE_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> countryCode </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 059_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:countryCode is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 059_2 </td>
   <td style="text-align:left;"> GL </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:countryCode is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 059_3 </td>
   <td style="text-align:left;"> GRL </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:countryCode is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 059_4 </td>
   <td style="text-align:left;"> XX </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:countryCode is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 059_5 </td>
   <td style="text-align:left;"> Australia </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:countryCode is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 059_6 </td>
   <td style="text-align:left;"> US </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:countryCode is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 059_7 </td>
   <td style="text-align:left;"> MX </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:countryCode is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 059_8 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:countryCode is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:countryCode="Australia": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:countryCode is not EMPTY"],[dwc:countryCode="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:countryCode is EMPTY"]

## Teste 060: [`VALIDATION_LICENCE_NOTEMPTY`](https://github.com/tdwg/bdq/issues/99) 

**Nome do teste**: `VALIDATION_LICENCE_NOTEMPTY` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/99 

**ID oficial do teste**: `15f78619-811a-4c6f-997a-a4c7888ad849` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Record-level` 

**Termos (colunas) testados**: `license` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dcterms:license?_ 

**Especificação**: 
> _COMPLIANT if dcterms:license is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The license at the record level might be derived from the license of the data set from which the record is retrieved_ 



<table>
<caption>Tabela 60: Termos testados e os resultados esperados para o teste VALIDATION_LICENCE_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> license </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 060_1 </td>
   <td style="text-align:left;"> CC0 1.0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dcterms:license is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 060_2 </td>
   <td style="text-align:left;"> corrosive commons </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dcterms:license is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 060_3 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dcterms:license is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 060_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dcterms:license is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 060_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dcterms:license is EMPTY or missing </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 060_6 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dcterms:license is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dcterms:license="CC0 1.0": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dcterms:license is not EMPTY"],[dcterms:license="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dcterms:license is EMPTY"]

## Teste 061: [`VALIDATION_POLYNOMIAL_CONSISTENT`](https://github.com/tdwg/bdq/issues/101) 

**Nome do teste**: `VALIDATION_POLYNOMIAL_CONSISTENT` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/101 

**ID oficial do teste**: `17f03f1f-f74d-40c0-8071-2927cfc9487b` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `scientificName, genericName, specificEpithet, infraspecificEpithet` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is the polynomial represented in dwc:scientificName consistent with the equivalent values in dwc:genericName, dwc:specificEpithet, dwc:infraspecificEpithet?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:scientificName is EMPTY, or all of dwc:genericName, dwc:specificEpithet and dwc:infraspecificEpithet are EMPTY; COMPLIANT if the polynomial, as represented in dwc:scientificName, is consistent with NOT_EMPTY values of dwc:genericName, dwc:specificEpithet, dwc:infraspecificEpithet; otherwise NOT_COMPLIANT._ 

**Código fonte de exemplo**: _https://github.com/FilteredPush/FP-KurationServices/blob/master/src/main/java/org/filteredpush/kuration/util/SciNameServiceUtil.java#L97_ 

**Notas**: _If dwc:specificEpithet is populated then this test expects that the value dwc:specificEpithet is the name of the second or species epithet of the scientificName.  If dwc:genericName is populated, this test expects that the value of dwc:genus is the first word of the value of dwc:scientificName.  If dwc:specificEpithet is populated then this test expects that the value dwc:specificEpithet is the name of the first or species epithet of the scientificName.  If dwc:infraspecificEpithet is populated, then this test expects that the value of dwc:infraspecificEpithet is the name of the lowest or terminal infraspecific epithet of the scientificName, excluding any rank designation._ 



<table>
<caption>Tabela 61: Termos testados e os resultados esperados para o teste VALIDATION_POLYNOMIAL_CONSISTENT.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> scientificName </th>
   <th style="text-align:left;"> genericName </th>
   <th style="text-align:left;"> specificEpithet </th>
   <th style="text-align:left;"> infraspecificEpithet </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 061_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> All  input terms are EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 061_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Hakea </td>
   <td style="text-align:left;"> decurrens </td>
   <td style="text-align:left;"> physocarpa </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificName is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 061_3 </td>
   <td style="text-align:left;"> Hakea decurrens ssp. physocarpa </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> decurrens </td>
   <td style="text-align:left;"> physocarpa </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is consistent with atomic parts (dwc:genus, dwc:specificEpithet and dwc:infraspecificEpithet) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 061_4 </td>
   <td style="text-align:left;"> Hakea decurrens ssp. physocarpa </td>
   <td style="text-align:left;"> Hakea </td>
   <td style="text-align:left;"> decurrens </td>
   <td style="text-align:left;"> physocarpa </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is consistent with atomic parts (dwc:genus, dwc:specificEpithet and dwc:infraspecificEpithet) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 061_5 </td>
   <td style="text-align:left;"> Hakea decurrens physocarpa </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> decurrens </td>
   <td style="text-align:left;"> physocarpa </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is consistent with atomic parts (dwc:genus, dwc:specificEpithet and dwc:infraspecificEpithet) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 061_6 </td>
   <td style="text-align:left;"> Hakea decurrens subsp. physocarpa W.R.Barker </td>
   <td style="text-align:left;"> Hakea </td>
   <td style="text-align:left;"> decurrens </td>
   <td style="text-align:left;"> physocarpa </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is consistent with atomic parts (dwc:genus, dwc:specificEpithet and dwc:infraspecificEpithet) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 061_7 </td>
   <td style="text-align:left;"> Hakea decurrens ssp. physocarpa </td>
   <td style="text-align:left;"> Hakea </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> physocarpa </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is consistent with not empty values in dwc:genus and dwc:infraspecificEpithet; dwc:specificEpithet is empty. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 061_8 </td>
   <td style="text-align:left;"> Hakea decurrens ssp. ? physocarpa </td>
   <td style="text-align:left;"> Hakea </td>
   <td style="text-align:left;"> decurrens </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is consistent with not empty values in dwc:genus and dwc:infraspecificEpithet; dwc:specificEpithet is empty. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 061_9 </td>
   <td style="text-align:left;"> Hakea decurrens ssp. Aff. physocarpa </td>
   <td style="text-align:left;"> Hakea </td>
   <td style="text-align:left;"> decurrens </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is inconsistent with atomic parts (dwc:genus, dwc:specificEpithet and dwc:infraspecificEpithet) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 061_10 </td>
   <td style="text-align:left;"> Hakea decurrens </td>
   <td style="text-align:left;"> Hakea </td>
   <td style="text-align:left;"> decurrens </td>
   <td style="text-align:left;"> physocarpa </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is inconsistent with atomic parts (dwc:genus, dwc:specificEpithet and dwc:infraspecificEpithet) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 061_11 </td>
   <td style="text-align:left;"> Hakea decurrens subsp. physocarpa W.R.Barker </td>
   <td style="text-align:left;"> Hakea </td>
   <td style="text-align:left;"> decurrens </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is consistent with dwc:genus and dwc:specificEpithet; dwc:infraspecificEpithet is empty. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 061_12 </td>
   <td style="text-align:left;"> Hakea decurrens </td>
   <td style="text-align:left;"> Hakea </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is consistent with dwc:genus; dwc:specificEpithet and dwc:infraspecificEpithet are both empty. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 061_13 </td>
   <td style="text-align:left;"> Hakea decurrens ssp. physocarpa W.R.Barker </td>
   <td style="text-align:left;"> Hakea </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> pyhsocarpa </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is inconsistent with dwc:infraspecificEpithet </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 061_14 </td>
   <td style="text-align:left;"> Hakea decurrens ssp. physocarpa </td>
   <td style="text-align:left;"> Hakea </td>
   <td style="text-align:left;"> physocarpa </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is inconsistent with dwc:specificEpithet </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 061_15 </td>
   <td style="text-align:left;"> Hakea decurrens </td>
   <td style="text-align:left;"> Hakea </td>
   <td style="text-align:left;"> physocarpa </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificName is inconsistent with dwc:specificEpithet </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:scientificName="Hakea decurrens ssp. physocarpa", dwc:genericName="", dwc:specificEpithet="decurrens", dwc:infraspecificEpithet="physocarpa": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="Values of all non-empty atomic terms are found in the polynomial"],[dwc:scientificName="Hakea decurrens", dwc:genericName="Hakea", dwc:specificEpithet="decurrens", dwc:infraspecificEpithet="physocarpa": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:scientificName is inconsistent with atomic parts (dwc:genus, dwc:specificEpithet and dwc:infraspecificEpithet)"]

## Teste 062: [`AMENDMENT_GEODETICDATUM_ASSUMEDDEFAULT`](https://github.com/tdwg/bdq/issues/102) 

**Nome do teste**: `AMENDMENT_GEODETICDATUM_ASSUMEDDEFAULT` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/102 

**ID oficial do teste**: `7498ca76-c4d4-42e2-8103-acacccbdffa7` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `decimalLatitude, decimalLongitude, geodeticDatum, coordinateUncertaintyInMeters` 

**Pré-requisitos externos (parâmetros)**: `bdq:defaultGeodeticDatum` 

**Descrição**: 
> _Propose amendment to dwc:geodeticDatum using the value of bdq:defaultGeodeticDatum if dwc:geodeticDatum is empty. If dwc:coordinateUncertaintyInMeters is not empty and there are not empty values for dwc:latitude and dwc:longitude, amend dwc:coordinateUncertaintyInMeters by adding a maximum datum shift._ 

**Especificação**: 
> _If dwc:geodeticDatum is EMPTY, fill in the value of dwc:geodeticDatum with the value of bdq:defaultGeodeticDatum, report FILLED_IN and, if dwc:coordinateUncertaintyInMeters, dwc:decimalLatitude and dwc:decimalLongitude are NOT_EMPTY, amend the value of dwc:coordinateUncertaintyInMeters by adding the maximum datum shift between the specified bdq:defaultGeodeticDatum and any other datum at the provided dwc:decimalLatitude and dwc:decimalLongitude and instead report AMENDED; otherwise NOT_AMENDED. bdq:defaultGeodeticDatum = "EPSG:4326" {[https://epsg.org/crs_4326/WGS-84.html]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _If the dwc:coordinateUncertaintyInMeters is EMPTY, not interpretable, or not valid, this amendment should not provide a dwc:coordinateUncertaintyInMeters. If the dwc:coordinateUncertaintyInMeters is not EMPTY and is valid, this amendment should add to the dwc:coordinateUncertaintyInMeters the uncertainty contributed by the maximum datum shift at the given coordinates. Since different systems have differing requirements for what the default datum should be, it is left unspecified, but should match whatever the target datum is in AMENDMENT_COORDINATES_CONVERTED (620749b9-7d9c-4890-97d2-be3d1cde6da8). After the amendment is performed, the dwc:geodeticDatum field should be the assumed default datum as parameterized. An example implementation to determine the uncertainty added by asserting a default datum (datum shift) where a known datum is not declared can be found in [datumshiftproj.py](https://github.com/VertNet/georefcalculator/blob/master/source/python/datumshiftproj.py) in the source code for the [Georeferencing Calculator](http://georeferencing.org/georefcalculator/gc.html) (Wieczorek & Wieczorek 2021). Included in the source code is a [5-degree grid](https://github.com/VertNet/georefcalculator/blob/master/datumerrordata.js) of datum shifts from an unknown datum to WGS84._ 



<table>
<caption>Tabela 62: Termos testados e os resultados esperados para o teste AMENDMENT_GEODETICDATUM_ASSUMEDDEFAULT.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> decimalLatitude </th>
   <th style="text-align:left;"> decimalLongitude </th>
   <th style="text-align:left;"> geodeticDatum </th>
   <th style="text-align:left;"> coordinateUncertaintyInMeters </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 062_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:geodeticDatum&quot;:&quot;EPSG:4326&quot;} </td>
   <td style="text-align:left;"> dwc:geodeticDatum is EMPTY so FILLED_IN with the default value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 062_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> WGS84 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:geodeticDatum contains and interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 062_3 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:geodeticDatum contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 062_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:geodeticDatum contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 062_5 </td>
   <td style="text-align:left;"> -30.123 </td>
   <td style="text-align:left;"> 130.321 </td>
   <td style="text-align:left;"> GDA </td>
   <td style="text-align:left;"> 50 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:geodeticDatum is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 062_6 </td>
   <td style="text-align:left;"> -30.00 </td>
   <td style="text-align:left;"> 130.00 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:geodeticDatum&quot;:&quot;EPSG:4326&quot;} </td>
   <td style="text-align:left;"> dwc:godeticDatum is EMPTY so filled with default </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:geodeticDatum="[null]", dwc:decimalLatitude="-30.00", dwc:decimalLongitude="130.00", dwc:coordinateUncertaintyInMeters="50": Response.status=AMENDED, Response.result=dwc:geodeticDatum="EPSG:4326", dwc:coordinateUncertaintyInMeters="2877", Response.comment="dwc:godeticDatum is EMPTY so filled with default and dwc:coordinateUncertaintyInMeters amended to maximum possible value"],[dwc:geodeticDatum="WGS84": Response.status=NOT_AMENDED, Response.result=, Response.comment="dwc:geodeticDatum contains and interpretable value"]

## Teste 063: [`VALIDATION_DCTYPE_NOTEMPTY`](https://github.com/tdwg/bdq/issues/103) 

**Nome do teste**: `VALIDATION_DCTYPE_NOTEMPTY` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/103 

**ID oficial do teste**: `374b091a-fc90-4791-91e5-c1557c649169` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Record-level` 

**Termos (colunas) testados**: `type` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dc:type?_ 

**Especificação**: 
> _COMPLIANT if dc:type is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 63: Termos testados e os resultados esperados para o teste VALIDATION_DCTYPE_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> type </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 063_1 </td>
   <td style="text-align:left;"> StillImage </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dc:type is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 063_2 </td>
   <td style="text-align:left;"> StillerImage </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dc:type is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 063_3 </td>
   <td style="text-align:left;"> anyOldTerm </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dc:type is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 063_4 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dc:type is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 063_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dc:type is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 063_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dc:type is EMPTY or missing </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 063_7 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dc:type is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dc:type="?": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dc:type is not EMPTY"],[dc:type="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dc:type is EMPTY"]

## Teste 064: [`VALIDATION_BASISOFRECORD_STANDARD`](https://github.com/tdwg/bdq/issues/104) 

**Nome do teste**: `VALIDATION_BASISOFRECORD_STANDARD` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/104 

**ID oficial do teste**: `42408a00-bf71-4892-a399-4325e2bc1fb8` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Record-level` 

**Termos (colunas) testados**: `basisOfRecord` 

**Pré-requisitos externos (parâmetros)**: `dwc:basisOfRecord vocabulary` 

**Descrição**: 
> _Does the value of dwc:basisOfRecord occur in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:basisOfRecord is EMPTY; COMPLIANT if the value of dwc:basisOfRecord is valid using the bdq:sourceAuthority; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "Darwin Core basisOfRecord" {[https://dwc.tdwg.org/terms/#dwc:basisOfRecord]}{dwc:basisOfRecord vocabulary [https://rs.gbif.org/vocabulary/dwc/basis_of_record.xml]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The term dwc:basisOfRecord has the comment "Recommended best practice is to use the standard label of one of the Darwin Core classes." The list of these values can be determined by searching https://github.com/tdwg/dwc/blob/master/vocabulary/term_versions.csv for rows with status="recommended" and rdf_type="http://www.w3.org/2000/01/rdf-schema#Class". For tests against a dwc:Occurrence record, the set of valid terms is more limited and embodied in the resource found at https://rs.gbif.org/vocabulary/dwc/basis_of_record.xml. This test must return NOT_COMPLIANT if there is leading or trailing whitespace or there are leading or trailing non-printing characters._ 



<table>
<caption>Tabela 64: Termos testados e os resultados esperados para o teste VALIDATION_BASISOFRECORD_STANDARD.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> basisOfRecord </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 064_1 </td>
   <td style="text-align:left;"> Preserved Specimen </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority is not available </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 064_2 </td>
   <td style="text-align:left;"> Preserved Specimen </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord matches a standard label of one of the Darwin Core classes </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 064_3 </td>
   <td style="text-align:left;"> Fossil Specimen </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord matches a standard label of one of the Darwin Core classes </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 064_4 </td>
   <td style="text-align:left;"> Human Observation </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord matches a standard label of one of the Darwin Core classes </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 064_5 </td>
   <td style="text-align:left;"> Taxon </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord matches a standard label of one of the Darwin Core classes </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 064_6 </td>
   <td style="text-align:left;"> Specimen </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord does not exactly match a standard label of one of the Darwin Core classes </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 064_7 </td>
   <td style="text-align:left;"> preserved specimen </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord does not match a standard label of one of the Darwin Core classes. Incorrect capitalization </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 064_8 </td>
   <td style="text-align:left;"> anyOldTerm </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord does not match a standard label of one of the Darwin Core classes </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 064_9 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord does not match a standard label of one of the Darwin Core classes </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 064_10 </td>
   <td style="text-align:left;"> present </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> bdq:sourceAuthority service is not available, try again later </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 064_11 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:basisOfRecord is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 064_12 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:basisOfRecord is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 064_13 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:basisOfRecord does not match a standard label of one of the Darwin Core classes </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:basisOfRecord="Taxon": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:basisOfRecord matches a standard label of one of the Darwin Core classes"],[dwc:basisOfRecord="Specimen": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:basisOfRecord does not exactly match a standard label of one of the Darwin Core classes"]

## Teste 065: [`VALIDATION_TAXON_NOTEMPTY`](https://github.com/tdwg/bdq/issues/105) 

**Nome do teste**: `VALIDATION_TAXON_NOTEMPTY` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/105 

**ID oficial do teste**: `06851339-843f-4a43-8422-4e61b9a00e75` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `taxonID, scientificNameID, acceptedNameUsageID, scientificName` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in any of the terms needed to determine that the taxon exists?_ 

**Especificação**: 
> _COMPLIANT if at least one term needed to determine the taxon of the entity exists and is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _This tests for records that have no taxonomic (NAME) information. If there is any value for any of the Information Elements, this may be useful information. See example._ 



<table>
<caption>Tabela 65: Termos testados e os resultados esperados para o teste VALIDATION_TAXON_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> taxonID </th>
   <th style="text-align:left;"> scientificNameID </th>
   <th style="text-align:left;"> acceptedNameUsageID </th>
   <th style="text-align:left;"> scientificName </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 065_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> All input fields are empty or missing </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 065_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Eucalyptus gunnii </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> at least enough terms exist that identify that an entity exists </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 065_3 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> at least enough terms exist that identify that an entity exists </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 065_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> XVF456 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> at least enough terms exist that identify that an entity exists </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 065_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Fred </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> at least enough terms exist that identify that an entity exists </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 065_6 </td>
   <td style="text-align:left;"> taxonID </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> at least enough terms exist that identify that an entity exists </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 065_7 </td>
   <td style="text-align:left;"> taxonID </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> at least enough terms exist that identify that an entity exists </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:taxonID="", dwc:scientificNameID="", dwc:acceptedNameUsageID="", dwc:parentNameUsageID="", dwc:originalNameUsageID="", dwc:taxonConceptID="", dwc:scientificName="Eucalyptus gunnii", dwc:higherClassification="", dwc:kingdom="", dwc:phylum="", dwc:class="", dwc:order="", dwc:family="", dwc:genus="", dwc:subgenus="", dwc:specificEpithet="", dwc:infraspecificEpithet="", dwc:vernacularName="" : Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="at least enough terms exist that identify that an entity exists"],[dwc:taxonID="", dwc:scientificNameID="", dwc:acceptedNameUsageID="", dwc:parentNameUsageID="", dwc:originalNameUsageID="", dwc:taxonConceptID="", dwc:scientificName="", dwc:higherClassification="", dwc:kingdom="", dwc:phylum="", dwc:class="", dwc:order="", dwc:family="", dwc:genus="", dwc:subgenus="", dwc:specificEpithet="", dwc:infraspecificEpithet="", dwc:vernacularName="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="All input fields are empty or missing"]

## Teste 066: [`VALIDATION_MINDEPTH_INRANGE`](https://github.com/tdwg/bdq/issues/107) 

**Nome do teste**: `VALIDATION_MINDEPTH_INRANGE` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/107 

**ID oficial do teste**: `04b2c8f3-c71b-4e95-8e43-f70374c5fb92` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `minimumDepthInMeters` 

**Pré-requisitos externos (parâmetros)**: `bdq:minimumValidDepthInMeters,bdq:maximumValidDepthInMeters` 

**Descrição**: 
> _Is the value of dwc:minimumDepthInMeters within the Parameter range?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:minimumDepthInMeters is EMPTY, or the value is not interpretable as number greater than or equal to zero; COMPLIANT if the value of dwc:minimumDepthInMeters is within the range of bdq:minimumValidDepthInMeters to bdq:maximumValidDepthInMeters inclusive; otherwise NOT_COMPLIANT bdq:minimumValidDepthInMeters default="0",bdq:maximumValidDepthInMeters default="11000"_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The Challenger Deep in the Mariana Trench is the deepest known point in Earth's oceans at 10,994 meters.  We have rounded up bdq:maximumValidDepthInMeters._ 



<table>
<caption>Tabela 66: Termos testados e os resultados esperados para o teste VALIDATION_MINDEPTH_INRANGE.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> minimumDepthInMeters </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 066_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:minimumDepthInMeters is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 066_2 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:minimumDepthInMeters is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 066_3 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:minimumDepthInMeters is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 066_4 </td>
   <td style="text-align:left;"> 12000 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:minimumDepthInMeters is not in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 066_5 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:minimumDepthInMeters is not interpretable as zero or positive value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 066_6 </td>
   <td style="text-align:left;"> -100 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:minimumDepthInMeters is not interpretable as zero or positive value </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:minimumDepthInMeters="1": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:minimumDepthInMeters is in range"]",[dwc:minimumDepthInMeters="12000": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:minimumDepthInMeters is not in range"]

## Teste 067: [`VALIDATION_MINELEVATION_LESSTHAN_MAXELEVATION`](https://github.com/tdwg/bdq/issues/108) 

**Nome do teste**: `VALIDATION_MINELEVATION_LESSTHAN_MAXELEVATION` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/108 

**ID oficial do teste**: `d708526b-6561-438e-aa1a-82cd80b06396` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `minimumElevationInMeters, maximumElevationInMeters` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is the value of dwc:minimumElevationInMeters a number less than or equal to the value of dwc:maximumElevationInMeters?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:maximumlevationInMeters or dwc:minimumElevationInMeters is EMPTY, or if either is not a number; COMPLIANT if the value of dwc:minimumElevationInMeters is a number less than or equal to the value of the number dwc:maximumElevationInMeters, otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 67: Termos testados e os resultados esperados para o teste VALIDATION_MINELEVATION_LESSTHAN_MAXELEVATION.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> minimumElevationInMeters </th>
   <th style="text-align:left;"> maximumElevationInMeters </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 067_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> All input fields EMPTY. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 067_2 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters is not a numeric value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 067_3 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters is equal to dwc: maximumElevationInMeters </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 067_4 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters is greater than dwc: maximumElevationInMeters </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 067_5 </td>
   <td style="text-align:left;"> -500 </td>
   <td style="text-align:left;"> -500 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters is equal to dwc: maximumElevationInMeters </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 067_6 </td>
   <td style="text-align:left;"> 8860 </td>
   <td style="text-align:left;"> 8860 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters is equal to dwc: maximumElevationInMeters </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 067_7 </td>
   <td style="text-align:left;"> -500 </td>
   <td style="text-align:left;"> 500 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:minimumElevationInMeters is less than dwc: maximumElevationInMeters </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:minimumElevationInMeters="0", dwc:maximumElevationInMeters="0": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:minimumElevationInMeters is equal to dwc: maximumElevationInMeters"],[dwc:minimumElevationInMeters="1", dwc:maximumElevationInMeters="0": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:minimumElevationInMeters is greater than dwc:maximumElevationInMeters"]

## Teste 068: [`VALIDATION_COORDINATEUNCERTAINTY_INRANGE`](https://github.com/tdwg/bdq/issues/109) 

**Nome do teste**: `VALIDATION_COORDINATEUNCERTAINTY_INRANGE` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/109 

**ID oficial do teste**: `c6adf2ea-3051-4498-97f4-4b2f8a105f57` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `coordinateUncertaintyInMeters` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is the value of dwc:coordinateUncertaintyInMeters a number between 1 and 20,037,509?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:coordinateUncertaintyInMeters is EMPTY; COMPLIANT if the value of  dwc:coordinateUncertaintyInMeters can be interpreted as a number between 1 and 20037509 inclusive; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The upper limit is one half the equatorial circumference of the earth._ 



<table>
<caption>Tabela 68: Termos testados e os resultados esperados para o teste VALIDATION_COORDINATEUNCERTAINTY_INRANGE.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> coordinateUncertaintyInMeters </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 068_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:coordinateUncertaintyInMeters is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 068_2 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:coordinateUncertaintyInMeters is a positive integer value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 068_3 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:coordinateUncertaintyInMeters is out of range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 068_4 </td>
   <td style="text-align:left;"> -1 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:coordinateUncertaintyInMeters is out of range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 068_5 </td>
   <td style="text-align:left;"> 20037510 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:coordinateUncertaintyInMeters is out of range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 068_6 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:coordinateUncertaintyInMeters is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 068_7 </td>
   <td style="text-align:left;"> 20037509 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:coordinateUncertaintyInMeters is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 068_8 </td>
   <td style="text-align:left;"> 999999999 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:coordinateUncertaintyInMeters is greater than allowable range </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:coordinateUncertaintyInMeters="1": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:coordinateUncertaintyInMeters is in range"],[dwc:coordinateUncertaintyInMeters="-1": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:coordinateUncertaintyInMeters is out of range"]

## Teste 069: [`VALIDATION_MAXELEVATION_INRANGE`](https://github.com/tdwg/bdq/issues/112) 

**Nome do teste**: `VALIDATION_MAXELEVATION_INRANGE` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/112 

**ID oficial do teste**: `c971fe3f-84c1-4636-9f44-b1ec31fd63c7` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `maximumElevationInMeters` 

**Pré-requisitos externos (parâmetros)**: `bdq:minimumValidElevationInMeters,bdq:maximumValidElevationInMeters` 

**Descrição**: 
> _Is the value of dwc:maximumElevationInMeters of a single record within a valid range_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:maximumElevationInMeters is EMPTY or the value cannot be interpreted as a number; COMPLIANT if the value of dwc:maximumElevationInMeters is within the range of bdq:minimumValidElevationInMeters to bdq:maximumValidElevationInMeters inclusive; otherwise NOT_COMPLIANT bdq:minimumValidElevationInMeters default = "-430",bdq:maximumValidElevationInMeters default = "8850"_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _We have rounded up the Parameter values. We are aware of sub-ice elevations in Antarctica to -3,500m and possible sampling in the atmosphere above the elevation of the top of Mt Everest that would fail this test but we support the odd false positive._ 



<table>
<caption>Tabela 69: Termos testados e os resultados esperados para o teste VALIDATION_MAXELEVATION_INRANGE.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> maximumElevationInMeters </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 069_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:maximumElevation is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 069_2 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:maximumElevation is in is range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 069_3 </td>
   <td style="text-align:left;"> -500 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:maximumElevation is not in range, i.e. is &lt;-430 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 069_4 </td>
   <td style="text-align:left;"> 8860 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:maximumElevation is not in range, i.e. is &gt;8850 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 069_5 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:maxElevation is not interpretable as a number </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:maximumElevationInMeters="0": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:maximumElevation is in is range"],[dwc:maximumElevationInMeters="-500": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:maximumElevation is not in range, i.e. is <-430"]

## Teste 070: [`AMENDMENT_OCCURRENCESTATUS_STANDARDIZED`](https://github.com/tdwg/bdq/issues/115) 

**Nome do teste**: `AMENDMENT_OCCURRENCESTATUS_STANDARDIZED` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/115 

**ID oficial do teste**: `f8f3a093-042c-47a3-971a-a482aaaf3b75` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Occurrence` 

**Termos (colunas) testados**: `occurrenceStatus` 

**Pré-requisitos externos (parâmetros)**: `dwc:occurrenceStatus vocabulary` 

**Descrição**: 
> _Propose amendment to the value of dwc:occurrenceStatus using bdq:sourceAuthority._ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:ocurrenceStatus is EMPTY; AMENDED the value of dwc:occurrenceStatus if could be unambiguously interpreted as a value in bdq:sourceAuthority; otherwise NOT_AMENDED bdq:sourceAuthority = "Darwin Core occurrenceStatus" {https://dwc.tdwg.org/list/#dwc_occurrenceStatus} {dwc:occurrenceStatus vocabulary [https://rs.gbif.org/vocabulary/gbif/occurrence_status_2020-07-15.xml]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The original recommended controlled vocabulary for this term consisted of "present" and "absent", which are the only two appropriate terms for a Darwin Core Occurrence. This is reflected in the suggested dwc:occurrenceStatus vocabulary for this test. Other values for dwc:occurrenceStatus should only arise under circumstances that do not refer to an Occurrence._ 



<table>
<caption>Tabela 70: Termos testados e os resultados esperados para o teste AMENDMENT_OCCURRENCESTATUS_STANDARDIZED.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> occurrenceStatus </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 070_1 </td>
   <td style="text-align:left;"> Sighted </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority not available or unreachable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 070_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:occurrenceStatus is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 070_3 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Input field contains uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 070_4 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:occurrenceStatus&quot;:&quot;present&quot;} </td>
   <td style="text-align:left;"> Input field contains interpretable value. This may be pushing it a little, but I would have interpreted 1/0 as present/absent </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:occurrenceStatus="1": Response.status=AMENDED, Response.result=dwc:occurrenceStatus="present", Response.comment="Input field contains interpretable value. This may be pushing it a little, but I would have interpreted 1/0 as present/absent"],[dwc:occurrenceStatus="X": Response.status=NOT_AMENDED, Response.result=, Response.comment="Input field contains uninterpretable value "X"]

## Teste 071: [`VALIDATION_OCCURRENCESTATUS_STANDARD`](https://github.com/tdwg/bdq/issues/116) 

**Nome do teste**: `VALIDATION_OCCURRENCESTATUS_STANDARD` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/116 

**ID oficial do teste**: `7af25f1e-a4e2-4ff4-b161-d1f25a5c3e47` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Occurrence` 

**Termos (colunas) testados**: `occurrenceStatus` 

**Pré-requisitos externos (parâmetros)**: `dwc:occurrenceStatus vocabulary` 

**Descrição**: 
> _Does the value of dwc:occurrenceStatus occur in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:occurrenceStatus is EMPTY; COMPLIANT if the value of dwc:occurrenceStatus is resolved by the bdq:sourceAuthority; otherwise NOT_COMPLIANT bdq:sourceAuthority = "Darwin Core occurrenceStatus" {https://dwc.tdwg.org/list/#dwc_occurrenceStatus} {dwc:occurrenceStatus vocabulary [https://rs.gbif.org/vocabulary/gbif/occurrence_status_2020-07-15.xml]}_ 

**Código fonte de exemplo**: _https://github.com/FilteredPush/rec_occur_qc/blob/86d413c2b193bb6983e0ad07b3dc0084de118af5/src/main/java/org/filteredpush/qc/metadata/DwCMetadataDQ.java#L479_ 

**Notas**: _The original recommended controlled vocabulary for this term consisted of "present" and "absent", which are the only two appropriate terms for a Darwin Core Occurrence. This is reflected in the suggested dwc:occurrenceStatus vocabulary for this test. Other values for dwc:occurrenceStatus should only arise under circumstances that do not refer to an Occurrence. This test must return NOT_COMPLIANT if there is leading or trailing whitespace or there are leading or trailing non-printing characters._ 



<table>
<caption>Tabela 71: Termos testados e os resultados esperados para o teste VALIDATION_OCCURRENCESTATUS_STANDARD.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> occurrenceStatus </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 071_1 </td>
   <td style="text-align:left;"> present </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceStatus matches a term in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 071_2 </td>
   <td style="text-align:left;"> sighted </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceStatus does not match a term in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 071_3 </td>
   <td style="text-align:left;"> anyOldTerm </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceStatus does not match a term in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 071_4 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceStatus does not match a term in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 071_5 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceStatus does not match a term in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 071_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:occurrenceStatus is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 071_7 </td>
   <td style="text-align:left;"> Sighted </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority not available or unreachable </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:occurrenceStatus="present": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:occurrenceStatus matches a term in the bdq:sourceAuthority"],[dwc:occurrenceStatus="presence": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:occurrenceStatus does not match a term in the bdq:sourceAuthority"]

## Teste 072: [`VALIDATION_OCCURRENCESTATUS_NOTEMPTY`](https://github.com/tdwg/bdq/issues/117) 

**Nome do teste**: `VALIDATION_OCCURRENCESTATUS_NOTEMPTY` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/117 

**ID oficial do teste**: `eb4a17f6-6bea-4cdd-93dd-d5a7e9d1eccf` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Occurrence` 

**Termos (colunas) testados**: `occurrenceStatus` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:occurrenceStatus?_ 

**Especificação**: 
> _COMPLIANT if dwc:occurrenceStatus is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 72: Termos testados e os resultados esperados para o teste VALIDATION_OCCURRENCESTATUS_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> occurrenceStatus </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 072_1 </td>
   <td style="text-align:left;"> http://arctos.database.museum/guid/MSB:Mamm:233627 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceStatus is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 072_2 </td>
   <td style="text-align:left;"> 000866d2-c177-4648-a200-ead4007051b9 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceStatus is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 072_3 </td>
   <td style="text-align:left;"> anyOldTerm </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceStatus is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 072_4 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceStatus is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 072_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceStatus is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 072_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceStatus is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 072_7 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceStatus is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 072_8 </td>
   <td style="text-align:left;"> present </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceStatus is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 072_9 </td>
   <td style="text-align:left;"> abs </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:occurrenceStatus is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:occurrenceStatus="?": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:occurrenceStatus is not EMPTY"],[dwc:occurrenceStatus="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:occurrenceStatus is EMPTY"]

## Teste 073: [`VALIDATION_DECIMALLATITUDE_NOTEMPTY`](https://github.com/tdwg/bdq/issues/119) 

**Nome do teste**: `VALIDATION_DECIMALLATITUDE_NOTEMPTY` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/119 

**ID oficial do teste**: `7d2485d5-1ba7-4f25-90cb-f4480ff1a275` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `decimalLatitude` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:decimalLatitude?_ 

**Especificação**: 
> _COMPLIANT if dwc:decimalLatitude is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 73: Termos testados e os resultados esperados para o teste VALIDATION_DECIMALLATITUDE_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> decimalLatitude </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 073_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatiitude is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 073_2 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatiitude is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 073_3 </td>
   <td style="text-align:left;"> 0.0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatiitude is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 073_4 </td>
   <td style="text-align:left;"> 41.0554 N </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatiitude is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 073_5 </td>
   <td style="text-align:left;"> 121.0534 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatiitude is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 073_6 </td>
   <td style="text-align:left;"> -99.2314 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatiitude is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 073_7 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatiitude is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 073_8 </td>
   <td style="text-align:left;"> 18.835941 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:decimalLatiitude is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:decimalLatitude="0": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:decimalLatiitude is not EMPTY"],[dwc:decimalLatitude="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:decimalLatiitude is EMPTY"]

## Teste 074: [`VALIDATION_SCIENTIFICNAMEID_NOTEMPTY`](https://github.com/tdwg/bdq/issues/120) 

**Nome do teste**: `VALIDATION_SCIENTIFICNAMEID_NOTEMPTY` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/120 

**ID oficial do teste**: `401bf207-9a55-4dff-88a5-abcd58ad97fa` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `scientificNameID` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:scientificNameID?_ 

**Especificação**: 
> _COMPLIANT if dwc:scientificNameID is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 74: Termos testados e os resultados esperados para o teste VALIDATION_SCIENTIFICNAMEID_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> scientificNameID </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 074_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 074_2 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 074_3 </td>
   <td style="text-align:left;"> 123 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 074_4 </td>
   <td style="text-align:left;"> 8fa58e08-08de-4ac1-b69c-1235340b7001 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 074_5 </td>
   <td style="text-align:left;"> https://www.gbif.org/species/212 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 074_6 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:scientificNameID="8fa58e08-08de-4ac1-b69c-1235340b7001": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:scientificNameID is not EMPTY"],[dwc:scientificNameID="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:scientificNameID is EMPTY"]

## Teste 075: [`VALIDATION_SCIENTIFICNAMEID_COMPLETE`](https://github.com/tdwg/bdq/issues/212) 

**Nome do teste**: `VALIDATION_SCIENTIFICNAMEID_COMPLETE` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/212 

**ID oficial do teste**: `6eeac3ed-f691-457f-a42e-eaa9c8a71ce8` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `scientificNameID` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Does the value of dwc:scientificNameID contain a complete identifier?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:scientificNameID is EMPTY; COMPLIANT if (1) dwc:scientificNameID is a validly formed LSID, or (2) dwc:scientificNameID is a validly formed URN with at least NID and NSS present, or (3) dwc:scientificNameID is in the form scope:value, or (4) dwc:scientificNameID is a validly formed URI with host and path where path consists of more than just "/"; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _If any single bdq:sourceAuthority such as GBIF is used, a valid and complete dwc:scientificNameID based on an alternative source authority is unlikely to provide a valid match. A text or number string as a namespace indicator without a URI will be ambiguous. As an example, GBIF's backbone taxonomy dataset can be found at https://doi.org/10.15468/39omei. When referencing a GBIF taxon by GBIF's identifier for that taxon, use the the pseudo-namespace "gbif:" and the form "gbif:{integer}" as the value for dwc:scientificNameID.  Note that GBIF currently uses "TaxonID" for this entity._ 



<table>
<caption>Tabela 75: Termos testados e os resultados esperados para o teste VALIDATION_SCIENTIFICNAMEID_COMPLETE.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> scientificNameID </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 075_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:scientificNameID is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 075_2 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID does not contain a URI or a namespace indicator </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 075_3 </td>
   <td style="text-align:left;"> Wallabia bicolor </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID does not contain a URI </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 075_4 </td>
   <td style="text-align:left;"> urn:lsid:marinespecies.org:taxname:208134 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID contains a URI and a namespace indicator </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 075_5 </td>
   <td style="text-align:left;"> urn:lsid:zoobank.org:act:17ADF24F-027F-44F6-9543-D3D0260CE79E </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID contains a URI and a namespace indicator </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 075_6 </td>
   <td style="text-align:left;"> urn:lsid:ipni.org:names:68749-2 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID contains a URI and a namespace indicator </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 075_7 </td>
   <td style="text-align:left;"> Wallabia bicolor (Desmarest, 1804) </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID does not contain a URI </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 075_8 </td>
   <td style="text-align:left;"> wallaby </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID does not contain a URI </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 075_9 </td>
   <td style="text-align:left;"> Hakea decurrens ssp. physocarpa </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID does not contain a URI </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 075_10 </td>
   <td style="text-align:left;"> Geranium sp. Pale pink flowers (M.Gray 5847) Vic. Herbarium </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID does not contain a URI </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 075_11 </td>
   <td style="text-align:left;"> dwc:scientificName </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID does not contain a URI or a namespace indicator </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 075_12 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:scientificNameID does not contain a URI </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:scientificNameID="urn:lsid:zoobank.org:act:17ADF24F-027F-44F6-9543-D3D0260CE79E": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:scientificNameID contains a URI and a namespace indicator"],[dwc:scientificNameID="Hakea decurrens ssp. physocarpa": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:scientificNameID does not contain a URI"]

## Teste 076: [`VALIDATION_GENUS_FOUND`](https://github.com/tdwg/bdq/issues/122) 

**Nome do teste**: `VALIDATION_GENUS_FOUND` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/122 

**ID oficial do teste**: `f2ce7d55-5b1d-426a-b00e-6d4efe3058ec` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `genus` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Does the value of dwc:genus occur at the rank of Genus in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available;  INTERNAL_PREREQUISITES_NOT_MET if dwc:genus is EMPTY; COMPLIANT if the value of dwc:genus was found as a value at the rank of genus by the bdq:sourceAuthority; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "GBIF Backbone Taxonomy" {[https://doi.org/10.15468/39omei]} {API endpoint [https://api.gbif.org/v1/species?datasetKey=d7dddbf4-2cf0-4f39-9b2a-bb099caae36c&name=]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The purpose of this test is to check whether the value is a name that is a result of a nomenclatural act at this rank. This excludes unpublished names, misspellings and vernacular names. It is expected that the test will designate the source authority against which to check. The same test might return distinct results when using distinct source authorities._ 



<table>
<caption>Tabela 76: Termos testados e os resultados esperados para o teste VALIDATION_GENUS_FOUND.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> genus </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 076_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:genus is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 076_2 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:genus does not have an equivalent at the rank of Genus in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 076_3 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:genus does not have an equivalent at the rank of Genus in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 076_4 </td>
   <td style="text-align:left;"> Egernia </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:genus has an equivalent at the rank of Genus in the Parameterized Source Authority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 076_5 </td>
   <td style="text-align:left;"> Egernea </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:genus does not have an equivalent at the rank of Genus in the bdq:sourceAuthority. This may be fixed using fuzzy matching at the AMENDMENT stage </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 076_6 </td>
   <td style="text-align:left;"> Scincidae </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:genus does not have an equivalent at the rank of Genus in the bdq:sourceAuthority. Scincidae is an family not a genus </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 076_7 </td>
   <td style="text-align:left;"> Wallabia </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:genus has an equivalent at the rank of Genus in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 076_8 </td>
   <td style="text-align:left;"> skink </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:genus does not have an equivalent at the rank of Genus in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 076_9 </td>
   <td style="text-align:left;"> Lizard </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:genus does not have an equivalent at the rank of Genus in the Parameterized Source Authority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 076_10 </td>
   <td style="text-align:left;"> dwc:genus </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:genus not found in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 076_11 </td>
   <td style="text-align:left;"> AnyGenus </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> the bdq:sourceAuthority was not Available or was unreachable </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:genus="Egernia": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:genus has an equivalent at the rank of Genus in the Parameterized Source Authority"],[dwc:genus="Egernea": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:genus does not have an equivalent at the rank of Genus in the bdq:sourceAuthority. This may be fixed using fuzzy matching at the AMENDMENT stage"]

## Teste 077: [`VALIDATION_CLASSIFICATION_CONSISTENT`](https://github.com/tdwg/bdq/issues/123) 

**Nome do teste**: `VALIDATION_CLASSIFICATION_CONSISTENT` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/123 

**ID oficial do teste**: `2750c040-1d4a-4149-99fe-0512785f2d5f` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `kingdom, phylum, class, order, family, genus` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Is the combination of higher classification taxonomic terms consistent using bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if all of the fields dwc:kingdom dwc:phylum, dwc:class, dwc:order, dwc:superfamily, dwc:family, dwc:subfamily, dwc:tribe, dwc:subtribe, dwc:genus are EMPTY; COMPLIANT if the combination of values of higher classification taxonomic terms (dwc:kingdom, dwc:phylum, dwc:class, dwc:order, dwc:superfamily, dwc:family, dwc:subfamily, dwc:tribe, dwc:subtribe, dwc:genus) are consistent with the lowest ranking matched element in the bdq:sourceAuthority; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "GBIF Backbone Taxonomy" {[https://doi.org/10.15468/39omei]} {API endpoint [https://api.gbif.org/v1/species?datasetKey=d7dddbf4-2cf0-4f39-9b2a-bb099caae36c&name=]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _A fail condition may arise either from the taxon terms being internally inconsistent (not all of the information can be true at the same time), or from the vocabulary being incapable of resolving the combination of classification values. Additional tests could be devised against a taxonomic authority to report the distinct failure conditions. This test specifically does not consider the content of dwc:higherClassification._ 



<table>
<caption>Tabela 77: Termos testados e os resultados esperados para o teste VALIDATION_CLASSIFICATION_CONSISTENT.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> kingdom </th>
   <th style="text-align:left;"> phylum </th>
   <th style="text-align:left;"> class </th>
   <th style="text-align:left;"> order </th>
   <th style="text-align:left;"> family </th>
   <th style="text-align:left;"> genus </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 077_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> All input fields are EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_2 </td>
   <td style="text-align:left;"> Plantae </td>
   <td style="text-align:left;"> Magnoliophyta </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms can be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_3 </td>
   <td style="text-align:left;"> Plantae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Magnoliopsida </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms can be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_4 </td>
   <td style="text-align:left;"> Plantae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Myrtales </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms can be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_5 </td>
   <td style="text-align:left;"> Plantae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Myrtaceae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms can be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Magnoliophyta </td>
   <td style="text-align:left;"> Magnoliopsida </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms can be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_7 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Magnoliophyta </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Myrtales </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms can be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_8 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Magnoliophyta </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Myrtaceae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms can be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Magnoliopsida </td>
   <td style="text-align:left;"> Myrtales </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms can be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Magnoliopsida </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Myrtaceae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms can be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_11 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Myrtales </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Punica </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms can be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_12 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Chordata </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Rhopalocera </td>
   <td style="text-align:left;"> Muricidae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms cannot be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_13 </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Arthropoda </td>
   <td style="text-align:left;"> Insecta </td>
   <td style="text-align:left;"> Coleoptera </td>
   <td style="text-align:left;"> Curculionidae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms can be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_14 </td>
   <td style="text-align:left;"> Plantae </td>
   <td style="text-align:left;"> Arthropoda </td>
   <td style="text-align:left;"> Insecta </td>
   <td style="text-align:left;"> Coleoptera </td>
   <td style="text-align:left;"> Curculionidae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms cannot be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_15 </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Magnoliophyta </td>
   <td style="text-align:left;"> Insecta </td>
   <td style="text-align:left;"> Coleoptera </td>
   <td style="text-align:left;"> Curculionidae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms cannot be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_16 </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Arthropoda </td>
   <td style="text-align:left;"> Magnoliopsida </td>
   <td style="text-align:left;"> Coleoptera </td>
   <td style="text-align:left;"> Curculionidae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms cannot be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_17 </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Arthropoda </td>
   <td style="text-align:left;"> Insecta </td>
   <td style="text-align:left;"> Myrtales </td>
   <td style="text-align:left;"> Curculionidae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms cannot be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_18 </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Arthropoda </td>
   <td style="text-align:left;"> Insecta </td>
   <td style="text-align:left;"> Coleoptera </td>
   <td style="text-align:left;"> Myrtaceae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> The combination of values of higher classification taxonomic terms cannot be unambiguously resolved by the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 077_19 </td>
   <td style="text-align:left;"> Animalia </td>
   <td style="text-align:left;"> Arthropoda </td>
   <td style="text-align:left;"> Insecta </td>
   <td style="text-align:left;"> Coleoptera </td>
   <td style="text-align:left;"> Curculionidae </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> the bdq:sourceAuthority was unavailable or unreachable </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:kingdom="", dwc:phylum="", dwc:class="", dwc:order="Myrtales", dwc:family="Myrtaceae": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="The combination of values of higher classification taxonomic terms (dwc:kingdom, dwc:phylum, dwc:class, dwc:order, dwc:family) can be unambiguously resolved by the bdq:sourceAuthority"],[dwc:kingdom="", dwc:phylum="Chordata", dwc:class="", dwc:order="Rhopalocera", dwc:family="Muricidae": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="The combination of values of higher classification taxonomic terms (dwc:kingdom, dwc:phylum, dwc:class, dwc:order, dwc:family) cannot be unambiguously resolved by the bdq:sourceAuthority"]

## Teste 078: [`VALIDATION_DAY_INRANGE`](https://github.com/tdwg/bdq/issues/125) 

**Nome do teste**: `VALIDATION_DAY_INRANGE` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/125 

**ID oficial do teste**: `8d787cb5-73e2-4c39-9cd1-67c7361dc02e` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `year, month, day` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is the value of dwc:day interpretable as a valid integer between 1 and 28 inclusive or 29, 30 or 31 given the relative month and year?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if (1) dwc:day is EMPTY, or (2) dwc:day is not interpretable as an integer, or (3) dwc:day is interpretable as an integer between 29 and 31 inclusive and dwc:month is not interpretable as an integer between 1 and 12, or (4) dwc:month is interpretable as the integer 2 and dwc:day is interpretable as the integer 29 and dwc:year is not interpretable as a valid ISO 8601-1 year; COMPLIANT if (1) the value of dwc:day is interpretable as an integer between 1 and 28 inclusive, or (2) dwc:day is interpretable as an integer between 29 and 30 and dwc:month is interpretable as an integer in the set (4,6,9,11), or (3) dwc:day is interpretable as an integer between 29 and 31 and dwc:month is interpretable as an integer in the set (1,3,5,7,8,10,12), or (4) dwc:day is interpretable as the integer 29 and dwc:month is interpretable as the integer 2 and dwc:year is interpretable as is a valid leap year (evenly divisible by 400 or (evenly divisible by 4 but not evenly divisible by 100)); otherwise NOT_COMPLIANT._ 

**Código fonte de exemplo**: _[event_date_qc DwCEventDQ.validationDayInrange()](https://github.com/FilteredPush/event_date_qc/blob/ddbc25e6a12e4cb1c3898cebc36a4225d2945296/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L809)_ 

**Notas**: _This test must take into account the given month and year, if present, to account for leap years. This is part of a group of similar tests (VALIDATION_DAY_INRANGE (8d787cb5-73e2-4c39-9cd1-67c7361dc02e, #VALIDATION_STARTDAYOFYEAR_INRANGE (85803c7e-2a5a-42e1-b8d3-299a44cafc46), VALIDATION_ENDDAYOFYEAR_INRANGE9a39d88c-7eee-46df-b32a-c109f9f81fb8))._ 



<table>
<caption>Tabela 78: Termos testados e os resultados esperados para o teste VALIDATION_DAY_INRANGE.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> year </th>
   <th style="text-align:left;"> month </th>
   <th style="text-align:left;"> day </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 078_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:day is EMPTY or Missing </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_3 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 32 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is not in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:day is not interpretable as an integer </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_5 </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:day is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_6 </td>
   <td style="text-align:left;"> 1949-10-20 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:day is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_7 </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_8 </td>
   <td style="text-align:left;"> 1952 </td>
   <td style="text-align:left;"> 2 </td>
   <td style="text-align:left;"> 30 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is not in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_9 </td>
   <td style="text-align:left;"> 1952 </td>
   <td style="text-align:left;"> 2 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:day is ambiguous </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_10 </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;"> 9 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_11 </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;"> 9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:day is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_12 </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_13 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 10 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_14 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 10 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:day is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_15 </td>
   <td style="text-align:left;"> 1599 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:day is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_16 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 13 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:day is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_17 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 99 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is not in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_18 </td>
   <td style="text-align:left;"> 1952 </td>
   <td style="text-align:left;"> 2 </td>
   <td style="text-align:left;"> 29 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is in range. Leap year </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_19 </td>
   <td style="text-align:left;"> 2000 </td>
   <td style="text-align:left;"> 2 </td>
   <td style="text-align:left;"> 29 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is in range. Leap year </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_20 </td>
   <td style="text-align:left;"> 1900 </td>
   <td style="text-align:left;"> 2 </td>
   <td style="text-align:left;"> 29 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is not in range. Not a leap year </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 078_21 </td>
   <td style="text-align:left;"> 1948 </td>
   <td style="text-align:left;"> 9 </td>
   <td style="text-align:left;"> 16 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is in range </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:day="15", dwc:month="", dwc:year="": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:day is in range"],[dwc:day="30", dwc:month="2", dwc:year="1952": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:day is not in range"]

## Teste 079: [`VALIDATION_MONTH_STANDARD`](https://github.com/tdwg/bdq/issues/126) 

**Nome do teste**: `VALIDATION_MONTH_STANDARD` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/126 

**ID oficial do teste**: `01c6dafa-0886-4b7e-9881-2c3018c98bdc` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `month` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is the value of dwc:month interpretable as an integer between 1 and 12 inclusive?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:month is EMPTY; COMPLIANT if the value of dwc:month is interpretable as an integer between 1 and 12 inclusive; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _event_date_qc [DwCEventDQ.validationMonthStandard()](https://github.com/FilteredPush/event_date_qc/blob/v3.0.0/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L673) Unit test in [DwcEventDQTest]{https://github.com/FilteredPush/event_date_qc/blob/v3.0.0/src/test/java/org/filteredpush/qc/date/DwcEventDQTest.java#L242)_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 79: Termos testados e os resultados esperados para o teste VALIDATION_MONTH_STANDARD.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> month </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 079_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:month is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 079_2 </td>
   <td style="text-align:left;"> null </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:month is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 079_3 </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:month is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 079_4 </td>
   <td style="text-align:left;"> 10 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:month is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 079_5 </td>
   <td style="text-align:left;"> v </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:month is ambiguous as &quot;v&quot; or &quot;5&quot; </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 079_6 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:month is not in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 079_7 </td>
   <td style="text-align:left;"> 13 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:month is not in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 079_8 </td>
   <td style="text-align:left;"> 99 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:month is not in range </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:month="10": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:month is in range"],[dwc:month="v": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:month is ambiguous as "v" or "5""]

## Teste 080: [`AMENDMENT_DAY_STANDARDIZED`](https://github.com/tdwg/bdq/issues/127) 

**Nome do teste**: `AMENDMENT_DAY_STANDARDIZED` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/127 

**ID oficial do teste**: `b129fa4d-b25b-43f7-9645-5ed4d44b357b` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `day` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Propose amendment to the value of dwc:day as an integer between 1 and 31 inclusive._ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:day is EMPTY; AMENDED the value of dwc:day if the value was unambiguously interpreted as an integer between 1 and 31 inclusive; otherwise NOT_AMENDED_ 

**Código fonte de exemplo**: _A potential minimal implementation is at: https://github.com/FilteredPush/event_date_qc/blob/238f234a4947b3c2820fb2fe3987326f9ead5e54/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L1114 unit test at  https://github.com/FilteredPush/event_date_qc/blob/238f234a4947b3c2820fb2fe3987326f9ead5e54/src/test/java/org/filteredpush/qc/date/DwcEventDQTest.java#L824_ 

**Notas**: _If dwc:day contains text that may be interpreted as Roman numerals, the result will be NOT_AMENDED as this is not standard. Values such as "3rd" or "12th" can be interpreted as the integers "3" and "12".  Text such as "5th Friday" is ambiguous._ 



<table>
<caption>Tabela 80: Termos testados e os resultados esperados para o teste AMENDMENT_DAY_STANDARDIZED.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> day </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 080_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:day is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 080_2 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:day is not a valid interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 080_3 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:day is ambiguous, either a &quot;X&quot;, &quot;No data&quot; or &quot;10&quot; </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 080_4 </td>
   <td style="text-align:left;"> 23rd </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:day&quot;:&quot;23&quot;} </td>
   <td style="text-align:left;"> dwc:day is interpretable as &quot;23&quot; </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 080_5 </td>
   <td style="text-align:left;"> IV </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:day is ambiguous, either &quot;IV&quot; or &quot;4&quot; </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 080_6 </td>
   <td style="text-align:left;"> 5th </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:day&quot;:&quot;5&quot;} </td>
   <td style="text-align:left;"> dwc:day is interpretable as &quot;5&quot; </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:day="23rd": Response.status=AMENDED, Response.result=dwc:day="23", Response.comment="dwc:day is interpretable as "23""],[dwc:day="X": Response.status=NOT_AMENDED, Response.result="", Response.comment="dwc:day is ambiguous, either a "X", "No data" or "10""]

## Teste 081: [`AMENDMENT_MONTH_STANDARDIZED`](https://github.com/tdwg/bdq/issues/128) 

**Nome do teste**: `AMENDMENT_MONTH_STANDARDIZED` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/128 

**ID oficial do teste**: `2e371d57-1eb3-4fe3-8a61-dff43ced50cf` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `month` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Propose an amendment to the value of dwc:month as an integer between 1 and 12 inclusive._ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:month is EMPTY; AMENDED the value of dwc:month if it was able to be unambiguously interpreted as an integer between 1 and 12 inclusive; otherwise NOT_AMENDED_ 

**Código fonte de exemplo**: _https://github.com/FilteredPush/event_date_qc/blob/f224e5a1e6db81bc6ca725f520dd06a71fcfb54e/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L1055 with unit test at https://github.com/FilteredPush/event_date_qc/blob/f224e5a1e6db81bc6ca725f520dd06a71fcfb54e/src/test/java/org/filteredpush/qc/date/DwcEventDQTest.java#L671 Internals of recognized string values (roman numerals, month names and abbreviations in multiple languages) use a combination of event_date_qc's DateUtils.cleanMonth() (see https://github.com/FilteredPush/event_date_qc/blob/23e4139d7f0ef71736f7fc7e984cfd2d0bfea093/src/main/java/org/filteredpush/qc/date/DateUtils.java#L2111  and Joda time's month recognition)_ 

**Notas**: _Implementations should translate interpretable Roman numerals in the range I-XII in dwc:month as integer month values 1-12, as some natural science domains use roman numeral months to avoid language and day/month vs moth/day order. In these cases, the result will be AMENDED numeric equivalents._ 



<table>
<caption>Tabela 81: Termos testados e os resultados esperados para o teste AMENDMENT_MONTH_STANDARDIZED.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> month </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 081_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:month is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 081_2 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:month contains an uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 081_3 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:month&quot;:&quot;10&quot;} </td>
   <td style="text-align:left;"> dwc:month interpreted as roman numerals </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 081_4 </td>
   <td style="text-align:left;"> IV </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:month&quot;:&quot;4&quot;} </td>
   <td style="text-align:left;"> dwc:month interpreted as roman numerals </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 081_5 </td>
   <td style="text-align:left;"> October </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:month contains an uninterpretable value </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:month="IV": Response.status=AMENDED, Response.result=dwc:month="4", Response.comment="dwc:month interpreted as roman numerals "],[dwc:month="October": Response.status=NOT_AMENDED, Response.result=, Response.comment="dwc:month contains an uninterpretable value"]

## Teste 082: [`VALIDATION_STARTDAYOFYEAR_INRANGE`](https://github.com/tdwg/bdq/issues/130) 

**Nome do teste**: `VALIDATION_STARTDAYOFYEAR_INRANGE` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/130 

**ID oficial do teste**: `85803c7e-2a5a-42e1-b8d3-299a44cafc46` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `eventDate, startDayOfYear` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is the value of dwc:startDayOfYear an integer between 1 and 365 inclusive, or 366 if a leap year?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:startDayOfYear is EMPTY or if the value of dwc:startDayOfYear is equal to 366 and (dwc:eventDate is EMPTY or the value of dwc:eventDate cannot be interpreted to find single year or a start year in a range); COMPLIANT if the value of dwc:startDayOfYear is an integer between 1 and 365, inclusive, or if the value of dwc:startDayOfYear is 366 and the start year interpreted from dwc:eventDate is a leap year; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _https://github.com/FilteredPush/event_date_qc/blob/23e4139d7f0ef71736f7fc7e984cfd2d0bfea093/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L832 Unit test at https://github.com/FilteredPush/event_date_qc/blob/5f2e7b30f8a8076977b2a609e0318068db80599a/src/test/java/org/filteredpush/qc/date/DwcEventDQTest.java#L609_ 

**Notas**: _See test VALIDATION_DAY_INRANGE (8d787cb5-73e2-4c39-9cd1-67c7361dc02e).  This test only asks if dwc:startDayOfYear is a valid value for the relevant year, not if it is consistent with the start day of the range specified in dwc:eventDate. In a non-leap year, the valid range is 1-365 inclusive, in a leap year 366 is also valid. This test should be run after the series of tests that assure that dwc:eventDate is populated, if possible (i.e., AMENDMENT_EVENTDATE_FROM_VERBATIM (6d0a0c10-5e4a-4759-b448-88932f399812), AMENDMENT_EVENTDATE_STANDARDIZED (718dfc3c-cb52-4fca-b8e2-0e722f375da7), and AMENDMENT_EVENT_DATE_FROM_YEARMONTHDAY (3892f432-ddd0-4a0a-b713-f2e2ecbd879d))._ 



<table>
<caption>Tabela 82: Termos testados e os resultados esperados para o teste VALIDATION_STARTDAYOFYEAR_INRANGE.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> eventDate </th>
   <th style="text-align:left;"> startDayOfYear </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 082_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:startDayOfYear is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 082_2 </td>
   <td style="text-align:left;"> 1964-11-01T10:00-0600 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:startDayOfYear is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 082_3 </td>
   <td style="text-align:left;"> 1949-09-15T12:34 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:startDayOfYear is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 082_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:startDayOfYear is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 082_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:startDayOfYear is ambiguous, either &quot;No data&quot; or &quot;10&quot; </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 082_6 </td>
   <td style="text-align:left;"> 1949-01-15T12:34/1949-01-20T17:00 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:startDayOfYear is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 082_7 </td>
   <td style="text-align:left;"> 1963-03-08T14:07-0600 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:startDayOfYear is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 082_8 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:startDayOfYear is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 082_9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 366 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:startDayOfYear is 366 and dwc:year is EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:eventDate="", dwc:startDayOfYear="15": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:startDayOfYear is in range"],[dwc:eventDate="", dwc:startDayOfYear="0": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:startDayOfYear is not in range"]

## Teste 083: [`VALIDATION_ENDDAYOFYEAR_INRANGE`](https://github.com/tdwg/bdq/issues/131) 

**Nome do teste**: `VALIDATION_ENDDAYOFYEAR_INRANGE` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/131 

**ID oficial do teste**: `9a39d88c-7eee-46df-b32a-c109f9f81fb8` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `eventDate, endDayOfYear` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is the value of dwc:endDayOfYear an integer between 1 and 365 inclusive, or 366 if a leap year?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:endDayOfYear is EMPTY or if the value of dwc:endDayOfYear is equal to 366 and (dwc:eventDate is EMPTY or the value of dwc:eventDate cannot be interpreted to find a single year or an end year in a range); COMPLIANT if the value of dwc:endDayOfYear is an integer between 1 and 365 inclusive, or if the value of dwc:endDayOfYear is 366 and the end year interpreted from dwc:eventDate is a leap year; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _https://github.com/FilteredPush/event_date_qc/blob/23e4139d7f0ef71736f7fc7e984cfd2d0bfea093/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L888  Unit test at https://github.com/FilteredPush/event_date_qc/blob/5f2e7b30f8a8076977b2a609e0318068db80599a/src/test/java/org/filteredpush/qc/date/DwcEventDQTest.java#L609_ 

**Notas**: _See test VALIDATION_DAY_INRANGE (8d787cb5-73e2-4c39-9cd1-67c7361dc02e). This test only asks if dwc:endDayOfYear is a valid value for the relevant year, not if it is consistent with the end day of the range specified in dwc:eventDate. In a non-leap year, the valid range is 1-365 inclusive, in a leap year 366 is also valid. This test should be run after the series of tests that assure that dwc:eventDate is populated, if possible (i.e., AMENDMENT_EVENTDATE_FROM_VERBATIM (6d0a0c10-5e4a-4759-b448-88932f399812), AMENDMENT_EVENTDATE_STANDARDIZED (718dfc3c-cb52-4fca-b8e2-0e722f375da7), and AMENDMENT_EVENT_DATE_FROM_YEARMONTHDAY (3892f432-ddd0-4a0a-b713-f2e2ecbd879d))._ 



<table>
<caption>Tabela 83: Termos testados e os resultados esperados para o teste VALIDATION_ENDDAYOFYEAR_INRANGE.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> eventDate </th>
   <th style="text-align:left;"> endDayOfYear </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 083_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> All input fields EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 083_2 </td>
   <td style="text-align:left;"> 1962-11-01T10:00-0600 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:endDayOfYear is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 083_3 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 20 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:endDayOfYear is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 083_4 </td>
   <td style="text-align:left;"> 1949-01-15T12:34/1949-01-20T17:00 </td>
   <td style="text-align:left;"> 20 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:endDayOfYear is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 083_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:endDayOfYear is ambiguous, either &quot;X&quot; or &quot;No data&quot; or &quot;10&quot; </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 083_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 367 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:endDayOfYear is not in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 083_7 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:endDayOfYear is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 083_8 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 366 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:endDayOfYear is 366 and dwc:eventDate is EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:eventDate="1949-01-15T12:34/1949-01-20T17:00", dwc:endDayOfYear="20": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:endDayOfYear is in range"],[dwc:eventDate="", dwc:endDayOfYear="x": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:endDayOfYear is ambiguous, either "X" or "No data" or "10"]

## Teste 084: [`AMENDMENT_EVENTDATE_FROM_YEARSTARTDAYOFYEARENDDAYOFYEAR`](https://github.com/tdwg/bdq/issues/132) 

**Nome do teste**: `AMENDMENT_EVENTDATE_FROM_YEARSTARTDAYOFYEARENDDAYOFYEAR` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/132 

**ID oficial do teste**: `eb0a44fa-241c-4d64-98df-ad4aa837307b` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `eventDate, startDayOfYear, endDayOfYear, year` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Propose amendment to the value of dwc:eventDate from values in dwc:year, dwc:startDayOfYear and dwc:endDayOfYear._ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:eventDate was not EMPTY or any of dwc:year, dwc:startDayOfYear, or dwc:endDayOfYear were EMPTY or any of the values in dwc:year, dwc:startDayOfYear, or dwc:endDayOfYear were not independently interpretable; FILLED_IN the value of dwc:eventDate from values in dwc:year, dwc:startDayOfYear and dwc:endDayOfYear if the value of dwc:startDayOfYear is less than the value of dwc:endDayOfYear; otherwise NOT_AMENDED_ 

**Código fonte de exemplo**: _https://github.com/FilteredPush/event_date_qc/blob/4665e4d3b43ce7ddf319b3d7a5d3dbfee1411250/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L828   Unit Test at:  https://github.com/FilteredPush/event_date_qc/blob/96a8981d997cceb2f39ba47d63f0b98c1b56680c/src/test/java/org/filteredpush/qc/date/DwcEventDQTest.java#L402_ 

**Notas**: _An attempt to populate dwc:eventDate from dwc:verbatimEventDate should be made before this test is run.   While year=1999, startDayOfYear=123  could be validly represented as an ISO date as either 1999-123 or 1999-05-03, the latter of these two forms SHOULD be used, thus, do not simply concatenate dwc:year and dwc:startDayOfYear. This test is only for cases that fall within the one year (as given in dwc:year) and hence "dwc:startDayOfYear will always be less than dwc:endDayOfYear". [or do we just leave this as being obvious from the Expected Response._ 



<table>
<caption>Tabela 84: Termos testados e os resultados esperados para o teste AMENDMENT_EVENTDATE_FROM_YEARSTARTDAYOFYEARENDDAYOFYEAR.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> eventDate </th>
   <th style="text-align:left;"> startDayOfYear </th>
   <th style="text-align:left;"> endDayOfYear </th>
   <th style="text-align:left;"> year </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 084_1 </td>
   <td style="text-align:left;"> 2021-10-29 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:eventDate is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 084_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> all inpuit fields are EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 084_3 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:year is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 084_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:year is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 084_5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 5 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:year is not interpretable as a valid year </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 084_6 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 5 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 1949 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:endDayOfYear is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 084_7 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 5 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> 2021 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;2021-01-05/2021-01-15&quot;} </td>
   <td style="text-align:left;"> dwc:eventDate was interpreted from dwc:year, dwc:startDayOfYear and dwc:endDayOfYear </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 084_8 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> 25 </td>
   <td style="text-align:left;"> 1901 </td>
   <td style="text-align:left;"> FILLED_IN </td>
   <td style="text-align:left;"> {&quot;dwc:eventDate&quot;:&quot;1901-01-15/1901-01-25&quot;} </td>
   <td style="text-align:left;"> dwc:eventDate was interpreted from dwc:year, dwc:startDayOfYear and dwc:endDayOfYear </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 084_9 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 25 </td>
   <td style="text-align:left;"> 15 </td>
   <td style="text-align:left;"> 1901 </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:startDayOfYear &gt; dwc:endDayOfyear </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:year="1901", dwc:startDayOfYear="15", dwc:endDayOfYear="25", dwc:eventDate="": Response.status=FILLED_IN, Response.result=dwc:eventDate="1901-01-15/1901-01-25", Response.comment="dwc:eventDate was interpreted from dwc:year, dwc:startDayOfYear and dwc:endDayOfYear"],[dwc:year="1901", dwc:startDayOfYear="25", dwc:endDayOfYear="15", dwc:eventDate="": Response.status=NOT_AMENDED, Response.result="", Response.comment="dwc:startDayOfYear > dwc:endDayOfyear"]

## Teste 085: [`AMENDMENT_LICENSE_STANDARDIZED`](https://github.com/tdwg/bdq/issues/133) 

**Nome do teste**: `AMENDMENT_LICENSE_STANDARDIZED` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/133 

**ID oficial do teste**: `dcbe5bd2-42a0-4aab-bb4d-8f148c6490f8` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Record-level` 

**Termos (colunas) testados**: `license` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Propose amendment to the value of dwc:license using bdq:sourceAuthority._ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; AMENDED value of dcterms:license if it could be unambiguously interpreted as a value in bdq:sourceAuthority; otherwise NOT_AMENDED. bdq:sourceAuthority default = "Creative Commons" {[https://creativecommons.org/]} {Creative Commons licenses [https://creativecommons.org/about/cclicenses/]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The license at the record level might be derived from the license of the data set from which the record is retrieved._ 



<table>
<caption>Tabela 85: Termos testados e os resultados esperados para o teste AMENDMENT_LICENSE_STANDARDIZED.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> license </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 085_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dcterms:license EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 085_2 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dcterms:license contains uninterpretable value &quot;x&quot; </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 085_3 </td>
   <td style="text-align:left;"> no license </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dcterms:license contains uninterpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 085_4 </td>
   <td style="text-align:left;"> CC0 </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dcterms:license&quot;:&quot;http://creativecommons.org/publicdomain/zero/1.0/legalcode&quot;} </td>
   <td style="text-align:left;"> Input field contains interpretable value </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 085_5 </td>
   <td style="text-align:left;"> AnyLicense </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> the bdq:sourceAuthority was unavailable or unreachable </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dcterms:license="CC0": Response.status=AMENDED, Response.result=dcterms:license="http://creativecommons.org/publicdomain/zero/1.0/legalcode", Response.comment="Input field contains interpretable value"],[dcterms:license="X": Response.status=NOT_AMENDED, Response.result="", Response.comment="dcterms:license contains uninterpretable value "X""]

## Teste 086: [`MEASURE_EVENTDATE_PRECISIONINSECONDS`](https://github.com/tdwg/bdq/issues/140) 

**Nome do teste**: `MEASURE_EVENTDATE_PRECISIONINSECONDS` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/140 

**ID oficial do teste**: `56b6c695-adf1-418e-95d2-da04cad7be53` 

**Tipo de teste**: `Measure` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `eventDate` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _What is the duration of dwc:eventDate in seconds?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:eventDate is EMPTY or if the value of dwc:eventDate is not a valid ISO 8601-1 date; otherwise RUN_HAS_RESULT with the result being the duration (sensu ISO 8601-1) expressed in the dwc:eventDate, in seconds._ 

**Código fonte de exemplo**: _event_date_qc v3.0.0 [DwCEventDQ.measureEventdateDurationinseconds()](https://github.com/FilteredPush/event_date_qc/blob/v3.0.0/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L109)_ 

**Notas**: _The duration of a day is 86400 seconds. Implementations should treat all days as 86400 seconds, but should include leap days (but not leap seconds) in durations that encompass them.  Consumers should treat assertions about event date duration as approximations, see: https://xkcd.com/2867/_ 



<table>
<caption>Tabela 86: Termos testados e os resultados esperados para o teste MEASURE_EVENTDATE_PRECISIONINSECONDS.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> eventDate </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 086_1 </td>
   <td style="text-align:left;"> 1880-05-08 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> 86400 </td>
   <td style="text-align:left;"> dwc:eventDate duration is the number of seconds in a day </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 086_2 </td>
   <td style="text-align:left;"> 1880-05-08/10 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> 259200 </td>
   <td style="text-align:left;"> dwc:eventDate duration is 3 days = 259,200 seconds&quot; </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 086_3 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;"> NOT_REPORTED </td>
   <td style="text-align:left;"> dwc:eventDate is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 086_4 </td>
   <td style="text-align:left;"> 95 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;"> NOT_REPORTED </td>
   <td style="text-align:left;"> dwc:eventDate does not contain a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 086_5 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;"> NOT_REPORTED </td>
   <td style="text-align:left;"> dwc:eventDate does not contain a valid ISO 8601-1:2019 date </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 086_6 </td>
   <td style="text-align:left;"> 2007-03-01T13:00:00Z/2008-05-11T15:30:00Z </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> 37765800 </td>
   <td style="text-align:left;"> dwc:eventDate precision is 37765800 seconds </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 086_7 </td>
   <td style="text-align:left;"> 2007 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> 31536000 </td>
   <td style="text-align:left;"> dwc:eventDate represents an interval of 365 days (365 days * 86400 seconds per day = 31536000  seconds). </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 086_8 </td>
   <td style="text-align:left;"> 1980 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> 31622400 </td>
   <td style="text-align:left;"> 1980 is a leap year.  dwc:eventDate represents an interval of 366 days (366 days * 86400 seconds per day = 31622400 seconds). </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:eventDate="1880-05-08/10": Response.status=RUN_HAS_RESULT, Response.result="259200", Response.comment="dwc:eventDate duration is 3 days = 259,200 seconds"],[dwc:eventDate="95": Response.status=INTERNAL_PREREQUISITES_NOT_MET, Response.result=NOT_REPORTED, Response.comment="dwc:eventDate does not contain a valid ISO 8601-1:2019 date"]

## Teste 087: [`VALIDATION_DAY_STANDARD`](https://github.com/tdwg/bdq/issues/147) 

**Nome do teste**: `VALIDATION_DAY_STANDARD` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/147 

**ID oficial do teste**: `47ff73ba-0028-4f79-9ce1-ee7008d66498` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Event` 

**Termos (colunas) testados**: `day` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is the value of dwc:day an integer between 1 and 31 inclusive?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:day is EMPTY; COMPLIANT if the value of the field dwc:day is an integer between 1 and 31 inclusive; otherwise NOT_COMPLIANT._ 

**Código fonte de exemplo**: _event_date_qc [DwCEventDQ.validationDayStandard()](https://github.com/FilteredPush/event_date_qc/blob/v3.0.0/src/main/java/org/filteredpush/qc/date/DwCEventDQ.java#L622)_ 

**Notas**: _This is part of a group of similar tests (VALIDATION_DAY_INRANGE (8d787cb5-73e2-4c39-9cd1-67c7361dc02e), VALIDATION_STARTDAYOFYEAR_INRANGE (85803c7e-2a5a-42e1-b8d3-299a44cafc46), VALIDATION_ENDDAYOFYEAR_INRANGE (9a39d88c-7eee-46df-b32a-c109f9f81fb8))._ 



<table>
<caption>Tabela 87: Termos testados e os resultados esperados para o teste VALIDATION_DAY_STANDARD.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> day </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 087_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:day is EMPTY or Missing </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 087_2 </td>
   <td style="text-align:left;"> 5 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 087_3 </td>
   <td style="text-align:left;"> 32 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is not in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 087_4 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is ambiguous, either &quot;No&quot; or &quot;10&quot; </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 087_5 </td>
   <td style="text-align:left;"> 30 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 087_6 </td>
   <td style="text-align:left;"> 99 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is not in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 087_7 </td>
   <td style="text-align:left;"> 29 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 087_8 </td>
   <td style="text-align:left;"> 2 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 087_9 </td>
   <td style="text-align:left;"> -1 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:day is not in range </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:day="15": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:day is in range"],[dwc:day="32": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:day is not in range"]

## Teste 088: [`VALIDATION_TAXONRANK_NOTEMPTY`](https://github.com/tdwg/bdq/issues/161) 

**Nome do teste**: `VALIDATION_TAXONRANK_NOTEMPTY` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/161 

**ID oficial do teste**: `14da5b87-8304-4b2b-911d-117e3c29e890` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `taxonRank` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:taxonRank?_ 

**Especificação**: 
> _COMPLIANT if dwc:taxonRank is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 88: Termos testados e os resultados esperados para o teste VALIDATION_TAXONRANK_NOTEMPTY.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> taxonRank </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 088_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank is EMPTY or missing </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 088_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 088_3 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 088_4 </td>
   <td style="text-align:left;"> ssp. </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 088_5 </td>
   <td style="text-align:left;"> genus </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 088_6 </td>
   <td style="text-align:left;"> cultivar </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 088_7 </td>
   <td style="text-align:left;"> anyOldTerm </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank is not EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 088_8 </td>
   <td style="text-align:left;"> 12345 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank is not EMPTY </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:taxonRank="genus": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:taxonRank is not EMPTY"],[dwc:taxonRank="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:taxonRank is EMPTY"]

## Teste 089: [`VALIDATION_TAXONRANK_STANDARD`](https://github.com/tdwg/bdq/issues/162) 

**Nome do teste**: `VALIDATION_TAXONRANK_STANDARD` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/162 

**ID oficial do teste**: `7bdb13a4-8a51-4ee5-be7f-20693fdb183e` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `taxonRank` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Does the value of dwc:taxonRank occur in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:taxonRank is EMPTY; COMPLIANT if the value of dwc:taxonRank is in the bdq:sourceAuthority; otherwise NOT_COMPLIANT. bdq:sourceAuthority default = "GBIF Vocabulary: Taxonomic Rank" {[https://api.gbif.org/v1/vocabularies/TaxonRank/concepts]} {dwc:taxonRank [https://dwc.tdwg.org/list/#dwc_taxonRank]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _This test must return NOT_COMPLIANT if there is leading or trailing whitespace or there are leading or trailing non-printing characters._ 



<table>
<caption>Tabela 89: Termos testados e os resultados esperados para o teste VALIDATION_TAXONRANK_STANDARD.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> taxonRank </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 089_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:taxonRank is EMPTY or missing </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 089_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:taxonRank is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 089_3 </td>
   <td style="text-align:left;"> kingdom </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank has an equivalent in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 089_4 </td>
   <td style="text-align:left;"> subkingdom </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank has an equivalent in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 089_5 </td>
   <td style="text-align:left;"> superfamily </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank has an equivalent in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 089_6 </td>
   <td style="text-align:left;"> species </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank has an equivalent in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 089_7 </td>
   <td style="text-align:left;"> especie </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank does not have an equivalent in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 089_8 </td>
   <td style="text-align:left;"> sp. </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank does not have an equivalent in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 089_9 </td>
   <td style="text-align:left;"> subspecies </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank has an equivalent in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 089_10 </td>
   <td style="text-align:left;"> ssp. </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank does not have an equivalent  in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 089_11 </td>
   <td style="text-align:left;"> subsp. </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank does not have an equivalent in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 089_12 </td>
   <td style="text-align:left;"> cultivar </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank has an equivalent in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 089_13 </td>
   <td style="text-align:left;"> ? </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:taxonRank does not have an equivalent  in the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 089_14 </td>
   <td style="text-align:left;"> AnyRank </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> the bdq:sourceAuthority was unavailable or unreachable </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:taxonRank="kingdom": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:taxonRank has an equivalent in the bdq:sourceAuthority"],[dwc:taxonRank="sp.": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:taxonRank does not have an equivalent in the bdq:sourceAuthority"]

## Teste 090: [`AMENDMENT_TAXONRANK_STANDARDIZED`](https://github.com/tdwg/bdq/issues/163) 

**Nome do teste**: `AMENDMENT_TAXONRANK_STANDARDIZED` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/163 

**ID oficial do teste**: `e39098df-ef46-464c-9aef-bcdeee2a88cb` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `taxonRank` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Propose amendment to the value of dwc:taxonRank using bdq:sourceAuthority._ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL PREREQUISITES_NOT_MET if dwc:taxonRank is EMPTY; AMENDED the value of dwc:taxonRank if it can be unambiguously matched to a term in bdq:sourceAuthority; otherwise NOT_AMENDED bdq:sourceAuthority default = "GBIF Vocabulary: Taxonomic Rank" {[https://api.gbif.org/v1/vocabularies/TaxonRank/concepts]} {dwc:taxonRank [https://dwc.tdwg.org/list/#dwc_taxonRank]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 



<table>
<caption>Tabela 90: Termos testados e os resultados esperados para o teste AMENDMENT_TAXONRANK_STANDARDIZED.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> taxonRank </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 090_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:taxonRank is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 090_2 </td>
   <td style="text-align:left;"> sp. </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:taxonRank&quot;:&quot;species&quot;} </td>
   <td style="text-align:left;"> dwc:taxonRank contains an interpretable value according to the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 090_3 </td>
   <td style="text-align:left;"> sic. </td>
   <td style="text-align:left;"> NOT_AMENDED </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:taxonRank does not contain an interpretable value according to the bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 090_4 </td>
   <td style="text-align:left;"> AnyRank </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> the bdq:sourceAuthority was unavailable or unreachable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 090_5 </td>
   <td style="text-align:left;"> especie </td>
   <td style="text-align:left;"> AMENDED </td>
   <td style="text-align:left;"> {&quot;dwc:taxonRank&quot;:&quot;species&quot;} </td>
   <td style="text-align:left;"> dwc:taxonRank does have an equivalent in the bdq:sourceAuthority as GBIF does currently have 4 language support </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:taxonRank="sp.": Response.status=AMENDED, Response.result=dwc:taxonRank="species", Response.comment="dwc:taxonRank contains an interpretable value according to the bdq:sourceAuthority"],[dwc:taxonRank="sic.": Response.status=NOT_AMENDED, Response.result="", Response.comment="dwc:taxonRank does not contain an interpretable value according to the bdq:sourceAuthority"]

## Teste 091: [`VALIDATION_MAXDEPTH_INRANGE`](https://github.com/tdwg/bdq/issues/187) 

**Nome do teste**: `VALIDATION_MAXDEPTH_INRANGE` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/187 

**ID oficial do teste**: `3f1db29a-bfa5-40db-9fd1-fde020d81939` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `maximumDepthInMeters` 

**Pré-requisitos externos (parâmetros)**: `bdq:minimumValidDepthInMeters,bdq:maximumValidDepthInMeters` 

**Descrição**: 
> _Is the value of dwc:maximumDepthInMeters within the Parameter range?_ 

**Especificação**: 
> _INTERNAL_PREREQUISITES_NOT_MET if dwc:maximumDepthInMeters is EMPTY or is not interpretable as a number greater than or equal to zero; COMPLIANT if the value of dwc:maximumDepthInMeters is within the range of bdq:minimumValidDepthInMeters to bdq:maximumValidDepthInMeters inclusive; otherwise NOT_COMPLIANT bdq:minimumValidDepthInMeters default="0",bdq:maximumValidDepthInMeters default="11000"_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _The Challenger Deep in the Mariana Trench is the deepest known point in Earth's oceans at 10,994 meters.  We have rounded up bdq:maximumValidDepthInMeters._ 



<table>
<caption>Tabela 91: Termos testados e os resultados esperados para o teste VALIDATION_MAXDEPTH_INRANGE.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> maximumDepthInMeters </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 091_1 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:maximumDepthInMeters is EMPTY. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 091_2 </td>
   <td style="text-align:left;"> 0 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:maximumDepthInMeters is in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 091_3 </td>
   <td style="text-align:left;"> -1 </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:maximumDepthInMeters is not in range </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 091_4 </td>
   <td style="text-align:left;"> 1200 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:maximumDepthInMeters is in range (&lt;11,000) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 091_5 </td>
   <td style="text-align:left;"> 99999 </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:maximumDepthInMeters is not in range (&gt;11,000) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 091_6 </td>
   <td style="text-align:left;"> x </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:maximumDepthInMeters is not interpretable as a number </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:maximumDepthInMeters="1200": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:maximumDepthInMeters is in range (<11,000)"],[dwc:maximumDepthInMeters="99999": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:maximumDepthInMeters is not in range (>11,000)"]

## Teste 092: [`VALIDATION_STATEPROVINCE_FOUND`](https://github.com/tdwg/bdq/issues/199) 

**Nome do teste**: `VALIDATION_STATEPROVINCE_FOUND` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/199 

**ID oficial do teste**: `4daa7986-d9b0-4dd5-ad17-2d7a771ea71a` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `stateProvince` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Does the value of dwc:stateProvince occur in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:stateProvince is EMPTY; COMPLIANT if the value of dwc:stateProvince occurs as an administrative entity that is a child to at least one entity representing an ISO country-like entity in the bdq:sourceAuthority; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "The Getty Thesaurus of Geographic Names (TGN)" {[https://www.getty.edu/research/tools/vocabularies/tgn/index.html]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Multiple values in the dwc:stateProvince field (whether to signify on a border or in a list of possibilities) will fail this test. This test must return NOT_COMPLIANT if there is leading or trailing whitespace or there are leading or trailing non-printing characters._ 



<table>
<caption>Tabela 92: Termos testados e os resultados esperados para o teste VALIDATION_STATEPROVINCE_FOUND.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> stateProvince </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 092_1 </td>
   <td style="text-align:left;"> AnyState </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority is unavailable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 092_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:stateProvince is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 092_3 </td>
   <td style="text-align:left;"> Moscow Oblast </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:stateProvince found in bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 092_4 </td>
   <td style="text-align:left;"> WA </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:stateProvince found in bdq:sourceAuthority. Matches Western Australia, Washington State (US) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 092_5 </td>
   <td style="text-align:left;"> Florida </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:stateProvince found in bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 092_6 </td>
   <td style="text-align:left;"> Tasmanian </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:stateProvince not found in bdq:sourceAuthority </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 092_7 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:stateProvince not found in bdq:sourceAuthority </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:stateProvince="Florida": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:stateProvince found in bdq:sourceAuthority"],[dwc:stateProvince="Tasmanian": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:stateProvince not found in bdq:sourceAuthority"]

## Teste 093: [`VALIDATION_COUNTRYSTATEPROVINCE_CONSISTENT`](https://github.com/tdwg/bdq/issues/200) 

**Nome do teste**: `VALIDATION_COUNTRYSTATEPROVINCE_CONSISTENT` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/200 

**ID oficial do teste**: `e654f562-44f8-43fd-983b-2aaba4c6dda9` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `country, stateProvince` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Are the combination of the values of dwc:country, dwc:stateProvince consistent with the values in the bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if the terms dwc:country or dwc:stateProvince are EMPTY; COMPLIANT if the value of dwc:stateProvince occurs as an administrative entity that is a child to the entity matching the value of dwc:country in the bdq:sourceAuthority, and the match to dwc:country is an ISO country-like entity in the bdq:sourceAuthority; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "The Getty Thesaurus of Geographic Names (TGN)" {[https://www.getty.edu/research/tools/vocabularies/tgn/index.html]}_ 

**Código fonte de exemplo**: _https://github.com/kurator-org/kurator-validation/blob/master/packages/kurator_dwca/workflows/dwca_geography_assessor.yaml_ 

**Notas**: _See table https://github.com/tdwg/bdq/issues/95#issuecomment-1226450014. A fail condition may arise from the content being internally inconsistent (not all of the information can be true at the same time), or from the vocabulary being incapable of resolving the combination of term values.  This test should match despite leading or trailing whitespace or there are leading or trailing non-printing characters._ 



<table>
<caption>Tabela 93: Termos testados e os resultados esperados para o teste VALIDATION_COUNTRYSTATEPROVINCE_CONSISTENT.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> country </th>
   <th style="text-align:left;"> stateProvince </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 093_1 </td>
   <td style="text-align:left;"> AnyCountry </td>
   <td style="text-align:left;"> AnyState </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority was not available or was unreachable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 093_2 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Tasmania </td>
   <td style="text-align:left;"> INTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> dwc:country is EMPTY </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 093_3 </td>
   <td style="text-align:left;"> Argentina </td>
   <td style="text-align:left;"> Rio Negro </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country is consistent with dwc:stateProvince </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 093_4 </td>
   <td style="text-align:left;"> USA </td>
   <td style="text-align:left;"> Maine </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country is consistent with dwc:stateProvince </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 093_5 </td>
   <td style="text-align:left;"> Australia </td>
   <td style="text-align:left;"> Florida </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:country is not consistent with dwc:stateProvince </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 093_6 </td>
   <td style="text-align:left;"> Australia </td>
   <td style="text-align:left;"> WA </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country is consistent with dwc:stateProvince </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 093_7 </td>
   <td style="text-align:left;"> Argentina </td>
   <td style="text-align:left;"> Rio </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:stateProvince is not consistent with dwc:country </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:country="Australia", dwc:stateProvince="WA": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:country is consistent with dwc:stateProvince. dwc:stateProvince matches Western Australia in dwc:country Australia"],[dwc:country="Australia", dwc:stateProvince="Florida": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:country is not consistent with dwc:stateProvince"]

## Teste 094: [`VALIDATION_COUNTRYSTATEPROVINCE_UNAMBIGUOUS`](https://github.com/tdwg/bdq/issues/201) 

**Nome do teste**: `VALIDATION_COUNTRYSTATEPROVINCE_UNAMBIGUOUS` 

**Última atualização**: `2023-09-18` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/201 

**ID oficial do teste**: `d257eb98-27cb-48e5-8d3c-ab9fca4edd11` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Location` 

**Termos (colunas) testados**: `country, stateProvince` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Is the combination of the values of the terms dwc:country, dwc:stateProvince unique in the bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if the terms dwc:country and dwc:stateProvince are EMPTY; COMPLIANT if the combination of values of dwc:country and dwc:stateProvince are unambiguously resolved to a single result with a child-parent relationship in the bdq:sourceAuthority and the entity matching the value of dwc:country in the bdq:sourceAuthority is an ISO country-like entity in the bdq:sourceAuthority; otherwise NOT_COMPLIANT bdq:sourceAuthority default = "The Getty Thesaurus of Geographic Names (TGN)" {[https://www.getty.edu/research/tools/vocabularies/tgn/index.html]}_ 

**Código fonte de exemplo**: _https://github.com/kurator-org/kurator-validation/blob/master/packages/kurator_dwca/workflows/dwca_geography_assessor.yaml_ 

**Notas**: _See table https://github.com/tdwg/bdq/issues/95#issuecomment-1226450014. A fail condition may arise from the content being internally inconsistent (not all of the information can be true at the same time), or from the vocabulary being incapable of uniquely resolving the combination of term values.  This test specifically does not consider the content of dwc:higherGeography._ 



<table>
<caption>Tabela 94: Termos testados e os resultados esperados para o teste VALIDATION_COUNTRYSTATEPROVINCE_UNAMBIGUOUS.</caption>
 <thead>
  <tr>
   <th style="text-align:left;"> testID </th>
   <th style="text-align:left;"> country </th>
   <th style="text-align:left;"> stateProvince </th>
   <th style="text-align:left;"> Response.status </th>
   <th style="text-align:left;"> Response.result </th>
   <th style="text-align:left;"> Response.comment </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 094_1 </td>
   <td style="text-align:left;"> AnyCountry </td>
   <td style="text-align:left;"> AnyState </td>
   <td style="text-align:left;"> EXTERNAL_PREREQUISITES_NOT_MET </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> bdq:sourceAuthority was not available or was unreachable </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 094_2 </td>
   <td style="text-align:left;"> Australia </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country and dwc:stateProvince are unambiguous </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 094_3 </td>
   <td style="text-align:left;"> Argentina </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country and dwc:stateProvince are unambiguous </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 094_4 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> Tasmania </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country and dwc:stateProvince are unambiguous </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 094_5 </td>
   <td style="text-align:left;"> Australia </td>
   <td style="text-align:left;"> Tasmania </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country and dwc:stateProvince are unambiguous </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 094_6 </td>
   <td style="text-align:left;"> Argentina </td>
   <td style="text-align:left;"> Rio Negro </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> COMPLIANT </td>
   <td style="text-align:left;"> dwc:country and dwc:stateProvince are unambiguous </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 094_7 </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> WA </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:country and dwc:stateProvince are ambiguous. Matches Western Australia, Washington State (US) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 094_8 </td>
   <td style="text-align:left;"> Australia </td>
   <td style="text-align:left;"> Florida </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:country and dwc:stateProvince are ambiguous </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 094_9 </td>
   <td style="text-align:left;"> Fred </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:country and dwc:stateProvince are ambiguous </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 094_10 </td>
   <td style="text-align:left;"> X </td>
   <td style="text-align:left;"> Y </td>
   <td style="text-align:left;"> RUN_HAS_RESULT </td>
   <td style="text-align:left;"> NOT_COMPLIANT </td>
   <td style="text-align:left;"> dwc:country and dwc:stateProvince are ambiguous </td>
  </tr>
</tbody>
</table>

**Outros exemplos**: [dwc:country="Russian Federation", dwc:stateProvince="Moscow Oblast": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:country and dwc:stateProvince are unambiguous"],[dwc:country="", dwc:stateProvince="WA": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:country and dwc:stateProvince are ambiguous. Matches Western Australia, Washington State (US)"]

## Teste 095: [`VALIDATION_KINGDOM_NOTEMPTY`](https://github.com/tdwg/bdq/issues/216) 

**Nome do teste**: `VALIDATION_KINGDOM_NOTEMPTY` 

**Última atualização**: `2024-01-28` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/216 

**ID oficial do teste**: `36ed36c9-b1a7-40b2-b5e2-0d012e772098` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `kingdom` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:kingdom?_ 

**Especificação**: 
> _COMPLIANT if dwc:kingdom is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 

\* A tabela com os exemplos para o teste VALIDATION_KINGDOM_NOTEMPTY ainda não está disponível.

**Outros exemplos**: [dwc:kingdom="kingdom": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:kingdom is not EMPTY"],[dwc:kingdom="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:kingdom is EMPTY"]

## Teste 096: [`VALIDATION_SCIENTIFICNAMEAUTHORSHIP_NOTEMPTY`](https://github.com/tdwg/bdq/issues/244) 

**Nome do teste**: `VALIDATION_SCIENTIFICNAMEAUTHORSHIP_NOTEMPTY` 

**Última atualização**: `2024-02-04` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/244 

**ID oficial do teste**: `49f1d386-5bed-43ae-bd43-deabf7df64fc` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `scientificNameAuthorship` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:scientificNameAuthorship?_ 

**Especificação**: 
> _COMPLIANT if dwc:scientificNameAuthorship is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 

\* A tabela com os exemplos para o teste VALIDATION_SCIENTIFICNAMEAUTHORSHIP_NOTEMPTY ainda não está disponível.

**Outros exemplos**: [dwc:scientificNameAuthorship="(Györfi, 1952)": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:scientificNameAuthorship is not EMPTY"],[dwc:scientificNameAuthorship="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:scientificNameAuthorship is EMPTY"]

## Teste 097: [`VALIDATION_NAMEPUBLISHEDINYEAR_NOTEMPTY`](https://github.com/tdwg/bdq/issues/259) 

**Nome do teste**: `VALIDATION_NAMEPUBLISHEDINYEAR_NOTEMPTY` 

**Última atualização**: `2024-02-07` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/259 

**ID oficial do teste**: `ff59f77d-71e9-4eb1-aac9-8bd05c50ff70` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Taxon` 

**Termos (colunas) testados**: `namePublishedInYear` 

**Pré-requisitos externos (parâmetros)**: Não especificado. Porém, conferir a existência de EXTERNAL_PREREQUISITES_NOT_MET em Response.status. 

**Descrição**: 
> _Is there a value in dwc:namePublishedInYear?_ 

**Especificação**: 
> _COMPLIANT if dwc:namePublishedInYear is not EMPTY; otherwise NOT_COMPLIANT_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 

\* A tabela com os exemplos para o teste VALIDATION_NAMEPUBLISHEDINYEAR_NOTEMPTY ainda não está disponível.

**Outros exemplos**: [dwc:namePublishedInYear="2024": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:namePublishedInYear is not EMPTY"],[dwc:namePublishedInYear="": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:namePublishedInYear is EMPTY"]

## Teste 098: [`VALIDATION_ESTABLISHMENTMEANS_STANDARD`](https://github.com/tdwg/bdq/issues/268) 

**Nome do teste**: `VALIDATION_ESTABLISHMENTMEANS_STANDARD` 

**Última atualização**: `2024-02-08` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/268 

**ID oficial do teste**: `4eb48fdf-7299-4d63-9d08-246902e2857f` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Occurrence` 

**Termos (colunas) testados**: `establishmentMeans` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Does the value of dwc:establishmentMeans occur in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:establishmentMeans is EMPTY; COMPLIANT if the value of dwc:establishmentMeans is in the bdq:sourceAuthority; otherwise NOT_COMPLIANT. bdq:sourceAuthority default = "Darwin Core establishmentMeans" {[https://dwc.tdwg.org/list/#dwc_establishmentMeans]} {dwc:establishmentMeans vocabulary API [https://api.gbif.org/v1/vocabularies/EstablishmentMeans/concepts]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _This test must return NOT_COMPLIANT if there is leading or trailing whitespace or there are leading or trailing non-printing characters._ 

\* A tabela com os exemplos para o teste VALIDATION_ESTABLISHMENTMEANS_STANDARD ainda não está disponível.

**Outros exemplos**: [dwc:establishmentMeans="native": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:establishmentMeans has an equivalent in the bdq:sourceAuthority"],[dwc:establishmentMeans="cultivated": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:establishmentMeans does not have an equivalent in the bdq:sourceAuthority"]

## Teste 099: [`AMENDMENT_ESTABLISHMENTMEANS_STANDARDIZED`](https://github.com/tdwg/bdq/issues/269) 

**Nome do teste**: `AMENDMENT_ESTABLISHMENTMEANS_STANDARDIZED` 

**Última atualização**: `2024-02-08` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/269 

**ID oficial do teste**: `15d15927-7a22-43f8-88d6-298f5eb45c4c` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Occurrence` 

**Termos (colunas) testados**: `establishmentMeans` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Propose amendment to the value of dwc:establishmentMeans using bdq:sourceAuthority._ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL PREREQUISITES_NOT_MET if dwc:establishmentMeans is EMPTY; AMENDED the value of dwc:establishmentMeans if it can be unambiguously matched to a term in bdq:sourceAuthority; otherwise NOT_AMENDED bdq:sourceAuthority default = "Darwin Core establishmentMeans" {[https://dwc.tdwg.org/list/#dwc_establishmentMeans]} {dwc:establishmentMeans vocabulary API [https://api.gbif.org/v1/vocabularies/EstablishmentMeans/concepts]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 

\* A tabela com os exemplos para o teste AMENDMENT_ESTABLISHMENTMEANS_STANDARDIZED ainda não está disponível.

**Outros exemplos**: [dwc:establishmentMeans="indigenous": Response.status=AMENDED, Response.result=dwc:establishmentMeans="native", Response.comment="dwc:establishmentMeans contains an interpretable value according to the bdq:sourceAuthority"],[dwc:establishmentMeans="species": Response.status=NOT_AMENDED, Response.result="", Response.comment="dwc:establishmentMeans does not contain an interpretable value according to the bdq:sourceAuthority"]

## Teste 100: [`VALIDATION_DEGREEOFESTABLISHMENT_STANDARD`](https://github.com/tdwg/bdq/issues/275) 

**Nome do teste**: `VALIDATION_DEGREEOFESTABLISHMENT_STANDARD` 

**Última atualização**: `2024-02-09` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/275 

**ID oficial do teste**: `060e7734-607d-4737-8b2c-bfa17788bf1a` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Occurrence` 

**Termos (colunas) testados**: `degreeOfEstablishment` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Does the value of dwc:degreeOfEstablishment occur in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:degreeOfEstablishment is EMPTY; COMPLIANT if the value of dwc:degreeOfEstablishment is in the bdq:sourceAuthority; otherwise NOT_COMPLIANT. bdq:sourceAuthority default = "Darwin Core degreeOfEstablishment" {[https://dwc.tdwg.org/list/#dwc_degreeOfEstablishment]} {dwc:degreeOfEstablishment vocabulary API [https://api.gbif.org/v1/vocabularies/DegreeOfEstablishment/concepts]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _This test must return NOT_COMPLIANT if there is leading or trailing whitespace or there are leading or trailing non-printing characters._ 

\* A tabela com os exemplos para o teste VALIDATION_DEGREEOFESTABLISHMENT_STANDARD ainda não está disponível.

**Outros exemplos**: [dwc:degreeOfEstablishment="cultivated": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:degreeOfEstablishment has an equivalent in the bdq:sourceAuthority"],[dwc:degreeOfEstablishment="grown in garden": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:degreeOfEstablishment does not have an equivalent in the bdq:sourceAuthority"]

## Teste 101: [`AMENDMENT_DEGREEOFESTABLISHMENT_STANDARDIZED`](https://github.com/tdwg/bdq/issues/276) 

**Nome do teste**: `AMENDMENT_DEGREEOFESTABLISHMENT_STANDARDIZED` 

**Última atualização**: `2024-02-09` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/276 

**ID oficial do teste**: `74ef1034-e289-4596-b5b0-cde73796697d` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Occurrence` 

**Termos (colunas) testados**: `degreeOfEstablishment` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Propose amendment to the value of dwc:degreeOfEstablishment using bdq:sourceAuthority._ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL PREREQUISITES_NOT_MET if dwc:degreeOfEstablishment is EMPTY; AMENDED the value of dwc:degreeOfEstablishment if it can be unambiguously matched to a term in bdq:sourceAuthority; otherwise NOT_AMENDED bdq:sourceAuthority default = "Darwin Core degreeOfEstablishment" {[https://dwc.tdwg.org/list/#dwc_degreeOfEstablishment]} {dwc:degreeOfEstablishment vocabulary API [https://api.gbif.org/v1/vocabularies/DegreeOfEstablishment/concepts]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 

\* A tabela com os exemplos para o teste AMENDMENT_DEGREEOFESTABLISHMENT_STANDARDIZED ainda não está disponível.

**Outros exemplos**: [dwc:degreeOfEstablishment="caged": Response.status=AMENDED, Response.result=dwc:degreeOfEstablishment="captive", Response.comment="dwc:degreeOfEstablishment contains an interpretable value according to the bdq:sourceAuthority"],[dwc:degreeOfEstablishment="tree": Response.status=NOT_AMENDED, Response.result="", Response.comment="dwc:degreeOfEstablishment does not contain an interpretable value according to the bdq:sourceAuthority"]

## Teste 102: [`VALIDATION_PATHWAY_STANDARD`](https://github.com/tdwg/bdq/issues/277) 

**Nome do teste**: `VALIDATION_PATHWAY_STANDARD` 

**Última atualização**: `2024-02-09` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/277 

**ID oficial do teste**: `5424e933-bee7-4125-839e-d8743ea69f93` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Occurrence` 

**Termos (colunas) testados**: `pathway` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Does the value of dwc:pathway occur in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:pathway is EMPTY; COMPLIANT if the value of dwc:pathway is in the bdq:sourceAuthority; otherwise NOT_COMPLIANT. bdq:sourceAuthority default = "Darwin Core pathway" {[https://dwc.tdwg.org/list/#dwc_pathway]} {dwc:pathway vocabulary API [https://api.gbif.org/v1/vocabularies/Pathway/concepts]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _This test must return NOT_COMPLIANT if there is leading or trailing whitespace or there are leading or trailing non-printing characters._ 

\* A tabela com os exemplos para o teste VALIDATION_PATHWAY_STANDARD ainda não está disponível.

**Outros exemplos**: [dwc:pathway="transportStowaway": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:pathway has an equivalent in the bdq:sourceAuthority"],[dwc:pathway="escapee": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:pathway does not have an equivalent in the bdq:sourceAuthority"]

## Teste 103: [`AMENDMENT_PATHWAY_STANDARDIZED`](https://github.com/tdwg/bdq/issues/278) 

**Nome do teste**: `AMENDMENT_PATHWAY_STANDARDIZED` 

**Última atualização**: `2024-02-09` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/278 

**ID oficial do teste**: `f9205977-f145-44f5-8cb9-e3e2e35ce908` 

**Tipo de teste**: `Amendment` 

**Contexto dos termos testados**: `Occurrence` 

**Termos (colunas) testados**: `pathway` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Propose amendment to the value of dwc:pathway using bdq:sourceAuthority._ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL PREREQUISITES_NOT_MET if dwc:pathway is EMPTY; AMENDED the value of dwc:pathway if it can be unambiguously matched to a term in bdq:sourceAuthority; otherwise NOT_AMENDED bdq:sourceAuthority default = "Darwin Core pathway" {[https://dwc.tdwg.org/list/#dwc_pathway]} {dwc:pathway vocabulary API [https://api.gbif.org/v1/vocabularies/Pathway/concepts]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _Not available_ 

\* A tabela com os exemplos para o teste AMENDMENT_PATHWAY_STANDARDIZED ainda não está disponível.

**Outros exemplos**: [dwc:pathway="Stowaway on Truck": Response.status=AMENDED, Response.result=dwc:pathway="transportStowaway", Response.comment="dwc:pathway contains an interpretable value according to the bdq:sourceAuthority"],[dwc:pathway="weed": Response.status=NOT_AMENDED, Response.result="", Response.comment="dwc:pathway does not contain an interpretable value according to the bdq:sourceAuthority"]

## Teste 104: [`VALIDATION_TYPESTATUS_STANDARD`](https://github.com/tdwg/bdq/issues/285) 

**Nome do teste**: `VALIDATION_TYPESTATUS_STANDARD` 

**Última atualização**: `2024-02-09` 

**Github** _**issue**_: https://github.com/tdwg/bdq/issues/285 

**ID oficial do teste**: `4833a522-12eb-4fe0-b4cf-7f7a337a6048` 

**Tipo de teste**: `Validation` 

**Contexto dos termos testados**: `Occurrence` 

**Termos (colunas) testados**: `typeStatus` 

**Pré-requisitos externos (parâmetros)**: `bdq:sourceAuthority` 

**Descrição**: 
> _Does the value of dwc:typeStatus occur in bdq:sourceAuthority?_ 

**Especificação**: 
> _EXTERNAL_PREREQUISITES_NOT_MET if the bdq:sourceAuthority is not available; INTERNAL_PREREQUISITES_NOT_MET if dwc:typeStatus is EMPTY; COMPLIANT if the value of dwc:typeStatus is in the bdq:sourceAuthority; otherwise NOT_COMPLIANT. bdq:sourceAuthority default = "Darwin Core typeStatus" {[https://dwc.tdwg.org/list/#dwc_typeStatus]} {dwc:typeStatus vocabulary API [(https://gbif.github.io/parsers/apidocs/org/gbif/api/vocabulary/TypeStatus.html]}_ 

**Código fonte de exemplo**: _Not available_ 

**Notas**: _This test must return NOT_COMPLIANT if there is leading or trailing whitespace or there are leading or trailing non-printing characters._ 

\* A tabela com os exemplos para o teste VALIDATION_TYPESTATUS_STANDARD ainda não está disponível.

**Outros exemplos**: [dwc:typeStatus="holotype": Response.status=RUN_HAS_RESULT, Response.result=COMPLIANT, Response.comment="dwc:typeStatus has an equivalent in the bdq:sourceAuthority"],[dwc:typeStatus="cleptotype": Response.status=RUN_HAS_RESULT, Response.result=NOT_COMPLIANT, Response.comment="dwc:typeStatus does not have an equivalent in the bdq:sourceAuthority"]

