# DarwinCoreBrasil
Termos DarwinCore para compartilhamento de dados e informações em biodiversidade com o objetivo identificar termos com vocabulário controlado e definir um conjunto de boas práticas no uso do padrão no Brasil junto com todas as instituições e organizações que produzem dados. 
https://dwc.tdwg.org/terms/

## Justificativa
O uso do padrão DarwinCore para compartilhamento de dados em biobiversidade tem aumentado no Brasil sendo que quase todas as instituições, organizações, fundações, programas e projetos que trabalham com dados tem publicado em alguma plataforma seja nacional ou internacional. Devido a grande heterogeneidade de tipos de dados, coleções e grupos existem dúvidas nos preenchimentos de cada campo. A discussão dos termos e melhores práticas vai contribuir a organizar os dados corretamente no Brasil, tendo em consideração todas as instituições e suas respetivas demandas e termos a serem considerados e compartilhados. 

## Classes e Termos DarwinCore

| [Record-level](https://github.com/sibbr/DarwinCoreBrasil#record-level) | [Ocurrence](https://github.com/sibbr/DarwinCoreBrasil#occurrence) | [Organism](https://github.com/sibbr/DarwinCoreBrasil#organism) | [MaterialSample](https://github.com/sibbr/DarwinCoreBrasil#materialsample)| [Event](https://github.com/sibbr/DarwinCoreBrasil#event) | [Location](https://github.com/sibbr/DarwinCoreBrasil#location) | [GeologicalContext](https://github.com/sibbr/DarwinCoreBrasil#geologicalcontext) | [Identification](https://github.com/sibbr/DarwinCoreBrasil#identification) | [Taxon](https://github.com/sibbr/DarwinCoreBrasil#taxon) | [MeasurementOrFact](https://github.com/sibbr/DarwinCoreBrasil#measurementorfact)
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

### Record-level

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/1" target="_blank" rel="noopener noreferrer"
        >datasetName</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:datasetName"
        >https://dwc.tdwg.org/terms/#dwc:datasetName</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome que identifica o conjunto de dados do qual o registro foi
        derivado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">datasetName</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Coleções de Zoologia:
            <a
              href="https://collectory.sibbr.gov.br/collectory/public/show/dr797"
              >Coleção de Mamíferos do MNRJ</a
          </li>
          <li>
            Herbários:
            <a
              href="https://collectory.sibbr.gov.br/collectory/public/show/dr839"
              >Rio de Janeiro Botanical Garden Herbarium Collection</a
          </li>
          <li>
            Subcoleções: <a href="https://collectory.sibbr.gov.br/collectory/public/showDataResource/dr895">Coleção/Subcoleção de Odonata da Coleção de
            Entomologia do MNRJ</a>
          </li>
          <li>
            Programa PELD:
            <a
              href="https://collectory.sibbr.gov.br/collectory/public/show/dr506"
              >PELD - ELPA | Ecology of Lahille’s bottlenose dolphin Tursiops
              truncatus gephyreus in the Patos Lagoon estuary and adjacent
              marine coast</a
            >
          </li>
          <li>
            Programa PPBio: <a href="https://collectory.sibbr.gov.br/collectory/public/show/dr651">PPBioMA | PPBio: Morcegos no Parque Nacional da
            Chapada dos Guimarães</a>
          </li>
          <li>
            Projeto de pesquisa: PREVIR:
            <a
              href="https://collectory.sibbr.gov.br/collectory/public/show/dr642"
              >Monitoramento de Fauna do Projeto Rede de Vigilância de Vírus
              (Previr). Observatório Pantanal AVES MT-2</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/2">type</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dc:type"
        >https://dwc.tdwg.org/terms/#dc:type</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">A natureza ou gênero do recurso.</td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        StillImage | MovingImage | Sound | PhysicalObject | Event | Text
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            PhysicalObject: exsicata ou espécime preservado
          </li>
          <li>
            Sound: arquivo com som. Colocar a url de acesso ao arquivo no termo
            associatedMedia
          </li>
          <li>StillImage: imagem da exsicata ou espéciem sem a amostra</li>
          <li>Text: registros obtidos da literatura</li>
          <li>Event: dados de ocorrência ou evento de amostragem sem coleta</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/3">modified</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dcterms:modified"
        >https://dwc.tdwg.org/terms/#dcterms:modified</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A data-hora mais recente em que o recurso foi alterado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">AAAA-MM-DD</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>2023-07-06</li>
          <li>2022-04-23</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/4">language</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dc:language"
        >https://dwc.tdwg.org/terms/#dc:language</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">A língua do recurso.</td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">pt | en | es</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>pt: Português</li>
          <li>en: Inglês</li>
          <li>es: Espanhol</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/5">license</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dcterms:license"
        >https://dwc.tdwg.org/terms/#dcterms:license</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A licença de uso do registro ou dado de pesquisa estabelecida para a utilização por outros usuários.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">CC0 | CC BY | CC BY - NC</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            <a href="https://sibbr.gov.br/page/termo-de-uso-de-dados.html"
              >Termo de uso SiBBr</a
            >
          </li>
          <li>
            <a href="https://sibbr.gov.br/page/licenca-uso.html">Licença CC0</a>
          </li>
          <li>
            <a href="https://sibbr.gov.br/page/licenca-uso.html"
              >Licença CC BY</a
            >
          </li>
          <li>
            <a href="https://sibbr.gov.br/page/licenca-uso.html"
              >Licença CC BY - NC</a
            >
          </li>
          <li><a href="https://www.gbif.org/pt/terms">Creative Commons</a></li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/6"
        >rightsHolder</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dcterms:rightsHolder"
        >https://dwc.tdwg.org/terms/#dcterms:rightsHolder</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Organização detentora dos direitos autorais do registro.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Nome completo escrito em extenso da instituição, fundação ou órgão com
        os direitos de propriedade do registro
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Universidade do Vale do Taquari</li>
          <li>Fundação Renova</li>
          <li>Programa de Pesquisas em Biodiversidade</li>
          <li>Museu de Pesquisas da Amazônia</li>
          <li>Instituto Profauna</li>
          <li>Conselho Nacional de Desenvolvimento Científico e Tecnológico</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/7"
        >accessRights</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dcterms:accessRights"
        >https://dwc.tdwg.org/terms/#dcterms:accessRights</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Informações sobre quem pode acessar ao registro.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Link para a política de dados e acesso da instituição
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            <a
              href="https://cidacs.bahia.fiocruz.br/plataformazika/wp-content/uploads/2022/04/POLITICA-DE-DADO-DA-FIOCRUZ.pdf"
              >Política de dados da Fiocruz</a
            >
          </li>
          <li>
            <a
              href="https://ppbio.inpa.gov.br/sites/default/files/politica_dou.pdf"
              >Política de dados do PPBio</a
            >
          </li>
          <li>
            <a
              href="https://dspace.jbrj.gov.br/jspui/bitstream/doc/125/1/Plano_de_Dados_Abertos_JBRJ_2021_2022_Versao_1.1.pdf"
              > Política de dados do JBRJ</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/8"
        >bibliographicCitation</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dcterms:bibliographicCitation"
        >https://dwc.tdwg.org/terms/#dcterms:bibliographicCitation</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma referência bibliográfica para o recurso como uma declaração
        indicando como esse registro deve ser citado (atribuído) quando
        utilizado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Link de acesso</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/9"
        >references</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dcterms:references"
        >https://dwc.tdwg.org/terms/#dcterms:references</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A referência ou citação oficial utilizada para descrever e/ou completar as informações do registro.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Link de acesso</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        Referenciar um táxon
        <ul>
        <li>
        Flora e Funga do Brasil:Shimizu, G.H.; Souza, L.F.; Gonçalves, D.J.P.; França, F. Vochysiaceae in Flora e Funga do Brasil. Jardim Botânico do Rio de Janeiro. Disponível em: <a href="https://floradobrasil.jbrj.gov.br/FB15294">https://floradobrasil.jbrj.gov.br/FB15294</a>. Acesso em: 07 jul. 2023
        </li>
        <li>
        Catálogo Taxonômico da Fauna do Brasil: Abreu-Júnior EF,Casali D 2023. Myrmecophagidae in Catálogo Taxonômico da Fauna do Brasil. PNUD. Disponível em: <a href="http://fauna.jbrj.gov.br/fauna/faunadobrasil/40390" >http://fauna.jbrj.gov.br/fauna/faunadobrasil/40390</a >. Acesso em: 07 Jul. 2023
        </li>
        <li>
        Catalogue of Life (CoL): <a href="https://www.catalogueoflife.org/data/taxon/3DR25"> https://www.catalogueoflife.org/data/taxon/3DR25 </a>
        </li>
        <li>
        WoRMS: Froese, R. and D. Pauly. Editors. (2023). FishBase. Rhincodon typus Smith, 1828. Accessed through: World Register of Marine Species at: <a href="https://www.marinespecies.org/aphia.php?p=taxdetails&id=105847"> https://www.marinespecies.org/aphia.php?p=taxdetails&id=105847 </a> on 2023-07-13</a >
        </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/10"
        >institutionID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:institutionID"
        >https://dwc.tdwg.org/terms/#dwc:institutionID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador da instituição que detém a guarda do(s) objeto(s) ou
        das informações referidas no registo.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/11"
        >collectionID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:collectionID"
        >https://dwc.tdwg.org/terms/#dwc:collectionID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para a coleção ou conjunto de dados do qual o registro
        foi derivado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/12"
        >datasetID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:datasetID"
        >https://dwc.tdwg.org/terms/#dwc:datasetID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para a coleção ou conjunto de dados do qual o registro
        foi derivado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Instituição]:[Programa]:[Projeto]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>RENOVA: RENOVA:PMBA:P164</li>
          <li>ICMBio: ICMBIO:SALVE:37463</li>
          <li>ICMBIO:SISBIO:XXXXX</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/13"
        >institutionCode</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:institutionCode"
        >https://dwc.tdwg.org/terms/#dwc:institutionCode</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome (ou sigla) em uso pela instituição que detém a guarda do(s)
        objeto(s) ou das informações referidas no registro.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Acrônimo da instituição]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>UFPR</li>
          <li>MZUSP</li>
          <li>EMBRAPA</li>
          <li>INPA</li>
          <li>MPEG</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/14"
        >collectionCode</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:collectionCode"
        >https://dwc.tdwg.org/terms/#dwc:collectionCode</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome, acrônimo ou código que identifica a coleção ou o conjunto de
        dados do qual o registro foi derivado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Acrônimo da coleção]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>RB</li>
          <li>ZUEC-MAM</li>
          <li>
            CBAM
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/15"
        >ownerInstitutionCode</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:ownerInstitutionCode"
        >https://dwc.tdwg.org/terms/#dwc:ownerInstitutionCode</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome (ou sigla) utilizado pela instituição proprietária do(s)
        objeto(s) ou das informações referidas no registro.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/16"
        >basisOfRecord</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:basisOfRecord"
        >https://dwc.tdwg.org/terms/#dwc:basisOfRecord</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A natureza específica do registro de dados.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        PreservedSpecimen | HumanObservation | MaterialSample | LivingSpecimen |
        MachineObservation
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>PreservedSpecimen: exsicata, espécime, cultivo</li>
          <li>MaterialSample: tecido, sangue, fêmur</li>
          <li>
            HumanObservation: inventário, evento de amostragem, ocorrência (ciência cidadã)
          </li>
          <li>MachineObservation: fotografia, câmera trap</li>
          <li>LivingSpecimen: Zoológico ou Jardim Botânico</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/17"
        >informationWithheld</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:informationWithheld"
        >https://dwc.tdwg.org/terms/#dwc:informationWithheld</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Informações adicionais que existem, mas que não foram compartilhadas no
        registro fornecido.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Coordenadas exatas disponíveis | Identificação até nivel de espécie
        disponível e não publicado
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Coordenadas exatas disponíveis</li>
          <li>Identificação até nivel de espécie e não publicado</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/18"
        >dataGeneralizations</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:dataGeneralizations"
        >https://dwc.tdwg.org/terms/#dwc:dataGeneralizations</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
       	Ações tomadas para tornar os dados compartilhados menos específicos ou completos do que em sua forma original. Sugere que dados alternativos de maior qualidade podem estar disponíveis mediante solicitação.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Ponto centróide (Estado, Município ou Localidade) para obtenção de
            coordenada
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/19"
        >dynamicProperties</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:dynamicProperties"
        >https://dwc.tdwg.org/terms/#dwc:dynamicProperties</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista de medidas, fatos, características ou afirmações adicionais
        sobre o registro. Destinado a fornecer um mecanismo para conteúdo
        estruturado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        [Formato JSON](https://www.json.org/json-pt.html)
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Coleções de zoologia:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/1dc6ebe2-f43f-4e74-8b5d-bbd3e8a40147"
              >Coleção de Aves da Unisinos</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

--- 

### Occurrence

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/20"
        >occurrenceID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:occurrenceID"
        >https://dwc.tdwg.org/terms/#dwc:occurrenceID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para a ocorrência (em oposição a um registro digital
        específico da ocorrência). Na ausência de um identificador exclusivo
        global persistente, construa um a partir de uma combinação de
        identificadores no registro que tornará o id de ocorrência globalmente
        exclusivo.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        <ul>
        <li>Coleção: [BR]:[InstitutionCode]:[CollectionCode]:[CatalogNumber]</li>
        <li>Evento amostragem: [EventID]_[id] | [EventID]_[Placa árvore ou anel captura]</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>BR:UFPR:Palotina:CESP010027</li>
          <li>br:ppbio:comcerrado:PNCG_Cidade_de_Pedra_TA_3000:1</li>
          <li>BRAZIL:PREVIR:21MT1A00001:MOUTH_SWAB</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/21"
        >catalogNumber</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:catalogNumber"
        >https://dwc.tdwg.org/terms/#dwc:catalogNumber</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador (de preferência exclusivo) para o registro dentro do
        conjunto de dados ou coleção.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[collectionCode]_[catalogNumber]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>RB_23493</li>
          <li>ACAM_354.1</li>
          <li>CESP010027</li>
          <li>INPA-ACA 000009</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/22"
        >recordNumber</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:recordNumber"
        >https://dwc.tdwg.org/terms/#dwc:recordNumber</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador dado à ocorrência no momento em que foi registrada.
        Muitas vezes serve como um link entre as notas de campo e um registro de
        ocorrência, como o número de um coletor de amostras.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Número de registro]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Herbário:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/bc8b4528-9a08-48ca-b3e4-da16ffd03ff2"
              >Herbário da Universidade Federal do Mato Grosso do Sul</a
            >
          </li>
          <li>
            Coleções de zoologia:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/28542092-5804-4de0-a9bb-9991cfc1786d"
              >Coleção de Répteis do Museu Nacional (MNRJ)</a
            >
          </li>
          <li>
            Coleções de zoologia:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/c0292efd-b25a-4c21-9c2d-3e2b0801c5a6"
              >Coleção de Mamíferos da Universidade do Mato Grosso (UFMT)</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/23"
        >recordedBy</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:recordedBy"
        >https://dwc.tdwg.org/terms/#dwc:recordedBy</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de nomes de pessoas, grupos ou
        organizações responsáveis pelo registro da ocorrência original. O
        coletor ou observador primário, especialmente aquele que aplica um
        identificador pessoal (recordnumber), deve ser listado primeiro.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[SOBRENOME, Inicial nome]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Herbário:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/86b9fb12-c2b9-4695-ade6-b0b00ba4e0a5"
              >Herbário IBGE</a
            >
          </li>
          <li>
            Projeto PELD:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/4cc24396-7858-4bc0-b0d6-5a9849633e72"
              >PELD - AGCV | Pequenos mamíferos terrestres em fragmentos de cerradão no Distrito Federal</a
            >
          </li>
          <li>
            Coleções de zoologia:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/34c20a2b-f1b3-4db3-adcd-f6fddbf534b1"
              >Coleção Entomológica do Instituto Oswaldo Cruz</a
            <
            </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/24"
        >recordedByID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:recordedByID"
        >https://dwc.tdwg.org/terms/#dwc:recordedByID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) do identificador global exclusivo da
        pessoa, pessoas, grupos ou organizações responsáveis pelo registro da
        ocorrência original.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/25"
        >individualCount</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:individualCount"
        >https://dwc.tdwg.org/terms/#dwc:individualCount</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O número de indivíduos presentes no momento da ocorrência.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Número de indivíduos]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Projeto:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/76a8b7c1-f4c9-4e79-809f-8631daa79eb3"
              >Soil Macrofauna communities Atlantic Rainforest</a
            >
          </li>
          <li>
            Coleções de zoologia:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/d53bd6f5-5da0-4d68-99c4-d0c0297dcf13"
              > ICMBio: Sisbio-Dibio</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/26"
        >organismQuantity</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:organismQuantity"
        >https://dwc.tdwg.org/terms/#dwc:organismQuantity</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um número ou valor de enumeração para a quantidade de organismos.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        27 (organismQuantity) com indíviduos (organismQuantityType)
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Projeto PELD:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/38464ecc-bb48-4df9-94b2-cad29389fa85"
              >	PELD - ABRS | Avaliação e monitoramento dos recifes de Abrolhos</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/27"
        >organismQuantityType</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:organismQuantityType"
        >https://dwc.tdwg.org/terms/#dwc:organismQuantityType</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O tipo de sistema de quantificação utilizado para a quantidade de
        organismos.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        27 (organismQuantity) com indíviduos (organismQuantityType)
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Projeto PELD:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/38464ecc-bb48-4df9-94b2-cad29389fa85"
              >PELD - ABRS | Avaliação e monitoramento dos recifes de Abrolhos</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/28">sex</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:sex"
        >https://dwc.tdwg.org/terms/#dwc:sex</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O sexo do(s) indivíduo(s) biológico(s) representado(s) na ocorrência.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Macho | Fêmea | Hermafrodita | Male | Female | Hermaphrodite
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Coleções de zoologia:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/c0292efd-b25a-4c21-9c2d-3e2b0801c5a6"
              >Coleção de Mamíferos da Universidade Federal de Mato Grosso (UFMT)</a
            >
          </li>
          <li>
            Coleções de zoologia:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/e07710e5-66dc-47b3-9a75-23bf2ef54534"
              >Coleção de Mamíferos da PUCRS (MCP)</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/29"
        >lifeStage</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:lifeStage"
        >https://dwc.tdwg.org/terms/#dwc:lifeStage</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A classe etária ou estágio de vida do(s) organismo(s) no momento em que
        a ocorrência foi registrada.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Zigoto | Ovos | Larva | Pupa | Juvenil | Adulto | Semente | Muda |
        Frutificação | Floração | Semente
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Herbário:
            <a href="https://www.gbif.org/occurrence/2236082236">NMNH Extant Specimen Records (USNM, US)</a>
          </li>
          <li>
            Projeto:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/b1e323db-e480-489e-ac14-f13a02d2f0ca"
              >Soil macrofauna biodiversity across land use systems in neotropical biomes</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/30"
        >reproductiveCondition</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:reproductiveCondition"
        >https://dwc.tdwg.org/terms/#dwc:reproductiveCondition</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A condição reprodutiva do(s) indivíduo(s) biológico(s) representado(s)
        na ocorrência.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Grávida | Não reprodutiva | Em flor | Frutífero
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/31">behavior</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:behavior"
        >https://dwc.tdwg.org/terms/#dwc:behavior</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O comportamento apresentado pelo sujeito no momento em que a ocorrência
        foi registrada.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Pelágico | Bentônico | Nectônicos | Planctônico | Árvore | Arbusto |
        Lianas | Subarbusto | Erva | Palmeira | Parasita | Liquenizado |
        Micorrízico | Bambu | Herbívoro | Polinizador | Predador | Ectoparasito
        | Ectoparasitoide | Séssil | Endoparasito | Endoparasitoide
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/32"
        >establishmentMeans</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:establishmentMeans"
        >https://dwc.tdwg.org/terms/#dwc:establishmentMeans</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Declaração sobre se um organismo ou organismos foram introduzidos em um
        determinado lugar e tempo através da atividade direta ou indireta dos
        humanos modernos.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Introduzida | Nativa | Incerto | Nativa reintroduzida | Introduzida por
        colonização assistida
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/33"
        >degreeOfEstablishment</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:degreeOfEstablishment"
        >https://dwc.tdwg.org/terms/#dwc:degreeOfEstablishment</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O grau em que um organismo sobrevive, se reproduz e expande seu alcance
        no lugar e tempo determinados.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Cultivada | Nativa |Invasora | Naturalizada |Introduzida | Domesticada |
        Criptogênico | Nativa - endêmica | Nativa - não endêmica | Origem
        incerta | Origem não conhecida
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            <a
              href="http://floradobrasil.jbrj.gov.br/reflora/listaBrasil/PrincipalUC/PrincipalUC.do;jsessionid=9E1CFFE3946CC896F95E9BAFC4601A7E#CondicaoTaxonCP"
              >Lista de Flora e Funga do Brasil</a
            >
          </li>
          <li>
            <a href="https://www.marinespecies.org/aphia.php?p=checklist"
              >WoRMS</a
            >
          </li>
          <li>
            <a
              href="http://fauna.jbrj.gov.br/fauna/listaBrasil/ConsultaPublicaUC/ConsultaPublicaUC.do"
              >Catálogo Taxônomico da Fauna do Brasil</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/34">pathway</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:pathway"
        >https://dwc.tdwg.org/terms/#dwc:pathway</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O processo pelo qual um organismo veio a estar em um determinado lugar
        em um determinado tempo
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Liberado para uso</li>
          <li>Transporte contaminante</li>
          <li>Corredor</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/35"
        >georeferenceVerificationStatus</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:georeferenceVerificationStatus"
        >https://dwc.tdwg.org/terms/#dwc:georeferenceVerificationStatus</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Descrição categórica do grau em que se verificou que o
        georreferenciamento representa a melhor descrição espacial possível para
        a localização da ocorrência.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Não é possível georreferenciar | Requer georrefenciamento | Requer
        verificação
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/36"
        >occurrenceStatus</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:occurrenceStatus"
        >https://dwc.tdwg.org/terms/#dwc:occurrenceStatus</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma declaração sobre a presença ou ausência de um táxon em um local.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Presença | Absença | Present | Absent</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Coleção de zoologia:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/e2463fb0-0ae8-4bf9-89d6-741c7506da0b"
              >	Coleção Entomológica do Instituto Oswaldo Cruz</a
            >
          </li>
          <li>
            Projeto PELD:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/f1481be4-5f9a-4707-878a-43e9651058d3"
              >	PELD - ELPA | Programa Pesquisa Ecológica de Longa Duração no Estuário da Lagoa dos Patos e Costa Marinha Adjacente</a
            </li>
            <li>
              Herbário:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/9896807a-a038-4eeb-9af9-c772ba3a01c5"
              > Herbário RADAMBRASIL</a
              >
            </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/37"
        >preparations</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:preparations"
        >https://dwc.tdwg.org/terms/#dwc:preparations</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista de preparações e métodos de conservação de um espécime.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Pele | Crânio | Esqueleto | Animal inteiro | Tecido | Extração DNA |
        Sangue
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Coleção de zoologia:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/1dc6ebe2-f43f-4e74-8b5d-bbd3e8a40147"
              >Coleção de Aves da Unisinos</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/38"
        >disposition</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:disposition"
        >https://dwc.tdwg.org/terms/#dwc:disposition</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O estado atual de um espécime em relação à coleção identificada em
        collectioncode ou collectionid.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Em coleção | Ausente | In collection | Missing | Voucher em outro local
        | Duplicatas em outro local | Voucher elsewhere | Duplicates elsewhere
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Herbário:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/d1bff69a-7e87-4fac-bb8d-4935b8fc1277"
              >Rio de Janeiro Botanical Garden DNA Collection - GGBN</a
            >
          </li>
          <li>
            Coleção de zoologia:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/6e4bb585-df36-4058-97a4-3238ec56bb3b"
              >ICMBio: Sisbio-Dibio</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/39"
        >associatedMedia</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:associatedMedia"
        >https://dwc.tdwg.org/terms/#dwc:associatedMedia</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de identificadores (publicação,
        identificador exclusivo global, url) de mídia associada à ocorrência.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[URL de acesso a imagem]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            <a
              href="https://image-server-ala.s3.amazonaws.com/Refauna/type_Coleoptera_Histeridae/type_Histeridae_Carcinops%20miserula/mnhnColeoptera00072_5.tif"
              >https://image-server-ala.s3.amazonaws.com/Refauna/type_Coleoptera_Histeridae/type_Histeridae_Carcinops%20miserula/mnhnColeoptera00072_5.tif</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/40"
        >associatedOccurrences</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:associatedOccurrences"
        >https://dwc.tdwg.org/terms/#dwc:associatedOccurrences</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de identificadores de outros
        registros de ocorrência e suas associações a esta ocorrência.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Parasita coletado de: “<a
              href="https://arctos.database.museum/guid/MSB:Mamm:215895?seid=950760"
              >https://arctos.database.museum/guid/MSB:Mamm:215895?seid=950760</a
            >”
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/41"
        >associatedReferences</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:associatedReferences"
        >https://dwc.tdwg.org/terms/#dwc:associatedReferences</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de identificadores (publicação,
        referência bibliográfica, identificador único global, url) da literatura
        associada à ocorrência.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Christopher J. Conroy, Jennifer L. Neuwald. 2008. Phylogeographic
            study of the California vole, Microtus californicus Journal of
            Mammalogy, 89(3):755-767.
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/42"
        >associatedSequences</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:associatedSequences"
        >https://dwc.tdwg.org/terms/#dwc:associatedSequences</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de identificadores (publicação,
        identificador único global, url) de informações de sequência genética
        associadas à ocorrência.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/43"
        >associatedTaxa</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:associatedTaxa"
        >https://dwc.tdwg.org/terms/#dwc:associatedTaxa</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de identificadores ou nomes de táxons
        e as associações desta ocorrência a cada um deles.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Predador de:“Apis mellifera”</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/44"
        >otherCatalogNumbers</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:otherCatalogNumbers"
        >https://dwc.tdwg.org/terms/#dwc:otherCatalogNumbers</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de números de catálogo totalmente
        qualificados anteriores ou alternativos ou outros identificadores usados
        por humanos para a mesma ocorrência, seja no atual ou em qualquer outro
        conjunto de dados ou coleção.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Herbário:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/65416160-a3cc-4411-8472-8ed9f6f64020"
              >Rio de Janeiro Botanical Garden Herbarium Collection</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/45"
        >occurrenceRemarks</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:occurrenceRemarks"
        >https://dwc.tdwg.org/terms/#dwc:occurrenceRemarks</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">Comentários ou notas sobre a ocorrência.</td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Encontrado morto</li>
          <li>Atropelado</li>
          <li>Hora da coleta</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

--- 

### Organism

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/46"
        >organismID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:organismID"
        >https://dwc.tdwg.org/terms/#dwc:organismID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para a instância do organismo (em oposição a um
        registro digital específico do organismo). Pode ser um identificador
        global exclusivo ou um identificador específico para o conjunto de
        dados.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Número de identificação do organismo]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Coleção de zoologia:
            <a href="https://www.gbif.org/occurrence/4089783173"
              >Birda - Global Observation Dataset</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/47"
        >organismName</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:organismName"
        >https://dwc.tdwg.org/terms/#dwc:organismName</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um nome textual ou rótulo atribuído a uma instância de um organismo.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Para coleções vivas. O nome do animal.</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/48"
        >organismScope</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:organismScope"
        >https://dwc.tdwg.org/terms/#dwc:organismScope</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma descrição do tipo de instância de organismo. Pode ser usado para
        indicar se a instância de organismo representa um organismo discreto ou
        se representa um tipo particular de agregação.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Vírus | Clone | Colônia | Zooplâncton | Fitoplâncton
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/49"
        >associatedOrganisms</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:associatedOrganisms"
        >https://dwc.tdwg.org/terms/#dwc:associatedOrganisms</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de identificadores de outros
        organismos e as associações deste organismo a cada um deles.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Pai/Mãe de: “<a
              href="http://arctos.database.museum/guid/MSB:Mamm:196208"
              >http://arctos.database.museum/guid/MSB:Mamm:196208</a
            >”
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/50"
        >previousIdentifications</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:previousIdentifications"
        >https://dwc.tdwg.org/terms/#dwc:previousIdentifications</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de atribuições anteriores de nomes ao
        organismo.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Anthus sp., identificado em campo por G. Iglesias</li>
          <li>
            Anthus correndera, identificação especializada por C. Cicero em 12/02/2009
            com base em morfologia.
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/51"
        >organismRemarks</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:organismRemarks"
        >https://dwc.tdwg.org/terms/#dwc:organismRemarks</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Comentários ou notas sobre a instância organismo.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Um de uma ninhada de seis</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

--- 

### MaterialSample

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/52"
        >MaterialSampleID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#materialsample"
        >https://dwc.tdwg.org/terms/#materialsample</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um resultado físico de um evento de amostragem (ou subamostragem). Em
        coleções biológicas, a amostra de material é tipicamente coletada, e
        preservada ou processada destrutivamente.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

--- 

### Event

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/53">eventID</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:eventID"
        >https://dwc.tdwg.org/terms/#dwc:eventID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para o conjunto de informações associadas a um evento
        (algo que ocorre em um local e horário). Pode ser um identificador
        exclusivo global ou um identificador específico para o conjunto de
        dados.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Projeto PELD:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/f8bd0b2d-39be-471f-b299-d4d3184c5963"
              >PELD - ELPA | Programa Pesquisa Ecológica de Longa Duração no Estuário da Lagoa dos Patos e Costa Marinha Adjacente</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/54"
        >parentEventID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:parentEventID"
        >https://dwc.tdwg.org/terms/#dwc:parentEventID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para o evento mais amplo que agrupa este e
        potencialmente outros eventos.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/55"
        >eventDate</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:eventDate"
        >https://dwc.tdwg.org/terms/#dwc:eventDate</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A data-hora ou o intervalo durante o qual um evento ocorreu. Para
        ocorrências, essa é a data-hora em que o evento foi registrado. Não
        adequado para um tempo em um contexto geológico.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">AAAA-MM-DD</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Data com ano: AAAA 
          </li>
          <li>
            Data com ano e mês: AAAA-MM
            </li>
          <li>
            Data completa: AAAA
          </li>
          <li>Intervalo de coleta: AAAA-MM-DD/AAAA-MM-DD | AAAA-MM/AAAA-MM | AAAA/AAAA</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/56"
        >eventTime</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:eventTime"
        >https://dwc.tdwg.org/terms/#dwc:eventTime</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O tempo ou intervalo durante o qual um evento ocorreu.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">ISO 8601-1:2019</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Projeto iNaturalist:
            <a href="https://www.gbif.org/occurrence/4028756291"
              >iNaturalist</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/57"
        >startDayOfYear</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:startDayOfYear"
        >https://dwc.tdwg.org/terms/#dwc:startDayOfYear</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O primeiro dia inteiro do ano em que o evento ocorreu (1 para 1º de
        janeiro, 365 para 31 de dezembro, exceto em um ano bissexto, caso em que
        é 366).
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">1 (1 de janeiro) | 366 (31 de dezembro)</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>Não encontrei</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/58"
        >endDayOfYear</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:endDayOfYear"
        >https://dwc.tdwg.org/terms/#dwc:endDayOfYear</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O último dia inteiro do ano em que o evento ocorreu (1 para 1º de
        janeiro, 365 para 31 de dezembro, exceto em um ano bissexto, caso em que
        é 366).
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">1 (1 de janeiro) | 366 (31 de dezembro)</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>Não encontrei</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/59">year</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:year"
        >https://dwc.tdwg.org/terms/#dwc:year</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O ano de quatro dígitos em que o evento ocorreu.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">AAAA</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>AAAA (termo darwin core para ano de coleta)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/60">month</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:month"
        >https://dwc.tdwg.org/terms/#dwc:month</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">O mês inteiro em que o evento ocorreu.</td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">MM</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>MM (termo darwin core para mês de coleta)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/61">day</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:day"
        >https://dwc.tdwg.org/terms/#dwc:day</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">O dia inteiro em que o evento ocorreu.</td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">DD</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>DD (termo darwin core para dia de coleta)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/62"
        >verbatimEventDate</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:verbatimEventDate"
        >https://dwc.tdwg.org/terms/#dwc:verbatimEventDate</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A representação original literal das informações de data e hora de um
        evento.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Data como estava escrito na planilha original antes de padronizar em
        DarwinCore
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/63">habitat</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:habitat"
        >https://dwc.tdwg.org/terms/#dwc:habitat</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma categoria ou descrição do habitat em que o evento ocorreu.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Mata Atlântica</li>
          <li>Cerrado</li>
          <li>Pantanal</li>
          <li>Arquipélagos</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/64"
        >samplingProtocol</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:samplingProtocol"
        >https://dwc.tdwg.org/terms/#dwc:samplingProtocol</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Os nomes, referências ou descrições dos métodos ou protocolos usados
        durante um evento.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">RAPELD | Parcelas | TSBF | Transectos</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Projeto Conexão Mata Atlântica:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/ddb66fc8-dc83-4d14-8270-25a7a814dfbc"
              >Projeto Recuperação de Serviços de Clima e Biodiversidade no Corredor Sudeste da Mata Atlântica Brasileira - Monitoramento Ecossistêmico</a
            >
          </li>
          <li>
            Projeto PELD:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/8dac4377-385c-4244-850a-74f122b353e4"
              >PELD - AGCV | Monitoramento de borboletas no Jardim Botânico de Brasília</a>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/65"
        >sampleSizeValue</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:sampleSizeValue"
        >https://dwc.tdwg.org/terms/#dwc:sampleSizeValue</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um valor numérico para uma medida do tamanho (duração do tempo,
        comprimento, área ou volume) de uma amostra em um evento de amostragem.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Valor numérico]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Projeto PELD:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/f1481be4-5f9a-4707-878a-43e9651058d3"
              >	PELD - ELPA | Programa Pesquisa Ecológica de Longa Duração no Estuário da Lagoa dos Patos e Costa Marinha Adjacente</a
            >
            </li>
            <li>
              Projeto:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/b2729b5d-a4f1-41d1-8c0a-ca78e9371f45"
              >	Soil macrofauna communities in an organic grain production system under conventional and no-tillage system</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/66"
        >sampleSizeUnit</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:sampleSizeUnit"
        >https://dwc.tdwg.org/terms/#dwc:sampleSizeUnit</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A unidade de medida do tamanho (duração do tempo, comprimento, área ou
        volume) de uma amostra em um evento de amostragem.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Minutos | Hora | Dia | Metros | Quilômetros | Metros quadrados
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Projeto PELD:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/f1481be4-5f9a-4707-878a-43e9651058d3"
              >	PELD - ELPA | Programa Pesquisa Ecológica de Longa Duração no Estuário da Lagoa dos Patos e Costa Marinha Adjacente</a
            >
          </li>
          <li>
            Projeto:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/b2729b5d-a4f1-41d1-8c0a-ca78e9371f45"
              >	Soil macrofauna communities in an organic grain production system under conventional and no-tillage system</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/67"
        >samplingEffort</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:samplingEffort"
        >https://dwc.tdwg.org/terms/#dwc:samplingEffort</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A quantidade de esforço despendido durante um evento.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Grades de amostragem | Pitfall | 50x50m | Busca ativa | Armadilha
        fotográfica | Encontros ocasionais | Registro Auditivo em Transectos
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Projeto PELD:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/49d1073b-d9ff-458c-9817-6dc93b837702"
              >PELD - AGCV | Pequenos mamíferos terrestres em fragmentos de cerradão no Distrito Federal</a
            >
          </li>
          <li>
            Projeto PELD:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/38464ecc-bb48-4df9-94b2-cad29389fa85"
              >PELD - ABRS | Avaliação e monitoramento dos recifes de Abrolhos</a
            >
          </li>
          <li>
            Projeto Conexão Mata Atlântica:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/bdc0b643-66f3-4b3e-8579-b77376cf90f4"
              >	Projeto Recuperação de Serviços de Clima e Biodiversidade no Corredor Sudeste da Mata Atlântica Brasileira - Monitoramento Ecossistêmico</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/68"
        >fieldNotes</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:fieldNotes"
        >https://dwc.tdwg.org/terms/#dwc:fieldNotes</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um de a) um indicador da existência de, b) uma referência a (publicação,
        uri), ou c) o texto de anotações feitas no campo sobre o evento.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Herbário:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/0e541351-f7b1-4098-b479-d3ac559c36f4"
              >	Rio de Janeiro Botanical Garden Herbarium Collection</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/69"
        >eventRemarks</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:eventRemarks"
        >https://dwc.tdwg.org/terms/#dwc:eventRemarks</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">Comentários ou notas sobre o evento.</td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Época chuvosa</li>
          <li>Época seca</li>
          <li>Tempo pós queimada</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

--- 

### Location

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/70"
        >locationID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:locationID"
        >https://dwc.tdwg.org/terms/#dwc:locationID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para o conjunto de informações de localização (dados
        associados a dcterms: location). Pode ser um identificador exclusivo
        global ou um identificador específico para o conjunto de dados.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/71"
        >higherGeography</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:higherGeography"
        >https://dwc.tdwg.org/terms/#dwc:higherGeography</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de nomes geográficos menos
        específicos do que as informações capturadas no termo localidade.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Oceano Atlântico Norte</li>
          <li>Argentina</li>
          <li>América do Sul</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/72"
        >continent</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:continent"
        >https://dwc.tdwg.org/terms/#dwc:continent</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome do continente em que a localização ocorre.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        África | Antártica | Europa | América do Norte | Oceania | América do
        Sul |Africa | Antartica | Asia | Europe | North America | Oceania |
        South America
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/73"
        >waterBody</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:waterBody"
        >https://dwc.tdwg.org/terms/#dwc:waterBody</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome do corpo d'água em que ocorre o local.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Oceano | Rio | Lago | Mar</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/74"
        >islandGroup</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:islandGroup"
        >https://dwc.tdwg.org/terms/#dwc:islandGroup</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome do grupo de ilhas em que a localização ocorre.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Conjunto de ilhas</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/76">island</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:island"
        >https://dwc.tdwg.org/terms/#dwc:island</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome da ilha ou área perto da qual o local ocorre.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Ilha</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/77">country</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:country"
        >https://dwc.tdwg.org/terms/#dwc:country</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome do país ou da principal unidade administrativa em que o local
        ocorre.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Brasil | Argentina | Colômbia</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/78"
        >countryCode</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:countryCode"
        >https://dwc.tdwg.org/terms/#dwc:countryCode</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O código padrão para o país em que o local ocorre.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">BR | AUS | EUA | FRA</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            <a
              href="https://www.ibge.gov.br/geociencias/organizacao-do-territorio/malhas-territoriais/15774-malhas.html"
              >IBGE</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/79"
        >stateProvince</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:stateProvince"
        >https://dwc.tdwg.org/terms/#dwc:stateProvince</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome da próxima região administrativa menor do que o país (estado,
        província, cantão, departamento, região, etc.) em que a localização
        ocorre.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Distrito Federal | Espírito Santo | São Paulo | Rio de Janeiro
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            <a
              href="https://www.ibge.gov.br/geociencias/organizacao-do-territorio/malhas-territoriais/15774-malhas.html"
              >IBGE</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/80">county</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:county"
        >https://dwc.tdwg.org/terms/#dwc:county</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome completo e não abreviado da próxima região administrativa menor
        do que o estado província (condado, condado, departamento, etc.) em que
        a localização ocorre.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Guiricema | Macaé | Itabuna | Ilhéus</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/cc66804e-8327-45a4-8690-b61061452736"
              >Projeto Conexão Mata Atlântica</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/82">locality</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:locality"
        >https://dwc.tdwg.org/terms/#dwc:locality</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">A descrição específica do local.</td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Parque Nacional Marinho dos Abrolhos</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/38464ecc-bb48-4df9-94b2-cad29389fa85"
              >PELD - ABRS | Avaliação e monitoramento dos recifes de Abrolhos</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/83"
        >verbatimLocality</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:verbatimLocality"
        >https://dwc.tdwg.org/terms/#dwc:verbatimLocality</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">A descrição textual original do local.</td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li> Km 3 da estrada BR-193 | Ponto 2 do Rio Doce
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/84"
        >minimumElevationInMeters</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:minimumElevationInMeters"
        >https://dwc.tdwg.org/terms/#dwc:minimumElevationInMeters</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O limite inferior da faixa de elevação (altitude, geralmente acima do
        nível do mar), em metros.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>10</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/85"
        >maximumElevationInMeters</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:maximumElevationInMeters"
        >https://dwc.tdwg.org/terms/#dwc:maximumElevationInMeters</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O limite superior da faixa de elevação (altitude, geralmente acima do
        nível do mar), em metros.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>100</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/86"
        >verbatimElevation</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:verbatimElevation"
        >https://dwc.tdwg.org/terms/#dwc:verbatimElevation</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A descrição original da elevação (altitude, geralmente acima do nível do
        mar) do local.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>10-100m</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/87"
        >verticalDatum</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:verticalDatum"
        >https://dwc.tdwg.org/terms/#dwc:verticalDatum</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O dado vertical usado como referência sobre o qual os valores nos termos
        de elevação são baseados.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>EGM84</li>
          <li>EGM96</li>
          <li>EGM2008</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/88"
        >minimumDepthInMeters</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:minimumDepthInMeters"
        >https://dwc.tdwg.org/terms/#dwc:minimumDepthInMeters</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A menor profundidade de uma faixa de profundidade abaixo da superfície
        local, em metros.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>100</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/89"
        >maximumDepthInMeters</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:maximumDepthInMeters"
        >https://dwc.tdwg.org/terms/#dwc:maximumDepthInMeters</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A maior profundidade de uma faixa de profundidade abaixo da superfície
        local, em metros.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>200</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/90"
        >verbatimDepth</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:verbatimDepth"
        >https://dwc.tdwg.org/terms/#dwc:verbatimDepth</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A descrição original da profundidade abaixo da superfície local.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>100-200m</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/92"
        >minimumDistanceAboveSurfaceInMeters</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a
        href="https://dwc.tdwg.org/terms/#dwc:minimumDistanceAboveSurfaceInMeters"
        >https://dwc.tdwg.org/terms/#dwc:minimumDistanceAboveSurfaceInMeters</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A menor distância em uma faixa de distância de uma superfície de
        referência na direção vertical, em metros. Use valores positivos para
        locais acima da superfície, valores negativos para locais abaixo. Se
        forem dadas medidas de profundidade, a superfície de referência é a
        localização dada pela profundidade, caso contrário, a superfície de
        referência é a localização dada pela elevação.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
              <li>1.5 (abaixo da superfície)</li>
              <li>4.2 (acima da superfície)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/94"
        >maximumDistanceAboveSurfaceInMeters</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a
        href="https://dwc.tdwg.org/terms/#dwc:maximumDistanceAboveSurfaceInMeters"
        >https://dwc.tdwg.org/terms/#dwc:maximumDistanceAboveSurfaceInMeters</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A maior distância em uma faixa de distância de uma superfície de
        referência na direção vertical, em metros. Use valores positivos para
        locais acima da superfície, valores negativos para locais abaixo. Se
        forem dadas medidas de profundidade, a superfície de referência é a
        localização dada pela profundidade, caso contrário, a superfície de
        referência é a localização dada pela elevação.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
              <li>1.5 (abaixo da superfície)</li>
              <li>4.2 (acima da superfície)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/95"
        >locationAccordingTo</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:locationAccordingTo"
        >https://dwc.tdwg.org/terms/#dwc:locationAccordingTo</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Informações sobre a fonte dessas informações de localização. Pode ser
        uma publicação (gazeta), instituição ou equipe de indivíduos.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li><a href="https://gadm.org/">GADM</a></li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/96"
        >locationRemarks</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:locationRemarks"
        >https://dwc.tdwg.org/terms/#dwc:locationRemarks</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">Comentários ou notas sobre o local.</td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
              Coleção de zoologia:
            <a href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/ea8ec403-27ad-4b6a-a633-ab1b92a21ce4"
              >	Coleção de Mamíferos da Universidade Federal de Mato Grosso (UFMT)</a
            >
            </li>
          <li>
            Projeto Conexão Mata Atlântica:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/0fbb4244-a111-42d9-b52a-269c92529d31"
              >Projeto Recuperação de Serviços de Clima e Biodiversidade no Corredor Sudeste da Mata Atlântica Brasileira - Monitoramento Ecossistêmico</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/97"
        >decimalLatitude</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:decimalLatitude"
        >https://dwc.tdwg.org/terms/#dwc:decimalLatitude</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A latitude geográfica (em graus decimais, usando o sistema de referência
        espacial dado em geodésico datum) do centro geográfico de uma
        localidade. Os valores positivos estão ao norte da linha do equador, os
        negativos estão ao sul dela. Os valores jurídicos situam-se entre -90 e
        90.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Latitude decimal]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/ea1bdcbe-d6a8-41df-9d7f-e3cbab5ff8e1"
              >	PELD - PNCA | Programa de Pesquisa de Longa Duração do Parque Nacional do Catimbau</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/98"
        >decimalLongitude</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:decimalLongitude"
        >https://dwc.tdwg.org/terms/#dwc:decimalLongitude</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A longitude geográfica (em graus decimais, usando o sistema de
        referência espacial dado em geodésico datum) do centro geográfico de uma
        localidade. Os valores positivos estão a leste do meridiano de
        greenwich, os valores negativos estão a oeste dele. Os valores jurídicos
        situam-se entre -180 e 180.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Longitude decimal]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/ea1bdcbe-d6a8-41df-9d7f-e3cbab5ff8e1"
              >	PELD - PNCA | Programa de Pesquisa de Longa Duração do Parque Nacional do Catimbau</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/99"
        >geodeticDatum</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:geodeticDatum"
        >https://dwc.tdwg.org/terms/#dwc:geodeticDatum</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O elipsoide, dado geodésico ou sistema de referência espacial (srs)
        sobre o qual as coordenadas geográficas dadas em latitude decimal e
        longitude decimal como baseadas.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">EPSG:4326 | WGS84</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/ea1bdcbe-d6a8-41df-9d7f-e3cbab5ff8e1"
              >PELD - PNCA | Programa de Pesquisa de Longa Duração do Parque Nacional do Catimbau</a
            >
            </li>
            <li>
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/14119ff6-6826-48c4-ae85-fb6122c8097d"
              >	Projeto Recuperação de Serviços de Clima e Biodiversidade no Corredor Sudeste da Mata Atlântica Brasileira - Monitoramento Ecossistêmico</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/100"
        >coordinateUncertaintyInMeters</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:coordinateUncertaintyInMeters"
        >https://dwc.tdwg.org/terms/#dwc:coordinateUncertaintyInMeters</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A distância horizontal (em metros) da latitude decimal e longitude
        decimal dadas, descrevendo o menor círculo que contém todo o local.
        Deixe o valor vazio se a incerteza for desconhecida, não puder ser
        estimada ou não for aplicável (porque não há coordenadas). Zero não é um
        valor válido para este termo.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            70 (limite mínimo razoável ou após 01/05/2000 de uma leitura de GPS
            em boas condições, se a precisão real não foi registrada na época
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/101"
        >coordinatePrecision</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:coordinatePrecision"
        >https://dwc.tdwg.org/terms/#dwc:coordinatePrecision</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma representação decimal da precisão das coordenadas dadas na latitude
        decimal e longitude decimal.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            0.0001 (limite normal de GPS para graus decimais)</li>
          <li>
            0.000278 (segundo mais próximo)</li>
          <li>
            0.01667 (minuto mais próximo)</li>
          <li>
            1.0 (grau mais próximo)
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/102"
        >pointRadiusSpatialFit</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:pointRadiusSpatialFit"
        >https://dwc.tdwg.org/terms/#dwc:pointRadiusSpatialFit</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A razão entre a área do raio do ponto (decimallatitude,
        decimallongitude, coordinateuncertaintyinmeters) e a área da
        representação espacial verdadeira (original ou mais específica) da
        localização. Os valores legais são 0, maior ou igual a 1, ou
        indefinidos. Um valor de 1 é uma correspondência exata ou 100% de
        sobreposição. Um valor de 0 deve ser usado se o raio de ponto fornecido
        não contiver completamente a representação original. O
        pontoradiusspatialfit é indefinido (e deve ser deixado vazio) se a
        representação original é um ponto sem incerteza e a georreferência dada
        não é esse mesmo ponto (sem incerteza). Se a georreferência original e
        dada forem o mesmo ponto, o pontoradiusspatialfit será 1.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>0</li>
          <li>1</li>
          <li>1.5708</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/103"
        >verbatimCoordinates</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:verbatimCoordinates"
        >https://dwc.tdwg.org/terms/#dwc:verbatimCoordinates</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        As coordenadas espaciais originais literais do lugar. O elipsoide de
        coordenadas, geodésico datum, ou sistema de referência espacial (srs)
        completo para essas coordenadas deve ser armazenado em verbatimsrs e o
        sistema de coordenadas deve ser armazenado em verbatimcoordinatesystem.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        [Coordenada original da coleta/medida em campo]
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>41 05 54S 121 05 34W</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/104"
        >verbatimLatitude</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:verbatimLatitude"
        >https://dwc.tdwg.org/terms/#dwc:verbatimLatitude</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A latitude original literal do lugar. O elipsoide de coordenadas,
        geodésico datum, ou sistema de referência espacial (srs) completo para
        essas coordenadas deve ser armazenado em verbatimsrs e o sistema de
        coordenadas deve ser armazenado em verbatimcoordinatesystem.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Latitude original medida em campo]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>41 05 54.03S</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/105"
        >verbatimLongitude</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:verbatimLongitude"
        >https://dwc.tdwg.org/terms/#dwc:verbatimLongitude</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A longitude original literal do lugar. O elipsoide de coordenadas,
        geodésico datum, ou sistema de referência espacial (srs) completo para
        essas coordenadas deve ser armazenado em verbatimsrs e o sistema de
        coordenadas deve ser armazenado em verbatimcoordinatesystem.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Longitude original medida em campo]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>121d 10’ 34” W</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/106"
        >verbatimCoordinateSystem</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:verbatimCoordinateSystem"
        >https://dwc.tdwg.org/terms/#dwc:verbatimCoordinateSystem</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O formato de coordenadas para o verbatimlatitude e verbatimlongitude ou
        o verbatimcoordinates do location.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Graus decimais | Graus minutos decimais | Graus segundos decimais | UTM
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/107"
        >verbatimSRS</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:verbatimSRS"
        >https://dwc.tdwg.org/terms/#dwc:verbatimSRS</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O elipsoide, dado geodésico ou sistema de referência espacial (srs) no
        qual as coordenadas dadas em verbatimlatitude e verbatimlongitude, ou
        verbatimcoordinates são baseadas.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">WGS84 | EPSG: 4326</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/108"
        >footprintWKT</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:footprintWKT"
        >https://dwc.tdwg.org/terms/#dwc:footprintWKT</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma representação de texto conhecido (wkt) da forma (pegada, geometria)
        que define o local. Um local pode ter uma representação de raio de ponto
        (consulte decimallatitude) e uma representação de pegada, e eles podem
        diferir uns dos outros.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <li> POLÍGONO (10 20, 11 20, 11 21, 10 21, 10 20) (a caixa delimitadora de um
        grau com cantos opostos em longitude=10, latitude=20 e longitude=11,
        latitude=21)
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/109"
        >footprintSRS</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:footprintSRS"
        >https://dwc.tdwg.org/terms/#dwc:footprintSRS</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O elipsoide, dado geodésico ou sistema de referência espacial (srs)
        sobre o qual a geometria dada na pegada é baseada.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/110"
        >footprintSpatialFit</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:footprintSpatialFit"
        >https://dwc.tdwg.org/terms/#dwc:footprintSpatialFit</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A razão entre a área da pegada (footprintwkt) e a área da representação
        espacial verdadeira (original ou mais específica) da localização. Os
        valores legais são 0, maior ou igual a 1, ou indefinidos. Um valor de 1
        é uma correspondência exata ou 100% de sobreposição. Um valor de 0 deve
        ser usado se a pegada fornecida não contiver completamente a
        representação original. O footprintspatialfit é indefinido (e deve ser
        deixado vazio) se a representação original é um ponto sem incerteza e a
        georreferência dada não é esse mesmo ponto (sem incerteza). Se a
        georreferência original e a georreferenciada dada forem o mesmo ponto, a
        pegadaspatialfit será 1.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/111"
        >georeferencedBy</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:georeferencedBy"
        >https://dwc.tdwg.org/terms/#dwc:georeferencedBy</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de nomes de pessoas, grupos ou
        organizações que determinaram a georreferência (representação espacial)
        para o local.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Nome completo]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/112"
        >georeferencedDate</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:georeferencedDate"
        >https://dwc.tdwg.org/terms/#dwc:georeferencedDate</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A data em que o local foi georreferenciado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>2009-02-20T08:40Z (20 de fevereiro de 2009 8:40 UTC)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/113"
        >georeferenceProtocol</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:georeferenceProtocol"
        >https://dwc.tdwg.org/terms/#dwc:georeferenceProtocol</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma descrição ou referência aos métodos usados para determinar a pegada
        espacial, coordenadas e incertezas.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/114"
        >georeferenceSources</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:georeferenceSources"
        >https://dwc.tdwg.org/terms/#dwc:georeferenceSources</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de mapas, gazetas ou outros recursos
        usados para georreferenciar a localização, descrita especificamente o
        suficiente para permitir que qualquer pessoa no futuro use os mesmos
        recursos.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Terrametrics 2008 no Google Earth</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/115"
        >georeferenceRemarks</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:georeferenceRemarks"
        >https://dwc.tdwg.org/terms/#dwc:georeferenceRemarks</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Notas ou comentários sobre a determinação da descrição espacial,
        explicitando pressupostos assumidos em adição ou oposição aos
        formalizados no método referido no protocolo georreferenciado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Distância estimada pela estrada (Rodovia 101)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

--- 

### GeologicalContext

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/116"
        >geologicalContextID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:geologicalContextID"
        >https://dwc.tdwg.org/terms/#dwc:geologicalContextID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Informações geológicas, como a estratigrafia, que qualificam uma região
        ou lugar.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/117"
        >earliestEonOrLowestEonothem</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:earliestEonOrLowestEonothem"
        >https://dwc.tdwg.org/terms/#dwc:earliestEonOrLowestEonothem</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome completo do éon geocronológico mais antigo possível ou o eonotema
        cronoestratigráfica mais baixa ou o nome informal ("pré-cambriano")
        atribuível ao horizonte estratigráfico a partir do qual o item
        catalogado foi coletado
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Fanerozoico</li>
          <li>Proterozoico</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/118"
        >latestEonOrHighestEonothem</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:latestEonOrHighestEonothem"
        >https://dwc.tdwg.org/terms/#dwc:latestEonOrHighestEonothem</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome completo do último éon geocronológico possível ou eonotema
        cronoestratigráfica mais alto ou o nome informal ("precambriano")
        atribuível ao horizonte estratigráfico a partir do qual o item
        catalogado foi coletado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Fanerozoico</li>
          <li>Proterozoico</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/119"
        >earliestEraOrLowestErathem</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:earliestEraOrLowestErathem"
        >https://dwc.tdwg.org/terms/#dwc:earliestEraOrLowestErathem</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome completo da era geocronológica mais antiga possível ou da menor
        era cronoestratigráfica atribuível ao horizonte estratigráfico a partir
        do qual o item catalogado foi coletado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Cenozoico</li>
          <li>Mezosoico</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/120"
        >latestEraOrHighestErathem</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:latestEraOrHighestErathem"
        >https://dwc.tdwg.org/terms/#dwc:latestEraOrHighestErathem</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome completo da última era geocronológica possível ou maior era
        cronoestratigráfica atribuível ao horizonte estratigráfico a partir do
        qual o item catalogado foi coletado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Cenozoico</li>
          <li>Mezosoico</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/121"
        >earliestPeriodOrLowestSystem</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:earliestPeriodOrLowestSystem"
        >https://dwc.tdwg.org/terms/#dwc:earliestPeriodOrLowestSystem</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome completo do período geocronológico mais antigo possível ou
        sistema cronoestratigráfico mais baixo atribuível ao horizonte
        estratigráfico a partir do qual o item catalogado foi coletado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Neogene</li>
          <li>Terciário</li>
          <li>Quartenário</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/122"
        >earliestEpochOrLowestSeries</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:earliestEpochOrLowestSeries"
        >https://dwc.tdwg.org/terms/#dwc:earliestEpochOrLowestSeries</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome completo da época geocronológica mais antiga possível ou da menor
        série cronoestratigráfica atribuível ao horizonte estratigráfico a
        partir do qual o item catalogado foi coletado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Holoceno</li>
          <li>Plestoceno</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/123"
        >latestEpochOrHighestSeries</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:latestEpochOrHighestSeries"
        >https://dwc.tdwg.org/terms/#dwc:latestEpochOrHighestSeries</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome completo da última época geocronológica possível ou maior série
        cronoestratigráfica atribuível ao horizonte estratigráfico a partir do
        qual o item catalogado foi coletado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Holoceno</li>
          <li>Plestoceno</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/124"
        >earliestAgeOrLowestStage</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:earliestAgeOrLowestStage"
        >https://dwc.tdwg.org/terms/#dwc:earliestAgeOrLowestStage</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome completo da idade geocronológica mais antiga possível ou estágio
        cronoestratigráfico mais baixo atribuível ao horizonte estratigráfico a
        partir do qual o item catalogado foi coletado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Atlântico</li>
          <li>Boreal</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/125"
        >latestAgeOrHighestStage</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:latestAgeOrHighestStage"
        >https://dwc.tdwg.org/terms/#dwc:latestAgeOrHighestStage</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome completo da última idade geocronológica possível ou estágio
        cronoestratigráfico mais alto atribuível ao horizonte estratigráfico a
        partir do qual o item catalogado foi coletado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Atlântico</li>
          <li>Boreal</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/126"
        >lowestBiostratigraphicZone</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:lowestBiostratigraphicZone"
        >https://dwc.tdwg.org/terms/#dwc:lowestBiostratigraphicZone</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Nome completo da zona geoestratigráfica mais baixa possível do horizonte
        estratigráfico a partir do qual o item catalogado foi coletado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Maastrichtiano</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/127"
        >highestBiostratigraphicZone</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:highestBiostratigraphicZone"
        >https://dwc.tdwg.org/terms/#dwc:highestBiostratigraphicZone</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Nome completo da zona geoestratigráfica mais alta possível do horizonte
        estratigráfico a partir do qual o item catalogado foi coletado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Blancan</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/128"
        >lithostratigraphicTerms</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:lithostratigraphicTerms"
        >https://dwc.tdwg.org/terms/#dwc:lithostratigraphicTerms</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A combinação de todos os nomes litoestratigráficos para a rocha da qual
        o item catalogado foi coletado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Pleistoceno-Weichseliano</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/129">group</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:group"
        >https://dwc.tdwg.org/terms/#dwc:group</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome completo do grupo litoestratigráfico do qual o item catalogado
        foi coletado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Grupo Paranoá</li>
          <li>Grupo Bambui</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/130"
        >formation</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:formation"
        >https://dwc.tdwg.org/terms/#dwc:formation</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome completo da formação litoestratigráfica da qual o item catalogado
        foi coletado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Serra do Mar</li>
          <li>Serra da Mantiqueira</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/131">member</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:member"
        >https://dwc.tdwg.org/terms/#dwc:member</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome completo do membro litoestratigráfico do qual o item catalogado
        foi coletado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/132">bed</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:bed"
        >https://dwc.tdwg.org/terms/#dwc:bed</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome completo do leito litoestratigráfico do qual o item catalogado
        foi coletado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Fm. Ribeirão do Torto</li>
          <li>Fm. Ribeirão São Miguel</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

--- 

### Identification

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/133"
        >identificationID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:identificationID"
        >https://dwc.tdwg.org/terms/#dwc:identificationID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para a identificação (o conjunto de informações
        associadas à atribuição de um nome científico). Pode ser um
        identificador exclusivo global ou um identificador específico para o
        conjunto de dados.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>9992</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/134"
        >verbatimIdentification</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:verbatimIdentification"
        >https://dwc.tdwg.org/terms/#dwc:verbatimIdentification</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma cadeia de caracteres que representa a identificação taxonômica como
        ela apareceu no registro original.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <li> Micrurus corallinus x Erythrolamprus aesculapii| Fabaceae? | Byrsonima
        coccolobifolia x B. verbascifolia
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/135"
        >identificationQualifier</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:identificationQualifier"
        >https://dwc.tdwg.org/terms/#dwc:identificationQualifier</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma breve frase ou um termo padrão ("cf.", "aff.") para expressar as
        dúvidas do determinante sobre a identificação.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">cf. aff. | sp. | spp.</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Coleção de zoologia:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/58811f37-1138-4db4-beeb-dd253798718e"
              >Coleção de Anfíbios do Museu Nacional (MNRJ)</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/136"
        >typeStatus</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:typeStatus"
        >https://dwc.tdwg.org/terms/#dwc:typeStatus</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de tipos nomenclaturais (status do
        tipo, nome científico tipificado, publicação) aplicada ao assunto.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Holótipo [originalNameUsage} | Isótipo | Síntipo | Léctotipo | Parátipo
        | Neótipo | Cótipo
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Coleção de zoologia:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/58811f37-1138-4db4-beeb-dd253798718e"
              >Coleção de Anfíbios do Museu Nacional (MNRJ)</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/137"
        >identifiedBy</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:identifiedBy"
        >https://dwc.tdwg.org/terms/#dwc:identifiedBy</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de nomes de pessoas, grupos ou
        organizações que atribuíram o táxon ao assunto.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        SOBRENOME, Inicial nome | Sobrenome, Inicial nome
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Herbário:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/03ba3a3e-5bfd-4e4a-a4e4-e1248e510a12"
              >Coleção de Briófitas do Herbário da Universidade Federal de Minas Gerais</a
            >
          </li>
          <li>
            Herbário:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/c7318d47-ca86-4041-8ba8-2a09dfd0b30c"
              >	Base de dados de Algae do Herbário R do Museu Nacional</a
            >
          </li>
          <li>
            Coleção de zoologia:
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/982e6bec-de01-4bfb-addd-6e55187215c4?lang=en_GB"
              >	Base de dados de Mamíferos da Coleção Zoológica MBML do INMA</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/138"
        >identifiedByID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:identifiedByID"
        >https://dwc.tdwg.org/terms/#dwc:identifiedByID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) do identificador global exclusivo da
        pessoa, pessoas, grupos ou organizações responsáveis por atribuir o
        táxon ao assunto.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/139"
        >dateIdentified</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:dateIdentified"
        >https://dwc.tdwg.org/terms/#dwc:dateIdentified</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A data em que o sujeito foi determinado como representando o táxon.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">AAAA-MM-DD</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/140"
        >identificationReferences</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:identificationReferences"
        >https://dwc.tdwg.org/terms/#dwc:identificationReferences</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de referências (publicação,
        identificador exclusivo global, url) usadas na identificação.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/141"
        >identificationVerificationStatus</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:identificationVerificationStatus"
        >https://dwc.tdwg.org/terms/#dwc:identificationVerificationStatus</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um indicador categórico do grau em que a identificação taxonômica foi
        verificada como correta.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/142"
        >identificationRemarks</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:identificationRemarks"
        >https://dwc.tdwg.org/terms/#dwc:identificationRemarks</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Comentários ou notas sobre a identificação.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

--- 

### Taxon

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/143">taxonID</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:taxonID"
        >https://dwc.tdwg.org/terms/#dwc:taxonID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para o conjunto de informações do táxon (dados
        associados à classe taxon). Pode ser um identificador exclusivo global
        ou um identificador específico para o conjunto de dados.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Checklist (termo obrigatório): 32567</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>TaxonID do banco taxonômico brasileiro</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/144"
        >scientificNameID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:scientificNameID"
        >https://dwc.tdwg.org/terms/#dwc:scientificNameID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para os detalhes nomenclaturais (não taxonômicos) de um
        nome científico.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/145"
        >acceptedNameUsageID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:acceptedNameUsageID"
        >https://dwc.tdwg.org/terms/#dwc:acceptedNameUsageID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para o uso do nome (significado documentado do nome de
        acordo com uma fonte) do táxon atualmente válido (zoológico) ou aceito
        (botânico).
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[identificador do nome aceito]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>6W3C4 (COL)</li>
          <li>2704179 (GBIF)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/146"
        >parentNameUsageID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:parentNameUsageID"
        >https://dwc.tdwg.org/terms/#dwc:parentNameUsageID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para o uso do nome (significado documentado do nome de
        acordo com uma fonte) do táxon pai direto e mais próximo de
        classificação superior (em uma classificação) do elemento mais
        específico do scientificname.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[identificador do pai do nome aceito]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>6T8N (COL)</li>
          <li>2704173 (GBIF)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/147"
        >originalNameUsageID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:originalNameUsageID"
        >https://dwc.tdwg.org/terms/#dwc:originalNameUsageID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para o uso do nome (significado documentado do nome de
        acordo com uma fonte) no qual o elemento terminal do scientificname foi
        originalmente estabelecido sob as regras do código nomenclatural
        associado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        [identificador do nome original da especie no momento da indentificação]
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>6W3C4 (COL)</li>
          <li>2704179 (GBIF)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/148"
        >nameAccordingToID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:nameAccordingToID"
        >https://dwc.tdwg.org/terms/#dwc:nameAccordingToID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para a fonte na qual a circunscrição do conceito de
        táxon específico é definida ou implícita. Consulte nameaccordingto.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/149"
        >namePublishedInID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:namePublishedInID"
        >https://dwc.tdwg.org/terms/#dwc:namePublishedInID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para a publicação em que o scientificname foi
        originalmente estabelecido sob as regras do código nomenclatural
        associado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/150"
        >taxonConceptID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:taxonConceptID"
        >https://dwc.tdwg.org/terms/#dwc:taxonConceptID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para o conceito taxonômico ao qual o registro se refere
        - não para os detalhes nomenclaturais de um táxon.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/151"
        >scientificName</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:scientificName"
        >https://dwc.tdwg.org/terms/#dwc:scientificName</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome científico completo, com informações de autoria e data, se
        conhecidas. Ao fazer parte de uma identificação, este deve ser o nome na
        classificação taxonômica de nível mais baixo que pode ser determinado.
        Este termo não deve conter qualificações de identificação, que devem ser
        fornecidas no termo identificationqualifier.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Nome científico do taxón]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Ceiba speciosa</li>
          <li>Eugenia uniflora</li>
          <li>Chrysocyon brachyurus</li>
          <li>Fabaceae</li>
          <li>Canidae</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/152"
        >acceptedNameUsage</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:acceptedNameUsage"
        >https://dwc.tdwg.org/terms/#dwc:acceptedNameUsage</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome completo, com informações de autoria e data, se conhecidas, do
        táxon atualmente válido (zoológico) ou aceito (botânico).
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Nome aceito do táxon]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Schwartzia adamantium (nome válido para Norantea adamantium)</li>
          <li>
            Arapaima gigas (nome válido para Arapaima arapaima)
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/153"
        >parentNameUsage</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:parentNameUsage"
        >https://dwc.tdwg.org/terms/#dwc:parentNameUsage</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome completo, com informações de autoria e data, se conhecidas, do
        táxon pai direto e mais próximo (em uma classificação) do elemento mais
        específico do nome científico.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <li> Saprinus
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/154"
        >originalNameUsage</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:originalNameUsage"
        >https://dwc.tdwg.org/terms/#dwc:originalNameUsage</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome do táxon, com informações de autoria e data, se conhecido, como
        apareceu originalmente quando estabelecido pela primeira vez sob as
        regras do código nomenclatural associado. O basiônimo (botânica) ou
        basônimo (bacteriologia) do nome científico ou o homônimo
        sênior/anterior para nomes substituídos.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Saprinus pipitzi</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            scientificName atual: Euspilotus (Neosaprinus) pipitzi (Marseul,
            1887)
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/155"
        >nameAccordingTo</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:nameAccordingTo"
        >https://dwc.tdwg.org/terms/#dwc:nameAccordingTo</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A referência à fonte na qual o conceito específico de táxon
        circunscrição é definido ou implícito - tradicionalmente significada
        pelo latim "sensu" ou "sec". (de secundum, que significa "de acordo
        com"). Para os táxons resultantes de identificações, deve ser dada uma
        referência às chaves, monografias, especialistas e outras fontes.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Franz NM, Cardona-Duque J (2013) Descrição de duas novas espécies e
            reavaliação filogenética de Perelleschus Wibmer &amp;amp
          </li>
          <li>
            O’Brien, 1986 (Coleoptera: Curculionidae), com um histórico completo
            do conceito taxonômico de Perelleschus sec. Franz &amp;amp
          </li>
          <li>
            Cardona-Duque, 2013. Syst Biodivers. 11: 209-236. (como a citação
            completa de Franz &amp;amp
          </li>
          <li>
            Cardona-Duque (2013) em Perelleschus splendida sec. Franz &amp;amp
          </li>
          <li>Cardona-Duque (2013))</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/156"
        >namePublishedIn</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:namePublishedIn"
        >https://dwc.tdwg.org/terms/#dwc:namePublishedIn</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma referência para a publicação em que o scientificname foi
        originalmente estabelecido sob as regras do código nomenclatural
        associado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/157"
        >namePublishedInYear</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:namePublishedInYear"
        >https://dwc.tdwg.org/terms/#dwc:namePublishedInYear</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O ano de quatro dígitos em que o nome científico foi publicado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>1915</li>
          <li>2008</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/158"
        >higherClassification</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:higherClassification"
        >https://dwc.tdwg.org/terms/#dwc:higherClassification</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de nomes de táxons terminando no
        posto imediatamente superior ao táxon referenciado no registro do táxon.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Animalia | Chordata | Vertebrata | Mammalia | Theria | Eutheria | Rodentia | Hystricognatha | Hystricognathi | Ctenomyidae | Ctenomyini | Ctenomys</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/159">kingdom</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:kingdom"
        >https://dwc.tdwg.org/terms/#dwc:kingdom</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome científico completo do reino em que o táxon está classificado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Animalia | Plantae | Fungi | Archaea | Chromista | Protozoa | Viruses
        |Bacteria
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/160">phylum</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:phylum"
        >https://dwc.tdwg.org/terms/#dwc:phylum</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Vocabulário controlado obrigatório. O nome científico completo do filo
        em que o táxon está classificado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Filo</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/161">class</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:class"
        >https://dwc.tdwg.org/terms/#dwc:class</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome científico completo da classe em que o táxon está classificado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Classe</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/162">order</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:order"
        >https://dwc.tdwg.org/terms/#dwc:order</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome científico completo da ordem em que o táxon está classificado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Ordem</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/163">family</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:family"
        >https://dwc.tdwg.org/terms/#dwc:family</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome científico completo da família em que o táxon está classificado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Família</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/164"
        >subfamily</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:subfamily"
        >https://dwc.tdwg.org/terms/#dwc:subfamily</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome científico completo da subfamília em que o táxon está
        classificado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Subfamília</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/165">genus</a>
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:genus"
        >https://dwc.tdwg.org/terms/#dwc:genus</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome científico completo do gênero em que o táxon está classificado.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Gênero</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/166"
        >genericName</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:genericName"
        >https://dwc.tdwg.org/terms/#dwc:genericName</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O gênero faz parte do nome científico sem autoria.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Panthera</li>
          <li>Felis</li>
          <li>Canis</li>
          <li>Rosa</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/167"
        >subgenus</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:subgenus"
        >https://dwc.tdwg.org/terms/#dwc:subgenus</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome científico completo do subgênero no qual o táxon está
        classificado. Os valores devem incluir o gênero para evitar confusão
        homônima.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Amerigo</li>
          <li>Symphyomyrtus</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/168"
        >infragenericEpithet</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:infragenericEpithet"
        >https://dwc.tdwg.org/terms/#dwc:infragenericEpithet</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A parte infragenérica de um nome binomial está acima das espécies, mas
        abaixo do gênero.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Epíteto infragenérico]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Triplinervia para o scientificName Alchornea triplinervia var.
            parvifolia
            </li>
          <li>
            Tigrinus para o scientificName Leopardus tigrinus guttulus
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/169"
        >specificEpithet</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:specificEpithet"
        >https://dwc.tdwg.org/terms/#dwc:specificEpithet</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome do primeiro ou epíteto de espécie do nome científico.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Epíteto específico]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>concolor</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/170"
        >infraspecificEpithet</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:infraspecificEpithet"
        >https://dwc.tdwg.org/terms/#dwc:infraspecificEpithet</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O nome do epíteto infraespecífico mais baixo ou terminal do nome
        científico, excluindo qualquer designação de classificação.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Epíteto infraespecífico]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            concolor (para scientificName Puma concolor concolor (Linnaeus,
            1771)
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/171"
        >cultivarEpithet</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:cultivarEpithet"
        >https://dwc.tdwg.org/terms/#dwc:cultivarEpithet</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Parte do nome de uma cultivar, grupo de cultivares que segue o nome
        científico.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            Atlantis (para scientificName Paphiopedilum Atlantis grex e
            taxonRank grex)
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/172"
        >taxonRank</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:taxonRank"
        >https://dwc.tdwg.org/terms/#dwc:taxonRank</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A classificação taxonômica do nome mais específico no nome científico.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Espécie | Gênero | Subespécie | Família | Ordem | Reino | Classe | Filo
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Categoria taxonômica</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/173"
        >verbatimTaxonRank</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:verbatimTaxonRank"
        >https://dwc.tdwg.org/terms/#dwc:verbatimTaxonRank</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A classificação taxonômica do nome mais específico no nome científico
        como aparece no registro original.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">sp. |subsp. | var.</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/174"
        >scientificNameAuthorship</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:scientificNameAuthorship"
        >https://dwc.tdwg.org/terms/#dwc:scientificNameAuthorship</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        As informações de autoria para o nome científico formatado de acordo com
        as convenções do código nomenclatural aplicável.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">
        Botânica [autor por extenso]; Zoologia [autor e ano] Verificar uso de
        parenteses.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/83c1d78e-9eb5-4492-b4bf-34941867a88e"
              >Herbário</a
            >
          </li>
          <li>
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/f1481be4-5f9a-4707-878a-43e9651058d3"
              >Coleções de zoologia</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/175"
        >vernacularName</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:vernacularName"
        >https://dwc.tdwg.org/terms/#dwc:vernacularName</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">Um nome comum ou vernáculo.</td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">[Nome comum do táxon]</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Lobo Guará</li>
          <li>Ipê-roxo</li>
          <li>Seringueira</li>
          <li>Arara</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/176"
        >nomenclaturalCode</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:nomenclaturalCode"
        >https://dwc.tdwg.org/terms/#dwc:nomenclaturalCode</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O código nomenclatural sob o qual o scientificname é construído.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">ICBN | ICZN | ICTV | ICNB</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            <a href="https://www.iapt-taxon.org/nomen/main.php">Herbário</a>
          </li>
          <li>
            <a href="https://code.iczn.org/?frame=1">Coleções de zoologia</a>
          </li>
          <li><a href="https://ictv.global/">Virus</a></li>
          <li>
            <a href="https://www.ncbi.nlm.nih.gov/books/NBK8817/">Bactérias</a>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/177"
        >taxonomicStatus</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:taxonomicStatus"
        >https://dwc.tdwg.org/terms/#dwc:taxonomicStatus</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O status do uso do scientificname como um rótulo para um táxon. Requer
        parecer taxonômico para definir o escopo de um táxon. Em seguida, são
        utilizadas regras de prioridade para definir o estatuto taxonômico da
        nomenclatura contida nesse âmbito, combinado com o parecer dos peritos.
        Deve estar vinculado a uma referência taxonômica específica que defina o
        conceito.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">Aceito | Inválido | Sinônimo homotípico</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/178"
        >nomenclaturalStatus</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:nomenclaturalStatus"
        >https://dwc.tdwg.org/terms/#dwc:nomenclaturalStatus</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O estatuto relacionado com a publicação original do nome e a sua
        conformidade com as regras de nomenclatura pertinentes. Ele é baseado
        essencialmente em um algoritmo de acordo com as regras de negócios do
        código. Não requer opinião taxonômica.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">nom. ambig. | nom. illeg.</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/179"
        >taxonRemarks</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:taxonRemarks"
        >https://dwc.tdwg.org/terms/#dwc:taxonRemarks</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Comentários ou notas sobre o táxon ou nome.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>
            <a
              href="https://ala-hub.sibbr.gov.br/ala-hub/occurrences/c7703576-ada5-460e-938a-996dea3a9277"
              >Coleções de zoologia</a
            >
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

--- 

### MeasurementOrFact

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/180"
        >measurementID</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:measurementID"
        >https://dwc.tdwg.org/terms/#dwc:measurementID</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Um identificador para o measurementorfact (informações relativas a
        medições, fatos, características ou afirmações). Pode ser um
        identificador exclusivo global ou um identificador específico para o
        conjunto de dados.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/181"
        >measurementType</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:measurementType"
        >https://dwc.tdwg.org/terms/#dwc:measurementType</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A natureza da medida, fato, característica ou asserção.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <li> Temperatura | Comprimento da cauda | DAP 
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/182"
        >measurementValue</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:measurementValue"
        >https://dwc.tdwg.org/terms/#dwc:measurementValue</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        O valor da medida, fato, característica ou asserção.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left">45 | 20 | 1 |</td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <li>Pode ser qualitativo ou quantitativo</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/183"
        >measurementAccuracy</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:measurementAccuracy"
        >https://dwc.tdwg.org/terms/#dwc:measurementAccuracy</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A descrição do erro potencial associado ao measurementvalue.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <li> 0.01
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/184"
        >measurementUnit</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:measurementUnit"
        >https://dwc.tdwg.org/terms/#dwc:measurementUnit</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        As unidades associadas ao measurementvalue.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <li> m | g | l |°C | mm | km² | m/s
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/185"
        >measurementDeterminedBy</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:measurementDeterminedBy"
        >https://dwc.tdwg.org/terms/#dwc:measurementDeterminedBy</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma lista (concatenada e separada) de nomes de pessoas, grupos ou
        organizações que determinaram o valor do measurementorfact.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/186"
        >measurementDeterminedDate</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:measurementDeterminedDate"
        >https://dwc.tdwg.org/terms/#dwc:measurementDeterminedDate</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        A data em que o measurementorfact foi feito.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <li> 2018-08-29T15:19 (15:19 horário local no dia 29 de Agosto de 2018)
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/187"
        >measurementMethod</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:measurementMethod"
        >https://dwc.tdwg.org/terms/#dwc:measurementMethod</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Uma descrição ou referência a (publicação, url) o método ou protocolo
        usado para determinar a medida, fato, característica ou asserção.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <li> Altímetro barométrico
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>

---

<table>
  <tr class="table-secondary">
    <th colspan="2">
      <a href="https://github.com/sibbr/DarwinCoreBrasil/issues/188"
        >measurementRemarks</a
      >
    </th>
  </tr>
  <tr>
    <td style="text-align: left">Identificador</td>
    <td style="text-align: left">
      <a href="https://dwc.tdwg.org/terms/#dwc:measurementRemarks"
        >https://dwc.tdwg.org/terms/#dwc:measurementRemarks</a
      >
    </td>
  </tr>
  <tbody>
    <tr>
      <td style="text-align: left">Definição</td>
      <td style="text-align: left">
        Comentários ou notas que acompanham o measurementorfact.
      </td>
    </tr>
    <tr>
      <td style="text-align: left">Domínio</td>
      <td style="text-align: left"></td>
    </tr>
    <tr>
      <td style="text-align: left">Exemplos</td>
      <td style="text-align: left">
        <ul>
          <!-- <li>NA</li> -->
        </ul>
      </td>
    </tr>
  </tbody>
</table>
