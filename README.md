## To run GPU-accelerated pyspark PCA (multi-node multi-gpu)
```bash
SPARK_MASTER=spark://hostname:port
PYTHON_ENV_PATH=~/miniconda3/envs/cuspark/bin/python

${SPARK_HOME}/bin/spark-submit --master ${SPARK_MASTER} \
  --conf spark.task.resource.gpu.amount=1 \
  --conf spark.executor.resource.gpu.amount=2 \
  --conf spark.executor.resource.gpu.discoveryScript=./getGpusResources.sh \
  --conf spark.files=${SPARK_HOME}/examples/src/main/scripts/getGpusResources.sh \
  --conf spark.pyspark.python=${PYTHON_ENV_PATH} \
  cuspark_pca.py
```

## To run GPU-accelerated pyspark Kmeans (single-gpu) 
```bash
    python cuspark_kmeans.py
```

## To reproduce a bug 
```bash
    python bug.py
```

## Contact
- [Jinfeng Li](jinfengl@nvidia.com) 
- [Bobby Wang](bobwang@nvidia.com)
- [Erik Ordentlich](eordentlich@nvidia.com) 
