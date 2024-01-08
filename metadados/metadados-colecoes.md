# Boas práticas para preenchimento dos metadados de coleções

## Introdução

## Justificativa

https://ipt.gbif.org/manual/en/ipt/latest/gbif-metadata-profile

### Dataset (Resource)

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Term name </th>
   <th style="text-align:left;"> Description </th>
   <th style="text-align:left;"> Boas práticas </th>
   <th style="text-align:left;"> Exemplos </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 
    <a 
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-resource.html#alternateIdentifier"
     >alternateIdentifier</a></td>
   <td style="text-align:left;"> Identificadores alternativos que são utilizados para rotular este recurso, possivelmente em diferentes sistemas de gerenciamento, podem ser listados aqui. Normalmente não é preciso 
modificar os valores padrão. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 
    <a 
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-resource.html#title"
     >title </td>
   <td style="text-align:left;"> É o nome do conjunto de dados. A recomendação é que corresponda ao campo “datasetName” da planilha de dados. É o título que irá aparecer na página do IPT e será utilizado na citação do recurso.
 </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-resource.html#title" >creator</a> </td>
   <td style="text-align:left;"> As pessoas e organizações que criaram o recurso. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a 
     href= "https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-resource.html#metadataProvider" >metadataProvider</a> </td>
   <td style="text-align:left;"> As pessoas e organizações responsáveis pela produção dos metadados do recurso.
 </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 
    <a
     href= "https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-resource.html#associatedParty" >associatedParty</a> </td>
   <td style="text-align:left;"> Outras pessoas ou organizações associada ao recurso. Essas partes podem desempenhar vários papéis na criação ou manutenção do recurso, e esses papéis devem ser indicados em  "role". </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-resource.html#contact" >contact</a> </td>
   <td style="text-align:left;"> As pessoas e organizações que devem ser contactadas para obter mais informações sobre o recurso ou a quem devem ser dirigidos problemas com o recurso ou seus dados. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-resource.html#pubDate" >pubDate </a> </td>
   <td style="text-align:left;"> A data em que o recurso foi publicado. O formato deve ser representado como CCYY, que representa um ano de 4 dígitos, ou como CCYY-MM-DD, que indica o ano completo, mês e dia. O mês e o dia são componentes opcionais. Os formatos devem estar em conformidade com o padrão ISO 8601. Por exemplo, 2010-09-20. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-resource.html#language" >language </a> </td>
   <td style="text-align:left;"> O idioma que a planilha ou fonte de dados foi preenchida. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-resource.html#additionalInfo" >additionalInfo </a> </td>
   <td style="text-align:left;"> Qualquer informação que não está descrita nos demais campos dos metadados. </td>
   <td style="text-align:left;">  </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-resource.html#url" >url </a> </td>
   <td style="text-align:left;"> A URL do recurso que está disponível online. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href= "https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-resource.html#abstract" >abstract</a> </td>
   <td style="text-align:left;"> Breve resumo do projeto. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
</tbody>
</table>

### Project

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Term </th>
   <th style="text-align:left;"> Definition </th>
   <th style="text-align:left;"> Boas práticas </th>
   <th style="text-align:left;"> Exemplos </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 
    <a
     href= "https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-project.html#title" >title</a> </td>
   <td style="text-align:left;"> Título do projeto. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-project.html#personnel" >personnel</a> </td>
   <td style="text-align:left;"> As pessoas envolvidas no projeto. Pode ser colocado os autores, colaboradores e demais pessoas e instituições associadas ao projeto. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-project.html#funding" >funding</a> </td>
   <td style="text-align:left;"> Informação sobre fontes de financiamento para o projeto (ex. número de contrato, nomes e endereços das fontes de financiamento). Outras informações relacionadas ao financiamento 
também podem ser incluídas </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-project.html#studyAreaDescription" > studyAreaDescription</a> </td>
   <td style="text-align:left;"> Documenta a área física associada com o projeto de pesquisa. Pode incluir descrições da cobertura geográfica, temporal e taxonômica do local de pesquisa.
 </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-project.html#designDescription" >designDescription</a> </td>
   <td style="text-align:left;"> Uma descrição textual geral dos delineamentos da pesquisa. Pode incluir descrições detalhadas dos objetivos, motivações, teorias, hipóteses, estratégias, desenho estatístico e trabalho feito. Pode copiar as informações da introdução e dos métodos de análise do projeto. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
</tbody>
</table>

### People and Organizations

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Term </th>
   <th style="text-align:left;"> Definition </th>
   <th style="text-align:left;"> Boas práticas </th>
   <th style="text-align:left;"> Exemplos </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-party.html#givenName"> givenName </a> </td>
   <td style="text-align:left;"> Primeiro nome do indivíduo associado ao recurso. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-party.html#surName" >surName </a> </td>
   <td style="text-align:left;"> Sobrenome do indivíduo associado ao recurso. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-party.html#organizationName">organizationName</a> </td>
   <td style="text-align:left;"> O nome completo da organização/instuição responsável pelo recurso. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-party.html#positionName"> positionName</a> </td>
   <td style="text-align:left;"> Cargo, função do responsável pelo recurso. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-party.html#electronicMailAddress" >electronicMailAddress</a> </td>
   <td style="text-align:left;"> E-mail da organização ou indivíduo responsável pelo recurso. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-party.html#deliveryPoint" >deliveryPoint</a> </td>
   <td style="text-align:left;"> Endereço da instituição responsável pelo recurso. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-party.html#role" >role</a> </td>
   <td style="text-align:left;"> Utilize este campo para descrever o papel que a parte desempenhou em relação ao recurso. Por exemplo, técnico, revisor, etc. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-party.html#phone">phone</a> </td>
   <td style="text-align:left;"> Telefone da instituição responsável pelo recurso. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-party.html#postalCode">postalCode</a> </td>
   <td style="text-align:left;"> Código Postal (CEP) da instituição responsável pelo recurso. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-party.html#city">city</a> </td>
   <td style="text-align:left;"> Cidade da instituição responsável pelo recurso. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-party.html#administrativeArea">administrativeArea</a> </td>
   <td style="text-align:left;"> Estado/região da instituição responsável pelo recurso. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-party.html#country">country</a> </td>
   <td style="text-align:left;"> País da instituição responsável pelo recurso. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-party.html#onlineUrl">onlineUrl</a> </td>
   <td style="text-align:left;"> Um link para informações online associadas, geralmente um site. Quando é representada por uma organização, esta é a URL de um site ou outras informações online sobre a organização. Se for um indivíduo, pode ser o site pessoal deles ou outras informações online relacionadas. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
</tbody>
</table>

### KeywordSet (General Keywords)

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Term </th>
   <th style="text-align:left;"> Definition </th>
   <th style="text-align:left;"> Boas práticas </th>
   <th style="text-align:left;"> Exemplos </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-resource.html#keyword">keyword</a> </td>
   <td style="text-align:left;"> Uma palavra-chave ou expressão-chave que fornece uma descrição sucinta do recurso ou está associada a ele. Cada campo de palavra-chave deve conter uma única palavra-chave (ou seja, as palavras-chave não devem ser separadas por vírgulas ou outros delimitadores). Por exemplo: biodiversidade. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-resource.html#keywordThesaurus">keywordThesaurus</a> </td>
   <td style="text-align:left;"> O nome do tesauro oficial de palavras-chave do qual a palavra-chave foi derivada. Se não existir um nome oficial de tesauro, mantenha um valor de espaço reservado, como "N/A" (não aplicável), em vez de remover este elemento, pois ele é necessário juntamente com o elemento de palavra-chave para constituir um conjunto de palavras-chave. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
</tbody>
</table>

### Taxonomic Coverage

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Term </th>
   <th style="text-align:left;"> Definition </th>
   <th style="text-align:left;"> Boas práticas </th>
   <th style="text-align:left;"> Exemplos </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#generalTaxonomicCoverage">generalTaxonomicCoverage</a> </td>
   <td style="text-align:left;"> A Cobertura Taxonômica contém informações sobre a taxonomia associada ao recurso. Isso inclui uma lista de nomes de espécies (ou níveis taxonômicos superiores) de um ou mais sistemas de classificação. Uma descrição da variedade de táxons abordados no conjunto de dados ou coleção. Utilize uma lista simples separada por vírgulas de táxons. Por exemplo, "Todas as plantas vasculares foram identificadas até a família ou espécie, musgos e liquens foram identificados como musgo ou liquen." </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#taxonomicClassification">taxonomicClassification </a> </td>
   <td style="text-align:left;"> Information about the range of taxa addressed in the dataset or collection. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#taxonRankName">taxonRankName</a> </td>
   <td style="text-align:left;"> The name of the taxonomic rank for which the Taxon rank value is provided. E.g., phylum, class, genus, species. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#taxonRankValue">taxonRankValue</a> </td>
   <td style="text-align:left;"> The name representing the taxonomic rank of the taxon being described. E.g. Acer would be an example of a genus rank value, and rubrum would be an example of a species rank value, together indicating the common name of red maple. It is recommended to start with Kingdom and include ranks down to the most detailed level possible. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#commonName">commonName</a> </td>
   <td style="text-align:left;"> Applicable common names; these common names may be general descriptions of a group of organisms if appropriate. E.g., invertebrates, waterfowl. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
</tbody>
</table>

### Geographic Coverage

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Term </th>
   <th style="text-align:left;"> Definition </th>
   <th style="text-align:left;"> Boas práticas </th>
   <th style="text-align:left;"> Exemplos </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#geographicDescription">geographicDescription</a> </td>
   <td style="text-align:left;"> A short text description of a dataset’s geographic areal domain. A text description is especially important to provide a geographic setting when the extent of the dataset cannot be well described by the &quot;boundingCoordinates&quot;. E.g., &quot;Manistee River watershed&quot;, &quot;extent of 7 1/2 minute quads containing any property belonging to Yellowstone National Park&quot; </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#geographicDescription">westBoundingCoordinate</a> </td>
   <td style="text-align:left;"> Subfield of boundingCoordinates field covering the W margin of a bounding box. The longitude in decimal degrees of the western-most point of the bounding box that is being described. E.g., -18.25, +25, 45.24755. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#eastBoundingCoordinate">eastBoundingCoordinate</a> </td>
   <td style="text-align:left;"> Subfield of boundingCoordinates field covering the E margin of a bounding box. The longitude in decimal degrees of the eastern-most point of the bounding box that is being described.   E.g., -18.25, +25, 45.24755. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#northBoundingCoordinate">northBoundingCoordinate</a> </td>
   <td style="text-align:left;"> Subfield of boundingCoordinates field covering the N margin of a bounding box.  The longitude in decimal degrees of the northern-most point of the bounding box that is being described. E.g., -18.25, +25, 65.24755. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#northBoundingCoordinate">southBoundingCoordinate</a> </td>
   <td style="text-align:left;"> Subfield of boundingCoordinates field covering the S margin of a bounding box. The longitude in decimal degrees of the southern-most point of the bounding box that is being described. E.g., -118.25, +25, 84.24755. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
</tbody>
</table>

## Temporal Coverage

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Term </th>
   <th style="text-align:left;"> Definition </th>
   <th style="text-align:left;"> Boas práticas </th>
   <th style="text-align:left;"> Exemplos </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#beginDate">beginDate</a> </td>
   <td style="text-align:left;"> Subfield of rangeOfDates field: It may be used multiple times with a endDate field to document multiple date ranges.   A single time stamp signifying the beginning of some time period. The calendar date field is used to express a date, giving the year, month, and day. The format should be one that complies with the International Standards Organization’s standard 8601. The recommended format for EML is YYYY-MM-DD, where Y is the four digit year, M is the two digit month code (01 - 12, where January = 01), and D is the two digit day of the month (01 - 31). This field can also be used to enter just the year portion of a date.  E.g. 2010-09-20 </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#endDate">endDate</a> </td>
   <td style="text-align:left;"> Subfield of rangeOfDates field: It may be used multiple times with a beginDate field to document multiple date ranges.  A single time stamp signifying the end of some time period. The calendar date field is used to express a date, giving the year, month, and day. The format should be one that complies with the International Standards Organization’s standard 8601. The recommended format for EML is YYYY-MM-DD, where Y is the four digit year, M is the two digit month code (01 - 12, where January = 01), and D is the two digit day of the month (01 - 31). This field can also be used to enter just the year portion of a date. E.g. 2010-09-20. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#singleDateTime">singleDateTime</a> </td>
   <td style="text-align:left;"> The SingleDateTime field is intended to describe a single date and time for an event. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
</tbody>
</table>

## Methods

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Term </th>
   <th style="text-align:left;"> Definition </th>
   <th style="text-align:left;"> Boas práticas </th>
   <th style="text-align:left;"> Exemplos </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-methods.html#methodStep">methodStep</a> </td>
   <td style="text-align:left;"> Este campo permite um conjunto de elementos que documentam uma série de métodos e procedimentos utilizados no estudo, e as etapas de processamento que levam à produção dos 
arquivos de dados. Eles incluem descrições de texto dos procedimentos, literatura relevante, software, instrumentação, fonte de dados e quaisquer medidas de controle de qualidade. Cada método deve ser descrito em detalhe suficiente para permitir que outros pesquisadores possam interpretar e repetir, se necessário, o estudo. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-methods.html#qualityControl">qualityControl</a> </td>
   <td style="text-align:left;"> Uma descrição de ações tomadas para controlar ou avaliar a qualidade dos dados resultantes da metodologia utilizada.
 </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-methods.html#sampling">sampling</a> </td>
   <td style="text-align:left;"> Description of sampling procedures including the geographic, temporal and taxonomic coverage of the study. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-methods.html#sampling">studyExtent</a> </td>
   <td style="text-align:left;"> Documenta a área física associada com o projeto de pesquisa. Pode incluir descrições da cobertura geográfica, temporal e taxonômica do local de pesquisa. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-methods.html#samplingDescription"> samplingDescription </a> </td>
   <td style="text-align:left;"> Descrição dos protocolos utilizados durante o projeto de pesquisa. O conteúdo deste elemento pode ser similar à descrição dos métodos encontrados na seção "métodos" de artigos de revistas 
científicas. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
</tbody>
</table>

### Intellectual Property Rights

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Term </th>
   <th style="text-align:left;"> Definition </th>
   <th style="text-align:left;"> Boas práticas </th>
   <th style="text-align:left;"> Exemplos </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-dataset.html#purpose">purpose</a> </td>
   <td style="text-align:left;"> A description of the purpose of this dataset. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-resource.html#intellectualRights">intellectualRights</a> </td>
   <td style="text-align:left;"> A rights management statement for the resource, or reference a service providing such information. Rights information encompasses Intellectual Property Rights (IPR), Copyright, and various Property Rights. In the case of a data set, rights might include requirements for use, requirements for attribution, or other requirements the owner would like to impose. E.g., © 2001 Regents of the University of California Santa Barbara. Free for use by all individuals provided that the owners are acknowledged in any use or publication. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
</tbody>
</table>

### Additional Metadata + Natural Collections Description Data (NCD) Related

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Term </th>
   <th style="text-align:left;"> Definition </th>
   <th style="text-align:left;"> Boas práticas </th>
   <th style="text-align:left;"> Exemplos </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> dateStamp </td>
   <td style="text-align:left;"> The dateTime the metadata document was created or modified. E.g., 2002-10-23T18:13:51.235+01:00 </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> metadataLanguage </td>
   <td style="text-align:left;"> The language in which the metadata document (as opposed to the resource being described by the metadata) is written. Composed of an ISO639-2/T three-letter language code and an ISO3166-1 three-letter country code. E.g., en_GB </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> hierarchyLevel </td>
   <td style="text-align:left;"> Dataset level to which the metadata applies; default value is “dataset” E.g., dataset </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-literature.html#citation">citation</a></td>
   <td style="text-align:left;"> The citation for the work itself. See eml </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> bibliography </td>
   <td style="text-align:left;"> A list of citations (see below) that form a bibliography on literature related / used in the dataset </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> physical </td>
   <td style="text-align:left;"> A container element for all of the elements that let you describe the internal/external characteristics and distribution of a data object (e.g., dataObject, dataFormat, distribution). Can repeat. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> resourceLogoUrl </td>
   <td style="text-align:left;"> URL of the logo associated with a resource. E.g., http://www.gbif.org/logo.jpg </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> parentCollectionIdentifier </td>
   <td style="text-align:left;"> Subfield of collection field. Is an optional field. Identifier for the parent collection for this sub-collection. Enables a hierarchy of collections and sub collections to be built. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> collectionName </td>
   <td style="text-align:left;"> Subfield of collection field. Is an optional field. Official name of the Collection in the local language. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> collectionIdentifier </td>
   <td style="text-align:left;"> Subfield of collection field.  Is an optional field. The URI (LSID or URL) of the collection. In RDF, used as URI of the collection resource. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> formationPeriod </td>
   <td style="text-align:left;"> Text description of the time period during which the collection was assembled. E.g., &quot;Victorian&quot;, or &quot;1922 - 1932&quot;, or &quot;c. 1750&quot;. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> livingTimePeriod </td>
   <td style="text-align:left;"> Time period during which biological material was alive (for palaeontological collections). </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> specimenPreservationMethod </td>
   <td style="text-align:left;"> Picklist keyword indicating the process or technique used to prevent physical deterioration of non-living collections. Expected to contain an instance from the Specimen Preservation Method Type Term vocabulary.   E.g., formaldehyde. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> jgtiCuratorialUnit </td>
   <td style="text-align:left;"> A quantitative descriptor (number of specimens, samples or batches). The actual quantification could be covered by



an exact number of “JGI-units” in the collection plus a measure of uncertainty (± x);


a range of numbers (x to x), with the lower value representing an exact number, when the higher value is omitted.



The discussion concluded that the quantification should encompass all specimens, not only those that have not yet been digitized. This is to avoid having to update the numbers too often. The number of non-public data (not digitized or not accessible) can be calculated from the GBIF numbers as opposed to the JGTI-data. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
</tbody>
</table>
