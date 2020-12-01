Task Description {#sec:task}
================

Annotate instances of the UCI ML Drug Review dataset with Eckman’s 6
fundamental emotions.\
The dataset contains around 280 000 reviews of different drugs. Table
[tab:example] below shows an example of an instance int the dataset:

[ht]

<span> |c|c|c|c|c|c|c|</span> uniqueID & drugName & condition & review &
rating & date & usefulCount\
46775 & Sulindac & Pain &

[x]<span>@c@c@</span>“I have taken this medication for 3 months,\
and it is the first time in 5 years I have\
been practicaly pain free!”

& 9 & 13-Nov-08 & 23\

[tab:example]

Setup {#sec:setup}
=====

Initial steps {#ssec:init}
-------------

We first drew up a list of annotation guidelines, which we formulated
having only read a few reviews and considering what the most interesting
information in these reviews was. Seeing as the reviews center around
some ailment that is treated by a drug, we thought it would be
interesting to consider the aspect of time in our annotation, by
dividing the event of taking the drug (the main point of all reviews)
into a before and after section. We also at this point decided on
Ekman’s 6 fundamental emotions as our model for annotation, and wanted
to try annotate intensity levels (3) as well.\

Trial Run {#sec:trial}
---------

Following this, we conducted a trial run of 15 annotations with our
guidelines thus far, to see whether they would need to be revised before
annotating a further 50 instances. We noticed that we mostly agreed on
the instances of emotion present in the reviews, but agreed to a lesser
extent on the degrees of intensity each emotion should be assigned. We
revised this in our annotation guidelines to be more explicit. We also
decided to not assume emotional states from bodily/physical conditions
unless these were explicitly mentioned. Agreement results ($\kappa$) are
mentioned in Section [sec:results].

Final Annotation Guidelines {#ssec:guide}
---------------------------

The following are the guidelines we used to annotate the 50 instances
from our dataset. Items in blue were added after the trial run, upon
revision of the guidelines.

1.  Annotate emotions of the **reviewer**

    -   Do not assume emotional states from bodily afflictions without
        reviewer’s mention: only annotate the emotional state as
        expressed linguistically

    -   Annotate emotions toward as well as resulting from drug

    -   Do not annotate your own emotional reactions to the review

2.  Use Ekman’s 6 fundamental emotions for annotation

    -   Anger, Fear, Joy, Sadness, Surprise, Disgust

3.  If an emotion occurs, identify its intensity (low, normal, high)

    -   If emotion implied (not explicitly): low intensity

    -   Expected emotion like ’Joy’ when drug works: normal intensity

    -   Intensifiers (e.g. “very” or “devastated”): high intensity

4.  Each instance (event of taking drug) has 2 parts: before and after
    the event

5.  Annotate a maximum of 2 emotions in both parts of an instance

    -   If 3 present, only annotate the 2 most prominent emotions

    -   If before/after event not mentioned, leave it blank

6.  Check yourself.

    -   Take a break if you feel fatigued

    -   If you are annotating patters (lots of sadness, lots of anger)
        take a step back and re-evaluate

Results {#sec:results}
=======

Table [tab:res] shows the agreement calculated between the two
annotators using Cohen’s kappa ($\kappa$).\
The agreement scores for the trial run of 15 items range between “fair”
and “moderate, while agreement on the main 50 items is slightly lower
(only ”fair“).\
Additionally, the $\kappa$ scores are generally lower when considering
the degrees of intensity annotated for each emotion. When degrees of
intensity are ignored and only occurrences of emotion annotated are
counted, the agreement score rises to ”moderate". In our annotations,
the degrees of intensity are clearly driving the agreement scores down
and are therefore not really reliable.\

[t!]

                      Agreement w. degrees ($\kappa$)   Agreement w/o degrees ($\kappa$)
  ------------------ --------------------------------- ----------------------------------
   Trial (15 items)                0.317                             0.484
   Main (50 items)                 0.288                             0.400
    All (65 items)                 0.294                             0.419

[tab:res]

[ ybar, enlargelimits=0.45, legend
style=<span>at=<span>(0.5,-0.15)</span>, anchor=north,legend
columns=-1</span>, ylabel=<span>frequency</span>, symbolic x
coords=<span>Annotator1,Annotator2</span>, xtick=data, nodes near
coords, nodes near coords align=<span>vertical</span>, ] coordinates
<span>(Annotator1,12) (Annotator2,13)</span>; coordinates
<span>(Annotator1,18) (Annotator2,9)</span>; coordinates
<span>(Annotator1,44) (Annotator2,30)</span>; coordinates
<span>(Annotator1,9) (Annotator2,12)</span>; coordinates
<span>(Annotator1,26) (Annotator2,7)</span>; coordinates
<span>(Annotator1,12) (Annotator2,5)</span>;

[fig:barplot]

Figure [fig:barplot] shows the overall emotions annotated by each
annotator. This plot does not consider degrees of intensity annotated,
only the frequency counts of emotions annotated in the reviews.\
Annotator1 annotated emotions more frequently than Annotator2, as can be
clearly seen for *Fear, Joy, Disgust* and *Surprise*. The discussion in
Section [sec:disc] will look at reasons that may have brought this
about.

Discussion {#sec:disc}
==========
