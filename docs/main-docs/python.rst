========================================
Python
========================================
.. highlight:: python

Python開発メモ

標準ライブラリ
------------------------
os::

  import os
  for f in os.listdir('txt/'):
    # do something

  import os
  if not os.path.exists(FOLDER):
    os.makedirs(FOLDER)

pandas
-------------
thousands::

  df = pd.read_csv('txt/'+f, sep='\t',names=['delay','count'],
                 thousands=',',dtype={'delay':str, 'count':int})

save csv::

  df.to-csv("filename", index=False)

matplotlib, seaborn
----------------------
rc::

  matplotlib.rc('font', size=12)
  matplotlib.rc('axes', labelsize=16, titlesize=16)
  matplotlib.rc('xtick', labelsize=16)
  matplotlib.rc('ytick', labelsize=16)
  plt.rc('text', usetex=True)
  #sns.set(font_scale=1.4)

savefig::

  fig.savefig("hoge.png")
