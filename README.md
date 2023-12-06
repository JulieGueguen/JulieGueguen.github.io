---
title: Untitled
format:
  modern2-cv-pdf: default
author: Julie Guéguen
cvfont: raleway #texlive fonts like raleway,fetamont,gillius,comfortaa
cvcolor: 
  main: B83B5E
  accent: 6A2C70
jobtitle: Chargée de missions bio-statistiques
sidebar:
  # image: portrait.jpg
  # bullets:
  #   - german
  #   - married
  sections: 
    - name: Contact
      items:
        - icon: map-marker
          text: Faulquemont, France
        - icon: github
          href: https://github.com/JulieGueguen
        - icon: envelope
          text: julie_gueguen@yahoo.fr
    - name: Programmation
      items: 
        - text: R
          exp: 
            text: "Maitrise"
            num: 1
        - text: SQL
          exp: 
            text: "Connaissance"
            num: 0.5
        - text: Latex
          exp: 
            text: "Connaissance"
            num: 0.3
        - text: Python
          exp: 
            text: "Connaissance"
            num: 0.2
    - name: Compétences 
      items:
        - "Statistiques : Données environnementales, flores/faunes, spatialisées et temporelles"
    - name: Outils
      items:
        - RStudio
        - Qgis
        - pgAdmin
        - MySQL, posGIS
    - name: OS
      items:
        - Windows
        - Linux (Fedora, Ubuntu)
    - name: Langues
      items:
        - Français (maternelle)
        - Anglais (CLES B1)
        - Espagnol (scolaire)
    - name: Formations
      items:
        - text: "Master Écologie Biodiversité et Évolution (EBE), Parcours Écologie théorique et modélisation"
          inst: "Université Pierre et Marie Curie (Paris 6) , Paris"
          time: "2009 - 2011"
          details: "Co-habilité avec le Museum national d’Histoire naturelle (MNHN), l'Université d’Orsay (paris XI), AgroParis-Tech et l’Ecole nationale supérieure (ENS Ulm)"
        - text: "Licence Mathématique-Informatique, Parcours Statistiques"
          inst: "Université Pierre et Marie Curie (Paris 6) , Paris"
          time: "2005 - 2008"
          # details: "Thesis: Modularity Maximization"
execute: 
  echo: false
---

```{r}
#| label: cvevents
cvevents <- function(tbl, when, what, where, descr) {
  
  command_start <- "\\cvevent"
  tbl[[where]] <- gsub("\n", " \\\\newline ", tbl[[where]])
  res <- paste0(
    command_start, "{", tbl[[when]], "}", 
    "{", tbl[[what]], "}",
    "{", tbl[[where]], "}",
    "{", tbl[[descr]], "}"
  )
  
  cat(res, sep = "\n\n\n")
}

cvproj <- function(tbl,what,role,items){
  command_start <- "\\cvproj"
  res <- paste0(
    command_start, "{", tbl[[what]], "}",
    "{", tbl[[role]], "}",
    "{", sapply(tbl[[items]], function(x)paste0(x,collapse = ", ")), "}"
  )
  
  cat(res, sep = "\n\n\n")
}
```

# Experience précedente

```{r}
#| label: experience prec
#| output: asis
tibble::tribble(
  ~role, ~institution, ~dates, ~details,
  "Chargée de mission Analyse de données pour l'évaluation environnementale", "Office Français de la biodiversité (OFB), Saint-Benoist (78) et Vincennes (75)", "08/2020 - 07/2023", "kmlklmlk",
) |>
  cvevents(when = "dates", what = "role", where = "institution", descr = "details")
```

# Experiences


```{r}
#| label: experience
#| output: asis
tibble::tribble(
  ~role, ~institution, ~dates, ~details,
  "Ingénieure d’étude bio-statistiques du projet Interreg SYNAQUA", "INRA, Thonon-les-bains (74)", "04/2017 - 09/2019", "kmlklmlk",
) |>
  cvevents(when = "dates", what = "role", where = "institution", descr = "details")
  
```

