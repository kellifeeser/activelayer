---
title: "**Active Layer Taxonomy**"
subtitle: "Taxa plots of clean 16S OTU tables including survey and experimental samples"
author: "Kelli Feeser"
date: '2023-09-20'
output:
  bookdown::html_document2:
    code_folding: hide
    css: styles.css
    number_sections: yes
    toc: yes
    toc_depth: 3
    fig.caption: yes
    keep_md: yes
  html_notebook:
    code_folding: hide
    df_print: paged
    number_sections: yes
    theme: cosmo
    toc: yes
    toc_depth: 2
  html_document: 
    code_folding: hide
    css: test.css
    fig_height: 4.5
    fig_width: 6
    number_sections: yes
    theme: cosmo
    toc: yes
    toc_depth: 2
editor_options:
  chunk_output_type: inline
---

\

::: homelink
<a href="https://kellifeeser.github.io/sctivelayer/index.html" target="_blank" style="text-align:right">Back to Home</a>
:::








# Import clean OTU tables {.unlisted .unnumbered .hidden}
\

 \
'Taxa' are OTUs






\

# Data Overview 

 - OTU tables rarefied to 1,096 reads / sample \
  - reads from 'Survey' and 'Experiment' were clustered together (OTUs correspond) \
  - at Domain level, only Bacteria detected \
  - among both datasets, a total of 1,724 unique OTUs detected \
  - only forward reads used

## Survey 

- n samples: 74 \
- n OTUs: 1,639 \

## Experiment 

- n samples: 55 \
- n OTUs: 1,402 \
\


# Set-up taxonomy for plotting {.unlisted .unnumbered .hidden}
\



## Global: Calculate  mean relative abundance by tax rank and export csv of relative abundance 

### merge samples within dataset 



### tax glom and export 

(no generating code just copy and replace)







## Samples: Calculate relative abundance by tax rank and export csv of relative abundance  


1. create vectors of top 10 taxa names to plot for all ranks
  - auto-generated code found: 
  a. set minimum threshold of 0.5% all-sample (a.k.a global) mean relative abundance
    - (so that taxa below this threshold won't get plotted)
2. tax glom by each rank
3. transform to relative abundance
3. psmelt
4. add column "[rank]_all" to preserve names not in top 10 
5. recode all taxa not in top 10 to by "LowAbundance" & revalue with specifics later (in dat_Survey.[rank].r and in dat_Exp.[rank].r)




### generating code: 


```r
Survey.rank.names<-rank_names(Survey)[2:6]
Exp.rank.names<-rank_names(Exp)[2:6] #change 6 to 7 if fungal

#change from survey to exp next

# add this line to beginning
  #  cat('\n # Set min plotting threshold to 0.5% relative abundance (all-sample a.k.a global mean) \n')

#also adding psmelt step

for(rank in Survey.rank.names) {

  cat('\n## \n')

  cat('################## \n')

  cat('# Survey:', rank, '# \n')

  cat('################## \n')

  cat('\n')
  
   cat('min_nname_Survey_', rank, '<-length(unique(Survey_', rank, '_Mean_Abund$', 
       rank, '[Survey_', rank, '_Mean_Abund$Survey_', rank, '_Mean > 0.5]))',
       sep = '')
  
  cat('\n \n ')

    cat('if (min_nname_Survey_', rank, ' < 10){
  Survey.', rank, '.names.to.plot<-top_n(Survey_', rank, '_Mean_Abund, min_nname_Survey_', rank, ', Survey_', rank, '_Mean)$',rank, ' 
} else {
  Survey.', rank, '.names.to.plot<-top_n(Survey_', rank, '_Mean_Abund, 10, Survey_', rank, '_Mean)$', rank, '
}', sep = '')

  cat('\n# \n')
  
  cat('\nSurvey.',rank,'.A <- tax_glom(Survey, taxrank="',rank,'")\n',sep = '')
  
  cat('Survey.',rank,' <- prune_taxa(taxa_sums(Survey.',rank,'.A) > 0, Survey.',rank,'.A)\n',sep = '')

  cat('Survey.',rank,'.r  = transform_sample_counts(Survey.',rank,', function(x) x / sum(x) )\n',sep = '')

  cat('dat_Survey.',rank,'.r <- psmelt(Survey.',rank,'.r)\n',sep = '')

  cat('dat_Survey.',rank,'.r$',rank,' <- as.character(dat_Survey.',rank,'.r$',rank,') \n',sep = '')

  cat('dat_Survey.',rank,'.r$',rank,'_all <- dat_Survey.',rank,'.r$',rank,' \n',sep = '')
  
  cat('dat_Survey.',rank,'.r$',rank,' <- if_else(dat_Survey.',rank,'.r$',rank,' %in% Survey.',rank,'.names.to.plot, dat_Survey.',rank,'.r$',rank,', "LowAbundance") \n',sep = '')

  cat('\n## \n')

  cat('\n \n')

}
```

### create vectors of top 10 taxa names

#### Survey




#### Exp







## Group low abundance (!%inc% top 10 taxa)

(no generating code just copy paste)

### Survey



# Survey taxonomy {.tabset .tabset-pills}



\
\

## Phylum {.unnumbered}
\
*Note:* Bacterial and archaeal phyla with a global abundance of ≤ 0.58% relative abundance have been agglomerated into "≤ 0.58% relative abundance". Vertical facets represent pits 1-4 and horizontal facets represent each basin-by-reach.\

<img src="figures/taxa_plots/AL-unnamed-chunk-1-1.png" width="155%" />

\
\

## Class {.unnumbered}
\
*Note:* Bacterial and archaeal classes with a global abundance of ≤ 2.8% relative abundance have been agglomerated into "≤ 2.8% relative abundance". Vertical facets represent pits 1-4 and horizontal facets represent each basin-by-reach.\

<img src="figures/taxa_plots/AL-unnamed-chunk-2-1.png" width="155%" />

\
\

## Order {.unnumbered}
\
*Note:* Bacterial and archaeal orders with a global abundance of ≤ 3.7% relative abundance have been agglomerated into "≤ 3.7% relative abundance". Vertical facets represent pits 1-4 and horizontal facets represent each basin-by-reach.\

<img src="figures/taxa_plots/AL-unnamed-chunk-3-1.png" width="155%" />

\
\

## Family {.unnumbered}
\
*Note:* Bacterial and archaeal families with a global abundance of ≤ 3.7% relative abundance have been agglomerated into "≤ 3.7% relative abundance". Vertical facets represent pits 1-4 and horizontal facets represent each basin-by-reach.\

<img src="figures/taxa_plots/AL-unnamed-chunk-4-1.png" width="155%" />

\
\

