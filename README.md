# Python-Class-122
digit Recognition

 #p = sns.heatmap(np.reshape(X[idx], (28,28)), cmap=plt.cm.gray, 
 p = sns.heatmap(np.array(X.loc[idx]).reshape(28,28), cmap=plt.cm.gray,
           
-------------------


samples_per_class = 5
#figure = plt.figure(figsize=(nclasses*2,(1+samples_per_class*2)))
figure = plt.figure(figsize=(25,(11)))
idx_cls = 0
for cls in classes:
  idxs = np.flatnonzero(y == cls)
  idxs = np.random.choice(idxs, samples_per_class, replace=False)
  i = 0
  for idx in idxs:
    plt_idx = i * nclasses + idx_cls + 1
    p = plt.subplot(samples_per_class, nclasses, plt_idx);
    #p = sns.heatmap(np.reshape(X[idx], (28,28)), cmap=plt.cm.gray, 
    p = sns.heatmap(np.array(X.loc[idx]).reshape(28,28), cmap=plt.cm.gray,
             xticklabels=False, yticklabels=False, cbar=False);
    p = plt.axis('off');
    i += 1
  idx_cls += 1
