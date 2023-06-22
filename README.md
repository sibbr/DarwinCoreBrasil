# DarwinCoreBrasil
Termos DarwinCore para compartilhamento de dados e informações em biodiversidade com o objetivo identificar termos com vocabulário controlado e definir um conjunto de boas práticas no uso do padrão no Brasil junto com todas as instituições e organizações que produzem dados. 
https://dwc.tdwg.org/terms/
## Justificativa
O uso do padrão DarwinCore para compartilhamento de dados em biobiversidade tem aumentado no Brasil sendo que quase todas as instituições, organizações, fundações, programas e projetos que trabalham com dados tem publicado em alguma plataforma seja nacional ou internacional. Devido a grande heterogeneidade de tipos de dados, coleções e grupos existem dúvidas nos preenchimentos de cada campo. A discussão dos termos e melhores práticas vai contribuir a organizar os dados corretamente no Brasil, tendo em consideração todas as instituições e suas respetivas demandas e termos a serem considerados e compartilhados. 
## Classes e Termos DarwinCore

| [Record-level](https://github.com/sibbr/DarwinCoreBrasil#record-level) | [Ocurrence](https://github.com/sibbr/DarwinCoreBrasil#occurrence) | [Organism](https://github.com/sibbr/DarwinCoreBrasil#organism) | [MaterialSample](https://github.com/sibbr/DarwinCoreBrasil#materialsample)| [Event](https://github.com/sibbr/DarwinCoreBrasil#event) | [Location](https://github.com/sibbr/DarwinCoreBrasil#location) | [GeologicalContext](https://github.com/sibbr/DarwinCoreBrasil#geologicalcontext) | [Identification](https://github.com/sibbr/DarwinCoreBrasil#identification) | [Taxon](https://github.com/sibbr/DarwinCoreBrasil#taxon) | [MeasurementOrFact](https://github.com/sibbr/DarwinCoreBrasil#measurementorfact)
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

### Record-level

> :warning:  Considerem este formato ao invés da tabela, pois ele pode crescer sem problemas.

|[datasetName](https://github.com/sibbr/DarwinCoreBrasil/issues/1)||
|--|--|
| Identificador| http://rs.tdwg.org/dwc/terms/datasetName |
| Definição | O nome que identifica o conjunto de dados do qual o registro foi derivado. |
| Domínio | n.a. |
| Exemplos | Abelhas de Itatiaia | 
---
|[type](https://github.com/sibbr/DarwinCoreBrasil/issues/2)||
|--|--|
| Identificador | http://purl.org/dc/elements/1.1/type |
| Definição | A natureza ou gênero do recurso. |
| Domínio | StillImage, MovingImage, Sound, PhysicalObject, Event, Text |
| Exemplos |  | 
---
---

| Termo | Definição | Domínio |
| :--- | :--- | :--- |
|[datasetName](https://github.com/sibbr/DarwinCoreBrasil/issues/1)|O nome que identifica o conjunto de dados do qual o registro foi derivado.| |
|[type](https://github.com/sibbr/DarwinCoreBrasil/issues/2)|A natureza ou gênero do recurso. | |
|[modified](https://github.com/sibbr/DarwinCoreBrasil/issues/3)|A data-hora mais recente em que o recurso foi alterado.| |
|[language](https://github.com/sibbr/DarwinCoreBrasil/issues/4)|A língua do recurso.| |
|[license](https://github.com/sibbr/DarwinCoreBrasil/issues/5)|Um documento legal dando permissão oficial para fazer algo com o recurso.| |
|[rightsHolder](https://github.com/sibbr/DarwinCoreBrasil/issues/6)|Uma pessoa ou organização que possui ou gerencia direitos sobre o recurso. | |
|[accessRights](https://github.com/sibbr/DarwinCoreBrasil/issues/7)|Informações sobre quem pode acessar o recurso ou uma indicação de seu status de segurança. | |
|[bibliographicCitation](https://github.com/sibbr/DarwinCoreBrasil/issues/8)|Uma referência bibliográfica para o recurso como uma declaração indicando como esse registro deve ser citado (atribuído) quando utilizado. | |
|[references](https://github.com/sibbr/DarwinCoreBrasil/issues/9)|Um recurso relacionado que é referenciado, citado ou apontado de outra forma pelo recurso descrito.| |
|[institutionID](https://github.com/sibbr/DarwinCoreBrasil/issues/10)|Um identificador da instituição que detém a guarda do(s) objeto(s) ou das informações referidas no registo.| |
|[collectionID](https://github.com/sibbr/DarwinCoreBrasil/issues/11)|Um identificador para a coleção ou conjunto de dados do qual o registro foi derivado.| |
|[datasetID](https://github.com/sibbr/DarwinCoreBrasil/issues/12)|Um identificador para a coleção ou conjunto de dados do qual o registro foi derivado.| |
|[institutionCode](https://github.com/sibbr/DarwinCoreBrasil/issues/13)|O nome (ou sigla) em uso pela instituição que detém a guarda do(s) objeto(s) ou das informações referidas no registro. | |
|[collectionCode](https://github.com/sibbr/DarwinCoreBrasil/issues/14)|O nome, acrônimo ou código que identifica a coleção ou o conjunto de dados do qual o registro foi derivado.| |
|[ownerInstitutionCode](https://github.com/sibbr/DarwinCoreBrasil/issues/15)|O nome (ou sigla) utilizado pela instituição proprietária do(s) objeto(s) ou das informações referidas no registo. | |
|[basisOfRecord](https://github.com/sibbr/DarwinCoreBrasil/issues/16)|A natureza específica do registro de dados.| |
|[informationWithheld](https://github.com/sibbr/DarwinCoreBrasil/issues/17)|Informações adicionais que existem, mas que não foram compartilhadas no registro fornecido.| |
|[dataGeneralizations](https://github.com/sibbr/DarwinCoreBrasil/issues/18)|Informações adicionais que existem, mas que não foram compartilhadas no registro fornecido.| |
|[dynamicProperties](https://github.com/sibbr/DarwinCoreBrasil/issues/19)|Uma lista de medidas, fatos, características ou afirmações adicionais sobre o registro. Destinado a fornecer um mecanismo para conteúdo estruturado. | |

### Occurrence

| Termo | Definição | Domínio |
| :--- | :--- | :--- |
|[occurrenceID](https://github.com/sibbr/DarwinCoreBrasil/issues/20)|Um identificador para a ocorrência (em oposição a um registro digital específico da ocorrência). Na ausência de um identificador exclusivo global persistente, construa um a partir de uma combinação de identificadores no registro que tornará o id de ocorrência globalmente exclusivo. | |
|[catalogNumber](https://github.com/sibbr/DarwinCoreBrasil/issues/21)|Um identificador (de preferência exclusivo) para o registro dentro do conjunto de dados ou coleção. | |
|[recordNumber](https://github.com/sibbr/DarwinCoreBrasil/issues/22)|Um identificador dado à ocorrência no momento em que foi registrada. Muitas vezes serve como um link entre as notas de campo e um registro de ocorrência, como o número de um coletor de amostras. | |
|[recordedBy](https://github.com/sibbr/DarwinCoreBrasil/issues/23)|Uma lista (concatenada e separada) de nomes de pessoas, grupos ou organizações responsáveis pelo registro da ocorrência original. O coletor ou observador primário, especialmente aquele que aplica um identificador pessoal (recordnumber), deve ser listado primeiro.| |
|[recordedByID](https://github.com/sibbr/DarwinCoreBrasil/issues/24)|Uma lista (concatenada e separada) do identificador global exclusivo da pessoa, pessoas, grupos ou organizações responsáveis pelo registro da ocorrência original.| |
|[individualCount](https://github.com/sibbr/DarwinCoreBrasil/issues/25)|O número de indivíduos presentes no momento da ocorrência.| |
|[organismQuantity](https://github.com/sibbr/DarwinCoreBrasil/issues/26)|Um número ou valor de enumeração para a quantidade de organismos. | |
|[organismQuantityType](https://github.com/sibbr/DarwinCoreBrasil/issues/27)|O tipo de sistema de quantificação utilizado para a quantidade de organismos. | |
|[sex](https://github.com/sibbr/DarwinCoreBrasil/issues/28)|O sexo do(s) indivíduo(s) biológico(s) representado(s) na ocorrência. | |
|[lifeStage](https://github.com/sibbr/DarwinCoreBrasil/issues/29)|A classe etária ou estágio de vida do(s) organismo(s) no momento em que a ocorrência foi registrada.| |
|[reproductiveCondition](https://github.com/sibbr/DarwinCoreBrasil/issues/30)|A condição reprodutiva do(s) indivíduo(s) biológico(s) representado(s) na ocorrência. | |
|[behavior](https://github.com/sibbr/DarwinCoreBrasil/issues/31)|O comportamento apresentado pelo sujeito no momento em que a ocorrência foi registrada. | |
|[establishmentMeans](https://github.com/sibbr/DarwinCoreBrasil/issues/32)|Declaração sobre se um organismo ou organismos foram introduzidos em um determinado lugar e tempo através da atividade direta ou indireta dos humanos modernos. | |
|[degreeOfEstablishment](https://github.com/sibbr/DarwinCoreBrasil/issues/33)|O grau em que um organismo sobrevive, se reproduz e expande seu alcance no lugar e tempo determinados.| |
|[pathway](https://github.com/sibbr/DarwinCoreBrasil/issues/34)|O processo pelo qual um organismo veio a estar em um determinado lugar em um determinado tempo| |
|[georeferenceVerificationStatus](https://github.com/sibbr/DarwinCoreBrasil/issues/35)|Descrição categórica do grau em que se verificou que o georreferenciamento representa a melhor descrição espacial possível para a localização da ocorrência.| |
|[occurrenceStatus](https://github.com/sibbr/DarwinCoreBrasil/issues/36)|Uma declaração sobre a presença ou ausência de um táxon em um local.| |
|[preparations](https://github.com/sibbr/DarwinCoreBrasil/issues/37)|Uma lista de preparações e métodos de conservação de um espécime. | |
|[disposition](https://github.com/sibbr/DarwinCoreBrasil/issues/38)|O estado atual de um espécime em relação à coleção identificada em collectioncode ou collectionid.| |
|[associatedMedia](https://github.com/sibbr/DarwinCoreBrasil/issues/39)|Uma lista (concatenada e separada) de identificadores (publicação, identificador exclusivo global, url) de mídia associada à ocorrência.| |
|[associatedOccurrences](https://github.com/sibbr/DarwinCoreBrasil/issues/40)|Uma lista (concatenada e separada) de identificadores de outros registros de ocorrência e suas associações a esta ocorrência. | |
|[associatedReferences](https://github.com/sibbr/DarwinCoreBrasil/issues/41)|Uma lista (concatenada e separada) de identificadores (publicação, referência bibliográfica, identificador único global, url) da literatura associada à ocorrência. | |
|[associatedSequences](https://github.com/sibbr/DarwinCoreBrasil/issues/42)|Uma lista (concatenada e separada) de identificadores (publicação, identificador único global, url) de informações de sequência genética associadas à ocorrência. | |
|[associatedTaxa](https://github.com/sibbr/DarwinCoreBrasil/issues/43)|Uma lista (concatenada e separada) de identificadores ou nomes de táxons e as associações desta ocorrência a cada um deles. | |
|[otherCatalogNumbers](https://github.com/sibbr/DarwinCoreBrasil/issues/44)|Uma lista (concatenada e separada) de números de catálogo totalmente qualificados anteriores ou alternativos ou outros identificadores usados por humanos para a mesma ocorrência, seja no atual ou em qualquer outro conjunto de dados ou coleção.| |
|[occurrenceRemarks](https://github.com/sibbr/DarwinCoreBrasil/issues/45)|Comentários ou notas sobre a ocorrência. | |

### Organism

| Termo | Definição | Domínio |
| :--- | :--- | :--- | 
|[organismID](https://github.com/sibbr/DarwinCoreBrasil/issues/46)|Um identificador para a instância do organismo (em oposição a um registro digital específico do organismo). Pode ser um identificador global exclusivo ou um identificador específico para o conjunto de dados. | |
|[organismName](https://github.com/sibbr/DarwinCoreBrasil/issues/47)|Um nome textual ou rótulo atribuído a uma instância de um organismo. | |
|[organismScope](https://github.com/sibbr/DarwinCoreBrasil/issues/48)|Uma descrição do tipo de instância de organismo. Pode ser usado para indicar se a instância de organismo representa um organismo discreto ou se representa um tipo particular de agregação. | |
|[associatedOrganisms](https://github.com/sibbr/DarwinCoreBrasil/issues/49)|Uma lista (concatenada e separada) de identificadores de outros organismos e as associações deste organismo a cada um deles.| |
|[previousIdentifications](https://github.com/sibbr/DarwinCoreBrasil/issues/50)|Uma lista (concatenada e separada) de atribuições anteriores de nomes ao organismo.| |
|[organismRemarks](https://github.com/sibbr/DarwinCoreBrasil/issues/51)|Comentários ou notas sobre a instância organismo.| |

### MaterialSample

| Termo | Definição | Domínio |
| :--- | :--- | :--- |
|[MaterialSampleID](https://github.com/sibbr/DarwinCoreBrasil/issues/52)|Um resultado físico de um evento de amostragem (ou subamostragem). Em coleções biológicas, a amostra de material é tipicamente coletada, e preservada ou processada destrutivamente. | |

### Event

| Termo | Definição | Domínio |
| :--- | :--- | :--- |
|[eventID](https://github.com/sibbr/DarwinCoreBrasil/issues/53)|Um identificador para o conjunto de informações associadas a um evento (algo que ocorre em um local e horário). Pode ser um identificador exclusivo global ou um identificador específico para o conjunto de dados. | |
|[parentEventID](https://github.com/sibbr/DarwinCoreBrasil/issues/54)|Um identificador para o evento mais amplo que agrupa este e potencialmente outros eventos. | |
|[eventDate](https://github.com/sibbr/DarwinCoreBrasil/issues/55)|A data-hora ou o intervalo durante o qual um evento ocorreu. Para ocorrências, essa é a data-hora em que o evento foi registrado. Não adequado para um tempo em um contexto geológico.| |
|[eventTime](https://github.com/sibbr/DarwinCoreBrasil/issues/56)|O tempo ou intervalo durante o qual um evento ocorreu. | |
|[startDayOfYear](https://github.com/sibbr/DarwinCoreBrasil/issues/57)|O primeiro dia inteiro do ano em que o evento ocorreu (1 para 1º de janeiro, 365 para 31 de dezembro, exceto em um ano bissexto, caso em que é 366).| |
|[endDayOfYear](https://github.com/sibbr/DarwinCoreBrasil/issues/58)|O último dia inteiro do ano em que o evento ocorreu (1 para 1º de janeiro, 365 para 31 de dezembro, exceto em um ano bissexto, caso em que é 366).| |
|[year](https://github.com/sibbr/DarwinCoreBrasil/issues/59)|O ano de quatro dígitos em que o evento ocorreu. | |
|[month](https://github.com/sibbr/DarwinCoreBrasil/issues/60)|O mês inteiro em que o evento ocorreu. | |
|[day](https://github.com/sibbr/DarwinCoreBrasil/issues/61)|O dia inteiro em que o evento ocorreu. | |
|[verbatimEventDate](https://github.com/sibbr/DarwinCoreBrasil/issues/62)|A representação original literal das informações de data e hora de um evento.| |
|[habitat](https://github.com/sibbr/DarwinCoreBrasil/issues/63)|Uma categoria ou descrição do habitat em que o evento ocorreu. | |
|[samplingProtocol](https://github.com/sibbr/DarwinCoreBrasil/issues/64)|Os nomes, referências ou descrições dos métodos ou protocolos usados durante um evento.| |
|[sampleSizeValue](https://github.com/sibbr/DarwinCoreBrasil/issues/65)|Um valor numérico para uma medida do tamanho (duração do tempo, comprimento, área ou volume) de uma amostra em um evento de amostragem. | |
|[sampleSizeUnit ](https://github.com/sibbr/DarwinCoreBrasil/issues/66)|A unidade de medida do tamanho (duração do tempo, comprimento, área ou volume) de uma amostra em um evento de amostragem. | |
|[samplingEffort](https://github.com/sibbr/DarwinCoreBrasil/issues/67)|A quantidade de esforço despendido durante um evento.| |
|[fieldNotes ](https://github.com/sibbr/DarwinCoreBrasil/issues/68)|Um de a) um indicador da existência de, b) uma referência a (publicação, uri), ou c) o texto de anotações feitas no campo sobre o evento. | |
|[eventRemarks](https://github.com/sibbr/DarwinCoreBrasil/issues/69)|Comentários ou notas sobre o evento. | |

### Location

| Termo | Definição | Domínio |
| :--- | :--- | :--- |
|[locationID](https://github.com/sibbr/DarwinCoreBrasil/issues/70)|Um identificador para o conjunto de informações de localização (dados associados a dcterms: location). Pode ser um identificador exclusivo global ou um identificador específico para o conjunto de dados.| |
|[higherGeography](https://github.com/sibbr/DarwinCoreBrasil/issues/71)|Uma lista (concatenada e separada) de nomes geográficos menos específicos do que as informações capturadas no termo localidade.| |
|[continent](https://github.com/sibbr/DarwinCoreBrasil/issues/72)|O nome do continente em que a localização ocorre.| |
|[waterBody](https://github.com/sibbr/DarwinCoreBrasil/issues/73)|O nome do corpo d'água em que ocorre o local.| |
|[islandGroup](https://github.com/sibbr/DarwinCoreBrasil/issues/74)|O nome do grupo de ilhas em que a localização ocorre.| |
|[island](https://github.com/sibbr/DarwinCoreBrasil/issues/76)|O nome da ilha ou área perto da qual o local ocorre. | |
|[country](https://github.com/sibbr/DarwinCoreBrasil/issues/77)|O nome do país ou da principal unidade administrativa em que o local ocorre. | |
|[countryCode](https://github.com/sibbr/DarwinCoreBrasil/issues/78)|O código padrão para o país em que o local ocorre. | |
|[stateProvince](https://github.com/sibbr/DarwinCoreBrasil/issues/79)|O nome da próxima região administrativa menor do que o país (estado, província, cantão, departamento, região, etc.) em que a localização ocorre.| |
|[county](https://github.com/sibbr/DarwinCoreBrasil/issues/80)|O nome completo e não abreviado da próxima região administrativa menor do que o estado província (condado, condado, departamento, etc.) em que a localização ocorre.| |
|[locality](https://github.com/sibbr/DarwinCoreBrasil/issues/82)|A descrição específica do local. | |
|[verbatimLocality](https://github.com/sibbr/DarwinCoreBrasil/issues/83)|A descrição textual original do local. | |
|[minimumElevationInMeters](https://github.com/sibbr/DarwinCoreBrasil/issues/84)|O limite inferior da faixa de elevação (altitude, geralmente acima do nível do mar), em metros.| |
|[maximumElevationInMeters](https://github.com/sibbr/DarwinCoreBrasil/issues/85)|O limite superior da faixa de elevação (altitude, geralmente acima do nível do mar), em metros.| |
|[verbatimElevation](https://github.com/sibbr/DarwinCoreBrasil/issues/86)|A descrição original da elevação (altitude, geralmente acima do nível do mar) do local.| |
|[verticalDatum](https://github.com/sibbr/DarwinCoreBrasil/issues/87)|O dado vertical usado como referência sobre o qual os valores nos termos de elevação são baseados. | |
|[minimumDepthInMeters](https://github.com/sibbr/DarwinCoreBrasil/issues/88)|A menor profundidade de uma faixa de profundidade abaixo da superfície local, em metros. | |
|[maximumDepthInMeters](https://github.com/sibbr/DarwinCoreBrasil/issues/89)|A maior profundidade de uma faixa de profundidade abaixo da superfície local, em metros. | |
|[verbatimDepth](https://github.com/sibbr/DarwinCoreBrasil/issues/90)|A descrição original da profundidade abaixo da superfície local. | |
|[minimumDistanceAboveSurfaceInMeters](https://github.com/sibbr/DarwinCoreBrasil/issues/92)|A menor distância em uma faixa de distância de uma superfície de referência na direção vertical, em metros. Use valores positivos para locais acima da superfície, valores negativos para locais abaixo. Se forem dadas medidas de profundidade, a superfície de referência é a localização dada pela profundidade, caso contrário, a superfície de referência é a localização dada pela elevação.| |
|[maximumDistanceAboveSurfaceInMeters](https://github.com/sibbr/DarwinCoreBrasil/issues/94)|A maior distância em uma faixa de distância de uma superfície de referência na direção vertical, em metros. Use valores positivos para locais acima da superfície, valores negativos para locais abaixo. Se forem dadas medidas de profundidade, a superfície de referência é a localização dada pela profundidade, caso contrário, a superfície de referência é a localização dada pela elevação.| |
|[locationAccordingTo](https://github.com/sibbr/DarwinCoreBrasil/issues/95)|Informações sobre a fonte dessas informações de localização. Pode ser uma publicação (gazeta), instituição ou equipe de indivíduos. | |
|[locationRemarks](https://github.com/sibbr/DarwinCoreBrasil/issues/96)|Comentários ou notas sobre o local.| |
|[decimalLatitude](https://github.com/sibbr/DarwinCoreBrasil/issues/97)|A latitude geográfica (em graus decimais, usando o sistema de referência espacial dado em geodésico datum) do centro geográfico de uma localidade. Os valores positivos estão ao norte da linha do equador, os negativos estão ao sul dela. Os valores jurídicos situam-se entre -90 e 90. | |
|[decimalLongitude](https://github.com/sibbr/DarwinCoreBrasil/issues/98)|A longitude geográfica (em graus decimais, usando o sistema de referência espacial dado em geodésico datum) do centro geográfico de uma localidade. Os valores positivos estão a leste do meridiano de greenwich, os valores negativos estão a oeste dele. Os valores jurídicos situam-se entre -180 e 180.| |
|[geodeticDatum](https://github.com/sibbr/DarwinCoreBrasil/issues/99)|O elipsoide, dado geodésico ou sistema de referência espacial (srs) sobre o qual as coordenadas geográficas dadas em latitude decimal e longitude decimal como baseadas.| |
|[coordinateUncertaintyInMeters](https://github.com/sibbr/DarwinCoreBrasil/issues/100)|A distância horizontal (em metros) da latitude decimal e longitude decimal dadas, descrevendo o menor círculo que contém todo o local. Deixe o valor vazio se a incerteza for desconhecida, não puder ser estimada ou não for aplicável (porque não há coordenadas). Zero não é um valor válido para este termo. | |
|[coordinatePrecision](https://github.com/sibbr/DarwinCoreBrasil/issues/101)|Uma representação decimal da precisão das coordenadas dadas na latitude decimal e longitude decimal. | |
|[pointRadiusSpatialFit](https://github.com/sibbr/DarwinCoreBrasil/issues/102)|A razão entre a área do raio do ponto (decimallatitude, decimallongitude, coordinateuncertaintyinmeters) e a área da representação espacial verdadeira (original ou mais específica) da localização. Os valores legais são 0, maior ou igual a 1, ou indefinidos. Um valor de 1 é uma correspondência exata ou 100% de sobreposição. Um valor de 0 deve ser usado se o raio de ponto fornecido não contiver completamente a representação original. O pontoradiusspatialfit é indefinido (e deve ser deixado vazio) se a representação original é um ponto sem incerteza e a georreferência dada não é esse mesmo ponto (sem incerteza). Se a georreferência original e dada forem o mesmo ponto, o pontoradiusspatialfit será 1. | |
|[verbatimCoordinates](https://github.com/sibbr/DarwinCoreBrasil/issues/103)|As coordenadas espaciais originais literais do lugar. O elipsoide de coordenadas, geodésico datum, ou sistema de referência espacial (srs) completo para essas coordenadas deve ser armazenado em verbatimsrs e o sistema de coordenadas deve ser armazenado em verbatimcoordinatesystem.| |
|[verbatimLatitude](https://github.com/sibbr/DarwinCoreBrasil/issues/104)|A latitude original literal do lugar. O elipsoide de coordenadas, geodésico datum, ou sistema de referência espacial (srs) completo para essas coordenadas deve ser armazenado em verbatimsrs e o sistema de coordenadas deve ser armazenado em verbatimcoordinatesystem.|
|[verbatimLongitude](https://github.com/sibbr/DarwinCoreBrasil/issues/105)|A longitude original literal do lugar. O elipsoide de coordenadas, geodésico datum, ou sistema de referência espacial (srs) completo para essas coordenadas deve ser armazenado em verbatimsrs e o sistema de coordenadas deve ser armazenado em verbatimcoordinatesystem. | |
|[verbatimCoordinateSystem](https://github.com/sibbr/DarwinCoreBrasil/issues/106)|O formato de coordenadas para o verbatimlatitude e verbatimlongitude ou o verbatimcoordinates do location. | |
|[verbatimSRS](https://github.com/sibbr/DarwinCoreBrasil/issues/107)|O elipsoide, dado geodésico ou sistema de referência espacial (srs) no qual as coordenadas dadas em verbatimlatitude e verbatimlongitude, ou verbatimcoordinates são baseadas.| |
|[footprintWKT](https://github.com/sibbr/DarwinCoreBrasil/issues/108)|Uma representação de texto conhecido (wkt) da forma (pegada, geometria) que define o local. Um local pode ter uma representação de raio de ponto (consulte decimallatitude) e uma representação de pegada, e eles podem diferir uns dos outros. |
|[footprintSRS](https://github.com/sibbr/DarwinCoreBrasil/issues/109)|O elipsoide, dado geodésico ou sistema de referência espacial (srs) sobre o qual a geometria dada na pegada é baseada. | |
|[footprintSpatialFit](https://github.com/sibbr/DarwinCoreBrasil/issues/110)|A razão entre a área da pegada (footprintwkt) e a área da representação espacial verdadeira (original ou mais específica) da localização. Os valores legais são 0, maior ou igual a 1, ou indefinidos. Um valor de 1 é uma correspondência exata ou 100% de sobreposição. Um valor de 0 deve ser usado se a pegada fornecida não contiver completamente a representação original. O footprintspatialfit é indefinido (e deve ser deixado vazio) se a representação original é um ponto sem incerteza e a georreferência dada não é esse mesmo ponto (sem incerteza). Se a georreferência original e a georreferenciada dada forem o mesmo ponto, a pegadaspatialfit será 1. | |
|[georeferencedBy](https://github.com/sibbr/DarwinCoreBrasil/issues/111)|Uma lista (concatenada e separada) de nomes de pessoas, grupos ou organizações que determinaram a georreferência (representação espacial) para o local. | |
|[georeferencedDate](https://github.com/sibbr/DarwinCoreBrasil/issues/112)|A data em que o local foi georreferenciado.| |
|[georeferenceProtocol](https://github.com/sibbr/DarwinCoreBrasil/issues/113)|Uma descrição ou referência aos métodos usados para determinar a pegada espacial, coordenadas e incertezas.| |
|[georeferenceSources](https://github.com/sibbr/DarwinCoreBrasil/issues/114)|Uma lista (concatenada e separada) de mapas, gazetas ou outros recursos usados para georreferenciar a localização, descrita especificamente o suficiente para permitir que qualquer pessoa no futuro use os mesmos recursos.| |
|[georeferenceRemarks](https://github.com/sibbr/DarwinCoreBrasil/issues/115)|Notas ou comentários sobre a determinação da descrição espacial, explicitando pressupostos assumidos em adição ou oposição aos formalizados no método referido no protocolo georreferenciado. | |

### GeologicalContext

| Termo | Definição | Domínio |
| :--- | :--- | :--- |
|[geologicalContextID](https://github.com/sibbr/DarwinCoreBrasil/issues/116)|Informações geológicas, como a estratigrafia, que qualificam uma região ou lugar.| |
|[earliestEonOrLowestEonothem](https://github.com/sibbr/DarwinCoreBrasil/issues/117)|O nome completo do éon geocronológico mais antigo possível ou o eonotema cronoestratigráfica mais baixa ou o nome informal ("pré-cambriano") atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado | |
|[latestEonOrHighestEonothem](https://github.com/sibbr/DarwinCoreBrasil/issues/118)|O nome completo do último éon geocronológico possível ou eonotema cronoestratigráfica mais alto ou o nome informal ("precambriano") atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado. | |
|[earliestEraOrLowestErathem](https://github.com/sibbr/DarwinCoreBrasil/issues/119)|O nome completo da era geocronológica mais antiga possível ou da menor era cronoestratigráfica atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado.| |
|[latestEraOrHighestErathem](https://github.com/sibbr/DarwinCoreBrasil/issues/120)|O nome completo da última era geocronológica possível ou maior era cronoestratigráfica atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado.| |
|[earliestPeriodOrLowestSystem](https://github.com/sibbr/DarwinCoreBrasil/issues/121)|O nome completo do período geocronológico mais antigo possível ou sistema cronoestratigráfico mais baixo atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado.| |
|[earliestEpochOrLowestSeries](https://github.com/sibbr/DarwinCoreBrasil/issues/122)|O nome completo da época geocronológica mais antiga possível ou da menor série cronoestratigráfica atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado.| |
|[latestEpochOrHighestSeries](https://github.com/sibbr/DarwinCoreBrasil/issues/123)|O nome completo da última época geocronológica possível ou maior série cronoestratigráfica atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado.| |
|[earliestAgeOrLowestStage](https://github.com/sibbr/DarwinCoreBrasil/issues/124)|O nome completo da idade geocronológica mais antiga possível ou estágio cronoestratigráfico mais baixo atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado.| |
|[latestAgeOrHighestStage](https://github.com/sibbr/DarwinCoreBrasil/issues/125)|O nome completo da última idade geocronológica possível ou estágio cronoestratigráfico mais alto atribuível ao horizonte estratigráfico a partir do qual o item catalogado foi coletado.| |
|[lowestBiostratigraphicZone](https://github.com/sibbr/DarwinCoreBrasil/issues/126)|Nome completo da zona geoestratigráfica mais baixa possível do horizonte estratigráfico a partir do qual o item catalogado foi coletado.| |
|[highestBiostratigraphicZone](https://github.com/sibbr/DarwinCoreBrasil/issues/127)|Nome completo da zona geoestratigráfica mais alta possível do horizonte estratigráfico a partir do qual o item catalogado foi coletado. | |
|[lithostratigraphicTerms](https://github.com/sibbr/DarwinCoreBrasil/issues/128)|A combinação de todos os nomes litoestratigráficos para a rocha da qual o item catalogado foi coletado.| |
|[group](https://github.com/sibbr/DarwinCoreBrasil/issues/129)|O nome completo do grupo litoestratigráfico do qual o item catalogado foi coletado.| |
|[formation](https://github.com/sibbr/DarwinCoreBrasil/issues/130)|O nome completo da formação litoestratigráfica da qual o item catalogado foi coletado. | |
|[member](https://github.com/sibbr/DarwinCoreBrasil/issues/131)|O nome completo do membro litoestratigráfico do qual o item catalogado foi coletado. | |
|[bed](https://github.com/sibbr/DarwinCoreBrasil/issues/132)|O nome completo do leito litoestratigráfico do qual o item catalogado foi coletado.| |

### Identification

| Termo | Definição | Domínio |
| :--- | :--- | :--- |
|[identificationID](https://github.com/sibbr/DarwinCoreBrasil/issues/133)|Um identificador para a identificação (o conjunto de informações associadas à atribuição de um nome científico). Pode ser um identificador exclusivo global ou um identificador específico para o conjunto de dados. | |
|[verbatimIdentification](https://github.com/sibbr/DarwinCoreBrasil/issues/134)|Uma cadeia de caracteres que representa a identificação taxonômica como ela apareceu no registro original. | |
|[identificationQualifier](https://github.com/sibbr/DarwinCoreBrasil/issues/135)|Uma breve frase ou um termo padrão ("cf.", "aff.") para expressar as dúvidas do determinante sobre a identificação.| |
|[typeStatus](https://github.com/sibbr/DarwinCoreBrasil/issues/136)|Uma lista (concatenada e separada) de tipos nomenclaturais (status do tipo, nome científico tipificado, publicação) aplicada ao assunto. | |
|[identifiedBy](https://github.com/sibbr/DarwinCoreBrasil/issues/137)|Uma lista (concatenada e separada) de nomes de pessoas, grupos ou organizações que atribuíram o táxon ao assunto.| |
|[identifiedByID](https://github.com/sibbr/DarwinCoreBrasil/issues/138)|Uma lista (concatenada e separada) do identificador global exclusivo da pessoa, pessoas, grupos ou organizações responsáveis por atribuir o táxon ao assunto.| |
|[dateIdentified](https://github.com/sibbr/DarwinCoreBrasil/issues/139)|A data em que o sujeito foi determinado como representando o táxon. | |
|[identificationReferences](https://github.com/sibbr/DarwinCoreBrasil/issues/140)|Uma lista (concatenada e separada) de referências (publicação, identificador exclusivo global, url) usadas na identificação. | |
|[identificationVerificationStatus](https://github.com/sibbr/DarwinCoreBrasil/issues/141)|Um indicador categórico do grau em que a identificação taxonômica foi verificada como correta.| |
|[identificationRemarks](https://github.com/sibbr/DarwinCoreBrasil/issues/142)|Comentários ou notas sobre a identificação. | |

### Taxon

| Termo | Definição | Domínio |
| :--- | :--- | :--- |
|[taxonID](https://github.com/sibbr/DarwinCoreBrasil/issues/143)|Um identificador para o conjunto de informações do táxon (dados associados à classe taxon). Pode ser um identificador exclusivo global ou um identificador específico para o conjunto de dados.| |
|[scientificNameID](https://github.com/sibbr/DarwinCoreBrasil/issues/144)|Um identificador para os detalhes nomenclaturais (não taxonômicos) de um nome científico. | |
|[acceptedNameUsageID](https://github.com/sibbr/DarwinCoreBrasil/issues/145)|Um identificador para o uso do nome (significado documentado do nome de acordo com uma fonte) do táxon atualmente válido (zoológico) ou aceito (botânico). | |
|[parentNameUsageID](https://github.com/sibbr/DarwinCoreBrasil/issues/146)|Um identificador para o uso do nome (significado documentado do nome de acordo com uma fonte) do táxon pai direto e mais próximo de classificação superior (em uma classificação) do elemento mais específico do scientificname. | |
|[originalNameUsageID](https://github.com/sibbr/DarwinCoreBrasil/issues/147)|Um identificador para o uso do nome (significado documentado do nome de acordo com uma fonte) no qual o elemento terminal do scientificname foi originalmente estabelecido sob as regras do código nomenclatural associado.| |
|[nameAccordingToID](https://github.com/sibbr/DarwinCoreBrasil/issues/148)|Um identificador para a fonte na qual a circunscrição do conceito de táxon específico é definida ou implícita. Consulte nameaccordingto. | |
|[namePublishedInID](https://github.com/sibbr/DarwinCoreBrasil/issues/149)|Um identificador para a publicação em que o scientificname foi originalmente estabelecido sob as regras do código nomenclatural associado. | |
|[taxonConceptID](https://github.com/sibbr/DarwinCoreBrasil/issues/150)|Um identificador para o conceito taxonômico ao qual o registro se refere - não para os detalhes nomenclaturais de um táxon. | |
|[scientificName](https://github.com/sibbr/DarwinCoreBrasil/issues/151)|O nome científico completo, com informações de autoria e data, se conhecidas. Ao fazer parte de uma identificação, este deve ser o nome na classificação taxonômica de nível mais baixo que pode ser determinado. Este termo não deve conter qualificações de identificação, que devem ser fornecidas no termo identificationqualifier. | |
|[acceptedNameUsage](https://github.com/sibbr/DarwinCoreBrasil/issues/152)|O nome completo, com informações de autoria e data, se conhecidas, do táxon atualmente válido (zoológico) ou aceito (botânico). | |
|[parentNameUsage](https://github.com/sibbr/DarwinCoreBrasil/issues/153)|O nome completo, com informações de autoria e data, se conhecidas, do táxon pai direto e mais próximo (em uma classificação) do elemento mais específico do nome científico. | |
|[originalNameUsage](https://github.com/sibbr/DarwinCoreBrasil/issues/154)|O nome do táxon, com informações de autoria e data, se conhecido, como apareceu originalmente quando estabelecido pela primeira vez sob as regras do código nomenclatural associado. O basiônimo (botânica) ou basônimo (bacteriologia) do nome científico ou o homônimo sênior/anterior para nomes substituídos. | |
|[nameAccordingTo](https://github.com/sibbr/DarwinCoreBrasil/issues/155)|A referência à fonte na qual o conceito específico de táxon circunscrição é definido ou implícito - tradicionalmente significada pelo latim "sensu" ou "sec". (de secundum, que significa "de acordo com"). Para os táxons resultantes de identificações, deve ser dada uma referência às chaves, monografias, especialistas e outras fontes. | |
|[namePublishedIn](https://github.com/sibbr/DarwinCoreBrasil/issues/156)|Uma referência para a publicação em que o scientificname foi originalmente estabelecido sob as regras do código nomenclatural associado. | |
|[namePublishedInYear](https://github.com/sibbr/DarwinCoreBrasil/issues/157)|O ano de quatro dígitos em que o nome científico foi publicado. | |
|[higherClassification](https://github.com/sibbr/DarwinCoreBrasil/issues/158)|Uma lista (concatenada e separada) de nomes de táxons terminando no posto imediatamente superior ao táxon referenciado no registro do táxon. | |
|[kingdom](https://github.com/sibbr/DarwinCoreBrasil/issues/159)|O nome científico completo do reino em que o táxon está classificado. | |
|[phylum](https://github.com/sibbr/DarwinCoreBrasil/issues/160)|Vocabulário controlado obrigatório. O nome científico completo do filo em que o táxon está classificado.| |
|[class](https://github.com/sibbr/DarwinCoreBrasil/issues/161)|O nome científico completo da classe em que o táxon está classificado.| |
|[order](https://github.com/sibbr/DarwinCoreBrasil/issues/162)|O nome científico completo da ordem em que o táxon está classificado. | |
|[family](https://github.com/sibbr/DarwinCoreBrasil/issues/163)|O nome científico completo da família em que o táxon está classificado. | |
|[subfamily](https://github.com/sibbr/DarwinCoreBrasil/issues/164)|O nome científico completo da subfamília em que o táxon está classificado.| |
|[genus](https://github.com/sibbr/DarwinCoreBrasil/issues/165)|O nome científico completo do gênero em que o táxon está classificado.| |
|[genericName](https://github.com/sibbr/DarwinCoreBrasil/issues/166)|O gênero faz parte do nome científico sem autoria.| |
|[subgenus](https://github.com/sibbr/DarwinCoreBrasil/issues/167)|O nome científico completo do subgênero no qual o táxon está classificado. Os valores devem incluir o gênero para evitar confusão homônima.| |
|[infragenericEpithet](https://github.com/sibbr/DarwinCoreBrasil/issues/168)|A parte infragenérica de um nome binomial está acima das espécies, mas abaixo do gênero.| |
|[specificEpithet](https://github.com/sibbr/DarwinCoreBrasil/issues/169)|O nome do primeiro ou epíteto de espécie do nome científico.| |
|[infraspecificEpithet](https://github.com/sibbr/DarwinCoreBrasil/issues/170)|O nome do epíteto infraespecífico mais baixo ou terminal do nome científico, excluindo qualquer designação de classificação.| |
|[cultivarEpithet](https://github.com/sibbr/DarwinCoreBrasil/issues/171)|Parte do nome de uma cultivar, grupo de cultivares que segue o nome científico. | |
|[taxonRank](https://github.com/sibbr/DarwinCoreBrasil/issues/172)|A classificação taxonômica do nome mais específico no nome científico.| |
|[verbatimTaxonRank](https://github.com/sibbr/DarwinCoreBrasil/issues/173)|A classificação taxonômica do nome mais específico no nome científico como aparece no registro original.| |
|[scientificNameAuthorship](https://github.com/sibbr/DarwinCoreBrasil/issues/174)|As informações de autoria para o nome científico formatado de acordo com as convenções do código nomenclatural aplicável. | |
|[vernacularName](https://github.com/sibbr/DarwinCoreBrasil/issues/175)|Um nome comum ou vernáculo. | |
|[nomenclaturalCode](https://github.com/sibbr/DarwinCoreBrasil/issues/176)|O código nomenclatural sob o qual o scientificname é construído.| |
|[taxonomicStatus](https://github.com/sibbr/DarwinCoreBrasil/issues/177)|O status do uso do scientificname como um rótulo para um táxon. Requer parecer taxonômico para definir o escopo de um táxon. Em seguida, são utilizadas regras de prioridade para definir o estatuto taxonômico da nomenclatura contida nesse âmbito, combinado com o parecer dos peritos. Deve estar vinculado a uma referência taxonômica específica que defina o conceito. | |
|[nomenclaturalStatus](https://github.com/sibbr/DarwinCoreBrasil/issues/178)|O estatuto relacionado com a publicação original do nome e a sua conformidade com as regras de nomenclatura pertinentes. Ele é baseado essencialmente em um algoritmo de acordo com as regras de negócios do código. Não requer opinião taxonômica.| |
|[taxonRemarks](https://github.com/sibbr/DarwinCoreBrasil/issues/179)|Comentários ou notas sobre o táxon ou nome. | |

### MeasurementOrFact

| Termo | Definição | Domínio |
| :--- | :--- | :--- |
|[measurementID](https://github.com/sibbr/DarwinCoreBrasil/issues/180)|Um identificador para o measurementorfact (informações relativas a medições, fatos, características ou afirmações). Pode ser um identificador exclusivo global ou um identificador específico para o conjunto de dados. | |
|[measurementType](https://github.com/sibbr/DarwinCoreBrasil/issues/181)|A natureza da medida, fato, característica ou asserção.| |
|[measurementValue](https://github.com/sibbr/DarwinCoreBrasil/issues/182)|O valor da medida, fato, característica ou asserção. | |
|[measurementAccuracy](https://github.com/sibbr/DarwinCoreBrasil/issues/183)|A descrição do erro potencial associado ao measurementvalue. | |
|[measurementUnit](https://github.com/sibbr/DarwinCoreBrasil/issues/184)|As unidades associadas ao measurementvalue.| |
|[measurementDeterminedBy](https://github.com/sibbr/DarwinCoreBrasil/issues/185)|Uma lista (concatenada e separada) de nomes de pessoas, grupos ou organizações que determinaram o valor do measurementorfact. | |
|[measurementDeterminedDate](https://github.com/sibbr/DarwinCoreBrasil/issues/186)|A data em que o measurementorfact foi feito. | |
|[measurementMethod](https://github.com/sibbr/DarwinCoreBrasil/issues/187)|Uma descrição ou referência a (publicação, url) o método ou protocolo usado para determinar a medida, fato, característica ou asserção. | |
|[measurementRemarks](https://github.com/sibbr/DarwinCoreBrasil/issues/188)|Comentários ou notas que acompanham o measurementorfact. | |
