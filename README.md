# Importing-a-tsv-files-in-R-programming-
# Importing a TSV file  (Top separated values)

library(tidyverse)

### US government Center for Medicare and Medicaid services

### Reading the data  
inpatient <- read_tsv("inpatient.tsv")
glimpse(inpatient)

### Since the same data can also be found on the internet, we can also import it
inpatient <- read_tsv('http://594442.youcanlearnit.net/inpatient.tsv')
glimpse(inpatient)


### Using your own names for the columns 
names <- c('DRG', 'ProviderID', 'Name','Address', 'City', 'State', 'ZipCode',
           'Region', 'Discharges', 'AverageCharges', 'AverageTotalPayments', 
           'AverageMedicarePayments')

### Supplying this to the new inspection data 
inpatient <- read_tsv('http://594442.youcanlearnit.net/inpatient.tsv', 
                      col_names = names)
glimpse(inpatient)
### you can see that all the variable names can be seen in the first line
### so we use the skip command to remove the first column or variable
inpatient <- read_tsv('http://594442.youcanlearnit.net/inpatient.tsv', 
                      col_names = names, skip = 1)
glimpse(inpatient)

#### Making some of data integers and some characters and some numerics
### you can make some as factors(f)

types <- 'ccccccccinnn'

### Supplying this to the new  data 
inpatient <- read_tsv('http://594442.youcanlearnit.net/inpatient.tsv', 
                      col_names = names, skip = 1, col_types = types)

glimpse(inpatient)





