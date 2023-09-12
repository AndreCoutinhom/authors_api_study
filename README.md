<h1 align="center">
  <img align="center" alt="lab" height="55" width="55" src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c7/Google_Scholar_logo.svg/2048px-Google_Scholar_logo.svg.png">




Authors API 

</h1>

Este projeto tem a função de desenvolver um pequeno website que armazena informações de autores científicos através de uma API da plataforma Scholar Google.

###

Utilizarei essa atividade para compreender as práticas de utilização de APIs em projetos de software. Além disso, busco utilidade para tornar buscas por referências bibliográficas mais ágeis e personalizadas.

## 👨‍🎓 Google Scholar Author API 

A API é fornecida através da plataforma SerpAPI.

#### Descrição do site: 

Nossa API de autor do Google Acadêmico permite que você extraia os resultados do autor da página de pesquisa de autor do Google Acadêmico. A API é acessada por meio do seguinte endpoint: /search?engine=google_scholar_author. Um usuário pode consultar o seguinte: https://serpapi.com/search?engine=google_scholar_author utilizando uma solicitação GET. Vá ao playground para uma demonstração ao vivo e interativa.

## Exemplos da API

`author_id`: LSsXyncAAAAJ

###

- GET 
```
https://serpapi.com/search.json?engine=google_scholar_author&author_id=LSsXyncAAAAJ
```
##

- Code to integrate
``` node.js
const SerpApi = require('google-search-results-nodejs');
const search = new SerpApi.GoogleSearch("2e41dbaaab0b58dfc03df862974dc84843780cacc7a53652d2c5b099f13e694f");

const params = {
  engine: "google_scholar_author",
  author_id: "LSsXyncAAAAJ"
};

const callback = function(data) {
  console.log(data["author"]);
};

// Show result as JSON
search.json(params, callback);
```
##

- JSON Example
``` json
{
  "search_metadata": {
    "id": "60802ce5de983402dbe1ae4c",
    "status": "Success",
    "json_endpoint": "https://serpapi.com/searches/79beba2444307aad/60802ce5de983402dbe1ae4c.json",
    "created_at": "2021-04-21 13:47:17 UTC",
    "processed_at": "2021-04-21 13:47:18 UTC",
    "google_scholar_author_url": "https://scholar.google.com/citations?user=LSsXyncAAAAJ&hl=en",
    "raw_html_file": "https://serpapi.com/searches/79beba2444307aad/60802ce5de983402dbe1ae4c.html",
    "total_time_taken": 1.26
  },
  "search_parameters": {
    "engine": "google_scholar_author",
    "author_id": "LSsXyncAAAAJ",
    "hl": "en"
  },
  "author": {
    "name": "Cliff Meyer",
    "affiliations": "Dana-Farber Cancer Institute and Harvard T.H. Chan School of Public Health",
    "email": "Adresse email validée de jimmy.harvard.edu",
    "interests": [
      {
        "title": "Computational Biology",
        "link": "https://scholar.google.com/citations?view_op=search_authors&hl=en&mauthors=label:computational_biology",
        "serpapi_link": "https://serpapi.com/search.json?engine=google_scholar_profiles&hl=en&mauthors=label%3Acomputational_biology"
      },
      {
        "title": "Epigenetics",
        "link": "https://scholar.google.com/citations?view_op=search_authors&hl=en&mauthors=label:epigenetics",
        "serpapi_link": "https://serpapi.com/search.json?engine=google_scholar_profiles&hl=en&mauthors=label%3Aepigenetics"
      },
      {
        "title": "Gene Regulation",
        "link": "https://scholar.google.com/citations?view_op=search_authors&hl=en&mauthors=label:gene_regulation",
        "serpapi_link": "https://serpapi.com/search.json?engine=google_scholar_profiles&hl=en&mauthors=label%3Agene_regulation"
      },
      ...
    ],
    "thumbnail": "https://scholar.google.com/citations/images/avatar_scholar_128.png"
  },
  "articles": [
    {
      "title": "Model-based analysis of ChIP-Seq (MACS)",
      "link": "https://scholar.google.com/citations?view_op=view_citation&hl=fr&user=LSsXyncAAAAJ&citation_for_view=LSsXyncAAAAJ:2osOgNQ5qMEC",
      "citation_id": "LSsXyncAAAAJ:2osOgNQ5qMEC",
      "authors": "Y Zhang, T Liu, CA Meyer, J Eeckhoute, DS Johnson, BE Bernstein, ...",
      "publication": "Genome biology 9 (9), 1-9, 2008",
      "cited_by": {
        "value": 9186,
        "link": "https://scholar.google.com/scholar?oi=bibs&hl=fr&cites=14252090027271643524",
        "serpapi_link": "https://serpapi.com/search.json?cites=14252090027271643524&engine=google_scholar&hl=en"
      },
      "year": "2008"
    },
    {
      "title": "Genome-wide analysis of estrogen receptor binding sites",
      "link": "https://scholar.google.com/citations?view_op=view_citation&hl=fr&user=LSsXyncAAAAJ&citation_for_view=LSsXyncAAAAJ:9yKSN-GCB0IC",
      "citation_id": "LSsXyncAAAAJ:9yKSN-GCB0IC",
      "authors": "JS Carroll, CA Meyer, J Song, W Li, TR Geistlinger, J Eeckhoute, ...",
      "publication": "Nature genetics 38 (11), 1289-1297, 2006",
      "cited_by": {
        "value": 1464,
        "link": "https://scholar.google.com/scholar?oi=bibs&hl=fr&cites=7951096779388712529",
        "serpapi_link": "https://serpapi.com/search.json?cites=7951096779388712529&engine=google_scholar&hl=en"
      },
      "year": "2006"
    },
    {
      "title": "Chromosome-wide mapping of estrogen receptor binding reveals long-range regulation requiring the forkhead protein FoxA1",
      "link": "https://scholar.google.com/citations?view_op=view_citation&hl=fr&user=LSsXyncAAAAJ&citation_for_view=LSsXyncAAAAJ:d1gkVwhDpl0C",
      "citation_id": "LSsXyncAAAAJ:d1gkVwhDpl0C",
      "authors": "JS Carroll, XS Liu, AS Brodsky, W Li, CA Meyer, AJ Szary, J Eeckhoute, ...",
      "publication": "Cell 122 (1), 33-43, 2005",
      "cited_by": {
        "value": 1371,
        "link": "https://scholar.google.com/scholar?oi=bibs&hl=fr&cites=12018554524946333077",
        "serpapi_link": "https://serpapi.com/search.json?cites=12018554524946333077&engine=google_scholar&hl=en"
      },
      "year": "2005"
    },
    ...
  ],
  "cited_by": {
    "table": [
      {
        "citations": {
          "all": 21934,
          "depuis_2016": 12302
        }
      },
      {
        "indice_h": {
          "all": 45,
          "depuis_2016": 36
        }
      },
      {
        "indice_i10": {
          "all": 59,
          "depuis_2016": 51
        }
      }
    ],
    "graph": [
      {
        "year": 2004,
        "citations": "59"
      },
      {
        "year": 2005,
        "citations": "65"
      },
      {
        "year": 2006,
        "citations": "159"
      },
      ...
    ]
  },
  "public_access": {
    "link": "https://scholar.google.com/citations?view_op=list_mandates&hl=fr&user=LSsXyncAAAAJ",
    "available": 39,
    "not_available": 0
  },
  "co_authors": [
    {
      "name": "Myles Brown",
      "link": "https://scholar.google.com/citations?user=wwxk-JMAAAAJ&hl=fr",
      "serpapi_link": "https://serpapi.com/search.json?author_id=wwxk-JMAAAAJ&engine=google_scholar_author&hl=en",
      "author_id": "wwxk-JMAAAAJ",
      "affiliations": "Emil Frei III Professor of Medicine, Dana-Farber Cancer Institute and Harvard Medical School",
      "email": "Adresse e-mail validée de dfci.harvard.edu",
      "thumbnail": "https://scholar.googleusercontent.com/citations?view_op=small_photo&user=wwxk-JMAAAAJ&citpid=10"
    },
    {
      "name": "Wei Li",
      "link": "https://scholar.google.com/citations?user=7IUCbE4AAAAJ&hl=fr",
      "serpapi_link": "https://serpapi.com/search.json?author_id=7IUCbE4AAAAJ&engine=google_scholar_author&hl=en",
      "author_id": "7IUCbE4AAAAJ",
      "affiliations": "Professor of Bioinformatics, University of California Irvine; Baylor College of Medicine",
      "email": "Adresse e-mail validée de uci.edu",
      "thumbnail": "https://scholar.googleusercontent.com/citations?view_op=small_photo&user=7IUCbE4AAAAJ&citpid=5"
    },
    {
      "name": "Tao Liu",
      "link": "https://scholar.google.com/citations?user=04GHe_kAAAAJ&hl=fr",
      "serpapi_link": "https://serpapi.com/search.json?author_id=04GHe_kAAAAJ&engine=google_scholar_author&hl=en",
      "author_id": "04GHe_kAAAAJ",
      "affiliations": "Assistant Professor, Roswell Park Comprehensive Cancer Center",
      "email": "Adresse e-mail validée de roswellpark.org",
      "thumbnail": "https://scholar.googleusercontent.com/citations?view_op=small_photo&user=04GHe_kAAAAJ&citpid=2"
    },
    ...
  ],
  "serpapi_pagination": {
    "next": "https://serpapi.com/search.json?author_id=LSsXyncAAAAJ&cstart=20&engine=google_scholar_author&hl=en"
  }
}
```
##

