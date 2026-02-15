helm template immich immich/immich --version 0.10.3 -f argoapps/immich-values.yaml --namespace immich --include-crds --skip-tests --output-dir ./immich-hydrated

cp ./immich-hydrated/immich/templates/*.yaml ./applications/immich-hydrated/