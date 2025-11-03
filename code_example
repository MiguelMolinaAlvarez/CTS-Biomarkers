library(meta)
library(metafor)
library(dmetar)
library(dplyr)



meta_data <- metacont(Ni, 
                      MEANi, 
                      SDi, 
                      Nc, 
                      MEANc, 
                      SDc,
                      data = x,
                      studlab = paste(AUTHOR_YEAR, BIOMARKER, sep = " - "),
                      common = FALSE, 
                      random = TRUE,
                      method.tau = "REML", 
                      # method.random.ci = "HK"
                      # method.random.ci = "classic"
                      prediction = TRUE, 
                      sm = "SMD"
                      )

forest(meta_data,
       label.e = "XX", 
       label.c = "XX",
       test.overall = TRUE,
       sortvar = TE, 
       layout = "RevMan5"
       )


pro_global_summary <- data.frame(k = meta_data$k,
                                 SMD = meta_data$TE.random,
                                 CI_lower = meta_data$lower.random,
                                 CI_upper = meta_data$upper.random,
                                 p_value = meta_data$pval.random,
                                 tau = meta_data$tau
                                 )
