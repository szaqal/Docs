# R Cheetsheet

### Remove DataFrame

```
rm(df)
```

### Obtain help

```
help(filter)
```
## Filter Dataframe

```
View(subset(DF_NAME, DF_NAME$PROP>100000 & DH_NAME$PROP<200000));
```

```
View(DH_NAME[ which(DF_NAME$ClassName=='org.jboss.dmr.ModelNode'), ])
```

```
View(subset(DF_NAME, regexpr("^java.*",DF_NAME$ClassName)>0));
```

### Filter DataFrame and sum computation

```
format(structure(sum(subset(DF_NAME$PROP, regexpr(".*java.*",DF_NAME$PROP)>0)), class="object_size"), units="auto");
```

## Library

```
library()
```
