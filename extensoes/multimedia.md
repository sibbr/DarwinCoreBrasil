# Multimedia

Extensão que informa metadados sobre recursos de multimídia, em particular links para arquivos de imagem, vídeo e áudio.

<table>
 <thead>
  <tr>
   <th style="text-align:left;"> Propiedades </th>
   <th style="text-align:left;"> Descrição </th>
   <th style="text-align:left;"> Domínio </th>
   <th style="text-align:left;"> Exemplo </th>
   <th style="text-align:left;"> Link </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> occurrenceID </td>
   <td style="text-align:left;"> Identificador utilizado para relacionar a ocorrência com os arquivos multimídia. Podem ser vários. </td>
   <td style="text-align:left;"> [occurrenceID] </td>
   <td style="text-align:left;"> BR:Refauna:MNHN:Coleoptera:00067 </td>
   <td style="text-align:left;"> 
 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> identifier </td>
   <td style="text-align:left;"> A URL pública que identifica e localiza o arquivo de mídia diretamente, não a página html na qual ele pode ser mostrado. </td>
   <td style="text-align:left;"> [url de acesso a imagem] </td>
   <td style="text-align:left;"> https://image-server-ala.s3.amazonaws.com/Refauna/type_Coleoptera_Histeridae/type_Histeridae_Acritus%20acinus/type_Histeridae_Acritus%20acinus_05.tif </td>
   <td style="text-align:left;"> http://purl.org/dc/terms/identifier </td>
  </tr>
  <tr>
   <td style="text-align:left;"> type </td>
   <td style="text-align:left;"> O tipo de objeto de mídia. Escolher entre StillImage, Sound ou MovingImage. </td>
   <td style="text-align:left;"> StillImage | Sound </td>
   <td style="text-align:left;"> StillImage | Sound </td>
   <td style="text-align:left;"> http://purl.org/dc/terms/type </td>
  </tr>
  <tr>
   <td style="text-align:left;"> format </td>
   <td style="text-align:left;"> O formato do arquivo de mídia. </td>
   <td style="text-align:left;"> JPEG | TIF | PNG | MP4 | JPG </td>
   <td style="text-align:left;"> JPG </td>
   <td style="text-align:left;"> http://purl.org/dc/terms/format </td>
  </tr>
  <tr>
   <td style="text-align:left;"> references </td>
   <td style="text-align:left;"> Uma página da Web html que mostra a imagem ou seus metadados. Esse link deve ser usado para visualizadores de imagens baseados em html, como FSI, e deve ser usado como um link de origem onde quer que o item de mídia seja mostrado. Recomenda-se fornecer essa url mesmo que exista um arquivo de mídia, pois ele será usado para vincular. </td>
   <td style="text-align:left;"> [Link de acesso] </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> http://purl.org/dc/terms/references </td>
  </tr>
  <tr>
   <td style="text-align:left;"> title </td>
   <td style="text-align:left;"> O título do arquivo de mídia. Fortemente recomendado, pois em muitos casos isso será usado como o título/texto do hiperlink. </td>
   <td style="text-align:left;"> [Título do arquivo] </td>
   <td style="text-align:left;"> Acritus (Picnacritus) acinus Marseul, 1863 </td>
   <td style="text-align:left;"> http://purl.org/dc/terms/title </td>
  </tr>
  <tr>
   <td style="text-align:left;"> description </td>
   <td style="text-align:left;"> Uma descrição textual do conteúdo do arquivo de mídia. </td>
   <td style="text-align:left;"> [Descrição] </td>
   <td style="text-align:left;"> Holótipo de Acritus acinus fotografado do Museu de História Natural de Chicago, EUA. </td>
   <td style="text-align:left;"> http://purl.org/dc/terms/description </td>
  </tr>
  <tr>
   <td style="text-align:left;"> created </td>
   <td style="text-align:left;"> A data em que a mídia foi tirada. </td>
   <td style="text-align:left;"> [AAAA-MM-DD] </td>
   <td style="text-align:left;"> [2018-04-23 </td>
   <td style="text-align:left;"> http://purl.org/dc/terms/created </td>
  </tr>
  <tr>
   <td style="text-align:left;"> creator </td>
   <td style="text-align:left;"> O criador e/ou autor do arquivo da imagem, vídeo ou som. </td>
   <td style="text-align:left;"> [Nome completo do criador] </td>
   <td style="text-align:left;"> Elison Caro </td>
   <td style="text-align:left;"> http://purl.org/dc/terms/creator </td>
  </tr>
  <tr>
   <td style="text-align:left;"> contributor </td>
   <td style="text-align:left;"> Qualquer colaborador além do criador que ajudou na gravação da mídia. </td>
   <td style="text-align:left;"> [Nome completo do contribuidor] </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> http://purl.org/dc/terms/contributor </td>
  </tr>
  <tr>
   <td style="text-align:left;"> publisher </td>
   <td style="text-align:left;"> Organização responsável pela disponibilização da mídia. </td>
   <td style="text-align:left;"> [Nome completo da organização] </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> http://purl.org/dc/terms/publisher </td>
  </tr>
  <tr>
   <td style="text-align:left;"> source </td>
   <td style="text-align:left;"> Se o item de mídia foi derivado ou retirado de outra fonte, essa é a referência ao arquivo. </td>
   <td style="text-align:left;"> [Citação da fonte] </td>
   <td style="text-align:left;"> 
 </td>
   <td style="text-align:left;"> http://purl.org/dc/terms/source </td>
  </tr>
  <tr>
   <td style="text-align:left;"> license </td>
   <td style="text-align:left;"> Licença para este objeto de mídia. Pode ser texto ou uma url como o Creative Commons usa. </td>
   <td style="text-align:left;"> CC0 | CC BY | CC BY - NC </td>
   <td style="text-align:left;"> CC BY - NC </td>
   <td style="text-align:left;"> http://purl.org/dc/terms/license </td>
  </tr>
  <tr>
   <td style="text-align:left;"> rightsHolder </td>
   <td style="text-align:left;"> Uma pessoa ou organização que possui ou gerencia direitos sobre a mídia. </td>
   <td style="text-align:left;"> [Nome completo] </td>
   <td style="text-align:left;"> Elison Caro </td>
   <td style="text-align:left;"> http://purl.org/dc/terms/rightsHolder </td>
  </tr>
</tbody>
</table>
