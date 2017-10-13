HW02\_Dplyr
================
Chad Fibke
2017-10-11

1.Installation of data set and data analysis packages
=====================================================

``` r
library(gapminder)
```

``` r
library(tidyverse)
```

    ## Loading tidyverse: ggplot2
    ## Loading tidyverse: tibble
    ## Loading tidyverse: tidyr
    ## Loading tidyverse: readr
    ## Loading tidyverse: purrr
    ## Loading tidyverse: dplyr

    ## Conflicts with tidy packages ----------------------------------------------

    ## filter(): dplyr, stats
    ## lag():    dplyr, stats

2.Quick exploration of data
===========================

### 2.A General analysis

What is the structure of gapminder?:

``` r
class(gapminder)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

The gapminder is a data.frame/tibble

How many rows and columns are in this tibble?:

``` r
str(gapminder)
```

    ## Classes 'tbl_df', 'tbl' and 'data.frame':    1704 obs. of  6 variables:
    ##  $ country  : Factor w/ 142 levels "Afghanistan",..: 1 1 1 1 1 1 1 1 1 1 ...
    ##  $ continent: Factor w/ 5 levels "Africa","Americas",..: 3 3 3 3 3 3 3 3 3 3 ...
    ##  $ year     : int  1952 1957 1962 1967 1972 1977 1982 1987 1992 1997 ...
    ##  $ lifeExp  : num  28.8 30.3 32 34 36.1 ...
    ##  $ pop      : int  8425333 9240934 10267083 11537966 13079460 14880372 12881816 13867957 16317921 22227415 ...
    ##  $ gdpPercap: num  779 821 853 836 740 ...

This shows us that there are 6 variables (columns), and 1704 observations (rows).

other ways to find these results?:

``` r
attributes(gapminder)
```

    ## $names
    ## [1] "country"   "continent" "year"      "lifeExp"   "pop"       "gdpPercap"
    ## 
    ## $class
    ## [1] "tbl_df"     "tbl"        "data.frame"
    ## 
    ## $row.names
    ##    [1]    1    2    3    4    5    6    7    8    9   10   11   12   13
    ##   [14]   14   15   16   17   18   19   20   21   22   23   24   25   26
    ##   [27]   27   28   29   30   31   32   33   34   35   36   37   38   39
    ##   [40]   40   41   42   43   44   45   46   47   48   49   50   51   52
    ##   [53]   53   54   55   56   57   58   59   60   61   62   63   64   65
    ##   [66]   66   67   68   69   70   71   72   73   74   75   76   77   78
    ##   [79]   79   80   81   82   83   84   85   86   87   88   89   90   91
    ##   [92]   92   93   94   95   96   97   98   99  100  101  102  103  104
    ##  [105]  105  106  107  108  109  110  111  112  113  114  115  116  117
    ##  [118]  118  119  120  121  122  123  124  125  126  127  128  129  130
    ##  [131]  131  132  133  134  135  136  137  138  139  140  141  142  143
    ##  [144]  144  145  146  147  148  149  150  151  152  153  154  155  156
    ##  [157]  157  158  159  160  161  162  163  164  165  166  167  168  169
    ##  [170]  170  171  172  173  174  175  176  177  178  179  180  181  182
    ##  [183]  183  184  185  186  187  188  189  190  191  192  193  194  195
    ##  [196]  196  197  198  199  200  201  202  203  204  205  206  207  208
    ##  [209]  209  210  211  212  213  214  215  216  217  218  219  220  221
    ##  [222]  222  223  224  225  226  227  228  229  230  231  232  233  234
    ##  [235]  235  236  237  238  239  240  241  242  243  244  245  246  247
    ##  [248]  248  249  250  251  252  253  254  255  256  257  258  259  260
    ##  [261]  261  262  263  264  265  266  267  268  269  270  271  272  273
    ##  [274]  274  275  276  277  278  279  280  281  282  283  284  285  286
    ##  [287]  287  288  289  290  291  292  293  294  295  296  297  298  299
    ##  [300]  300  301  302  303  304  305  306  307  308  309  310  311  312
    ##  [313]  313  314  315  316  317  318  319  320  321  322  323  324  325
    ##  [326]  326  327  328  329  330  331  332  333  334  335  336  337  338
    ##  [339]  339  340  341  342  343  344  345  346  347  348  349  350  351
    ##  [352]  352  353  354  355  356  357  358  359  360  361  362  363  364
    ##  [365]  365  366  367  368  369  370  371  372  373  374  375  376  377
    ##  [378]  378  379  380  381  382  383  384  385  386  387  388  389  390
    ##  [391]  391  392  393  394  395  396  397  398  399  400  401  402  403
    ##  [404]  404  405  406  407  408  409  410  411  412  413  414  415  416
    ##  [417]  417  418  419  420  421  422  423  424  425  426  427  428  429
    ##  [430]  430  431  432  433  434  435  436  437  438  439  440  441  442
    ##  [443]  443  444  445  446  447  448  449  450  451  452  453  454  455
    ##  [456]  456  457  458  459  460  461  462  463  464  465  466  467  468
    ##  [469]  469  470  471  472  473  474  475  476  477  478  479  480  481
    ##  [482]  482  483  484  485  486  487  488  489  490  491  492  493  494
    ##  [495]  495  496  497  498  499  500  501  502  503  504  505  506  507
    ##  [508]  508  509  510  511  512  513  514  515  516  517  518  519  520
    ##  [521]  521  522  523  524  525  526  527  528  529  530  531  532  533
    ##  [534]  534  535  536  537  538  539  540  541  542  543  544  545  546
    ##  [547]  547  548  549  550  551  552  553  554  555  556  557  558  559
    ##  [560]  560  561  562  563  564  565  566  567  568  569  570  571  572
    ##  [573]  573  574  575  576  577  578  579  580  581  582  583  584  585
    ##  [586]  586  587  588  589  590  591  592  593  594  595  596  597  598
    ##  [599]  599  600  601  602  603  604  605  606  607  608  609  610  611
    ##  [612]  612  613  614  615  616  617  618  619  620  621  622  623  624
    ##  [625]  625  626  627  628  629  630  631  632  633  634  635  636  637
    ##  [638]  638  639  640  641  642  643  644  645  646  647  648  649  650
    ##  [651]  651  652  653  654  655  656  657  658  659  660  661  662  663
    ##  [664]  664  665  666  667  668  669  670  671  672  673  674  675  676
    ##  [677]  677  678  679  680  681  682  683  684  685  686  687  688  689
    ##  [690]  690  691  692  693  694  695  696  697  698  699  700  701  702
    ##  [703]  703  704  705  706  707  708  709  710  711  712  713  714  715
    ##  [716]  716  717  718  719  720  721  722  723  724  725  726  727  728
    ##  [729]  729  730  731  732  733  734  735  736  737  738  739  740  741
    ##  [742]  742  743  744  745  746  747  748  749  750  751  752  753  754
    ##  [755]  755  756  757  758  759  760  761  762  763  764  765  766  767
    ##  [768]  768  769  770  771  772  773  774  775  776  777  778  779  780
    ##  [781]  781  782  783  784  785  786  787  788  789  790  791  792  793
    ##  [794]  794  795  796  797  798  799  800  801  802  803  804  805  806
    ##  [807]  807  808  809  810  811  812  813  814  815  816  817  818  819
    ##  [820]  820  821  822  823  824  825  826  827  828  829  830  831  832
    ##  [833]  833  834  835  836  837  838  839  840  841  842  843  844  845
    ##  [846]  846  847  848  849  850  851  852  853  854  855  856  857  858
    ##  [859]  859  860  861  862  863  864  865  866  867  868  869  870  871
    ##  [872]  872  873  874  875  876  877  878  879  880  881  882  883  884
    ##  [885]  885  886  887  888  889  890  891  892  893  894  895  896  897
    ##  [898]  898  899  900  901  902  903  904  905  906  907  908  909  910
    ##  [911]  911  912  913  914  915  916  917  918  919  920  921  922  923
    ##  [924]  924  925  926  927  928  929  930  931  932  933  934  935  936
    ##  [937]  937  938  939  940  941  942  943  944  945  946  947  948  949
    ##  [950]  950  951  952  953  954  955  956  957  958  959  960  961  962
    ##  [963]  963  964  965  966  967  968  969  970  971  972  973  974  975
    ##  [976]  976  977  978  979  980  981  982  983  984  985  986  987  988
    ##  [989]  989  990  991  992  993  994  995  996  997  998  999 1000 1001
    ## [1002] 1002 1003 1004 1005 1006 1007 1008 1009 1010 1011 1012 1013 1014
    ## [1015] 1015 1016 1017 1018 1019 1020 1021 1022 1023 1024 1025 1026 1027
    ## [1028] 1028 1029 1030 1031 1032 1033 1034 1035 1036 1037 1038 1039 1040
    ## [1041] 1041 1042 1043 1044 1045 1046 1047 1048 1049 1050 1051 1052 1053
    ## [1054] 1054 1055 1056 1057 1058 1059 1060 1061 1062 1063 1064 1065 1066
    ## [1067] 1067 1068 1069 1070 1071 1072 1073 1074 1075 1076 1077 1078 1079
    ## [1080] 1080 1081 1082 1083 1084 1085 1086 1087 1088 1089 1090 1091 1092
    ## [1093] 1093 1094 1095 1096 1097 1098 1099 1100 1101 1102 1103 1104 1105
    ## [1106] 1106 1107 1108 1109 1110 1111 1112 1113 1114 1115 1116 1117 1118
    ## [1119] 1119 1120 1121 1122 1123 1124 1125 1126 1127 1128 1129 1130 1131
    ## [1132] 1132 1133 1134 1135 1136 1137 1138 1139 1140 1141 1142 1143 1144
    ## [1145] 1145 1146 1147 1148 1149 1150 1151 1152 1153 1154 1155 1156 1157
    ## [1158] 1158 1159 1160 1161 1162 1163 1164 1165 1166 1167 1168 1169 1170
    ## [1171] 1171 1172 1173 1174 1175 1176 1177 1178 1179 1180 1181 1182 1183
    ## [1184] 1184 1185 1186 1187 1188 1189 1190 1191 1192 1193 1194 1195 1196
    ## [1197] 1197 1198 1199 1200 1201 1202 1203 1204 1205 1206 1207 1208 1209
    ## [1210] 1210 1211 1212 1213 1214 1215 1216 1217 1218 1219 1220 1221 1222
    ## [1223] 1223 1224 1225 1226 1227 1228 1229 1230 1231 1232 1233 1234 1235
    ## [1236] 1236 1237 1238 1239 1240 1241 1242 1243 1244 1245 1246 1247 1248
    ## [1249] 1249 1250 1251 1252 1253 1254 1255 1256 1257 1258 1259 1260 1261
    ## [1262] 1262 1263 1264 1265 1266 1267 1268 1269 1270 1271 1272 1273 1274
    ## [1275] 1275 1276 1277 1278 1279 1280 1281 1282 1283 1284 1285 1286 1287
    ## [1288] 1288 1289 1290 1291 1292 1293 1294 1295 1296 1297 1298 1299 1300
    ## [1301] 1301 1302 1303 1304 1305 1306 1307 1308 1309 1310 1311 1312 1313
    ## [1314] 1314 1315 1316 1317 1318 1319 1320 1321 1322 1323 1324 1325 1326
    ## [1327] 1327 1328 1329 1330 1331 1332 1333 1334 1335 1336 1337 1338 1339
    ## [1340] 1340 1341 1342 1343 1344 1345 1346 1347 1348 1349 1350 1351 1352
    ## [1353] 1353 1354 1355 1356 1357 1358 1359 1360 1361 1362 1363 1364 1365
    ## [1366] 1366 1367 1368 1369 1370 1371 1372 1373 1374 1375 1376 1377 1378
    ## [1379] 1379 1380 1381 1382 1383 1384 1385 1386 1387 1388 1389 1390 1391
    ## [1392] 1392 1393 1394 1395 1396 1397 1398 1399 1400 1401 1402 1403 1404
    ## [1405] 1405 1406 1407 1408 1409 1410 1411 1412 1413 1414 1415 1416 1417
    ## [1418] 1418 1419 1420 1421 1422 1423 1424 1425 1426 1427 1428 1429 1430
    ## [1431] 1431 1432 1433 1434 1435 1436 1437 1438 1439 1440 1441 1442 1443
    ## [1444] 1444 1445 1446 1447 1448 1449 1450 1451 1452 1453 1454 1455 1456
    ## [1457] 1457 1458 1459 1460 1461 1462 1463 1464 1465 1466 1467 1468 1469
    ## [1470] 1470 1471 1472 1473 1474 1475 1476 1477 1478 1479 1480 1481 1482
    ## [1483] 1483 1484 1485 1486 1487 1488 1489 1490 1491 1492 1493 1494 1495
    ## [1496] 1496 1497 1498 1499 1500 1501 1502 1503 1504 1505 1506 1507 1508
    ## [1509] 1509 1510 1511 1512 1513 1514 1515 1516 1517 1518 1519 1520 1521
    ## [1522] 1522 1523 1524 1525 1526 1527 1528 1529 1530 1531 1532 1533 1534
    ## [1535] 1535 1536 1537 1538 1539 1540 1541 1542 1543 1544 1545 1546 1547
    ## [1548] 1548 1549 1550 1551 1552 1553 1554 1555 1556 1557 1558 1559 1560
    ## [1561] 1561 1562 1563 1564 1565 1566 1567 1568 1569 1570 1571 1572 1573
    ## [1574] 1574 1575 1576 1577 1578 1579 1580 1581 1582 1583 1584 1585 1586
    ## [1587] 1587 1588 1589 1590 1591 1592 1593 1594 1595 1596 1597 1598 1599
    ## [1600] 1600 1601 1602 1603 1604 1605 1606 1607 1608 1609 1610 1611 1612
    ## [1613] 1613 1614 1615 1616 1617 1618 1619 1620 1621 1622 1623 1624 1625
    ## [1626] 1626 1627 1628 1629 1630 1631 1632 1633 1634 1635 1636 1637 1638
    ## [1639] 1639 1640 1641 1642 1643 1644 1645 1646 1647 1648 1649 1650 1651
    ## [1652] 1652 1653 1654 1655 1656 1657 1658 1659 1660 1661 1662 1663 1664
    ## [1665] 1665 1666 1667 1668 1669 1670 1671 1672 1673 1674 1675 1676 1677
    ## [1678] 1678 1679 1680 1681 1682 1683 1684 1685 1686 1687 1688 1689 1690
    ## [1691] 1691 1692 1693 1694 1695 1696 1697 1698 1699 1700 1701 1702 1703
    ## [1704] 1704

``` r
dim(gapminder)
```

    ## [1] 1704    6

The attributes of the data set will list all the variables names, tell us the structure, but the row names would be useless here. This attributes function could be usefull if each row was a person's name instead of obs 1. dim can also be a quick way to look at the number of rows/columns.

What is the data type of each variable?:

``` r
 sapply(gapminder,class)
```

    ##   country continent      year   lifeExp       pop gdpPercap 
    ##  "factor"  "factor" "integer" "numeric" "integer" "numeric"

sapply will list the class type for all the variables in this data set! I found how to do this [here](https://www.r-bloggers.com/find-type-of-variables-in-a-data-frame/)

### 2.B *Basic* analysis of a categorical variable

#### Continents

``` r
CON <- gapminder %>% select(continent)

table(CON)
```

    ## CON
    ##   Africa Americas     Asia   Europe  Oceania 
    ##      624      300      396      360       24

``` r
barplot(table(CON), main = "Number of observations from each continent", xlab = "continent", ylab ="Frequency", ylim = c(0, 750))
```

![](HW02_Dplyr_files/figure-markdown_github-ascii_identifiers/Barplot%20for%20continent-1.png)

### 2.C *Basic* analysis of a quantitative variable

#### Discrete: Population

Lets look at the summary statistics and make a boxplot

``` r
summary(gapminder$year)  
```

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##    1952    1966    1980    1980    1993    2007

``` r
boxplot(gapminder$year, main= "Boxplot", xlab= "Sample.1", ylab= "Years", ylim = c(1925, 2025))
```

![](HW02_Dplyr_files/figure-markdown_github-ascii_identifiers/Years_Boxplot-1.png)

#### Continues: GDP Per Capita

Lets summarize, but with a cool graph to make up for the **plain Jane** graphs above

``` r
summary(gapminder$gdpPercap) 
```

    ##     Min.  1st Qu.   Median     Mean  3rd Qu.     Max. 
    ##    241.2   1202.1   3531.8   7215.3   9325.5 113523.1

``` r
ggplot(gapminder, aes(gdpPercap)) +
  geom_density(alpha = 0.5, aes(group = continent, color = continent, fill = continent)) +
  scale_x_log10() +
  theme_classic() +
  labs(title = "GDPPerCapita Density Plot")
```

![](HW02_Dplyr_files/figure-markdown_github-ascii_identifiers/GDP_Density-1.png)

3.A deeper exploration of data
==============================

### Lets look into how the **relative** GDP has changed for some Asian countries over time:

I expect that gdp per capita will increace over time for **every selected country in Asia**... but lets find out!

lets find the starting gdp Per Capita for all the Asian countries (1952), and lets normalize all the gdp Per capita to the first year for that corresponding country!

``` r
selected.gapminder <- gapminder %>% select(continent, country, year, pop, gdpPercap)

Asian.Countries <- selected.gapminder %>% filter(continent == "Asia")

Asian.Countries.1 <- arrange(Asian.Countries, country, year, pop)

Asian.Countries.2 <-Asian.Countries.1  %>% group_by(country, year) %>%  summarize(mean_gdp=mean(gdpPercap))

Asian.Countries.3 <-Asian.Countries.2 %>% mutate(relative_gdp = mean_gdp/ nth(mean_gdp,1))

popsize <- Asian.Countries.1$pop

fixed <- data.frame(Asian.Countries.3, popsize )

head(fixed)
```

    ##       country year mean_gdp relative_gdp  popsize
    ## 1 Afghanistan 1952 779.4453    1.0000000  8425333
    ## 2 Afghanistan 1957 820.8530    1.0531246  9240934
    ## 3 Afghanistan 1962 853.1007    1.0944972 10267083
    ## 4 Afghanistan 1967 836.1971    1.0728105 11537966
    ## 5 Afghanistan 1972 739.9811    0.9493689 13079460
    ## 6 Afghanistan 1977 786.1134    1.0085549 14880372

note: I could not get the population size to stay in the tibble so thats why I had to add the cooridinating population size tibble!

Alright so we have used some of the cool tricks in Dplyr to digest this data, but now lets use ggplots to see what it spits out!

``` r
(Crazy<-ggplot(Asian.Countries.3, aes(x = year, y = relative_gdp))+ geom_jitter()+
labs(y = "Relative GDP/Capita", x = "Years", title = "Asian Countries' GPD/Capita Over the Years")+
facet_wrap(~ country, nrow = 5))
```

![](HW02_Dplyr_files/figure-markdown_github-ascii_identifiers/Some.crazy.scatter.plots-1.png)

I tried splitting the counties across 5 rows, but this seems like a lot!I'm going to pick a view countries to compare so this doesn’t hurt your eyes.

``` r
(Easyfix <-subset(fixed, country %in% c("Syria","Singapore", "Iraq")))
```

    ##       country year  mean_gdp relative_gdp  popsize
    ## 109      Iraq 1952  4129.766    1.0000000  5441766
    ## 110      Iraq 1957  6229.334    1.5083987  6248643
    ## 111      Iraq 1962  8341.738    2.0199057  7240260
    ## 112      Iraq 1967  8931.460    2.1627036  8519282
    ## 113      Iraq 1972  9576.038    2.3187845 10061506
    ## 114      Iraq 1977 14688.235    3.5566749 11882916
    ## 115      Iraq 1982 14517.907    3.5154309 14173318
    ## 116      Iraq 1987 11643.573    2.8194267 16543189
    ## 117      Iraq 1992  3745.641    0.9069862 17861905
    ## 118      Iraq 1997  3076.240    0.7448944 20775703
    ## 119      Iraq 2002  4390.717    1.0631879 24001816
    ## 120      Iraq 2007  4471.062    1.0826429 27499638
    ## 301 Singapore 1952  2315.138    1.0000000  1127000
    ## 302 Singapore 1957  2843.104    1.2280495  1445929
    ## 303 Singapore 1962  3674.736    1.5872640  1750200
    ## 304 Singapore 1967  4977.419    2.1499444  1977600
    ## 305 Singapore 1972  8597.756    3.7137118  2152400
    ## 306 Singapore 1977 11210.089    4.8420821  2325300
    ## 307 Singapore 1982 15169.161    6.5521622  2651869
    ## 308 Singapore 1987 18861.531    8.1470431  2794552
    ## 309 Singapore 1992 24769.891   10.6990982  3235865
    ## 310 Singapore 1997 33519.477   14.4783911  3802309
    ## 311 Singapore 2002 36023.105   15.5598076  4197776
    ## 312 Singapore 2007 47143.180   20.3630086  4553009
    ## 325     Syria 1952  1643.485    1.0000000  3661549
    ## 326     Syria 1957  2117.235    1.2882591  4149908
    ## 327     Syria 1962  2193.037    1.3343819  4834621
    ## 328     Syria 1967  1881.924    1.1450809  5680812
    ## 329     Syria 1972  2571.423    1.5646157  6701172
    ## 330     Syria 1977  3195.485    1.9443341  7932503
    ## 331     Syria 1982  3761.838    2.2889390  9410494
    ## 332     Syria 1987  3116.774    1.8964418 11242847
    ## 333     Syria 1992  3340.543    2.0325966 13219062
    ## 334     Syria 1997  4014.239    2.4425158 15081016
    ## 335     Syria 2002  4090.925    2.4891766 17155814
    ## 336     Syria 2007  4184.548    2.5461426 19314747

``` r
Easyfix <- ggplot(Easyfix, aes(x = year, y = relative_gdp, size = popsize))+ geom_jitter()+
labs(y = "Relative GDP/Capita", x = "Years", title = "Asian Countries' GPD/Capita Over the Years") + facet_wrap(~ country)

(Easyfix <- Easyfix + geom_line(color= "darkblue", lwd = 1))
```

![](HW02_Dplyr_files/figure-markdown_github-ascii_identifiers/easy.on.the.eyes-1.png)

II used geom\_line so we can see the trend in the measure of difference in relative GDP/capita between all years and 1952. I also scaled each observation by the corresponding population size!

We can see that only some countries show an increased GDP/capita over time, so I was wrong because I did not consider cofounder variables (war, political stability, and much more)!

4.But I want to do more!
========================

The provided code:

``` r
filter(gapminder, country == c("Rwanda", "Afghanistan"))
```

    ## # A tibble: 12 x 6
    ##        country continent  year lifeExp      pop gdpPercap
    ##         <fctr>    <fctr> <int>   <dbl>    <int>     <dbl>
    ##  1 Afghanistan      Asia  1957  30.332  9240934  820.8530
    ##  2 Afghanistan      Asia  1967  34.020 11537966  836.1971
    ##  3 Afghanistan      Asia  1977  38.438 14880372  786.1134
    ##  4 Afghanistan      Asia  1987  40.822 13867957  852.3959
    ##  5 Afghanistan      Asia  1997  41.763 22227415  635.3414
    ##  6 Afghanistan      Asia  2007  43.828 31889923  974.5803
    ##  7      Rwanda    Africa  1952  40.000  2534927  493.3239
    ##  8      Rwanda    Africa  1962  43.000  3051242  597.4731
    ##  9      Rwanda    Africa  1972  44.600  3992121  590.5807
    ## 10      Rwanda    Africa  1982  46.218  5507565  881.5706
    ## 11      Rwanda    Africa  1992  23.599  7290203  737.0686
    ## 12      Rwanda    Africa  2002  43.413  7852401  785.6538

This will not provide all the observations, this is because when using == the country vector is not the same length as the filter vector 'c("Rwanda", "Afghanistan")'. So the filter will look through each observation for "Rwanda" if found the observation will be kept THEN "Afghanistan". This causes every second Afghanistan observation to be found (notice that we only have the year 1957, which is found in every second observation). This is also why we only have every first Rwanda observation as well.
...but this will find all the observations!

``` r
filter(gapminder, country %in% c("Rwanda", "Afghanistan"))
```

    ## # A tibble: 24 x 6
    ##        country continent  year lifeExp      pop gdpPercap
    ##         <fctr>    <fctr> <int>   <dbl>    <int>     <dbl>
    ##  1 Afghanistan      Asia  1952  28.801  8425333  779.4453
    ##  2 Afghanistan      Asia  1957  30.332  9240934  820.8530
    ##  3 Afghanistan      Asia  1962  31.997 10267083  853.1007
    ##  4 Afghanistan      Asia  1967  34.020 11537966  836.1971
    ##  5 Afghanistan      Asia  1972  36.088 13079460  739.9811
    ##  6 Afghanistan      Asia  1977  38.438 14880372  786.1134
    ##  7 Afghanistan      Asia  1982  39.854 12881816  978.0114
    ##  8 Afghanistan      Asia  1987  40.822 13867957  852.3959
    ##  9 Afghanistan      Asia  1992  41.674 16317921  649.3414
    ## 10 Afghanistan      Asia  1997  41.763 22227415  635.3414
    ## # ... with 14 more rows

\`\`\`
