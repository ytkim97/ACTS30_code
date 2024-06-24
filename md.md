```{r, fig.width=10, fig.height=9}
library(NMF)
nmfta <- table(Tumor@meta.data$RNA_snn_res.0.9, Tumor@meta.data$pcR)
similarity_matrix <-as.matrix(dist(nmfta))
nmf <- nmf(similarity_matrix, rank = 2:5) # 오래걸린다


nmf$fit # 결과
consensusmap(nmf$fit) # consensus matrix

a = if(requireNamespace("Biobase", quietly=TRUE)){
plot(nmf)
}

a
```

![image](https://github.com/ytkim97/ACTS30_code/assets/173645918/9a284151-61cc-4bf7-a01d-dd2a5a9b3d21)
