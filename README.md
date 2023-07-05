# DarwinCoreBrasil
Termos DarwinCore para compartilhamento de dados e informações em biodiversidade com o objetivo identificar termos com vocabulário controlado e definir um conjunto de boas práticas no uso do padrão no Brasil junto com todas as instituições e organizações que produzem dados. 
https://dwc.tdwg.org/terms/
## Justificativa
O uso do padrão DarwinCore para compartilhamento de dados em biobiversidade tem aumentado no Brasil sendo que quase todas as instituições, organizações, fundações, programas e projetos que trabalham com dados tem publicado em alguma plataforma seja nacional ou internacional. Devido a grande heterogeneidade de tipos de dados, coleções e grupos existem dúvidas nos preenchimentos de cada campo. A discussão dos termos e melhores práticas vai contribuir a organizar os dados corretamente no Brasil, tendo em consideração todas as instituições e suas respetivas demandas e termos a serem considerados e compartilhados. 
## Classes e Termos DarwinCore

| [Record-level](https://github.com/sibbr/DarwinCoreBrasil#record-level) | [Ocurrence](https://github.com/sibbr/DarwinCoreBrasil#occurrence) | [Organism](https://github.com/sibbr/DarwinCoreBrasil#organism) | [MaterialSample](https://github.com/sibbr/DarwinCoreBrasil#materialsample)| [Event](https://github.com/sibbr/DarwinCoreBrasil#event) | [Location](https://github.com/sibbr/DarwinCoreBrasil#location) | [GeologicalContext](https://github.com/sibbr/DarwinCoreBrasil#geologicalcontext) | [Identification](https://github.com/sibbr/DarwinCoreBrasil#identification) | [Taxon](https://github.com/sibbr/DarwinCoreBrasil#taxon) | [MeasurementOrFact](https://github.com/sibbr/DarwinCoreBrasil#measurementorfact)
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

### Record-level


#### [datasetName](https://github.com/sibbr/DarwinCoreBrasil/issues/1)


|Identificador |https://dwc.tdwg.org/terms/#dwc:datasetName                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome que identifica o conjunto de dados do qual o registro foi derivado.                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|Domínio       |datasetName                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|Exemplos      |Para coleções: Coleção de Mamíferos do Museu Nacional do Rio de Janeiro ; Para subcoleções: Coleção/Subcoleção de Odonata da Coleção de Entomologia do Museu Nacional do Rio de Janeiro ; Para dado de projeto de pesquisa: Amostragem de espécies lenhosas no Parque Nacional Chapada das Mesas ; PELD: PELD - ELPA &#124; Ecology of Lahille's bottlenose dolphin Tursiops truncatus gephyreus in the Patos Lagoon estuary and adjacent marine coast ; PPBio: PPBioMA &#124; PPBio: Morcegos no Parque Nacional da Tijuca |


---

#### [type](https://github.com/sibbr/DarwinCoreBrasil/issues/2)


|Identificador |https://dwc.tdwg.org/terms/#dc:type                                                       |
|:-------------|:-----------------------------------------------------------------------------------------|
|Definição     |A natureza ou gênero do recurso.                                                          |
|Domínio       |StillImage &#124; MovingImage &#124; Sound &#124; PhysicalObject &#124; Event &#124; Text |
|Exemplos      |                                                                                          |


---

#### [modified](https://github.com/sibbr/DarwinCoreBrasil/issues/3)


|Identificador |https://dwc.tdwg.org/terms/#dcterms:modified            |
|:-------------|:-------------------------------------------------------|
|Definição     |A data-hora mais recente em que o recurso foi alterado. |
|Domínio       |AAAA-MM-DD                                              |
|Exemplos      |                                                        |


---

#### [language](https://github.com/sibbr/DarwinCoreBrasil/issues/4)


|Identificador |https://dwc.tdwg.org/terms/#dc:language |
|:-------------|:---------------------------------------|
|Definição     |A língua do recurso.                    |
|Domínio       |pt &#124; en &#124; es                  |
|Exemplos      |                                        |


---

#### [license](https://github.com/sibbr/DarwinCoreBrasil/issues/5)


|Identificador |https://dwc.tdwg.org/terms/#dcterms:license                               |
|:-------------|:-------------------------------------------------------------------------|
|Definição     |Um documento legal dando permissão oficial para fazer algo com o recurso. |
|Domínio       |CC BY - NC &#124; CC0 &#124; CC BY                                        |
|Exemplos      |                                                                          |


---

#### [rightsHolder](https://github.com/sibbr/DarwinCoreBrasil/issues/6)


|Identificador |https://dwc.tdwg.org/terms/#dcterms:rightsHolder                           |
|:-------------|:--------------------------------------------------------------------------|
|Definição     |Uma pessoa ou organização que possui ou gerencia direitos sobre o recurso. |
|Domínio       |Nome completo da instituição, fundação ou órgão                            |
|Exemplos      |                                                                           |


---

#### [accessRights](https://github.com/sibbr/DarwinCoreBrasil/issues/7)


|Identificador |https://dwc.tdwg.org/terms/#dcterms:accessRights                                                                                                                                                                                           |
|:-------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Informações sobre quem pode acessar o recurso ou uma indicação de seu status de segurança.                                                                                                                                                 |
|Domínio       |link para a politica de acesso da instituição                                                                                                                                                                                              |
|Exemplos      |Politica dados Fiocruz: https://www.arca.fiocruz.br/bitstream/handle/icict/46408/VPEIC_versao_PORTUGUES_2021-03-22.pdf?sequence=2&isAllowed=y ; Política de dados do PPBio: https://ppbio.inpa.gov.br/sites/default/files/politica_dou.pdf |


---

#### [bibliographicCitation](https://github.com/sibbr/DarwinCoreBrasil/issues/8)


|Identificador |https://dwc.tdwg.org/terms/#dcterms:bibliographicCitation                                                                                  |
|:-------------|:------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma referência bibliográfica para o recurso como uma declaração indicando como esse registro deve ser citado (atribuído) quando utilizado. |
|Domínio       |link de acesso                                                                                                                             |
|Exemplos      |                                                                                                                                           |


---

#### [references](https://github.com/sibbr/DarwinCoreBrasil/issues/9)


|Identificador |https://dwc.tdwg.org/terms/#dcterms:references                                                      |
|:-------------|:---------------------------------------------------------------------------------------------------|
|Definição     |Um recurso relacionado que é referenciado, citado ou apontado de outra forma pelo recurso descrito. |
|Domínio       |link de acesso                                                                                      |
|Exemplos      |                                                                                                    |


---

#### [institutionID](https://github.com/sibbr/DarwinCoreBrasil/issues/10)


|Identificador |https://dwc.tdwg.org/terms/#dwc:institutionID                                                                                                                                                |
|:-------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um identificador da instituição que detém a guarda do(s) objeto(s) ou das informações referidas no registo.                                                                                  |
|Domínio       |MNRJ &#124; INPA                                                                                                                                                                             |
|Exemplos      |para zoologia: https://ala-hub.sibbr.gov.br/ala-hub/occurrences/7a7fd7a2-04b7-4232-b13f-8a06e9fa14c1 e https://ala-hub.sibbr.gov.br/ala-hub/occurrences/41e3ad42-a052-40b6-95dd-8f5001a312bc |


---

#### [collectionID](https://github.com/sibbr/DarwinCoreBrasil/issues/11)


|Identificador |https://dwc.tdwg.org/terms/#dwc:collectionID                                                                                                                                                                                                                                                                    |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um identificador para a coleção ou conjunto de dados do qual o registro foi derivado.                                                                                                                                                                                                                           |
|Domínio       |Anfíbios MNRJ &#124; ColCrustaceaINPA &#124; MFS-FLORES                                                                                                                                                                                                                                                         |
|Exemplos      |Para coleções de botânica: https://ala-hub.sibbr.gov.br/ala-hub/occurrences/adfb9207-d797-4fe8-b620-6e5d06c05a16 e para zoologia: https://ala-hub.sibbr.gov.br/ala-hub/occurrences/7a7fd7a2-04b7-4232-b13f-8a06e9fa14c1 e https://ala-hub.sibbr.gov.br/ala-hub/occurrences/41e3ad42-a052-40b6-95dd-8f5001a312bc |


---

#### [datasetID](https://github.com/sibbr/DarwinCoreBrasil/issues/12)


|Identificador |https://dwc.tdwg.org/terms/#dwc:datasetID                                             |
|:-------------|:-------------------------------------------------------------------------------------|
|Definição     |Um identificador para a coleção ou conjunto de dados do qual o registro foi derivado. |
|Domínio       |[instituição]:[Programa]:[Projeto]                                                    |
|Exemplos      |Projetos Fundação Renova - RENOVA:PMBA:P164;Projetos ICMBio - ICMBIO:SALVE:XXX        |


---

#### [institutionCode](https://github.com/sibbr/DarwinCoreBrasil/issues/13)


|Identificador |https://dwc.tdwg.org/terms/#dwc:institutionCode                                                                        |
|:-------------|:----------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome (ou sigla) em uso pela instituição que detém a guarda do(s) objeto(s) ou das informações referidas no registro. |
|Domínio       |[Acrônimo da instituição]                                                                                              |
|Exemplos      |Acrônimo da instituição. Não o nome completo. Mesmo acrônimo para todos os datasets da instituição                     |


---

#### [collectionCode](https://github.com/sibbr/DarwinCoreBrasil/issues/14)


|Identificador |https://dwc.tdwg.org/terms/#dwc:collectionCode                                                                       |
|:-------------|:--------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome, acrônimo ou código que identifica a coleção ou o conjunto de dados do qual o registro foi derivado.          |
|Domínio       |[Acrônimo da coleção]                                                                                                |
|Exemplos      |Acrônimo da coleção ; Herbários: Index Herbariorum ; Coleções Zoológicas: verificar Sociedade Brasileira de Zoologia |


---

#### [ownerInstitutionCode](https://github.com/sibbr/DarwinCoreBrasil/issues/15)


|Identificador |https://dwc.tdwg.org/terms/#dwc:ownerInstitutionCode                                                                |
|:-------------|:-------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome (ou sigla) utilizado pela instituição proprietária do(s) objeto(s) ou das informações referidas no registro. |
|Domínio       |MNRJ &#124; INPA                                                                                                    |
|Exemplos      |                                                                                                                    |


---

#### [basisOfRecord](https://github.com/sibbr/DarwinCoreBrasil/issues/16)


|Identificador |https://dwc.tdwg.org/terms/#dwc:basisOfRecord                                                                                                                                                                                       |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |A natureza específica do registro de dados.                                                                                                                                                                                         |
|Domínio       |PreservedSpecimen &#124; HumanObservation &#124; MaterialSample &#124; LivingSpecimen &#124; MachineObservation                                                                                                                     |
|Exemplos      |para coleções de herbário: https://ala-hub.sibbr.gov.br/ala-hub/occurrences/885bdb7b-66ef-427e-b5f6-c6ae3702c179 / para coleções de zoologia: https://ala-hub.sibbr.gov.br/ala-hub/occurrences/7a7fd7a2-04b7-4232-b13f-8a06e9fa14c1 |


---

#### [informationWithheld](https://github.com/sibbr/DarwinCoreBrasil/issues/17)


|Identificador |https://dwc.tdwg.org/terms/#dwc:informationWithheld                                         |
|:-------------|:-------------------------------------------------------------------------------------------|
|Definição     |Informações adicionais que existem, mas que não foram compartilhadas no registro fornecido. |
|Domínio       |                                                                                            |
|Exemplos      |Coordenadas exatas disponíveis; Identificação até nivel de espécie                          |


---

#### [dataGeneralizations](https://github.com/sibbr/DarwinCoreBrasil/issues/18)


|Identificador |https://dwc.tdwg.org/terms/#dwc:dataGeneralizations                                         |
|:-------------|:-------------------------------------------------------------------------------------------|
|Definição     |Informações adicionais que existem, mas que não foram compartilhadas no registro fornecido. |
|Domínio       |                                                                                            |
|Exemplos      |Ponto centroide (Estado, Municipio ou Localidade) para obtenção de coordenada               |


---

#### [dynamicProperties](https://github.com/sibbr/DarwinCoreBrasil/issues/19)


|Identificador |https://dwc.tdwg.org/terms/#dwc:dynamicProperties                                                                                                    |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista de medidas, fatos, características ou afirmações adicionais sobre o registro. Destinado a fornecer um mecanismo para conteúdo estruturado. |
|Domínio       |JSON                                                                                                                                                 |
|Exemplos      |{"Peso (gr)":22} ; {"Peso (gr)":22, "Cor":"azul"} ; {"DAP (cm)":34, "Altura (m)":2.3}                                                                |


---

### Occurrence


#### [occurrenceID](https://github.com/sibbr/DarwinCoreBrasil/issues/20)


|Identificador |https://dwc.tdwg.org/terms/#dwc:occurrenceID                                                                                                                                                                                                                                               |
|:-------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um identificador para a ocorrência (em oposição a um registro digital específico da ocorrência). Na ausência de um identificador exclusivo global persistente, construa um a partir de uma combinação de identificadores no registro que tornará o id de ocorrência globalmente exclusivo. |
|Domínio       |Identificador único do registro                                                                                                                                                                                                                                                            |
|Exemplos      |Dados de coleção: [BR]:[InstitutionCode]:[CollectionCode]:[CatalogNumber]; Dados evento amostragem: [EventID]_[id] ou [EventID]_[Placa arvore, anel captura]                                                                                                                               |


---

#### [catalogNumber](https://github.com/sibbr/DarwinCoreBrasil/issues/21)


|Identificador |https://dwc.tdwg.org/terms/#dwc:catalogNumber                                                       |
|:-------------|:---------------------------------------------------------------------------------------------------|
|Definição     |Um identificador (de preferência exclusivo) para o registro dentro do conjunto de dados ou coleção. |
|Domínio       |[collectionCode]_[catalogNumber]                                                                    |
|Exemplos      |RB_23493 &#124; ACAM_354.1 &#124;                                                                   |


---

#### [recordNumber](https://github.com/sibbr/DarwinCoreBrasil/issues/22)


|Identificador |https://dwc.tdwg.org/terms/#dwc:recordNumber                                                                                                                                                                                                                                                                                          |
|:-------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um identificador dado à ocorrência no momento em que foi registrada. Muitas vezes serve como um link entre as notas de campo e um registro de ocorrência, como o número de um coletor de amostras.                                                                                                                                    |
|Domínio       |34 &#124; 625 &#124; 	JD-059                                                                                                                                                                                                                                                                                                           |
|Exemplos      |Para coleções herbário: https://ala-hub.sibbr.gov.br/ala-hub/occurrences/bc8b4528-9a08-48ca-b3e4-da16ffd03ff2 - JABOT Para coleções de Zoologia: https://ala-hub.sibbr.gov.br/ala-hub/occurrences/28542092-5804-4de0-a9bb-9991cfc1786d - MNRJ e https://ala-hub.sibbr.gov.br/ala-hub/occurrences/c0292efd-b25a-4c21-9c2d-3e2b0801c5a6 |


---

#### [recordedBy](https://github.com/sibbr/DarwinCoreBrasil/issues/23)


|Identificador |https://dwc.tdwg.org/terms/#dwc:recordedBy                                                                                                                                                                                                                              |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de nomes de pessoas, grupos ou organizações responsáveis pelo registro da ocorrência original. O coletor ou observador primário, especialmente aquele que aplica um identificador pessoal (recordnumber), deve ser listado primeiro. |
|Domínio       |Alvarenga, D. D &#124; Ribeiro, F. Juliana                                                                                                                                                                                                                              |
|Exemplos      |Para coleções herbário: https://ala-hub.sibbr.gov.br/ala-hub/occurrences/86b9fb12-c2b9-4695-ade6-b0b00ba4e0a5. Para coleções de Zoologia:https://ala-hub.sibbr.gov.br/ala-hub/occurrences/4cc24396-7858-4bc0-b0d6-5a9849633e72                                          |


---

#### [recordedByID](https://github.com/sibbr/DarwinCoreBrasil/issues/24)


|Identificador |https://dwc.tdwg.org/terms/#dwc:recordedByID                                                                                                                       |
|:-------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) do identificador global exclusivo da pessoa, pessoas, grupos ou organizações responsáveis pelo registro da ocorrência original. |
|Domínio       |                                                                                                                                                                   |
|Exemplos      |                                                                                                                                                                   |


---

#### [individualCount](https://github.com/sibbr/DarwinCoreBrasil/issues/25)


|Identificador |https://dwc.tdwg.org/terms/#dwc:individualCount            |
|:-------------|:----------------------------------------------------------|
|Definição     |O número de indivíduos presentes no momento da ocorrência. |
|Domínio       |1 &#124; 10 &#124; 25                                      |
|Exemplos      |                                                           |


---

#### [organismQuantity](https://github.com/sibbr/DarwinCoreBrasil/issues/26)


|Identificador |https://dwc.tdwg.org/terms/#dwc:organismQuantity                  |
|:-------------|:-----------------------------------------------------------------|
|Definição     |Um número ou valor de enumeração para a quantidade de organismos. |
|Domínio       |27 (organismQuantity) com indíviduos (organismQuantityType)       |
|Exemplos      |                                                                  |


---

#### [organismQuantityType](https://github.com/sibbr/DarwinCoreBrasil/issues/27)


|Identificador |https://dwc.tdwg.org/terms/#dwc:organismQuantityType                          |
|:-------------|:-----------------------------------------------------------------------------|
|Definição     |O tipo de sistema de quantificação utilizado para a quantidade de organismos. |
|Domínio       |27 (organismQuantity) com indíviduos (organismQuantityType)                   |
|Exemplos      |                                                                              |


---

#### [sex](https://github.com/sibbr/DarwinCoreBrasil/issues/28)


|Identificador |https://dwc.tdwg.org/terms/#dwc:sex                                                   |
|:-------------|:-------------------------------------------------------------------------------------|
|Definição     |O sexo do(s) indivíduo(s) biológico(s) representado(s) na ocorrência.                 |
|Domínio       |Macho &#124; Femea &#124; Hermafrodita &#124; Male &#124; Female &#124; Hermaphrodite |
|Exemplos      |                                                                                      |


---

#### [lifeStage](https://github.com/sibbr/DarwinCoreBrasil/issues/29)


|Identificador |https://dwc.tdwg.org/terms/#dwc:lifeStage                                                                                              |
|:-------------|:--------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |A classe etária ou estágio de vida do(s) organismo(s) no momento em que a ocorrência foi registrada.                                   |
|Domínio       |Zigoto &#124; Ovos &#124;Larva &#124; Pupa &#124; Juvenil &#124; Adulto &#124; Semente &#124; Muda &#124; Frutificação &#124; Floração |
|Exemplos      |zoologia: ipt.sibbr.gov.br/sibbr/resource?r=soil_macrofauna_clasen / http://vocab.nerc.ac.uk/collection/S11/current/                   |


---

#### [reproductiveCondition](https://github.com/sibbr/DarwinCoreBrasil/issues/30)


|Identificador |https://dwc.tdwg.org/terms/#dwc:reproductiveCondition                                 |
|:-------------|:-------------------------------------------------------------------------------------|
|Definição     |A condição reprodutiva do(s) indivíduo(s) biológico(s) representado(s) na ocorrência. |
|Domínio       |Grávida &#124; Não reprodutiva &#124; Em flor &#124; Frutífero                        |
|Exemplos      |                                                                                      |


---

#### [behavior](https://github.com/sibbr/DarwinCoreBrasil/issues/31)


|Identificador |https://dwc.tdwg.org/terms/#dwc:behavior                                                                                    |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------|
|Definição     |O comportamento apresentado pelo sujeito no momento em que a ocorrência foi registrada.                                     |
|Domínio       |Pelágico &#124; Bentônico &#124; Nectônicos &#124; Planctônico &#124; Árvore &#124; Arbusto &#124; Lianas &#124; Subarbusto |
|Exemplos      |                                                                                                                            |


---

#### [establishmentMeans](https://github.com/sibbr/DarwinCoreBrasil/issues/32)


|Identificador |https://dwc.tdwg.org/terms/#dwc:establishmentMeans                                                                                                              |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Declaração sobre se um organismo ou organismos foram introduzidos em um determinado lugar e tempo através da atividade direta ou indireta dos humanos modernos. |
|Domínio       |Introduzida &#124; Nativa &#124; Incerto &#124; Errante &#124;Nativa reintroduzida &#124; Introduzida por colonização assistida                                 |
|Exemplos      |                                                                                                                                                                |


---

#### [degreeOfEstablishment](https://github.com/sibbr/DarwinCoreBrasil/issues/33)


|Identificador |https://dwc.tdwg.org/terms/#dwc:degreeOfEstablishment                                                                                                                                                                                                                                                                                                |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O grau em que um organismo sobrevive, se reproduz e expande seu alcance no lugar e tempo determinados.                                                                                                                                                                                                                                               |
|Domínio       |Cultivada &#124; Nativa &#124;Invasora &#124; Naturalizada &#124;Introduzida &#124; Domesticada &#124; Criptogênico &#124; Nativa - endêmica &#124; Nativa - não endêmica &#124; Origem incerta &#124; Origem não conhecida                                                                                                                          |
|Exemplos      |Para coleções de herbário: http://floradobrasil.jbrj.gov.br/reflora/listaBrasil/PrincipalUC/PrincipalUC.do;jsessionid=9E1CFFE3946CC896F95E9BAFC4601A7E#CondicaoTaxonCP / Para espécies marinhas: WoRMS - World Register of Marine Species /Para coleções zoológicas: http://fauna.jbrj.gov.br/fauna/listaBrasil/PrincipalUC/PrincipalUC.do?lingua=en |


---

#### [pathway](https://github.com/sibbr/DarwinCoreBrasil/issues/34)


|Identificador |https://dwc.tdwg.org/terms/#dwc:pathway                                                        |
|:-------------|:----------------------------------------------------------------------------------------------|
|Definição     |O processo pelo qual um organismo veio a estar em um determinado lugar em um determinado tempo |
|Domínio       |Liberado para uso &#124; Transporte contaminante &#124; Corredor                               |
|Exemplos      |                                                                                               |


---

#### [georeferenceVerificationStatus](https://github.com/sibbr/DarwinCoreBrasil/issues/35)


|Identificador |https://dwc.tdwg.org/terms/#dwc:georeferenceVerificationStatus                                                                                               |
|:-------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Descrição categórica do grau em que se verificou que o georreferenciamento representa a melhor descrição espacial possível para a localização da ocorrência. |
|Domínio       |Não é possível georreferenciar &#124; Requer georrefenciamento &#124; Requer verificação                                                                     |
|Exemplos      |                                                                                                                                                             |


---

#### [occurrenceStatus](https://github.com/sibbr/DarwinCoreBrasil/issues/36)


|Identificador |https://dwc.tdwg.org/terms/#dwc:occurrenceStatus                     |
|:-------------|:--------------------------------------------------------------------|
|Definição     |Uma declaração sobre a presença ou ausência de um táxon em um local. |
|Domínio       |Presença &#124; Absença &#124;Present &#124;Absent                   |
|Exemplos      |                                                                     |


---

#### [preparations](https://github.com/sibbr/DarwinCoreBrasil/issues/37)


|Identificador |https://dwc.tdwg.org/terms/#dwc:preparations                                                            |
|:-------------|:-------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista de preparações e métodos de conservação de um espécime.                                       |
|Domínio       |pele&#124; crânio &#124; esqueleto &#124;animal inteiro &#124; tecido &#124; extração DNA &#124; Sangue |
|Exemplos      |                                                                                                        |


---

#### [disposition](https://github.com/sibbr/DarwinCoreBrasil/issues/38)


|Identificador |https://dwc.tdwg.org/terms/#dwc:disposition                                                        |
|:-------------|:--------------------------------------------------------------------------------------------------|
|Definição     |O estado atual de um espécime em relação à coleção identificada em collectioncode ou collectionid. |
|Domínio       |in collection &#124; missing &#124; voucher elsewhere &#124; duplicates elsewhere                  |
|Exemplos      |                                                                                                   |


---

#### [associatedMedia](https://github.com/sibbr/DarwinCoreBrasil/issues/39)


|Identificador |https://dwc.tdwg.org/terms/#dwc:associatedMedia                                                                                             |
|:-------------|:-------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de identificadores (publicação, identificador exclusivo global, url) de mídia associada à ocorrência.    |
|Domínio       |url de acesso a imagem                                                                                                                      |
|Exemplos      |https://image-server-ala.s3.amazonaws.com/Refauna/type_Coleoptera_Histeridae/type_Histeridae_Carcinops%20miserula/mnhnColeoptera00072_5.tif |


---

#### [associatedOccurrences](https://github.com/sibbr/DarwinCoreBrasil/issues/40)


|Identificador |https://dwc.tdwg.org/terms/#dwc:associatedOccurrences                                                                         |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de identificadores de outros registros de ocorrência e suas associações a esta ocorrência. |
|Domínio       |Parasita coletado de: "https://arctos.database.museum/guid/MSB:Mamm:215895?seid=950760"                                       |
|Exemplos      |                                                                                                                              |


---

#### [associatedReferences](https://github.com/sibbr/DarwinCoreBrasil/issues/41)


|Identificador |https://dwc.tdwg.org/terms/#dwc:associatedReferences                                                                                                                |
|:-------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de identificadores (publicação, referência bibliográfica, identificador único global, url) da literatura associada à ocorrência. |
|Domínio       |Christopher J. Conroy, Jennifer L. Neuwald. 2008. Phylogeographic study of the California vole, Microtus californicus Journal of Mammalogy, 89(3):755-767.          |
|Exemplos      |                                                                                                                                                                    |


---

#### [associatedSequences](https://github.com/sibbr/DarwinCoreBrasil/issues/42)


|Identificador |https://dwc.tdwg.org/terms/#dwc:associatedSequences                                                                                                               |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de identificadores (publicação, identificador único global, url) de informações de sequência genética associadas à ocorrência. |
|Domínio       |                                                                                                                                                                  |
|Exemplos      |                                                                                                                                                                  |


---

#### [associatedTaxa](https://github.com/sibbr/DarwinCoreBrasil/issues/43)


|Identificador |https://dwc.tdwg.org/terms/#dwc:associatedTaxa                                                                              |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de identificadores ou nomes de táxons e as associações desta ocorrência a cada um deles. |
|Domínio       |Predador de:"Apis mellifera"                                                                                                |
|Exemplos      |                                                                                                                            |


---

#### [otherCatalogNumbers](https://github.com/sibbr/DarwinCoreBrasil/issues/44)


|Identificador |https://dwc.tdwg.org/terms/#dwc:otherCatalogNumbers                                                                                                                                                                                                 |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de números de catálogo totalmente qualificados anteriores ou alternativos ou outros identificadores usados por humanos para a mesma ocorrência, seja no atual ou em qualquer outro conjunto de dados ou coleção. |
|Domínio       |FMNH:Mammal:1234                                                                                                                                                                                                                                    |
|Exemplos      |                                                                                                                                                                                                                                                    |


---

#### [occurrenceRemarks](https://github.com/sibbr/DarwinCoreBrasil/issues/45)


|Identificador |https://dwc.tdwg.org/terms/#dwc:occurrenceRemarks                                                       |
|:-------------|:-------------------------------------------------------------------------------------------------------|
|Definição     |Comentários ou notas sobre a ocorrência.                                                                |
|Domínio       |Encontrado morto &#124; Atropelado &#124; Hora da coleta                                                |
|Exemplos      |zoologia: Buscar: Data resource: Coleção de Aves da Unisinos &#124; Registro de ocorrência &#124; SiBBr |


---

### Organism


#### [organismID](https://github.com/sibbr/DarwinCoreBrasil/issues/46)


|Identificador |https://dwc.tdwg.org/terms/#dwc:organismID                                                                                                                                                                      |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um identificador para a instância do organismo (em oposição a um registro digital específico do organismo). Pode ser um identificador global exclusivo ou um identificador específico para o conjunto de dados. |
|Domínio       |http://arctos.database.museum/guid/WNMU:Mamm:1249                                                                                                                                                               |
|Exemplos      |                                                                                                                                                                                                                |


---

#### [organismName](https://github.com/sibbr/DarwinCoreBrasil/issues/47)


|Identificador |https://dwc.tdwg.org/terms/#dwc:organismName                         |
|:-------------|:--------------------------------------------------------------------|
|Definição     |Um nome textual ou rótulo atribuído a uma instância de um organismo. |
|Domínio       |J Pod &#124; Huberta                                                 |
|Exemplos      |                                                                     |


---

#### [organismScope](https://github.com/sibbr/DarwinCoreBrasil/issues/48)


|Identificador |https://dwc.tdwg.org/terms/#dwc:organismScope                                                                                                                                               |
|:-------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma descrição do tipo de instância de organismo. Pode ser usado para indicar se a instância de organismo representa um organismo discreto ou se representa um tipo particular de agregação. |
|Domínio       |Vírus &#124; Clone &#124; Colônia &#124; Zooplancton                                                                                                                                        |
|Exemplos      |                                                                                                                                                                                            |


---

#### [associatedOrganisms](https://github.com/sibbr/DarwinCoreBrasil/issues/49)


|Identificador |https://dwc.tdwg.org/terms/#dwc:associatedOrganisms                                                                          |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de identificadores de outros organismos e as associações deste organismo a cada um deles. |
|Domínio       |Pai/Mãe de: "http://arctos.database.museum/guid/MSB:Mamm:196208"                                                             |
|Exemplos      |                                                                                                                             |


---

#### [previousIdentifications](https://github.com/sibbr/DarwinCoreBrasil/issues/50)


|Identificador |https://dwc.tdwg.org/terms/#dwc:previousIdentifications                                                                                                     |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de atribuições anteriores de nomes ao organismo.                                                                         |
|Domínio       |Anthus sp., identificado em campo por G. Iglesias &#124; Anthus correndera, identificação especializada por C. Cicero em 12/02/2009 com base em morfologia. |
|Exemplos      |                                                                                                                                                            |


---

#### [organismRemarks](https://github.com/sibbr/DarwinCoreBrasil/issues/51)


|Identificador |https://dwc.tdwg.org/terms/#dwc:organismRemarks   |
|:-------------|:-------------------------------------------------|
|Definição     |Comentários ou notas sobre a instância organismo. |
|Domínio       |Um de uma ninhada de seis                         |
|Exemplos      |                                                  |


---

### MaterialSample


#### [MaterialSampleID](https://github.com/sibbr/DarwinCoreBrasil/issues/52)


|Identificador |https://dwc.tdwg.org/terms/#materialsample                                                                                                                                           |
|:-------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um resultado físico de um evento de amostragem (ou subamostragem). Em coleções biológicas, a amostra de material é tipicamente coletada, e preservada ou processada destrutivamente. |
|Domínio       |                                                                                                                                                                                     |
|Exemplos      |                                                                                                                                                                                     |


---

### Event


#### [eventID](https://github.com/sibbr/DarwinCoreBrasil/issues/53)


|Identificador |https://dwc.tdwg.org/terms/#dwc:eventID                                                                                                                                                                             |
|:-------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um identificador para o conjunto de informações associadas a um evento (algo que ocorre em um local e horário). Pode ser um identificador exclusivo global ou um identificador específico para o conjunto de dados. |
|Domínio       |                                                                                                                                                                                                                    |
|Exemplos      |para zoologia: https://ala-hub.sibbr.gov.br/ala-hub/occurrences/f8bd0b2d-39be-471f-b299-d4d3184c5963                                                                                                                |


---

#### [parentEventID](https://github.com/sibbr/DarwinCoreBrasil/issues/54)


|Identificador |https://dwc.tdwg.org/terms/#dwc:parentEventID                                              |
|:-------------|:------------------------------------------------------------------------------------------|
|Definição     |Um identificador para o evento mais amplo que agrupa este e potencialmente outros eventos. |
|Domínio       |                                                                                           |
|Exemplos      |                                                                                           |


---

#### [eventDate](https://github.com/sibbr/DarwinCoreBrasil/issues/55)


|Identificador |https://dwc.tdwg.org/terms/#dwc:eventDate                                                                                                                                              |
|:-------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |A data-hora ou o intervalo durante o qual um evento ocorreu. Para ocorrências, essa é a data-hora em que o evento foi registrado. Não adequado para um tempo em um contexto geológico. |
|Domínio       |AAAA-MM-DD                                                                                                                                                                             |
|Exemplos      |                                                                                                                                                                                       |


---

#### [eventTime](https://github.com/sibbr/DarwinCoreBrasil/issues/56)


|Identificador |https://dwc.tdwg.org/terms/#dwc:eventTime              |
|:-------------|:------------------------------------------------------|
|Definição     |O tempo ou intervalo durante o qual um evento ocorreu. |
|Domínio       |ISO 8601-1:2019                                        |
|Exemplos      |                                                       |


---

#### [startDayOfYear](https://github.com/sibbr/DarwinCoreBrasil/issues/57)


|Identificador |https://dwc.tdwg.org/terms/#dwc:startDayOfYear                                                                                                       |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O primeiro dia inteiro do ano em que o evento ocorreu (1 para 1º de janeiro, 365 para 31 de dezembro, exceto em um ano bissexto, caso em que é 366). |
|Domínio       |1 (1 de janeiro) &#124; 366 (31 de dezembro)                                                                                                         |
|Exemplos      |                                                                                                                                                     |


---

#### [endDayOfYear](https://github.com/sibbr/DarwinCoreBrasil/issues/58)


|Identificador |https://dwc.tdwg.org/terms/#dwc:endDayOfYear                                                                                                       |
|:-------------|:--------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O último dia inteiro do ano em que o evento ocorreu (1 para 1º de janeiro, 365 para 31 de dezembro, exceto em um ano bissexto, caso em que é 366). |
|Domínio       |1 (1 de janeiro) &#124; 366 (31 de dezembro)                                                                                                       |
|Exemplos      |                                                                                                                                                   |


---

#### [year](https://github.com/sibbr/DarwinCoreBrasil/issues/59)


|Identificador |https://dwc.tdwg.org/terms/#dwc:year             |
|:-------------|:------------------------------------------------|
|Definição     |O ano de quatro dígitos em que o evento ocorreu. |
|Domínio       |AAAA                                             |
|Exemplos      |                                                 |


---

#### [month](https://github.com/sibbr/DarwinCoreBrasil/issues/60)


|Identificador |https://dwc.tdwg.org/terms/#dwc:month  |
|:-------------|:--------------------------------------|
|Definição     |O mês inteiro em que o evento ocorreu. |
|Domínio       |MM                                     |
|Exemplos      |                                       |


---

#### [day](https://github.com/sibbr/DarwinCoreBrasil/issues/61)


|Identificador |https://dwc.tdwg.org/terms/#dwc:day    |
|:-------------|:--------------------------------------|
|Definição     |O dia inteiro em que o evento ocorreu. |
|Domínio       |DD                                     |
|Exemplos      |                                       |


---

#### [verbatimEventDate](https://github.com/sibbr/DarwinCoreBrasil/issues/62)


|Identificador |https://dwc.tdwg.org/terms/#dwc:verbatimEventDate                               |
|:-------------|:-------------------------------------------------------------------------------|
|Definição     |A representação original literal das informações de data e hora de um evento.   |
|Domínio       |Data como estava escrito na planilha original antes de padronizar em DarwinCore |
|Exemplos      |                                                                                |


---

#### [habitat](https://github.com/sibbr/DarwinCoreBrasil/issues/63)


|Identificador |https://dwc.tdwg.org/terms/#dwc:habitat                        |
|:-------------|:--------------------------------------------------------------|
|Definição     |Uma categoria ou descrição do habitat em que o evento ocorreu. |
|Domínio       |Mata Atlântica &#124; Cerrado &#124; Pantanal                  |
|Exemplos      |                                                               |


---

#### [samplingProtocol](https://github.com/sibbr/DarwinCoreBrasil/issues/64)


|Identificador |https://dwc.tdwg.org/terms/#dwc:samplingProtocol                                                                                                                                                                                                                                                                                                                                 |
|:-------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Os nomes, referências ou descrições dos métodos ou protocolos usados durante um evento.                                                                                                                                                                                                                                                                                          |
|Domínio       |RAPELD&#124; Parcelas &#124; TSBF &#124; Transectos                                                                                                                                                                                                                                                                                                                              |
|Exemplos      |botânica: Registro: BR:MG:Conexão Mata Atlântica:2021:Flora:20 &#124; Registro de ocorrência &#124; SiBBr / zoologia: https://ipt.sibbr.gov.br/sibbr/resource?r=soil_macrofauna_clasen / zoologia: https://ala-hub.sibbr.gov.br/ala-hub/occurrences/8dac4377-385c-4244-850a-74f122b353e4 / https://ala-hub.sibbr.gov.br/ala-hub/occurrences/0fbb4244-a111-42d9-b52a-269c92529d31 |


---

#### [sampleSizeValue](https://github.com/sibbr/DarwinCoreBrasil/issues/65)


|Identificador |https://dwc.tdwg.org/terms/#dwc:sampleSizeValue                                                                                         |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um valor numérico para uma medida do tamanho (duração do tempo, comprimento, área ou volume) de uma amostra em um evento de amostragem. |
|Domínio       |625                                                                                                                                     |
|Exemplos      |zoologia: https://ipt.sibbr.gov.br/sibbr/resource?r=soil_macrofauna_clasen                                                              |


---

#### [sampleSizeUnit](https://github.com/sibbr/DarwinCoreBrasil/issues/66)


|Identificador |https://dwc.tdwg.org/terms/#dwc:sampleSizeUnit                                                                                              |
|:-------------|:-------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |A unidade de medida do tamanho (duração do tempo, comprimento, área ou volume) de uma amostra em um evento de amostragem.                   |
|Domínio       |Minutos &#124; Hora&#124; Dia &#124; Metros &#124; Quilômetros &#124; Metros quadrados                                                      |
|Exemplos      |zoologia: Soil macrofauna communities in various land use systems in Canoinhas and Três Barras, Santa Catarina state, Brazil (sibbr.gov.br) |


---

#### [samplingEffort](https://github.com/sibbr/DarwinCoreBrasil/issues/67)


|Identificador |https://dwc.tdwg.org/terms/#dwc:samplingEffort                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|:-------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |A quantidade de esforço despendido durante um evento.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|Domínio       |Grades de amostragem &#124; Pitfall &#124; 50x50m &#124; Busca ativa &#124; Armadilha fotográfica &#124; Encontros ocasionais &#124; Registro Auditivo em Transectos                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|Exemplos      |Registro: BR:MG:Conexão Mata Atlântica:2022:Entomofauna:1 &#124; Registro de ocorrência &#124; SiBBr / zoologia: https://ala-hub.sibbr.gov.br/ala-hub/occurrences/49d1073b-d9ff-458c-9817-6dc93b837702 / botânica: https://www.researchgate.net/publication/267833419_MANUAL_PARA_O_MONITORAMENTO_DE_PARCELAS_PERMANENTES_NOS_BIOMAS_CERRADO_E_PANTANAL / zoologia: https://idoc.pub/documents/biologia-da-conservaao-e-manejo-da-vida-silvestrecullenrudyrudranevalladare-1pdf-d4pqv821zdnp // animais terrestres: https://www.gov.br/icmbio/pt-br/assuntos/monitoramento/gestao-da-informacao/biblioteca/programas-de-monitoramento-de-ambientes-continentais/protocolo_mamiferos-caatinga.pdf // répteis: https://www.gov.br/icmbio/pt-br/assuntos/monitoramento/gestao-da-informacao/biblioteca/programas-de-monitoramento-de-ambientes-continentais/protocolo_monitoramento_de_squamata-_ran-1.pdf |


---

#### [fieldNotes](https://github.com/sibbr/DarwinCoreBrasil/issues/68)


|Identificador |https://dwc.tdwg.org/terms/#dwc:fieldNotes                                                                                                |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um de a) um indicador da existência de, b) uma referência a (publicação, uri), ou c) o texto de anotações feitas no campo sobre o evento. |
|Domínio       |                                                                                                                                          |
|Exemplos      |                                                                                                                                          |


---

#### [eventRemarks](https://github.com/sibbr/DarwinCoreBrasil/issues/69)


|Identificador |https://dwc.tdwg.org/terms/#dwc:eventRemarks                                                                                                                                                                               |
|:-------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Comentários ou notas sobre o evento.                                                                                                                                                                                       |
|Domínio       |Época chuvosa &#124; Época seca &#124; Tempo pós queimada                                                                                                                                                                  |
|Exemplos      |botânica: Registro: br:ppbio:comcerrado:chapadadosguimarães:asteraceae:B Jtempopósqueima5/A20205 &#124; Registro de ocorrência &#124; SiBBr / zoologia: https://ipt.sibbr.gov.br/sibbr/resource?r=soil_macrofauna_clasen / |


---

### Location


#### [locationID](https://github.com/sibbr/DarwinCoreBrasil/issues/70)


|Identificador |https://dwc.tdwg.org/terms/#dwc:locationID                                                                                                                                                                 |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um identificador para o conjunto de informações de localização (dados associados a dcterms: location). Pode ser um identificador exclusivo global ou um identificador específico para o conjunto de dados. |
|Domínio       |                                                                                                                                                                                                           |
|Exemplos      |                                                                                                                                                                                                           |


---

#### [higherGeography](https://github.com/sibbr/DarwinCoreBrasil/issues/71)


|Identificador |https://dwc.tdwg.org/terms/#dwc:higherGeography                                                                                 |
|:-------------|:-------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de nomes geográficos menos específicos do que as informações capturadas no termo localidade. |
|Domínio       |Oceano Atlântico Norte &#124; Argentina &#124; América do Sul                                                                   |
|Exemplos      |                                                                                                                                |


---

#### [continent](https://github.com/sibbr/DarwinCoreBrasil/issues/72)


|Identificador |https://dwc.tdwg.org/terms/#dwc:continent                                                                  |
|:-------------|:----------------------------------------------------------------------------------------------------------|
|Definição     |O nome do continente em que a localização ocorre.                                                          |
|Domínio       |Africa &#124; Antartica &#124; Asia &#124; Europe &#124; North America &#124; Oceania &#124; South America |
|Exemplos      |                                                                                                           |


---

#### [waterBody](https://github.com/sibbr/DarwinCoreBrasil/issues/73)


|Identificador |https://dwc.tdwg.org/terms/#dwc:waterBody     |
|:-------------|:---------------------------------------------|
|Definição     |O nome do corpo d'água em que ocorre o local. |
|Domínio       |Oceano &#124; Rio &#124; Lago &#124; Mar      |
|Exemplos      |                                              |


---

#### [islandGroup](https://github.com/sibbr/DarwinCoreBrasil/issues/74)


|Identificador |https://dwc.tdwg.org/terms/#dwc:islandGroup           |
|:-------------|:-----------------------------------------------------|
|Definição     |O nome do grupo de ilhas em que a localização ocorre. |
|Domínio       |Conjunto de ilhas                                     |
|Exemplos      |                                                      |


---

#### [island](https://github.com/sibbr/DarwinCoreBrasil/issues/76)


|Identificador |https://dwc.tdwg.org/terms/#dwc:island               |
|:-------------|:----------------------------------------------------|
|Definição     |O nome da ilha ou área perto da qual o local ocorre. |
|Domínio       |Ilha                                                 |
|Exemplos      |                                                     |


---

#### [country](https://github.com/sibbr/DarwinCoreBrasil/issues/77)


|Identificador |https://dwc.tdwg.org/terms/#dwc:country                                      |
|:-------------|:----------------------------------------------------------------------------|
|Definição     |O nome do país ou da principal unidade administrativa em que o local ocorre. |
|Domínio       |Brasil                                                                       |
|Exemplos      |                                                                             |


---

#### [countryCode](https://github.com/sibbr/DarwinCoreBrasil/issues/78)


|Identificador |https://dwc.tdwg.org/terms/#dwc:countryCode        |
|:-------------|:--------------------------------------------------|
|Definição     |O código padrão para o país em que o local ocorre. |
|Domínio       |BR                                                 |
|Exemplos      |                                                   |


---

#### [stateProvince](https://github.com/sibbr/DarwinCoreBrasil/issues/79)


|Identificador |https://dwc.tdwg.org/terms/#dwc:stateProvince                                                                                                    |
|:-------------|:------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome da próxima região administrativa menor do que o país (estado, província, cantão, departamento, região, etc.) em que a localização ocorre. |
|Domínio       |Distrito Federal &#124; Espírito Santo &#124; São Paulo &#124; Rio de Janeiro                                                                    |
|Exemplos      |                                                                                                                                                 |


---

#### [county](https://github.com/sibbr/DarwinCoreBrasil/issues/80)


|Identificador |https://dwc.tdwg.org/terms/#dwc:county                                                                                                                               |
|:-------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome completo e não abreviado da próxima região administrativa menor do que o estado província (condado, condado, departamento, etc.) em que a localização ocorre. |
|Domínio       |Guiricema                                                                                                                                                            |
|Exemplos      |https://ala-hub.sibbr.gov.br/ala-hub/occurrences/cc66804e-8327-45a4-8690-b61061452736                                                                                |


---

#### [locality](https://github.com/sibbr/DarwinCoreBrasil/issues/82)


|Identificador |https://dwc.tdwg.org/terms/#dwc:locality                                              |
|:-------------|:-------------------------------------------------------------------------------------|
|Definição     |A descrição específica do local.                                                      |
|Domínio       |Lago Calado, margem esquerda Rio Solimões                                             |
|Exemplos      |https://ala-hub.sibbr.gov.br/ala-hub/occurrences/41e3ad42-a052-40b6-95dd-8f5001a312bc |


---

#### [verbatimLocality](https://github.com/sibbr/DarwinCoreBrasil/issues/83)


|Identificador |https://dwc.tdwg.org/terms/#dwc:verbatimLocality         |
|:-------------|:--------------------------------------------------------|
|Definição     |A descrição textual original do local.                   |
|Domínio       |Km 3 da estrada BR-193 &#124; Ponto 2 do Rio Doce &#124; |
|Exemplos      |                                                         |


---

#### [minimumElevationInMeters](https://github.com/sibbr/DarwinCoreBrasil/issues/84)


|Identificador |https://dwc.tdwg.org/terms/#dwc:minimumElevationInMeters                                        |
|:-------------|:-----------------------------------------------------------------------------------------------|
|Definição     |O limite inferior da faixa de elevação (altitude, geralmente acima do nível do mar), em metros. |
|Domínio       |- 100 &#124; 802                                                                                |
|Exemplos      |                                                                                                |


---

#### [maximumElevationInMeters](https://github.com/sibbr/DarwinCoreBrasil/issues/85)


|Identificador |https://dwc.tdwg.org/terms/#dwc:maximumElevationInMeters                                        |
|:-------------|:-----------------------------------------------------------------------------------------------|
|Definição     |O limite superior da faixa de elevação (altitude, geralmente acima do nível do mar), em metros. |
|Domínio       |- 205 &#124; 1236                                                                               |
|Exemplos      |                                                                                                |


---

#### [verbatimElevation](https://github.com/sibbr/DarwinCoreBrasil/issues/86)


|Identificador |https://dwc.tdwg.org/terms/#dwc:verbatimElevation                                       |
|:-------------|:---------------------------------------------------------------------------------------|
|Definição     |A descrição original da elevação (altitude, geralmente acima do nível do mar) do local. |
|Domínio       |100 - 200m                                                                              |
|Exemplos      |                                                                                        |


---

#### [verticalDatum](https://github.com/sibbr/DarwinCoreBrasil/issues/87)


|Identificador |https://dwc.tdwg.org/terms/#dwc:verticalDatum                                                      |
|:-------------|:--------------------------------------------------------------------------------------------------|
|Definição     |O dado vertical usado como referência sobre o qual os valores nos termos de elevação são baseados. |
|Domínio       |EGM84 &#124; EGM96 &#124; EGM2008                                                                  |
|Exemplos      |                                                                                                   |


---

#### [minimumDepthInMeters](https://github.com/sibbr/DarwinCoreBrasil/issues/88)


|Identificador |https://dwc.tdwg.org/terms/#dwc:minimumDepthInMeters                                     |
|:-------------|:----------------------------------------------------------------------------------------|
|Definição     |A menor profundidade de uma faixa de profundidade abaixo da superfície local, em metros. |
|Domínio       |0 &#124; 100                                                                             |
|Exemplos      |                                                                                         |


---

#### [maximumDepthInMeters](https://github.com/sibbr/DarwinCoreBrasil/issues/89)


|Identificador |https://dwc.tdwg.org/terms/#dwc:maximumDepthInMeters                                     |
|:-------------|:----------------------------------------------------------------------------------------|
|Definição     |A maior profundidade de uma faixa de profundidade abaixo da superfície local, em metros. |
|Domínio       |0 &#124; 200                                                                             |
|Exemplos      |                                                                                         |


---

#### [verbatimDepth](https://github.com/sibbr/DarwinCoreBrasil/issues/90)


|Identificador |https://dwc.tdwg.org/terms/#dwc:verbatimDepth                    |
|:-------------|:----------------------------------------------------------------|
|Definição     |A descrição original da profundidade abaixo da superfície local. |
|Domínio       |100 - 200m                                                       |
|Exemplos      |                                                                 |


---

#### [minimumDistanceAboveSurfaceInMeters](https://github.com/sibbr/DarwinCoreBrasil/issues/92)


|Identificador |https://dwc.tdwg.org/terms/#dwc:minimumDistanceAboveSurfaceInMeters                                                                                                                                                                                                                                                                                                                                |
|:-------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |A menor distância em uma faixa de distância de uma superfície de referência na direção vertical, em metros. Use valores positivos para locais acima da superfície, valores negativos para locais abaixo. Se forem dadas medidas de profundidade, a superfície de referência é a localização dada pela profundidade, caso contrário, a superfície de referência é a localização dada pela elevação. |
|Domínio       |- 1.5 (abaixo da superfície) &#124; 4.2 (acima da superfície)                                                                                                                                                                                                                                                                                                                                      |
|Exemplos      |                                                                                                                                                                                                                                                                                                                                                                                                   |


---

#### [maximumDistanceAboveSurfaceInMeters](https://github.com/sibbr/DarwinCoreBrasil/issues/94)


|Identificador |https://dwc.tdwg.org/terms/#dwc:maximumDistanceAboveSurfaceInMeters                                                                                                                                                                                                                                                                                                                                |
|:-------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |A maior distância em uma faixa de distância de uma superfície de referência na direção vertical, em metros. Use valores positivos para locais acima da superfície, valores negativos para locais abaixo. Se forem dadas medidas de profundidade, a superfície de referência é a localização dada pela profundidade, caso contrário, a superfície de referência é a localização dada pela elevação. |
|Domínio       |- 1.5 (abaixo da superfície) &#124; 4.2 (acima da superfície)                                                                                                                                                                                                                                                                                                                                      |
|Exemplos      |                                                                                                                                                                                                                                                                                                                                                                                                   |


---

#### [locationAccordingTo](https://github.com/sibbr/DarwinCoreBrasil/issues/95)


|Identificador |https://dwc.tdwg.org/terms/#dwc:locationAccordingTo                                                                                 |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Informações sobre a fonte dessas informações de localização. Pode ser uma publicação (gazeta), instituição ou equipe de indivíduos. |
|Domínio       |GADM                                                                                                                                |
|Exemplos      |                                                                                                                                    |


---

#### [locationRemarks](https://github.com/sibbr/DarwinCoreBrasil/issues/96)


|Identificador |https://dwc.tdwg.org/terms/#dwc:locationRemarks                                                                                                                                                                                                       |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Comentários ou notas sobre o local.                                                                                                                                                                                                                   |
|Domínio       |Vazante do córrego&#124; MIG FLORA FME1 (número da parcela) &#124; Rodovia MT 305                                                                                                                                                                     |
|Exemplos      |zoologia: https://ipt.sibbr.gov.br/sibbr/resource?r=zufmsamp e https://ala-hub.sibbr.gov.br/ala-hub/occurrences/ea8ec403-27ad-4b6a-a633-ab1b92a21ce4/ botânica: https://ala-hub.sibbr.gov.br/ala-hub/occurrences/0fbb4244-a111-42d9-b52a-269c92529d31 |


---

#### [decimalLatitude](https://github.com/sibbr/DarwinCoreBrasil/issues/97)


|Identificador |https://dwc.tdwg.org/terms/#dwc:decimalLatitude                                                                                                                                                                                                                                            |
|:-------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |A latitude geográfica (em graus decimais, usando o sistema de referência espacial dado em geodésico datum) do centro geográfico de uma localidade. Os valores positivos estão ao norte da linha do equador, os negativos estão ao sul dela. Os valores jurídicos situam-se entre -90 e 90. |
|Domínio       |-8.4608539999999994                                                                                                                                                                                                                                                                        |
|Exemplos      |https://ala-hub.sibbr.gov.br/ala-hub/occurrences/ea1bdcbe-d6a8-41df-9d7f-e3cbab5ff8e1                                                                                                                                                                                                      |


---

#### [decimalLongitude](https://github.com/sibbr/DarwinCoreBrasil/issues/98)


|Identificador |https://dwc.tdwg.org/terms/#dwc:decimalLongitude                                                                                                                                                                                                                                                            |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |A longitude geográfica (em graus decimais, usando o sistema de referência espacial dado em geodésico datum) do centro geográfico de uma localidade. Os valores positivos estão a leste do meridiano de greenwich, os valores negativos estão a oeste dele. Os valores jurídicos situam-se entre -180 e 180. |
|Domínio       |-37.305917000000001                                                                                                                                                                                                                                                                                         |
|Exemplos      |https://ala-hub.sibbr.gov.br/ala-hub/occurrences/ea1bdcbe-d6a8-41df-9d7f-e3cbab5ff8e1                                                                                                                                                                                                                       |


---

#### [geodeticDatum](https://github.com/sibbr/DarwinCoreBrasil/issues/99)


|Identificador |https://dwc.tdwg.org/terms/#dwc:geodeticDatum                                                                                                                                 |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O elipsoide, dado geodésico ou sistema de referência espacial (srs) sobre o qual as coordenadas geográficas dadas em latitude decimal e longitude decimal como baseadas.      |
|Domínio       |EPSG:4326 &#124; WGS84                                                                                                                                                        |
|Exemplos      |https://ala-hub.sibbr.gov.br/ala-hub/occurrences/ea1bdcbe-d6a8-41df-9d7f-e3cbab5ff8e1 e https://ala-hub.sibbr.gov.br/ala-hub/occurrences/14119ff6-6826-48c4-ae85-fb6122c8097d |


---

#### [coordinateUncertaintyInMeters](https://github.com/sibbr/DarwinCoreBrasil/issues/100)


|Identificador |https://dwc.tdwg.org/terms/#dwc:coordinateUncertaintyInMeters                                                                                                                                                                                                                                                    |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |A distância horizontal (em metros) da latitude decimal e longitude decimal dadas, descrevendo o menor círculo que contém todo o local. Deixe o valor vazio se a incerteza for desconhecida, não puder ser estimada ou não for aplicável (porque não há coordenadas). Zero não é um valor válido para este termo. |
|Domínio       |30 (limite mínimo razoável  ou após 01/05/2000 de uma leitura de GPS em boas condições, se a precisão real não foi registrada na época                                                                                                                                                                           |
|Exemplos      |                                                                                                                                                                                                                                                                                                                 |


---

#### [coordinatePrecision](https://github.com/sibbr/DarwinCoreBrasil/issues/101)


|Identificador |https://dwc.tdwg.org/terms/#dwc:coordinatePrecision                                                                                                          |
|:-------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma representação decimal da precisão das coordenadas dadas na latitude decimal e longitude decimal.                                                         |
|Domínio       |0.0001 (limite normal de GPS para graus decimais) &#124; 0.000278 (segundo mais próximo) &#124; 0.01667 (minuto mais próximo) &#124; 1.0 (grau mais próximo) |
|Exemplos      |                                                                                                                                                             |


---

#### [pointRadiusSpatialFit](https://github.com/sibbr/DarwinCoreBrasil/issues/102)


|Identificador |https://dwc.tdwg.org/terms/#dwc:pointRadiusSpatialFit                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |A razão entre a área do raio do ponto (decimallatitude, decimallongitude, coordinateuncertaintyinmeters) e a área da representação espacial verdadeira (original ou mais específica) da localização. Os valores legais são 0, maior ou igual a 1, ou indefinidos. Um valor de 1 é uma correspondência exata ou 100% de sobreposição. Um valor de 0 deve ser usado se o raio de ponto fornecido não contiver completamente a representação original. O pontoradiusspatialfit é indefinido (e deve ser deixado vazio) se a representação original é um ponto sem incerteza e a georreferência dada não é esse mesmo ponto (sem incerteza). Se a georreferência original e dada forem o mesmo ponto, o pontoradiusspatialfit será 1. |
|Domínio       |0 &#124; 1 &#124; 1.5708                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|Exemplos      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |


---

#### [verbatimCoordinates](https://github.com/sibbr/DarwinCoreBrasil/issues/103)


|Identificador |https://dwc.tdwg.org/terms/#dwc:verbatimCoordinates                                                                                                                                                                                                                                       |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |As coordenadas espaciais originais literais do lugar. O elipsoide de coordenadas, geodésico datum, ou sistema de referência espacial (srs) completo para essas coordenadas deve ser armazenado em verbatimsrs e o sistema de coordenadas deve ser armazenado em verbatimcoordinatesystem. |
|Domínio       |41 05 54S 121 05 34W                                                                                                                                                                                                                                                                      |
|Exemplos      |                                                                                                                                                                                                                                                                                          |


---

#### [verbatimLatitude](https://github.com/sibbr/DarwinCoreBrasil/issues/104)


|Identificador |https://dwc.tdwg.org/terms/#dwc:verbatimLatitude                                                                                                                                                                                                                          |
|:-------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |A latitude original literal do lugar. O elipsoide de coordenadas, geodésico datum, ou sistema de referência espacial (srs) completo para essas coordenadas deve ser armazenado em verbatimsrs e o sistema de coordenadas deve ser armazenado em verbatimcoordinatesystem. |
|Domínio       |41 05 54.03S                                                                                                                                                                                                                                                              |
|Exemplos      |                                                                                                                                                                                                                                                                          |


---

#### [verbatimLongitude](https://github.com/sibbr/DarwinCoreBrasil/issues/105)


|Identificador |https://dwc.tdwg.org/terms/#dwc:verbatimLongitude                                                                                                                                                                                                                          |
|:-------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |A longitude original literal do lugar. O elipsoide de coordenadas, geodésico datum, ou sistema de referência espacial (srs) completo para essas coordenadas deve ser armazenado em verbatimsrs e o sistema de coordenadas deve ser armazenado em verbatimcoordinatesystem. |
|Domínio       |121d 10' 34" W                                                                                                                                                                                                                                                             |
|Exemplos      |                                                                                                                                                                                                                                                                           |


---

#### [verbatimCoordinateSystem](https://github.com/sibbr/DarwinCoreBrasil/issues/106)


|Identificador |https://dwc.tdwg.org/terms/#dwc:verbatimCoordinateSystem                                                   |
|:-------------|:----------------------------------------------------------------------------------------------------------|
|Definição     |O formato de coordenadas para o verbatimlatitude e verbatimlongitude ou o verbatimcoordinates do location. |
|Domínio       |Graus decimais &#124; Graus minutos decimais &#124; Graus segundos decimais &#124; UTM                     |
|Exemplos      |                                                                                                           |


---

#### [verbatimSRS](https://github.com/sibbr/DarwinCoreBrasil/issues/107)


|Identificador |https://dwc.tdwg.org/terms/#dwc:verbatimSRS                                                                                                                                    |
|:-------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O elipsoide, dado geodésico ou sistema de referência espacial (srs) no qual as coordenadas dadas em verbatimlatitude e verbatimlongitude, ou verbatimcoordinates são baseadas. |
|Domínio       |WGS84 &#124; EPSG: 4326                                                                                                                                                        |
|Exemplos      |                                                                                                                                                                               |


---

#### [footprintWKT](https://github.com/sibbr/DarwinCoreBrasil/issues/108)


|Identificador |https://dwc.tdwg.org/terms/#dwc:footprintWKT                                                                                                                                                                                                    |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma representação de texto conhecido (wkt) da forma (pegada, geometria) que define o local. Um local pode ter uma representação de raio de ponto (consulte decimallatitude) e uma representação de pegada, e eles podem diferir uns dos outros. |
|Domínio       |POLÍGONO ((10 20, 11 20, 11 21, 10 21, 10 20)) (a caixa delimitadora de um grau com cantos opostos em longitude=10, latitude=20 e longitude=11, latitude=21)                                                                                    |
|Exemplos      |                                                                                                                                                                                                                                                |


---

#### [footprintSRS](https://github.com/sibbr/DarwinCoreBrasil/issues/109)


|Identificador |https://dwc.tdwg.org/terms/#dwc:footprintSRS                                                                           |
|:-------------|:----------------------------------------------------------------------------------------------------------------------|
|Definição     |O elipsoide, dado geodésico ou sistema de referência espacial (srs) sobre o qual a geometria dada na pegada é baseada. |
|Domínio       |espg: 4326                                                                                                             |
|Exemplos      |                                                                                                                       |


---

#### [footprintSpatialFit](https://github.com/sibbr/DarwinCoreBrasil/issues/110)


|Identificador |https://dwc.tdwg.org/terms/#dwc:footprintSpatialFit                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |A razão entre a área da pegada (footprintwkt) e a área da representação espacial verdadeira (original ou mais específica) da localização. Os valores legais são 0, maior ou igual a 1, ou indefinidos. Um valor de 1 é uma correspondência exata ou 100% de sobreposição. Um valor de 0 deve ser usado se a pegada fornecida não contiver completamente a representação original. O footprintspatialfit é indefinido (e deve ser deixado vazio) se a representação original é um ponto sem incerteza e a georreferência dada não é esse mesmo ponto (sem incerteza). Se a georreferência original e a georreferenciada dada forem o mesmo ponto, a pegadaspatialfit será 1. |
|Domínio       |0 &#124; 1 &#124; 1.5708                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|Exemplos      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |


---

#### [georeferencedBy](https://github.com/sibbr/DarwinCoreBrasil/issues/111)


|Identificador |https://dwc.tdwg.org/terms/#dwc:georeferencedBy                                                                                                         |
|:-------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de nomes de pessoas, grupos ou organizações que determinaram a georreferência (representação espacial) para o local. |
|Domínio       |Janet Fang&#124; Kristina Yamamoto                                                                                                                      |
|Exemplos      |                                                                                                                                                        |


---

#### [georeferencedDate](https://github.com/sibbr/DarwinCoreBrasil/issues/112)


|Identificador |https://dwc.tdwg.org/terms/#dwc:georeferencedDate    |
|:-------------|:----------------------------------------------------|
|Definição     |A data em que o local foi georreferenciado.          |
|Domínio       |2009-02-20T08:40Z (20 de fevereiro de 2009 8:40 UTC) |
|Exemplos      |                                                     |


---

#### [georeferenceProtocol](https://github.com/sibbr/DarwinCoreBrasil/issues/113)


|Identificador |https://dwc.tdwg.org/terms/#dwc:georeferenceProtocol                                                        |
|:-------------|:-----------------------------------------------------------------------------------------------------------|
|Definição     |Uma descrição ou referência aos métodos usados para determinar a pegada espacial, coordenadas e incertezas. |
|Domínio       |                                                                                                            |
|Exemplos      |                                                                                                            |


---

#### [georeferenceSources](https://github.com/sibbr/DarwinCoreBrasil/issues/114)


|Identificador |https://dwc.tdwg.org/terms/#dwc:georeferenceSources                                                                                                                                                                          |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de mapas, gazetas ou outros recursos usados para georreferenciar a localização, descrita especificamente o suficiente para permitir que qualquer pessoa no futuro use os mesmos recursos. |
|Domínio       |Terrametrics 2008 no Google Earth                                                                                                                                                                                            |
|Exemplos      |                                                                                                                                                                                                                             |


---

#### [georeferenceRemarks](https://github.com/sibbr/DarwinCoreBrasil/issues/115)


|Identificador |https://dwc.tdwg.org/terms/#dwc:georeferenceRemarks                                                                                                                                           |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Notas ou comentários sobre a determinação da descrição espacial, explicitando pressupostos assumidos em adição ou oposição aos formalizados no método referido no protocolo georreferenciado. |
|Domínio       |Distância estimada pela estrada (Rodovia 101)                                                                                                                                                 |
|Exemplos      |                                                                                                                                                                                              |


---

### GeologicalContext


#### [geologicalContextID](https://github.com/sibbr/DarwinCoreBrasil/issues/116)


|Identificador |https://dwc.tdwg.org/terms/#dwc:geologicalContextID                               |
|:-------------|:---------------------------------------------------------------------------------|
|Definição     |Informações geológicas, como a estratigrafia, que qualificam uma região ou lugar. |
|Domínio       |                                                                                  |
|Exemplos      |                                                                                  |


---

#### [earliestEonOrLowestEonothem](https://github.com/sibbr/DarwinCoreBrasil/issues/117)


|Identificador |https://dwc.tdwg.org/terms/#dwc:earliestEonOrLowestEonothem                                                                                                                                                                         |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome completo do éon geocronológico mais antigo possível ou o eonotema cronoestratigráfica mais baixa ou o nome informal ("pré-cambriano") atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado |
|Domínio       |Fanerozoico &#124; Proterozoico                                                                                                                                                                                                     |
|Exemplos      |                                                                                                                                                                                                                                    |


---

#### [latestEonOrHighestEonothem](https://github.com/sibbr/DarwinCoreBrasil/issues/118)


|Identificador |https://dwc.tdwg.org/terms/#dwc:latestEonOrHighestEonothem                                                                                                                                                                  |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome completo do último éon geocronológico possível ou eonotema cronoestratigráfica mais alto ou o nome informal ("precambriano") atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado. |
|Domínio       |Fanerozoico &#124; Proterozoico                                                                                                                                                                                             |
|Exemplos      |                                                                                                                                                                                                                            |


---

#### [earliestEraOrLowestErathem](https://github.com/sibbr/DarwinCoreBrasil/issues/119)


|Identificador |https://dwc.tdwg.org/terms/#dwc:earliestEraOrLowestErathem                                                                                                                             |
|:-------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome completo da era geocronológica mais antiga possível ou da menor era cronoestratigráfica atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado. |
|Domínio       |Cenozoico &#124; Mezosoico                                                                                                                                                             |
|Exemplos      |                                                                                                                                                                                       |


---

#### [latestEraOrHighestErathem](https://github.com/sibbr/DarwinCoreBrasil/issues/120)


|Identificador |https://dwc.tdwg.org/terms/#dwc:latestEraOrHighestErathem                                                                                                                      |
|:-------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome completo da última era geocronológica possível ou maior era cronoestratigráfica atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado. |
|Domínio       |Cenozoico &#124; Mezosoico                                                                                                                                                     |
|Exemplos      |                                                                                                                                                                               |


---

#### [earliestPeriodOrLowestSystem](https://github.com/sibbr/DarwinCoreBrasil/issues/121)


|Identificador |https://dwc.tdwg.org/terms/#dwc:earliestPeriodOrLowestSystem                                                                                                                                     |
|:-------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome completo do período geocronológico mais antigo possível ou sistema cronoestratigráfico mais baixo atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado. |
|Domínio       |Neogene &#124; Terciário &#124; Quartenário                                                                                                                                                      |
|Exemplos      |                                                                                                                                                                                                 |


---

#### [earliestEpochOrLowestSeries](https://github.com/sibbr/DarwinCoreBrasil/issues/122)


|Identificador |https://dwc.tdwg.org/terms/#dwc:earliestEpochOrLowestSeries                                                                                                                                |
|:-------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome completo da época geocronológica mais antiga possível ou da menor série cronoestratigráfica atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado. |
|Domínio       |Holoceno &#124; Plestoceno                                                                                                                                                                 |
|Exemplos      |                                                                                                                                                                                           |


---

#### [latestEpochOrHighestSeries](https://github.com/sibbr/DarwinCoreBrasil/issues/123)


|Identificador |https://dwc.tdwg.org/terms/#dwc:latestEpochOrHighestSeries                                                                                                                         |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome completo da última época geocronológica possível ou maior série cronoestratigráfica atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado. |
|Domínio       |Holoceno &#124; Plestoceno                                                                                                                                                         |
|Exemplos      |                                                                                                                                                                                   |


---

#### [earliestAgeOrLowestStage](https://github.com/sibbr/DarwinCoreBrasil/issues/124)


|Identificador |https://dwc.tdwg.org/terms/#dwc:earliestAgeOrLowestStage                                                                                                                                       |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome completo da idade geocronológica mais antiga possível ou estágio cronoestratigráfico mais baixo atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado. |
|Domínio       |Atlântico &#124; Boreal                                                                                                                                                                        |
|Exemplos      |                                                                                                                                                                                               |


---

#### [latestAgeOrHighestStage](https://github.com/sibbr/DarwinCoreBrasil/issues/125)


|Identificador |https://dwc.tdwg.org/terms/#dwc:latestAgeOrHighestStage                                                                                                                                  |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome completo da última idade geocronológica possível ou estágio cronoestratigráfico mais alto atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado. |
|Domínio       |Atlântico &#124; Boreal                                                                                                                                                                  |
|Exemplos      |                                                                                                                                                                                         |


---

#### [lowestBiostratigraphicZone](https://github.com/sibbr/DarwinCoreBrasil/issues/126)


|Identificador |https://dwc.tdwg.org/terms/#dwc:lowestBiostratigraphicZone                                                                               |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Nome completo da zona geoestratigráfica mais baixa possível do horizonte estratigráfico a partir do qual o item catalogado foi coletado. |
|Domínio       |Maastrichtiano                                                                                                                           |
|Exemplos      |                                                                                                                                         |


---

#### [highestBiostratigraphicZone](https://github.com/sibbr/DarwinCoreBrasil/issues/127)


|Identificador |https://dwc.tdwg.org/terms/#dwc:highestBiostratigraphicZone                                                                             |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Nome completo da zona geoestratigráfica mais alta possível do horizonte estratigráfico a partir do qual o item catalogado foi coletado. |
|Domínio       |Blancan                                                                                                                                 |
|Exemplos      |                                                                                                                                        |


---

#### [lithostratigraphicTerms](https://github.com/sibbr/DarwinCoreBrasil/issues/128)


|Identificador |https://dwc.tdwg.org/terms/#dwc:lithostratigraphicTerms                                                 |
|:-------------|:-------------------------------------------------------------------------------------------------------|
|Definição     |A combinação de todos os nomes litoestratigráficos para a rocha da qual o item catalogado foi coletado. |
|Domínio       |Pleistoceno-Weichseliano                                                                                |
|Exemplos      |                                                                                                        |


---

#### [group](https://github.com/sibbr/DarwinCoreBrasil/issues/129)


|Identificador |https://dwc.tdwg.org/terms/#dwc:group                                               |
|:-------------|:-----------------------------------------------------------------------------------|
|Definição     |O nome completo do grupo litoestratigráfico do qual o item catalogado foi coletado. |
|Domínio       |Grupo Paranoá &#124; Grupo Bambui                                                   |
|Exemplos      |                                                                                    |


---

#### [formation](https://github.com/sibbr/DarwinCoreBrasil/issues/130)


|Identificador |https://dwc.tdwg.org/terms/#dwc:formation                                              |
|:-------------|:--------------------------------------------------------------------------------------|
|Definição     |O nome completo da formação litoestratigráfica da qual o item catalogado foi coletado. |
|Domínio       |Serra do Mar &#124; Serra da Mantiqueira                                               |
|Exemplos      |                                                                                       |


---

#### [member](https://github.com/sibbr/DarwinCoreBrasil/issues/131)


|Identificador |https://dwc.tdwg.org/terms/#dwc:member                                               |
|:-------------|:------------------------------------------------------------------------------------|
|Definição     |O nome completo do membro litoestratigráfico do qual o item catalogado foi coletado. |
|Domínio       |                                                                                     |
|Exemplos      |                                                                                     |


---

#### [bed](https://github.com/sibbr/DarwinCoreBrasil/issues/132)


|Identificador |https://dwc.tdwg.org/terms/#dwc:bed                                                 |
|:-------------|:-----------------------------------------------------------------------------------|
|Definição     |O nome completo do leito litoestratigráfico do qual o item catalogado foi coletado. |
|Domínio       |Fm. Ribeirão do Torto &#124; Fm. Ribeirão São Miguel                                |
|Exemplos      |                                                                                    |


---

### Identification


#### [identificationID](https://github.com/sibbr/DarwinCoreBrasil/issues/133)


|Identificador |https://dwc.tdwg.org/terms/#dwc:identificationID                                                                                                                                                                     |
|:-------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um identificador para a identificação (o conjunto de informações associadas à atribuição de um nome científico). Pode ser um identificador exclusivo global ou um identificador específico para o conjunto de dados. |
|Domínio       |9992                                                                                                                                                                                                                 |
|Exemplos      |                                                                                                                                                                                                                     |


---

#### [verbatimIdentification](https://github.com/sibbr/DarwinCoreBrasil/issues/134)


|Identificador |https://dwc.tdwg.org/terms/#dwc:verbatimIdentification                                                     |
|:-------------|:----------------------------------------------------------------------------------------------------------|
|Definição     |Uma cadeia de caracteres que representa a identificação taxonômica como ela apareceu no registro original. |
|Domínio       |Anser anser × Branta canadensis &#124; Pachyporidae? &#124; Aconitum pilipes × A. variegatum               |
|Exemplos      |                                                                                                           |


---

#### [identificationQualifier](https://github.com/sibbr/DarwinCoreBrasil/issues/135)


|Identificador |https://dwc.tdwg.org/terms/#dwc:identificationQualifier                                                             |
|:-------------|:-------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma breve frase ou um termo padrão ("cf.", "aff.") para expressar as dúvidas do determinante sobre a identificação. |
|Domínio       |cf. aff. &#124; sp. &#124; spp.                                                                                     |
|Exemplos      |                                                                                                                    |


---

#### [typeStatus](https://github.com/sibbr/DarwinCoreBrasil/issues/136)


|Identificador |https://dwc.tdwg.org/terms/#dwc:typeStatus                                                                                               |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de tipos nomenclaturais (status do tipo, nome científico tipificado, publicação) aplicada ao assunto. |
|Domínio       |Holótipo [originalNameUsage} &#124; Isótipo &#124; Síntipo &#124; Léctotipo &#124; Parátipo &#124; Neótipo &#124; Cótipo                 |
|Exemplos      |Buscar: Data resource: Base de dados de Coleoptera do MZUSP &#124; Registro de ocorrência &#124; SiBBr                                   |


---

#### [identifiedBy](https://github.com/sibbr/DarwinCoreBrasil/issues/137)


|Identificador |https://dwc.tdwg.org/terms/#dwc:identifiedBy                                                                                                                                                                                                                                                        |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de nomes de pessoas, grupos ou organizações que atribuíram o táxon ao assunto.                                                                                                                                                                                   |
|Domínio       |Maciel-Silva, A. As &#124; A.C Loss &#124; Barbosa, S.O                                                                                                                                                                                                                                             |
|Exemplos      |herbário: https://ala-hub.sibbr.gov.br/ala-hub/occurrences/03ba3a3e-5bfd-4e4a-a4e4-e1248e510a12 e https://ala-hub.sibbr.gov.br/ala-hub/occurrences/c7318d47-ca86-4041-8ba8-2a09dfd0b30c/ zoologia: https://ala-hub.sibbr.gov.br/ala-hub/occurrences/982e6bec-de01-4bfb-addd-6e55187215c4?lang=en_GB |


---

#### [identifiedByID](https://github.com/sibbr/DarwinCoreBrasil/issues/138)


|Identificador |https://dwc.tdwg.org/terms/#dwc:identifiedByID                                                                                                                |
|:-------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) do identificador global exclusivo da pessoa, pessoas, grupos ou organizações responsáveis por atribuir o táxon ao assunto. |
|Domínio       |                                                                                                                                                              |
|Exemplos      |                                                                                                                                                              |


---

#### [dateIdentified](https://github.com/sibbr/DarwinCoreBrasil/issues/139)


|Identificador |https://dwc.tdwg.org/terms/#dwc:dateIdentified                      |
|:-------------|:-------------------------------------------------------------------|
|Definição     |A data em que o sujeito foi determinado como representando o táxon. |
|Domínio       |AAAA-MM-DD                                                          |
|Exemplos      |                                                                    |


---

#### [identificationReferences](https://github.com/sibbr/DarwinCoreBrasil/issues/140)


|Identificador |https://dwc.tdwg.org/terms/#dwc:identificationReferences                                                                     |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de referências (publicação, identificador exclusivo global, url) usadas na identificação. |
|Domínio       |                                                                                                                             |
|Exemplos      |                                                                                                                             |


---

#### [identificationVerificationStatus](https://github.com/sibbr/DarwinCoreBrasil/issues/141)


|Identificador |https://dwc.tdwg.org/terms/#dwc:identificationVerificationStatus                               |
|:-------------|:----------------------------------------------------------------------------------------------|
|Definição     |Um indicador categórico do grau em que a identificação taxonômica foi verificada como correta. |
|Domínio       |                                                                                               |
|Exemplos      |                                                                                               |


---

#### [identificationRemarks](https://github.com/sibbr/DarwinCoreBrasil/issues/142)


|Identificador |https://dwc.tdwg.org/terms/#dwc:identificationRemarks |
|:-------------|:-----------------------------------------------------|
|Definição     |Comentários ou notas sobre a identificação.           |
|Domínio       |                                                      |
|Exemplos      |                                                      |


---

### Taxon


#### [taxonID](https://github.com/sibbr/DarwinCoreBrasil/issues/143)


|Identificador |https://dwc.tdwg.org/terms/#dwc:taxonID                                                                                                                                                         |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um identificador para o conjunto de informações do táxon (dados associados à classe taxon). Pode ser um identificador exclusivo global ou um identificador específico para o conjunto de dados. |
|Domínio       |32567                                                                                                                                                                                           |
|Exemplos      |                                                                                                                                                                                                |


---

#### [scientificNameID](https://github.com/sibbr/DarwinCoreBrasil/issues/144)


|Identificador |https://dwc.tdwg.org/terms/#dwc:scientificNameID                                          |
|:-------------|:-----------------------------------------------------------------------------------------|
|Definição     |Um identificador para os detalhes nomenclaturais (não taxonômicos) de um nome científico. |
|Domínio       |                                                                                          |
|Exemplos      |                                                                                          |


---

#### [acceptedNameUsageID](https://github.com/sibbr/DarwinCoreBrasil/issues/145)


|Identificador |https://dwc.tdwg.org/terms/#dwc:acceptedNameUsageID                                                                                                        |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um identificador para o uso do nome (significado documentado do nome de acordo com uma fonte) do táxon atualmente válido (zoológico) ou aceito (botânico). |
|Domínio       |6W3C4 (COL) &#124; 2704179 (GBIF)                                                                                                                          |
|Exemplos      |                                                                                                                                                           |


---

#### [parentNameUsageID](https://github.com/sibbr/DarwinCoreBrasil/issues/146)


|Identificador |https://dwc.tdwg.org/terms/#dwc:parentNameUsageID                                                                                                                                                                                |
|:-------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um identificador para o uso do nome (significado documentado do nome de acordo com uma fonte) do táxon pai direto e mais próximo de classificação superior (em uma classificação) do elemento mais específico do scientificname. |
|Domínio       |6T8N (COL) &#124; 2704173 (GBIF)                                                                                                                                                                                                 |
|Exemplos      |                                                                                                                                                                                                                                 |


---

#### [originalNameUsageID](https://github.com/sibbr/DarwinCoreBrasil/issues/147)


|Identificador |https://dwc.tdwg.org/terms/#dwc:originalNameUsageID                                                                                                                                                                         |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um identificador para o uso do nome (significado documentado do nome de acordo com uma fonte) no qual o elemento terminal do scientificname foi originalmente estabelecido sob as regras do código nomenclatural associado. |
|Domínio       |6W3C4 (COL) &#124; 2704179 (GBIF)                                                                                                                                                                                           |
|Exemplos      |                                                                                                                                                                                                                            |


---

#### [nameAccordingToID](https://github.com/sibbr/DarwinCoreBrasil/issues/148)


|Identificador |https://dwc.tdwg.org/terms/#dwc:nameAccordingToID                                                                                        |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um identificador para a fonte na qual a circunscrição do conceito de táxon específico é definida ou implícita. Consulte nameaccordingto. |
|Domínio       |                                                                                                                                         |
|Exemplos      |                                                                                                                                         |


---

#### [namePublishedInID](https://github.com/sibbr/DarwinCoreBrasil/issues/149)


|Identificador |https://dwc.tdwg.org/terms/#dwc:namePublishedInID                                                                                          |
|:-------------|:------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um identificador para a publicação em que o scientificname foi originalmente estabelecido sob as regras do código nomenclatural associado. |
|Domínio       |                                                                                                                                           |
|Exemplos      |                                                                                                                                           |


---

#### [taxonConceptID](https://github.com/sibbr/DarwinCoreBrasil/issues/150)


|Identificador |https://dwc.tdwg.org/terms/#dwc:taxonConceptID                                                                              |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um identificador para o conceito taxonômico ao qual o registro se refere - não para os detalhes nomenclaturais de um táxon. |
|Domínio       |                                                                                                                            |
|Exemplos      |                                                                                                                            |


---

#### [scientificName](https://github.com/sibbr/DarwinCoreBrasil/issues/151)


|Identificador |https://dwc.tdwg.org/terms/#dwc:scientificName                                                                                                                                                                                                                                                                                          |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome científico completo, com informações de autoria e data, se conhecidas. Ao fazer parte de uma identificação, este deve ser o nome na classificação taxonômica de nível mais baixo que pode ser determinado. Este termo não deve conter qualificações de identificação, que devem ser fornecidas no termo identificationqualifier. |
|Domínio       |Ceiba speciosa &#124;Eugenia uniflora &#124; Chrysocyon brachyurus                                                                                                                                                                                                                                                                      |
|Exemplos      |                                                                                                                                                                                                                                                                                                                                        |


---

#### [acceptedNameUsage](https://github.com/sibbr/DarwinCoreBrasil/issues/152)


|Identificador |https://dwc.tdwg.org/terms/#dwc:acceptedNameUsage                                                                               |
|:-------------|:-------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome completo, com informações de autoria e data, se conhecidas, do táxon atualmente válido (zoológico) ou aceito (botânico). |
|Domínio       |Tamias minimus (nome válido para Eutamias minimus)                                                                              |
|Exemplos      |                                                                                                                                |


---

#### [parentNameUsage](https://github.com/sibbr/DarwinCoreBrasil/issues/153)


|Identificador |https://dwc.tdwg.org/terms/#dwc:parentNameUsage                                                                                                                              |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome completo, com informações de autoria e data, se conhecidas, do táxon pai direto e mais próximo (em uma classificação) do elemento mais específico do nome científico. |
|Domínio       |Rubiaceae                                                                                                                                                                    |
|Exemplos      |                                                                                                                                                                             |


---

#### [originalNameUsage](https://github.com/sibbr/DarwinCoreBrasil/issues/154)


|Identificador |https://dwc.tdwg.org/terms/#dwc:originalNameUsage                                                                                                                                                                                                                                                                 |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome do táxon, com informações de autoria e data, se conhecido, como apareceu originalmente quando estabelecido pela primeira vez sob as regras do código nomenclatural associado. O basiônimo (botânica) ou basônimo (bacteriologia) do nome científico ou o homônimo sênior/anterior para nomes substituídos. |
|Domínio       |Pinus abies                                                                                                                                                                                                                                                                                                       |
|Exemplos      |                                                                                                                                                                                                                                                                                                                  |


---

#### [nameAccordingTo](https://github.com/sibbr/DarwinCoreBrasil/issues/155)


|Identificador |https://dwc.tdwg.org/terms/#dwc:nameAccordingTo                                                                                                                                                                                                                                                                                                                                                                        |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |A referência à fonte na qual o conceito específico de táxon circunscrição é definido ou implícito - tradicionalmente significada pelo latim "sensu" ou "sec". (de secundum, que significa "de acordo com"). Para os táxons resultantes de identificações, deve ser dada uma referência às chaves, monografias, especialistas e outras fontes.                                                                          |
|Domínio       |Franz NM, Cardona-Duque J (2013) Descrição de duas novas espécies e reavaliação filogenética de Perelleschus Wibmer & O'Brien, 1986 (Coleoptera: Curculionidae), com um histórico completo do conceito taxonômico de Perelleschus sec. Franz & Cardona-Duque, 2013. Syst Biodivers. 11: 209-236. (como a citação completa de Franz & Cardona-Duque (2013) em Perelleschus splendida sec. Franz & Cardona-Duque (2013)) |
|Exemplos      |                                                                                                                                                                                                                                                                                                                                                                                                                       |


---

#### [namePublishedIn](https://github.com/sibbr/DarwinCoreBrasil/issues/156)


|Identificador |https://dwc.tdwg.org/terms/#dwc:namePublishedIn                                                                                          |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma referência para a publicação em que o scientificname foi originalmente estabelecido sob as regras do código nomenclatural associado. |
|Domínio       |                                                                                                                                         |
|Exemplos      |                                                                                                                                         |


---

#### [namePublishedInYear](https://github.com/sibbr/DarwinCoreBrasil/issues/157)


|Identificador |https://dwc.tdwg.org/terms/#dwc:namePublishedInYear             |
|:-------------|:---------------------------------------------------------------|
|Definição     |O ano de quatro dígitos em que o nome científico foi publicado. |
|Domínio       |1915 &#124; 2008                                                |
|Exemplos      |                                                                |


---

#### [higherClassification](https://github.com/sibbr/DarwinCoreBrasil/issues/158)


|Identificador |https://dwc.tdwg.org/terms/#dwc:higherClassification                                                                                                                                                      |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de nomes de táxons terminando no posto imediatamente superior ao táxon referenciado no registro do táxon.                                                              |
|Domínio       |Animalia &#124; Chordata &#124; Vertebrata &#124; Mammalia &#124; Theria &#124; Eutheria &#124; Rodentia &#124; Hystricognatha &#124; Hystricognathi &#124; Ctenomyidae &#124; Ctenomyini &#124; Ctenomys |
|Exemplos      |                                                                                                                                                                                                          |


---

#### [kingdom](https://github.com/sibbr/DarwinCoreBrasil/issues/159)


|Identificador |https://dwc.tdwg.org/terms/#dwc:kingdom                                                                           |
|:-------------|:-----------------------------------------------------------------------------------------------------------------|
|Definição     |O nome científico completo do reino em que o táxon está classificado.                                             |
|Domínio       |Animalia &#124; Plantae &#124; Fungi &#124; Archaea &#124;Chromista &#124; Protozoa &#124; Viruses &#124;Bacteria |
|Exemplos      |                                                                                                                  |


---

#### [phylum](https://github.com/sibbr/DarwinCoreBrasil/issues/160)


|Identificador |https://dwc.tdwg.org/terms/#dwc:phylum                                                                   |
|:-------------|:--------------------------------------------------------------------------------------------------------|
|Definição     |Vocabulário controlado obrigatório. O nome científico completo do filo em que o táxon está classificado. |
|Domínio       |Filo                                                                                                     |
|Exemplos      |                                                                                                         |


---

#### [class](https://github.com/sibbr/DarwinCoreBrasil/issues/161)


|Identificador |https://dwc.tdwg.org/terms/#dwc:class                                  |
|:-------------|:----------------------------------------------------------------------|
|Definição     |O nome científico completo da classe em que o táxon está classificado. |
|Domínio       |Classe                                                                 |
|Exemplos      |                                                                       |


---

#### [order](https://github.com/sibbr/DarwinCoreBrasil/issues/162)


|Identificador |https://dwc.tdwg.org/terms/#dwc:order                                 |
|:-------------|:---------------------------------------------------------------------|
|Definição     |O nome científico completo da ordem em que o táxon está classificado. |
|Domínio       |Ordem                                                                 |
|Exemplos      |                                                                      |


---

#### [family](https://github.com/sibbr/DarwinCoreBrasil/issues/163)


|Identificador |https://dwc.tdwg.org/terms/#dwc:family                                  |
|:-------------|:-----------------------------------------------------------------------|
|Definição     |O nome científico completo da família em que o táxon está classificado. |
|Domínio       |Familia                                                                 |
|Exemplos      |                                                                        |


---

#### [subfamily](https://github.com/sibbr/DarwinCoreBrasil/issues/164)


|Identificador |https://dwc.tdwg.org/terms/#dwc:subfamily                                  |
|:-------------|:--------------------------------------------------------------------------|
|Definição     |O nome científico completo da subfamília em que o táxon está classificado. |
|Domínio       |Subfamilia                                                                 |
|Exemplos      |                                                                           |


---

#### [genus](https://github.com/sibbr/DarwinCoreBrasil/issues/165)


|Identificador |https://dwc.tdwg.org/terms/#dwc:genus                                  |
|:-------------|:----------------------------------------------------------------------|
|Definição     |O nome científico completo do gênero em que o táxon está classificado. |
|Domínio       |Gênero                                                                 |
|Exemplos      |                                                                       |


---

#### [genericName](https://github.com/sibbr/DarwinCoreBrasil/issues/166)


|Identificador |https://dwc.tdwg.org/terms/#dwc:genericName        |
|:-------------|:--------------------------------------------------|
|Definição     |O gênero faz parte do nome científico sem autoria. |
|Domínio       |Panthera &#124; Felis &#124; Canis &#124;Rosa      |
|Exemplos      |                                                   |


---

#### [subgenus](https://github.com/sibbr/DarwinCoreBrasil/issues/167)


|Identificador |https://dwc.tdwg.org/terms/#dwc:subgenus                                                                                                    |
|:-------------|:-------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome científico completo do subgênero no qual o táxon está classificado. Os valores devem incluir o gênero para evitar confusão homônima. |
|Domínio       |Amerigo &#124; Strobus                                                                                                                      |
|Exemplos      |                                                                                                                                            |


---

#### [infragenericEpithet](https://github.com/sibbr/DarwinCoreBrasil/issues/168)


|Identificador |https://dwc.tdwg.org/terms/#dwc:infragenericEpithet                                      |
|:-------------|:----------------------------------------------------------------------------------------|
|Definição     |A parte infragenérica de um nome binomial está acima das espécies, mas abaixo do gênero. |
|Domínio       |Abacetillus (para o scientificName Abacetus (Abacetillus) ambiguus)                      |
|Exemplos      |                                                                                         |


---

#### [specificEpithet](https://github.com/sibbr/DarwinCoreBrasil/issues/169)


|Identificador |https://dwc.tdwg.org/terms/#dwc:specificEpithet              |
|:-------------|:------------------------------------------------------------|
|Definição     |O nome do primeiro ou epíteto de espécie do nome científico. |
|Domínio       |concolor                                                     |
|Exemplos      |                                                             |


---

#### [infraspecificEpithet](https://github.com/sibbr/DarwinCoreBrasil/issues/170)


|Identificador |https://dwc.tdwg.org/terms/#dwc:infraspecificEpithet                                                                         |
|:-------------|:----------------------------------------------------------------------------------------------------------------------------|
|Definição     |O nome do epíteto infraespecífico mais baixo ou terminal do nome científico, excluindo qualquer designação de classificação. |
|Domínio       |concolor (para scientificName Puma concolor concolor (Linnaeus, 1771)                                                        |
|Exemplos      |                                                                                                                             |


---

#### [cultivarEpithet](https://github.com/sibbr/DarwinCoreBrasil/issues/171)


|Identificador |https://dwc.tdwg.org/terms/#dwc:cultivarEpithet                                 |
|:-------------|:-------------------------------------------------------------------------------|
|Definição     |Parte do nome de uma cultivar, grupo de cultivares que segue o nome científico. |
|Domínio       |Atlantis (para scientificName Paphiopedilum Atlantis grex e taxonRank grex)     |
|Exemplos      |                                                                                |


---

#### [taxonRank](https://github.com/sibbr/DarwinCoreBrasil/issues/172)


|Identificador |https://dwc.tdwg.org/terms/#dwc:taxonRank                              |
|:-------------|:----------------------------------------------------------------------|
|Definição     |A classificação taxonômica do nome mais específico no nome científico. |
|Domínio       |Espécie &#124; Gênero &#124; Subespécie                                |
|Exemplos      |Categoria taxonômica                                                   |


---

#### [verbatimTaxonRank](https://github.com/sibbr/DarwinCoreBrasil/issues/173)


|Identificador |https://dwc.tdwg.org/terms/#dwc:verbatimTaxonRank                                                        |
|:-------------|:--------------------------------------------------------------------------------------------------------|
|Definição     |A classificação taxonômica do nome mais específico no nome científico como aparece no registro original. |
|Domínio       |sp. &#124;subsp. &#124; var.                                                                             |
|Exemplos      |                                                                                                         |


---

#### [scientificNameAuthorship](https://github.com/sibbr/DarwinCoreBrasil/issues/174)


|Identificador |https://dwc.tdwg.org/terms/#dwc:scientificNameAuthorship                                                                  |
|:-------------|:-------------------------------------------------------------------------------------------------------------------------|
|Definição     |As informações de autoria para o nome científico formatado de acordo com as convenções do código nomenclatural aplicável. |
|Domínio       |Nome do autor                                                                                                             |
|Exemplos      |                                                                                                                          |


---

#### [vernacularName](https://github.com/sibbr/DarwinCoreBrasil/issues/175)


|Identificador |https://dwc.tdwg.org/terms/#dwc:vernacularName        |
|:-------------|:-----------------------------------------------------|
|Definição     |Um nome comum ou vernáculo.                           |
|Domínio       |Puma &#124; Ipê-roxo&#124; Seringueira &#124; Canguru |
|Exemplos      |                                                      |


---

#### [nomenclaturalCode](https://github.com/sibbr/DarwinCoreBrasil/issues/176)


|Identificador |https://dwc.tdwg.org/terms/#dwc:nomenclaturalCode                                                                                                                                                                     |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O código nomenclatural sob o qual o scientificname é construído.                                                                                                                                                      |
|Domínio       |ICBN &#124; ICZN &#124; ICTV &#124; ICNB                                                                                                                                                                              |
|Exemplos      |Para coleções herbário: https://www.iapt-taxon.org/nomen/main.php Para coleções de Zoologia: https://code.iczn.org/?frame=1 Para virus: https://ictv.global/ e bacterias: https://www.ncbi.nlm.nih.gov/books/NBK8817/ |


---

#### [taxonomicStatus](https://github.com/sibbr/DarwinCoreBrasil/issues/177)


|Identificador |https://dwc.tdwg.org/terms/#dwc:taxonomicStatus                                                                                                                                                                                                                                                                                                                               |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O status do uso do scientificname como um rótulo para um táxon. Requer parecer taxonômico para definir o escopo de um táxon. Em seguida, são utilizadas regras de prioridade para definir o estatuto taxonômico da nomenclatura contida nesse âmbito, combinado com o parecer dos peritos. Deve estar vinculado a uma referência taxonômica específica que defina o conceito. |
|Domínio       |aceito &#124; inválido &#124; sinônimo homotípico                                                                                                                                                                                                                                                                                                                             |
|Exemplos      |                                                                                                                                                                                                                                                                                                                                                                              |


---

#### [nomenclaturalStatus](https://github.com/sibbr/DarwinCoreBrasil/issues/178)


|Identificador |https://dwc.tdwg.org/terms/#dwc:nomenclaturalStatus                                                                                                                                                                                                 |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |O estatuto relacionado com a publicação original do nome e a sua conformidade com as regras de nomenclatura pertinentes. Ele é baseado essencialmente em um algoritmo de acordo com as regras de negócios do código. Não requer opinião taxonômica. |
|Domínio       |nom. ambig. &#124; nom. illeg.                                                                                                                                                                                                                      |
|Exemplos      |                                                                                                                                                                                                                                                    |


---

#### [taxonRemarks](https://github.com/sibbr/DarwinCoreBrasil/issues/179)


|Identificador |https://dwc.tdwg.org/terms/#dwc:taxonRemarks |
|:-------------|:--------------------------------------------|
|Definição     |Comentários ou notas sobre o táxon ou nome.  |
|Domínio       |                                             |
|Exemplos      |                                             |


---

### MeasurementOrFact


#### [measurementID](https://github.com/sibbr/DarwinCoreBrasil/issues/180)


|Identificador |https://dwc.tdwg.org/terms/#dwc:measurementID                                                                                                                                                                           |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Um identificador para o measurementorfact (informações relativas a medições, fatos, características ou afirmações). Pode ser um identificador exclusivo global ou um identificador específico para o conjunto de dados. |
|Domínio       |                                                                                                                                                                                                                        |
|Exemplos      |                                                                                                                                                                                                                        |


---

#### [measurementType](https://github.com/sibbr/DarwinCoreBrasil/issues/181)


|Identificador |https://dwc.tdwg.org/terms/#dwc:measurementType         |
|:-------------|:-------------------------------------------------------|
|Definição     |A natureza da medida, fato, característica ou asserção. |
|Domínio       |temperatura &#124; comprimento da cauda                 |
|Exemplos      |                                                        |


---

#### [measurementValue](https://github.com/sibbr/DarwinCoreBrasil/issues/182)


|Identificador |https://dwc.tdwg.org/terms/#dwc:measurementValue     |
|:-------------|:----------------------------------------------------|
|Definição     |O valor da medida, fato, característica ou asserção. |
|Domínio       |45 &#124; 20 &#124; 1                                |
|Exemplos      |                                                     |


---

#### [measurementAccuracy](https://github.com/sibbr/DarwinCoreBrasil/issues/183)


|Identificador |https://dwc.tdwg.org/terms/#dwc:measurementAccuracy          |
|:-------------|:------------------------------------------------------------|
|Definição     |A descrição do erro potencial associado ao measurementvalue. |
|Domínio       |0.01                                                         |
|Exemplos      |                                                             |


---

#### [measurementUnit](https://github.com/sibbr/DarwinCoreBrasil/issues/184)


|Identificador |https://dwc.tdwg.org/terms/#dwc:measurementUnit   |
|:-------------|:-------------------------------------------------|
|Definição     |As unidades associadas ao measurementvalue.       |
|Domínio       |m &#124; g &#124; l &#124;°C &#124; mm &#124; km² |
|Exemplos      |                                                  |


---

#### [measurementDeterminedBy](https://github.com/sibbr/DarwinCoreBrasil/issues/185)


|Identificador |https://dwc.tdwg.org/terms/#dwc:measurementDeterminedBy                                                                       |
|:-------------|:-----------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma lista (concatenada e separada) de nomes de pessoas, grupos ou organizações que determinaram o valor do measurementorfact. |
|Domínio       |                                                                                                                              |
|Exemplos      |                                                                                                                              |


---

#### [measurementDeterminedDate](https://github.com/sibbr/DarwinCoreBrasil/issues/186)


|Identificador |https://dwc.tdwg.org/terms/#dwc:measurementDeterminedDate          |
|:-------------|:------------------------------------------------------------------|
|Definição     |A data em que o measurementorfact foi feito.                       |
|Domínio       |2018-08-29T15:19 (15:19 horário local no dia 29 de Agosto de 2018) |
|Exemplos      |                                                                   |


---

#### [measurementMethod](https://github.com/sibbr/DarwinCoreBrasil/issues/187)


|Identificador |https://dwc.tdwg.org/terms/#dwc:measurementMethod                                                                                       |
|:-------------|:---------------------------------------------------------------------------------------------------------------------------------------|
|Definição     |Uma descrição ou referência a (publicação, url) o método ou protocolo usado para determinar a medida, fato, característica ou asserção. |
|Domínio       |Altímetro barométrico                                                                                                                   |
|Exemplos      |                                                                                                                                        |


---

#### [measurementRemarks](https://github.com/sibbr/DarwinCoreBrasil/issues/188)


|Identificador |https://dwc.tdwg.org/terms/#dwc:measurementRemarks       |
|:-------------|:--------------------------------------------------------|
|Definição     |Comentários ou notas que acompanham o measurementorfact. |
|Domínio       |                                                         |
|Exemplos      |                                                         |


