# FRACASSO_MORVAN_AVC_dossier

#  **I. Introduction**

En 2019 et selon l'organisation mondiale de la santé, 12.22 millions de personnes ont subit un AVC et 6.55 millions de personnes en sont décédées, faisant de ce dernier la deuxième cause de décès dans le monde. L'AVC, accident vasculaire cérébral aussi appellé ataque, apparaît lorsque la circulation sanguine est interrompue par un vaisseau sanguin bouché (AVC ishémique) ou encore un vaisseau sanguin rompu (AVC hémorragique). Les signes d'alertes sont une apparition soudaine et brutale d'une déformation de la bouche, une faiblesse d'un côté du corps ou encore des troubles de la parole. En cas d'attaque, le risque de décès est élevé et si celui-çi n'entraîne pas la mort, il peut causer des repercussions à long terme comme la perte de vue et de parole ou encore une paralysie. Selon l'INSERM, le meilleur moyen de lutter contre les AVC est la prévention dite "première" c'est-à-dire sur le dépistage et le contrôle des risques vasculaires : la pression artérielle, le niveau de cholestérol, le diabète, l'obésité, la consommation d'alcool, le tabagisme ou encore la sédentarité. 

Dans cette analyse, nous allons nous servir d'une base de données issue de Kaggle contenant 40910 observations dans l'objectif de prévoir ces accidents vasculaires cérébraux avec plusieurs facteurs d'influences. Cette base de données contient donc une variable à expliquer qui est de type binaire c'est-à-dire qu'elle prend 1 lorsque l'individu a subit un accident vasculaire cérébral et elle prend 0 lorsque cette personne n'a subit aucun accident. Nous avons également dans cette base dix variables explicatives dont trois variables quantitatives discrètes (l'âge, le taux de glucose et l'indice de masse corporelle), une variable catégorielle (la catégorie socio-professionnelle), et cinq variables binaires (l'hypertension, maladie cardiovasculaire, le fait d'être marié, la localisation, la cigarette).

# **II. Analyse exploratoire**

Afin d'augmenter nos connaissances sur les variables présentes dans la base de données, nous réalisons quelques statistiques descriptives. Dans un premier temps, nous commençons par faire une analyse univariée de notre variable dépendante ainsi que de nos variables explicatives. Dans un deuxième temps, afin
d'avoir un apriori sur les relations existantes entre les variables explicatives et notre variable à expliquer qualitatives, nous réalisons une analyse bivariée. 

## *II.1. Analyse univariée* 

### II.1.A. Variable dépendante


<p align="center">
<img width="1430" alt="Capture d’écran 2023-02-08 à 15 19 43" src="https://user-images.githubusercontent.com/118168094/217556039-42a19a1f-d5c5-4328-bb05-10faf0e085c1.png">
</p>

Nous commençons par faire une analyse rapide de la variable qualitative à prédire qui prend 0 lorsque l'individu ne subit pas d'arrêt cardiaque vasculaire et qui prend 1 lorsque celui-çi en subit un. Nous observons que globalement la variable dépendante semble très bien répartie puisque nous observons que l'effectif de la catégorie 1 prend 20460 observations et l'effectif de la catégorie 0 prend 20450 observations. Ceçi nous affirme que cette variable n'est pas déséquilibrée puisqu'il y'a autant d'effectifs dans la modalité 1 que dans la modalité 0. Nous n'allons donc pas devoir procéder par des techniques de sous ou sur échnatillonnage pour ajuster la distrbution des deux classes. Nous pouvons passer à la suite de l'analyse exploratoire en faisant quelques statistiques descriptives sur les variables explicatives. 

### II.1.B. Variables explicatives

<p align="center">
<img width="429" alt="Capture d’écran 2023-02-08 à 15 49 42" src="https://user-images.githubusercontent.com/118168094/217563922-ad4ea162-0a82-46d4-bea2-83fccc2924f3.png">
</p>

Le tableau ci-dessus représente un récapitultaif des statistiques des trois variables explicatives quantitatives. En effet, il rend compte du nombre total des valeurs que prennent ces variables, de leurs moyennes, médiances et écart-types. Il décrit également les valeurs minimums et maximums ainsi que leurs premiers et troisièmes quartiles. Nous pouvons explorer et analyser chaque variable indépendemment des autres: 

 **L'âge:** Nous nous intéressons d'abord à l'âge de nos individus. Nous remarquons dans un premier temps que la valeur minimum est de -9, ce qui signifie qu'une faute de frappe a été commise puisque nous devrions avoir uniquement des valeurs positives. Cette valeur devra être supprimée par la suite. Ensuite, nous observons un écart assez important entre cette valeur minimum et la valeur maximum; l'âge maximum est de 103 ans ce qui est probable, néanmoins cette valeur peut-être également et potentiellement considérée comme atypique. Dans un deuxième temps, nous nous intéressons à la médiane et la moyenne de cette variable. La moyenne est de 51,33 tandis que la médiane est de 52 ce qui signifie que la moyenne d'âge des individus est de 51,33 et que 50% des individus ont 52 ans. Si nous nous intéressons de plus près à l'écart entre ces deux mesures nous pouvons dire que s'il existe des valeurs atypiques, celles-çi se trouvent en-dessous de la moyenne puisque cette dernière est en-dessous de la médiane. Intéressons nous désormais aux quartiles : comme le premier quartile est de 35 et le troisième quartile de 68, nous pouvons dire que 25% des individus ont moins de 35 ans et que 75% ont moins de 68 ans. Nous pouvons supposer que plus l'âge est élevé et plus le nombre de personnes subissant un AVC est important. 

 **L'IMC(Indice de masse corporelle):** Nous nous intéressons ensuite à l'indice de masse corporelle de cette population. Comme pour l'âge, nous remarquons un écart très important entre la valeur minimum et la valeur maximum de l'IMC, en effet la valeur la plus petite est de 11,5 tandis que la valeur la plus élevée est de 92. Cette dernière valeur semble trop élevée puisque l'IMC moyen est de 30,4 et nous supposons qu'elle est anormale, nous verrons par la suite s'il faut la supprimer. Si nous nous intéressons à la moyenne et la médiane qui sont respectivement de 30,4 et de 29,4, nous pouvons dire que l'IMC moyen est de 30,4 et 50% des individus ont un indice de masse corporelle à 29,4. En regardant de plus prés cet écart, nous pouvons supposer que s'il existe des valeurs atypiques, celles-çi se trouvent au dessus de la moyenne puisque celle-çi se trouve être au-dessus de la médiane. Intéressons nous désormais aux quartiles : comme le premier quartile est de 25,9 et le troisième quartile de 34,1, nous pouvons dire que 25% des individus ont une masse corporelle de 25,9
et que 75% possèdent un indice 34,1. Nous pouvons supposer que plus l'indice de masse corporelle est élevé et plus le nombre de personnes subissant un AVC est important. 

 **Le niveau moyen de glycémie:** Nous nous intéressons dernièrement au niveau moyen de glycémie de notre base de données. Comme pour les deux variables précédentes, nous observons un écart très important entre la valeur minimum et la valeur maximum du niveau moyen de glycémie; la valeur minimum est de 55,12 tandis que la valeur maximum est de 271,74. Si nous nous intéressons à la moyenne et la médiane qui sont respectivement de 122,07 et de 97,92, nous pouvons dire que que la moyenne du niveau moyen de glycémie est de 122,07 et que 50% possédent un niveau moyen de glycémie égale à 97,92. En regardant de plus prés cet écart, nous pouvons supposer que s'il existe des valeurs atypiques, celles-çi se trouvent au dessus de la moyenne puisque celle-çi se trouve être au-dessus de la médiane. Intéressons nous désormais aux quartiles : comme le premier quartile est de 55,12 et le troisième quartile de 167,59 nous pouvons dire que 25% possèdent un niveau moyen de glycémie de 55,12 tandis que 75% en possèdent un de 167,59. Nous supposons que plus le niveau moyen de glycémie est élevé et plus le nombre de personnes atteintes d'un AVC est élevé. 

<p align="center">
<img width="1430" alt="Capture d’écran 2023-02-08 à 15 19 19" src="https://user-images.githubusercontent.com/118168094/217556189-214e38b1-4b6c-41dd-8875-835174993f96.png">
  
<img width="392" alt="Capture d’écran 2023-02-08 à 17 49 00" src="https://user-images.githubusercontent.com/118168094/217597008-d5fe812a-8272-4cd6-919e-d534e5d191a3.png">
  
</p>

La figure ci-desus représente l'histogramme des trois variables explicatives quantitatives et en dessous on retrouve respectivement le skewness (en haut) ainsi que le kurtosis (en bas) de ces variables. Le premier est le coefficient d’asymétrie de la distribution, il évalue le défaut de symétrie d’une distribution : il est nul pour une distribution symétrique, positif pour une distribution étalée à droite et négatif pour une distribution étalée à gauche. Le deuxième est le coefficient d’aplatissement de la distribution : il évalue le défaut d’aplatissement d’une distribution. Il est nul pour une distribution normale, négatif pour une distribution moins “aplatie” et positif pour une distribution davantage “aplatie” qu’une distribution normale. Ces trois mesures vont nous donner une idée de la distribution des observations correspondant aux trois variables. Globalement, nous observons que seule la variable "âge" semble correctement distribuée, les deux autres variables quant à elles semblent anormalement distribués. À présent, intéressons-nous à chaque variable indépendemment des autres: 

 **L'âge:** Nous nous intéressons d'abord à l'histogramme représentant la distribution de l'âge de nos individus. À priori, la variable semble normalement distribuée. Intéréssons nous au skewness et au kurtosis, le premier est de -0.078 et le deuxième est de -0.8, ces deux sont assez proche de 0 mais négatifs ce qui signifie que la distribution est légèrement étalée à gauche et moins aplatie que la normale. 

 **L'IMC(Indice de masse corporelle):** Intéressons nous ensuite à l'histogramme représentant la distribution de l'indice de masse corporelle. À priori, la variable ne semble pas normalement distribuée. Intéréssons nous au skewness et au kurtosis, le premier est de 1,077 et le deuxième est de 2.63, ces deux sont assez loins de 0 et positifs ce qui sifnifie que la distribution est étalée à droite  et moins aplatie que la normale. 

 **Le niveau moyen de glycémie:** Nous nous intéressons dernièrement à l'histogramme représentant la distribution du niveau moyen de glycémie.  À priori, la variable ne semble pas normalement distribuée. Intéréssons nous au skewness et au kurtosis, le premier étant de 0,94 et le deuxième de -0,5, nous pouvons dire que la diribution est étalée à droité et moins aplatie qu'une distribution normale. 

<p align="center">
<img width="1248" alt="Capture d’écran 2023-02-08 à 15 18 59" src="https://user-images.githubusercontent.com/118168094/217556311-95172a55-abad-409b-94b0-9dc5d57aa0c5.png">
</p>

La figure ci-dessus représente l'effectif des modalités dans chaque variable catégorielle. Afin de mieux comprendre nos variables explicatives, nous allons expliquer ce que représente les valeurs pour chaque variable.

 **Sex:** Cette première variable représente le sexe de l'individu, celle-çi prend 0 lorsque l'individu est un homme et prend 1 lorsque l'individu est une femme. 

 **Hypertension:** Cette deuxième variable représente le fait qu'un individu fasse de l'hypertension ou non. Cette dernière prend 0 si celui-çi n'en fait pas et prend 1 lorsqu'il en fait. 

 **Heart_disease:** Cette troisième variable représente le fait d'avoir une maladie cardiaque ou non. Cette dernière prend 0 lorsque l'individu n'a pas de maladie cardiaque et prend 1 lorsque ce dernier présente une maladie cardiaque.  

 **Ever_married:** Cette quatrième variable représente le fait d'être marié ou non. Celle-çi prend 1 lorsque l'individu est marié et prend 0 lorsqu'il n'est pas marié. 

 **Work_type:** Cette cinquième variable représente la catégorie socio-professionnelle de la personne. Elle prend 0 lorsque l'individu est un enfant, prend 1 lorsque l'individu n'a jamais travaillé, prend 2 lorsque l'individu travaille dans le public, prend 3 lorsque celui-çi est un entrepreneur et enfin prend 4 lorsqu'il travaille dans le privé. 

 **Residence_type:**  Cette sixième variable représente la localisation de la personne concernée. Elle prend 0 lorsque l'individu habite dans une zone rurale et prend 1 lorsque l'individu habite dans une zone urbaine. 

 **smoking_status:** Cette dernière variable représente le fait que l'individu fume ou non, cette dernière prend 0 lorsque ce dernier ne fume pas et prend 1 lorsque l'individu fume. 

## *II.2. Analyse bivariée*

Nous commençons par regarder les distributions des variables âge, indice de masse corporelle et le niveau moyen de glycémie en fonction des deux modalités de la variable dépendante. 

<p align="center">
<img width="1428" alt="Capture d’écran 2023-02-08 à 15 18 33" src="https://user-images.githubusercontent.com/118168094/217556473-8cef10f8-0a85-4313-87f4-b0c8f567d00c.png">
</p>

Les graphiques ci-dessus représentent les histogrammes des variables explicatives quantitatives. Sur chaque histogramme, nous avons la distinction entre les deux types d’évènements, en jaune sont représentés les cas d'observations ne subissant pas d'AVC et les cas d'AVC sont représentés en violet. Globalement, nous ne voyons pas des différences au sein des distributions pour les deux catégories. Nous regardons les deux distributions de chaque variable indépendemment des autres. 

 **avg_glucose_level:** Pour la troisième variable, c'est-à-dire le niveau moyen de glycémie, nous remarquons sur la figure que les distributions à gauche semblent différentes entre les cas d'AVC et ceux qui n'en subissent pas. En effet, la distribution des cas de non AVC est beaucoup plus élevée que la catégorie des ACV. Si nous nous intéressons à la partie droite de la distribution, nous remarquons qu'à l'inverse la distribution pour les cas d'AVC est plus élevée que celle des non AVC. Nous supposons donc que cette variable apporte de l'information qui permettrait de distinguer les cas d'AVC et les cas sains. 

 **age:** En ce qui concerne la variable age, nous ne remarquons pas une grande  différence entre la distribution des cas d'AVC et la distribution des cas inverse. La distribution des cas d'AVC semble un peu plus élevée et plus étalée que celle des cas de non AVC. 

 **bmi:** Nous regardons dans un dernier temps les deux distributions de la variable de l'indice de masse corporelle. Comme pour la variable âge, nous ne voyons pas de grande différence entre les deux catégories même si la catégorie d'AVC semble un peu plus élevée. 

Nous supposons donc que pour ces deux dernières variables, celles-çi apporteraient peu d'information concernant la distinction entre les deux catégories. Pour aller plus loin dans notre analyse, nous pouvons réaliser des boîtes à moustaches pour chaque variable en fonction des deux catégories. Nous pourrons voir les différences de répartition de façon plus précise.

<p align="center">
<img width="1428" alt="Capture d’écran 2023-02-08 à 15 18 15" src="https://user-images.githubusercontent.com/118168094/217556984-5cf3a9a7-c8fa-4218-8356-1004bdbfb7b2.png">
</p>

Pour chaque graphique, le boxplot bleu représente la distribution des cas qui ne subissent pas d'AVC et le boxplot orange représente celui de la distribution des cas d'AVC. Globalement, nous n'observons pas de différence entre les deux catégories notamment pour la variable d'indice de masse corporelle. Les médianes et les quartiles semblent très proches pour cette variable, en effet la médiane reste à 30 peu importe la catégorie. En ce qui concerne la variable âge, nous remarquons une légère différence, en effet la médiane pour les cas qui ne subissent pas d'AVC est de 50 environ tandis que celui des cas d'AVC est de 57 environ. Enfin, pour la variable taux de glycémie, nous observons une différence entre ces deux catégories que ce soit pour les médianes que pour les quartiles. En effet, la médiane pour les cas d'AVC semble plus élevée et les quartiles plus éloignés. 

En résumé, nous supposons que les variables age et taux de glycémie apportent de l'information en ce qui concerne la distinction des cas d'AVC et les cas inverses, tandis que la variable indice de masse corporelle apporte peu d'information dans la prédiction des cas d'AVC et les cas inverses. Ces hypothèses vont devoir être confirmer par la suite avec des tests.

<p align="center">
<img width="1437" alt="Capture d’écran 2023-02-08 à 15 18 00" src="https://user-images.githubusercontent.com/118168094/217557044-db645f71-8b5e-4133-a0f0-56c4f3d3322d.png">
</p>

Cette figure ci-dessus représente le nombre d'effectifs en fonction des variables catégorielles mais également en fonction des modalités que prennent la variable à prédire.

# **III. Préparation de la base de données**

Après avoir analyser nos variables une à une puis les relations existantes entre ces dernières et la variable à prédire, nous pouvons entamer la préparation de notre base de données. Nous commençons par nettoyer notre base en supprimant les valeurs manquantes ainsi que les valeurs extrêmes afin qu'elles n'aient pas d'influence dans les estimations futures. Nous finissons par dichotomiser notre variable "work_type" ayant cinq modalités. Dans un deuxième temps, nous passons à la sélection des variables en faisant quelques tests statistiques. 

## *III.1. Nettoyage des données*

Dans cette première petite analyse, nous observons des anomalies en ce qui concerne la variable "sex". Premièrement, nous observons avec la fonction info() que cette variable est de type float alors qu'elle devrait être de type integer, de plus nous constations qu'elle ne comporte que 40907 valeurs numériques alors que les autres variables comportent 40910 valeurs numériques. Deuxièmement, lorsque nous essayons de transformer cette variable sous format integer, cela ne marche pas. Nous supposons que ce problême est dû au fait que cette variable comporte des valeurs manquantes. Nous passons donc directement à la suppression des valeurs manquantes et des valeurs atypiques dans notre base de données.

### III.1.A. Valeurs manquantes

Nous avons vérifié si nos variables comportaient des valeurs manquantes en faisant la somme des NA de chaque colonne. Nous avons donc remarqué que la variable "sex" possèdait trois valeurs manquantes. Nous les avons supprimées et nous sommes arrivé une base de données comportant 40907 observations. La transformation de la variable en integer est devenue possible. À présent, nous passons à l'analyse des points atypiques.

### III.1.B. Points atypiques

<p align="center">
<img width="1429" alt="Capture d’écran 2023-02-08 à 15 17 38" src="https://user-images.githubusercontent.com/118168094/217557090-5515a071-ccdc-4dc3-ab9e-f4a1790e5426.png">
</p>

À partir des boîtes à moustaches, nous observons que sur les trois variables quantitatives explicatives, seulement une, présente des valeurs plus extrêmes. L'âge et le taux de glycémie ne présentent aucunes valeurs potentiellement atypiques. Cependant, la variable "bmi"(indice de masse corporelle) présente des valeurs atypiques surtout pour les individus ayant un indice supérieure à 70. Si nous nous rappelons de notre première figure qui représente les boîtes à moustaches en fonction des deux catégories, nous remarquons que les valeurs extrêmes concernent notamment les individus n'ayant pas subi d'accident vasculaire. Nous utilisons donc un test ESD (obtenu sur Github proposé par François) pour confirmer ou non la présence de valeurs extrêmes pour cette variable. À l'issu de ce test, nous observons que la variable "bmi" présente cinq valeurs atypiques qui sont au-dessus de 92, nous gardons donc seulement les individus pour lesquels le niveau de masse corporelle est inférieur à 92.

### III.1.C. Dichotomisation

Dans cette dernière partie sur le nettoyage des données, nous dichotomisons notre variable "work_type" afin d'avoir cinq variables binaires avec work_type_0(enfants), work_type_1(non travailleurs), work_type_2(travailleurs dans le public), work_type_3(travailleurs indépendants) et work_type_4(travailleurs dans le privé). Nous savons que cette dichotomisation crée des déséquilibres dans ces nouvelles variables surtout en ce qui concerne les deux premières variables mais nous décidons néanmoins de les garder pour la suite de l'analyse puisqu'elles contiennent des informations que nous jugeons importantes. 

## *III.2. Sélection des variables*

Afin de procéder à une séléction de variables, nous réalisons des tests statistiques sur les liasons entre les variables explicatives quantitatives et qualitatives sur notre variable à prédire. En ce qui concerne les variables quantiatives, nous procédons à un test de Mann-Withney permettant de voir si ces dernières permettent d'expliquer la variable "stroke". Nous faisons de même avec les variables qualitatives avec le test d'indépendance de Khi-2. 

### III.2.A. Tests entre Stroke et les variables explicatives

#### III.2.A.1. Variables quantitatives

Précédemment, nous avons posé des hypothèses sur les liens existant entre les trois variables explicatives et la variable à prédire grâce aux histogrammes de distribution et aux boîtes à moustaches en fonction des modalités 0 et 1. Nous avons supposé qu'il y'avait une différence significative entre les statistiques et les fréquences lorsque la variable à prédire prenait 0 ou 1 pour les deux variables "âge" et "taux de glycémie". En revanche, nous avions eu des doutes quant à la différence entre les deux catégories pour la variable "indice de masse corporelle" supposant que cette dernière possédait peu d'information pour expliquer les cas d'AVC et les cas contraires. Nous cherchons donc à savoir si les valeurs des deux catégories pour la variable à prédire sont différentes en fonction de chacunes des trois variables quantitatives. Pour cela, nous allons utiliser un test permettant de mesurer les différences entre les moyennes de deux groupes afin de savoir si elles sont statistiquement significatives.

Le test de Student nous permet de tester cette hypothèse. Cependant, il faut répondre à deux conditions pour l’utiliser, à savoir la normalité de distribution des variables quantitatives, ainsi que l’égalité des variances. Si la première condition n’est pas respectée, il faudra passer par le test de Wilcoxon-Mann-Withney qui est un test non paramétrique puisqu'il n’a pas besoin de condition sur la distribution de probabilité au préalable. Nous commençons donc par effectué le test de Kolmogorov-smirnov afin de savoir si les variables quantitatives suivent une loi normale. 

<p align="center">
<img width="304" alt="Capture d’écran 2023-02-08 à 15 38 21" src="https://user-images.githubusercontent.com/118168094/217561689-a3d79066-0467-43e0-bf6d-4babeadecfb5.png">
</p>

Nous retrouvons ci-dessus les p-values de chaque variable associée au test de normalité. Nous rappelons que ce test repose sur deux hypothèses: l’hypothèse nulle (distribution gaussienne) et l’hypothèse alternative (distribution non gaussienne). Lorsque la p-value est inférieure à 0.05, l’hypothèse nulle est rejetée,  ce qui signifie que la distribution est non gaussienne et que la variable ne suit pas une loi normale. Si les variables suivent une loi normale, nous utilisons alors le test de Bartlett pour vérifier l’égalité des variances, dans le cas contraire nous utilisons le test de la somme des rangs de Wilcoxon. Nous voyons, içi, que les p-values sont de 0 ce qui signifie que ces trois variables ne suivent pas une loi normale et nous devons effectué le test de Wilcoxon. 

<p align="center">
<img width="948" alt="Capture d’écran 2023-02-08 à 15 38 30" src="https://user-images.githubusercontent.com/118168094/217561703-efd4aa49-ba86-49c7-8ec5-943518ba50ce.png">
</p>

Ci-dessus nous retrouvons les p-values du test de Mann-Withney. Ce dernier, comme le test de Student, utilise le rang de chaque observation afin de voir si les groupes sont issus de la même population, c’est-à-dire qu’ils ont une position équivalente. Lorsque la p-value est inférieure à 0.05, cela signifie que les moyennes des échantillons sont significativement différentes, et donc que les variables quantitatives possèdent une liaison avec la variable dépendante. Au vu des résultats qui sont de 0, nous pouvons dire que ces trois variables permettent d'expliquer la valeur que prend la variable à prédire. Nous sommes donc rassurées par rapport aux première hypothèses faites sur la variable "bmi". Nous conservons donc ces trois variables.

#### III.2.A.2. Variables qualitatives

À présent, nous essayons de voir s'il existe une relation entre nos variables qualitatives et notre variable à prédire. Nous devons utiliser le test de Khi-2 permettant de tester l'indépendance entre deux variables qualitatives.

<p align="center">
<img width="599" alt="Capture d’écran 2023-02-08 à 15 38 43" src="https://user-images.githubusercontent.com/118168094/217561721-a88b99b2-a772-4fe7-b909-f4a7c0b87bfd.png">
</p>

Affichées ci-dessus, nous retrouvons les p-values du test de Khi-deux des variables explicatives sur notre variable à prédire. Nous rappelons que l'hypothèse nulle est l'indépendance des variables entre-elles et l'hypothèse alternative est la dépendance entre ces deux variables. Si la p-value est inférieur à 0,05 alors l'hypothèse d'indépendance est rejetée et ces deux variables sont statistiquement liées. À l'issu de ce test, nous observons que les p-values sont toutes inférieures à 0,05, cela signifie qu'au seuil de 5% les variables explicatives sont statistiquement dépendantes avec la variable à prédire stroke. 

### III.2.B. Tests entre les variables explicatives 

Après avoir vérifié que toutes nos variables soient importantes pour expliquer notre variable dépendantes, nous regardons les liens existant entre les variables explicatives. Pour les variables qualitatives, nous nous référons également au test de Khi-deux afin de voir si il existe des relations d'indépendances entre nos variables, s'il en existe une nous ne pouvons pas introduire les deux mêmes variables dans un même modèle. Ensuite, nous utilisons le test au rang de spearman avec une matrice de corrélation afin de voir si il n'existe pas de corrélations trop fortes entre nos variables sinon nous devrions supprimer une variable. 

#### III.2.B.1. Variables qualitatives

<p align="center">
<img width="722" alt="Capture d’écran 2023-02-08 à 15 38 58" src="https://user-images.githubusercontent.com/118168094/217561739-b83da1c5-dd5f-40c1-ad81-37b4aaf709cd.png">
</p>

Ci-dessus, nous retrouvons un extrait des résultats de notre test. (Nous avons mis qu'un extrait car la sortie prenait trop de place). D'apès les p-values ci-dessus, nous observons malheureusement que presque toutes nos variables sont dépendantes puisque leurs p-values sont toutes inférieures à 0,05 à l'exception de quelques pairs de variables. Pour ne pas perdre trop d'information, nous préférons les garder pour la suite de notre étude. 

#### III.2.B.2. Variables quantitatives

À présent, nous passons à l'analyse des relations entre les variables quantitatives grâce à la matrice de corrélation. Si les corrélations sont supérieures à 0,5, nous n'intégrerons pas ces variables dans un même modèle dans la partie modélisation.

<p align="center">
<img width="718" alt="Capture d’écran 2023-02-08 à 15 58 27" src="https://user-images.githubusercontent.com/118168094/217566367-56154409-7f44-441b-ab3c-239a83de065f.png">
</p>

À l'issu de la matrice ci-dessus, nous observons des corrélations toutes inférieures à 0,2 en valeur absolue. Nous pouvons donc garder les trois variables pour la suite de l'étude. En résumé, nous ne supprimons aucune variable pour la partie modélisation.

## *III.3. Standardisation*

Dans cette dernière partie de la préparation de nos données, nous séparons notre jeu de données en base d'entraînement et base de test. Ensuite nous standardisons nos variables explicatives quantitatives de notre jeu d'entrainement et de test. 

# **IV. Modélisation**

Après avoir analysé et nettoyé notre base de données. Nous passons à la modélisation. Nous allons effectuer 6 modèles qui sont des algorithmes de classification binaire. Nous déterminerons le/les meilleurs modèles et nous effectuerons un grid search sur ces derniers afin d'améliorer leurs performances. 

## *IV.1. Modèles utilisés*

Pour distinguer les cas d’AVC, de ceux qui ne le sont pas, nous avons utilisé plusieurs modèles.

Premièrement nous avons effectué une régression logistique.

Ensuite nous avons effectué plusieurs algorithmes (SVM) qui utilisent des vecteurs de supports pour séparer les données en 2 classes. Ces vecteurs sont utilisés pour construire une frontière de décision (hyperplans) qui séparent les classes avec les plus grandes marges possibles. 
Nous avons effectué 4 sortes de SVM différents :

-	Un SVM linéaire 
-	Un SVM à noyau linéaire 
-	Un SVM à noyau polynomial 
-	Un SVM à noyau RBF (radial basis function)

Un SVM linéaire ne transforme pas les données d’entrée et utilise une fonction linéaire pour construire la frontière de décision en utilisant les variables d ‘entrée telles qu’elles. Les SVM à noyau, utilisent un noyau pour transformer les données d’entrée dans un espace de caractéristiques plus élevées, ce qui peut faciliter la séparation des données pour la classification binaire. En effet nous ne sommes pas certaines que nos données soient linéairement séparables. 

De plus nous avons utilisé l’algorithme SGDClassifier, qui est basé sur la descente de gradient stochastique pour trouver les poids optimaux de chaque variables afin de minimiser l’erreur de classification. 

Enfin nous avons utilisé un modèle de réseau de neurones feedforward. 

## *IV.2. Comparaison des modèles* 

Nous avons effectué une première cross-validation avec 5 folds pour les 6 modèles suivants : SVM linéaire, les 3 SVM avec noyaux, ainsi que la regression logistique et le SGDClassifier. Le graphique ci-dessous représente le score de précision qui est le nombre de classifications correctes par rapport au nombre total de classifications, pour les 5 folds.

<p align="center">
<img width="583" alt="Capture d’écran 2023-02-07 à 23 46 23" src="https://user-images.githubusercontent.com/118168094/217384916-a746d20b-e7cd-496f-8fdd-c08f9a5056e7.png">
</p>

Les modèles SVM avec un noyau rbf et polynomial ont les meilleurs score de précision en moyenne sur les 5 folds, mais le modèle svc avec noyau rbf est tout de même le meilleur, avec 78%. Le score de précision n'est pas forcément l'indicateur le plus fiable pour comparer des modèles, ainsi nous avons comparé les modèles avec 3 indicateurs afin de déterminer ceux qui ont les meilleurs performances. Ces indicateurs sont le Recall (qui identifie la proportion de résultats positifs bien identifiés), l’AUC (qui mesure la capacité des modèles à distinguer les prédictions positives et négatives) et le F1-score (qui permet de combiner le recall et la précision).

<p align="center">
<img width="886" alt="Capture d’écran 2023-02-08 à 15 43 25" src="https://user-images.githubusercontent.com/118168094/217562466-49f706da-7e19-4377-a693-1260878ffc1a.png">
</p>

D'après les scores dans le tableau, nous avons deux modèles qui ressortent ex aequo avec 78% pour les 3 indicateurs. Premièrement, nous retrouvons le SVM avec noyau rbf, qui était le plus performant en terme de précision précédemment. Puis nous retrouvons le réseau de neuronne.

Ces modèles ont été entainés avec des valeurs d'hyper-paramètres par défauts. Nous allons donc tuner nos 2 meilleurs modèles afin d'améliorer leur performances et de les départager avec des hyper-paramètres optimaux.


## *IV.3. Grid Search sur meilleurs modèles* 

Le grid search permet de trouver les valeurs optimales des hyper-paramètres en testant différentes combinaisons d’hyperparamètres et en comparant les performances.  Nous avons cherché à optimiser à la fois le nombre de couches cachées et le nombre de neurones présents dans les couches. 

Pour le réseau de neuronnes nous avons cherché à optimiser à la fois le nombre de couches cachées et le nombre de neurones présents dans les couches. Ainsi nous avons testé une plage de 1 à 3 couches de neurones et une plage de 5 valeurs concernant le nombre de neurones par couche (nous avons testé le nombre de neurones suivants : 10, 25 ,50, 75 et 100).

<p align="center">
<img width="420" alt="Capture d’écran 2023-02-08 à 00 44 43" src="https://user-images.githubusercontent.com/118168094/217392757-d7f4599e-766d-4e5c-b025-820f4ae44b40.png">
</p>

Le tableau ci-dessus, nous indique les résultats obtenus par le grid search concernant le nombre d’hyper-paramètres à prendre en compte. Pour réaliser un modèle optimal nous devons prendre en compte 3 couches cachées ainsi que 100 neurones par couche.

Ensuite, nous avons effectué le grid search pour le modèle SVM avec noyau rbf. Nous avons cherché à optimiser le paramètre C qui est un paramètre de régularisation permettant de contrôler la balance entre la maximisation de la marge et la minimisation de l’erreur de classification. Nous avons également cherché à optimiser gamma qui détermine l’influence de l’échantillon d’entrainement sur la classification. Les valeurs testées pour gamma sont : 0,01, 0,1, 0,5, 1, 2. Celles pour C sont : 1, 10 et 100. 

<p align="center">
<img width="491" alt="Capture d’écran 2023-02-08 à 00 45 14" src="https://user-images.githubusercontent.com/118168094/217392789-e1b4c27a-6212-44f8-b6a2-fbedcb66f554.png">
</p>

Les résultats obtenus par le gridsearch concernant le SVM à noyau rbf se trouvent dans le tableau ci-dessus. Pour réaliser un modèle optimal nous devons prendre une valeur de C de 100 ainsi qu’une valeur pour gamma de 2. 

Pour terminer notre analyse, nous avons entrainé nos 2 modèles avec les hyper-paramètres optimaux. 

<p align="center">
<img width="679" alt="Capture d’écran 2023-02-08 à 00 45 45" src="https://user-images.githubusercontent.com/118168094/217392805-b0a262cd-322e-4358-8ef0-dff7336bdb8e.png">
</p>

Le tableau ci-dessus, répertorie les valeurs des 3 indicateurs pour le réseau de neurone et le SVM avec noyau rbf,  effectués avec les hyper-paramètres des grid-search. Nous observons que le SVM avec kernel rbf a un score légèrement plus élevé avec le recall (0,98 vs 0,96 pour le réseau de neurones). Cependant, sur le F1 score et l'AUC, le réseau de neuronnes obtient des valeurs plus élevées de 0,96% (vs 0,94 pour le SVM). Pour vérifier que nos modèles n'aient pas de sur-ajustement, nous avons également regardé ces 3 indicateurs sur le jeu train. 

Nous obtenons les valeurs suivantes pour le SVM avec noyau rbf sur le jeu train :

- recall_svc_rbf : 0.99
- f1 svc rbf : 0.97
- auc svc rbf : 0.97

Ainsi que ces valeurs pour le réseau de neuronne avec le jeu train :

- Recall : 0.97
- F1 score : 0.97
- auc : 0.97

Que ce soit pour le modèle SVM rbf et le réseau de neuronne, les valeurs obtenues avec le jeu d'entrainement sont légérement plus élevées mais restent très proches de celles obtenues avec le jeu test. Le risque de sur ou sous ajustement est éloigné. 

Notre meilleur modèle est donc le réseau de neuronne qui obtient des valeurs plus élevées pour 2 indicateurs sur 3, et qui a des valeurs plus proche entre celles obtenues par le jeu d'entrainement et le jeu test. Un F1 score de 96% signifie que notre réseau de neuronne a bien classé avec une précision de 96% les individus qui ont vraiment eu un AVC. De plus, avec un score de 96% pour le recall, cela signifie que le modèle a correctement classé 96% des individus qui ont vraiment eu un AVC. Enfin l'AUC de 96%, signifie que le modèle a une capacité de 96% a bien discriminer le groupe de personnes aillant eu un AVC, de celui qui n'en a pas eu. 

# **V. Conclusion**

Dans ce projet nous avons appliqué différents modèles dans le but de prédire les cas d'AVC. Notre jeu de données, contenant des données équilibrées entre les cas d'AVC et ceux qui n'en sont pas, nous n'avons pas eu besoin d'appliquer des méthodes de rééchantillonnage. Cependant, avant de commencer nous avons nettoyé la base, ainsi qu'effectué une sélection de variables. Nous avons décidé de conserver l'intégralité de nos variables explicatives malgré des variables qualitatives explicatives dépendantes entre-elles, pour ne pas perdre trop d'information en les supprimant. Après avoir dichotomisé une variables qualitative à plus de 2 modalitées ainsi que standardisé nos variables quantitatives dans notre jeu train et test, nous sommes passées à la  modélisation. 
Nous avons effectué 7 modèles, qui sont des algorithmes de classification binaire. Nous retrouvons donc la régression logistique, des svm avec des noyaux différents (linéaire, polynomial, rbf) ainsi qu'un svm linéaire, un sgdClassifier et un réseau de neuronnes. Pour comparer ces modèles en terme de performances nous décidons d'effectuer une cross-validation de 5 folds sur tous les modèles (à part le réseau de neuronnes) et de comparer la moyenne de l'accuracy sur les folds. En repérant que le svm à kernel rbf obtient le meilleur score, nous décidons d'utiliser 3 indicateurs (recall, f1-score, auc) pour comparer cette fois nos 7 modèles. Sans surprise, SVM avec kernel rbf est en tête mais se retrouve ex-aequo avec le réseau de neuronnes. Pour départager nos deux modèles, nous effectuons un grid-search sur chacun afin d'optimiser leurs hyper-paramètres et d'améliorer leurs performances. Le réseau de neuronnes obtient de meilleurs résultats sur 2 indicateurs sur 3. Ainsi, le réseau de neuronnes est notre modèle le plus performant pour prédire les cas d'AVC, selon notre analyse. 
