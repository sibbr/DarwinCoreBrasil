# Boas práticas para preenchimento dos metadados de coleções

## Introdução

## Justificativa

https://ipt.gbif.org/manual/en/ipt/latest/gbif-metadata-profile

### Dataset (Recurso)

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Nome do termo </th>
   <th style="text-align:left;"> Descrição </th>
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
   <td style="text-align:left;"> Identificadores alternativos que são utilizados para rotular o recurso. Normalmente não é preciso modificar os valores padrão. </td>
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
   <td style="text-align:left;"> As pessoas e organizações que devem ser contatadas para obter mais informações sobre o recurso ou a quem devem ser dirigidos problemas com o recurso ou seus dados. </td>
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

### Projeto

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Termo </th>
   <th style="text-align:left;"> Definição </th>
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

### Pessoas e Organizações

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Termo </th>
   <th style="text-align:left;"> Definição </th>
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

### Palavras-chaves

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Termo </th>
   <th style="text-align:left;"> Definição </th>
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

### Cobertura Taxonômica

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Termo </th>
   <th style="text-align:left;"> Definição </th>
   <th style="text-align:left;"> Boas práticas </th>
   <th style="text-align:left;"> Exemplos </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#generalTaxonomicCoverage">generalTaxonomicCoverage</a> </td>
   <td style="text-align:left;"> A Cobertura Taxonômica contém informações sobre a taxonomia associada ao recurso. Isso inclui uma lista de nomes de espécies (ou níveis taxonômicos superiores) de um ou mais sistemas de classificação. Uma descrição da variedade de táxons abordados no conjunto de dados ou coleção. Utilize uma lista simples separada por vírgulas de táxons. Por exemplo, "Todas as plantas vasculares foram identificadas até a família ou espécie, musgos e líquens foram identificados como musgo ou líquen." </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#taxonomicClassification">taxonomicClassification </a> </td>
   <td style="text-align:left;"> Informações sobre a variedade de táxons abordados no conjunto de dados ou coleção. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#taxonRankName">taxonRankName</a> </td>
   <td style="text-align:left;"> O nome do nível taxonômico para o qual o valor do rank taxonômico é fornecido. Por exemplo, filo, classe, gênero, espécie.
 </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#taxonRankValue">taxonRankValue</a> </td>
   <td style="text-align:left;"> O nome que representa o nível taxonômico do táxon sendo descrito. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#commonName">commonName</a> </td>
   <td style="text-align:left;"> Nomes comuns. Esses nomes comuns podem ser descrições gerais de um grupo de organismos. Por exemplo, invertebrados, aves aquáticas.
 </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
</tbody>
</table>

### Cobertura Geográfica

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Termo </th>
   <th style="text-align:left;"> Definição </th>
   <th style="text-align:left;"> Boas práticas </th>
   <th style="text-align:left;"> Exemplos </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#geographicDescription">geographicDescription</a> </td>
   <td style="text-align:left;"> Uma breve descrição textual do domínio espacial de uma coleção de dados. Uma descrição textual é especialmente importante para fornecer um contexto geográfico quando a extensão do conjunto de dados não pode ser bem descrita pelas "boundingCoordinates" (coordenadas delimitadoras). Por exemplo, "Bacia do Rio Manistee", "extensão dos quadrantes de 7 minutos e meio que contêm qualquer propriedade pertencente ao Parque Nacional de Yellowstone. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#geographicDescription">westBoundingCoordinate</a> </td>
   <td style="text-align:left;"> Subcampo do campo boundingCoordinates que abrange a margem oeste de uma caixa delimitadora. A longitude em graus decimais do ponto mais ocidental da caixa delimitadora que está sendo descrita.</td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#eastBoundingCoordinate">eastBoundingCoordinate</a> </td>
   <td style="text-align:left;"> Subcampo do campo boundingCoordinates que abrange a margem leste de uma caixa delimitadora. A longitude em graus decimais do ponto mais oriental da caixa delimitadora que está sendo descrita. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#northBoundingCoordinate">northBoundingCoordinate</a> </td>
   <td style="text-align:left;"> Subcampo do campo boundingCoordinates que abrange a margem norte de uma caixa delimitadora. A longitude em graus decimais do ponto mais setentrional da caixa delimitadora que está sendo descrita.  </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#northBoundingCoordinate">southBoundingCoordinate</a> </td>
   <td style="text-align:left;"> Subcampo do campo boundingCoordinates que abrange a margem sul de uma caixa delimitadora. A longitude em graus decimais do ponto mais meridional da caixa delimitadora que está sendo descrita. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
</tbody>
</table>

## Cobertura Temporal

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Termo </th>
   <th style="text-align:left;"> Definição </th>
   <th style="text-align:left;"> Boas práticas </th>
   <th style="text-align:left;"> Exemplos </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#beginDate">beginDate</a> </td>
   <td style="text-align:left;"> Subcampo do campo rangeOfDates: Pode ser usado várias vezes com um campo endDate para indicar vários intervalos de datas. Uma única data e hora que representa o início de algum período de tempo. O campo de data do calendário é usado para expressar uma data, fornecendo o ano, mês e dia. O formato deve estar em conformidade com o padrão 8601 da Organização Internacional de Normalização. O formato recomendado para EML é AAAA-MM-DD, onde A é o ano de quatro dígitos, M é o código de mês de dois dígitos (01 - 12, onde janeiro = 01), e D é o dia do mês de dois dígitos (01 - 31). Este campo também pode ser usado para inserir apenas a parte do ano de uma data. Por exemplo, 2010-09-20. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#endDate">endDate</a> </td>
   <td style="text-align:left;"> Subcampo do campo rangeOfDates: Pode ser usado várias vezes com um campo beginDate para documentar vários intervalos de datas. Uma única data e hora que representa o final de algum período de tempo. O campo de data do calendário é usado para expressar uma data, fornecendo o ano, mês e dia. O formato deve estar em conformidade com o padrão 8601 da Organização Internacional de Normalização. O formato recomendado para EML é AAAA-MM-DD, onde A é o ano de quatro dígitos, M é o código de mês de dois dígitos (01 - 12, onde janeiro = 01), e D é o dia do mês de dois dígitos (01 - 31). Este campo também pode ser usado para inserir apenas a parte do ano de uma data. Por exemplo, 2010-09-20.  </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-coverage.html#singleDateTime">singleDateTime</a> </td>
   <td style="text-align:left;"> O campo SingleDateTime destina-se a descrever uma única data e hora para um evento. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
</tbody>
</table>

## Métodos

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Termo </th>
   <th style="text-align:left;"> Definição </th>
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
   <td style="text-align:left;"> Descrição dos procedimentos de amostragem, incluindo a cobertura geográfica, temporal e taxonômica do estudo.
 </td>
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

### Direitos de Propriedade Intelectual

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Termo </th>
   <th style="text-align:left;"> Definição </th>
   <th style="text-align:left;"> Boas práticas </th>
   <th style="text-align:left;"> Exemplos </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-dataset.html#purpose">purpose</a> </td>
   <td style="text-align:left;"> Uma descrição do propósito deste conjunto de dados.
 </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;">
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-resource.html#intellectualRights">intellectualRights</a> </td>
   <td style="text-align:left;"> Uma declaração de gerenciamento de direitos para o recurso, ou referência a um serviço que fornece tais informações. As informações sobre direitos abrangem Direitos de Propriedade Intelectual (DPI), Direitos Autorais e vários Direitos de Propriedade. No caso de um conjunto de dados, os direitos podem incluir requisitos de uso, requisitos de atribuição ou outros requisitos que o proprietário deseja impor. Por exemplo, © 2001 Regents da Universidade da Califórnia, Santa Bárbara. Livre para uso por todas as pessoas, desde que os proprietários sejam reconhecidos em qualquer uso ou publicação. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
</tbody>
</table>

### Metadado Adicional + Dados de Descrição de Coleções Naturais

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Termo </th>
   <th style="text-align:left;"> Definição </th>
   <th style="text-align:left;"> Boas práticas </th>
   <th style="text-align:left;"> Exemplos </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> dateStamp </td>
   <td style="text-align:left;"> A data e hora em que o documento de metadados foi criado ou modificado. Por exemplo, 2002-10-23T18:13:51.235+01:00. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> metadataLanguage </td>
   <td style="text-align:left;"> O idioma no qual o documento de metadados (em oposição ao recurso sendo descrito pelos metadados) está escrito. Composto por um código de idioma de três letras ISO639-2/T e um código de país de três letras ISO3166-1. Por exemplo, en_GB. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> hierarchyLevel </td>
   <td style="text-align:left;"> Nível do conjunto de dados ao qual os metadados se aplicam. O valor padrão é "dataset".  </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 
    <a
     href="https://sbclter.msi.ucsb.edu/external/InformationManagement/EML_211_schema/docs/eml-2.1.1/eml-literature.html#citation">citation</a></td>
   <td style="text-align:left;"> A citação para o próprio trabalho. Consulte o formato EML (Ecological Metadata Language) para obter detalhes específicos sobre como estruturar essa citação nos metadados. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> bibliography </td>
   <td style="text-align:left;"> Uma lista de citações que formam uma bibliografia sobre literatura relacionada ou utilizada no conjunto de dados. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> physical </td>
   <td style="text-align:left;"> Um elemento contêiner para todos os elementos que permitem descrever as características internas/externas e distribuição de um objeto de dados (por exemplo, dataObject, dataFormat, distribution). Pode se repetir. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> resourceLogoUrl </td>
   <td style="text-align:left;">
URL do logotipo associado a um recurso. Por exemplo, http://www.gbif.org/logo.jpg. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> parentCollectionIdentifier </td>
   <td style="text-align:left;"> Identificador para a coleção principal desta subcoleção. Permite a construção de uma hierarquia de coleções e subcoleções. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> collectionName </td>
   <td style="text-align:left;"> Nome oficial da coleção no idioma local. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> collectionIdentifier </td>
   <td style="text-align:left;"> O URI (LSID ou URL) da coleção. Em RDF, utilizado como URI do recurso da coleção. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> formationPeriod </td>
   <td style="text-align:left;"> Descrição textual do período de tempo durante o qual a coleção foi reunida. Por exemplo, "Victoriana", ou "1922 - 1932", ou "cerca de 1750". </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> livingTimePeriod </td>
   <td style="text-align:left;"> Período de tempo durante o qual o material biológico estava vivo (para coleções paleontológicas). </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> specimenPreservationMethod </td>
   <td style="text-align:left;"> Palavra-chave da lista de opções indicando o processo ou técnica usada para evitar a deterioração física de coleções não vivas. É esperado que se inclua um termo do vocabulário de Tipos de Método de Preservação de Espécimes. Por exemplo, formaldeído. </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> jgtiCuratorialUnit </td>
   <td style="text-align:left;"> Um descritor quantitativo (número de espécimes, amostras ou lotes). A quantificação real pode ser coberta por um número exato de "unidades JGI" na coleção, mais uma medida de incerteza (± x); uma faixa de números (x a x), com o valor mais baixo representando um número exato, quando o valor mais alto é omitido. A quantificação deve abranger todos os espécimes, não apenas aqueles que ainda não foram digitalizados. O número de dados não públicos (não digitalizados ou não acessíveis) pode ser calculado a partir dos números do GBIF.  </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
</tbody>
</table>
