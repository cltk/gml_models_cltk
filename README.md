# Middle Low German Models

Trained POS tagger for MLG.

Training Set and Citations
==========================
>ReN-Team. 2018. “Referenzkorpus Mittelniederdeutsch/Niederrheinisch (1200-1650).” Archived in Hamburger Zentrum für Sprachkorpora. Version 0.6. Publication date 2018-03-07. http://hdl.handle.net/11022/0000-0007-C64C-5.

>Ingrid Schröder. 2014. “Das Referenzkorpus: Neue Perspektiven für die mittelniederdeutsche Grammatikographie.” Jahrbuch für Germanistische Sprachgeschichte, 5(1), pp. 150-164. http://www.degruyter.com/view/j/jbgsg.2014.5.issue-1/jbgsg-2014-0011/jbgsg-2014-0011.xml .

>Robert Peters, Norbert Nagel. 2014. “Das digitale ‚Referenzkorpus Mittelniederdeutsch / Niederrheinisch (ReN)‘.” Jahrbuch für Germanistische Sprachgeschichte, 5(1), pp. 165-175. https://www.degruyter.com/view/j/jbgsg.2014.5.issue-1/jbgsg-2014-0012/jbgsg-2014-0012.xml .

Training the Tagger
===================


``` python
    >>> from nltk import DefaultTagger, UnigramTagger, BigramTagger
    >>> t0 = DefaultTagger('NA')
    >>> t1 = UnigramTagger([tags], backoff=t0)
    >>> t2 = BigramTagger([tags], backoff=t1)
```

Saving the Tagger
=================

``` python
    >>> ffile = open("backoff_tagger.pickle", 'wb')
    >>> pickle.dump(t2, ffile)
    >>> f.close()
```

Loading the Tagger
==================

``` python
  >>> ffile = open('bitagger_pos', 'rb')
  >>> tagger = pickle.load(ffile)
  >>> ffile.close()
```
