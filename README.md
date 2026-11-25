# eks-demo-app

Demo nginx app. This repo owns **how the app is built and packaged**:

- `app/`: Dockerfile and page.
- `chart/`: Helm chart describing how to deploy it.
- `.github/workflows/build-push.yml`: builds and tests the image, pushes it to ECR, then packages
  the chart (version `1.0.<run>`, appVersion = image tag) and pushes it to ECR as an OCI artifact.

It does **not** deploy anything. Argo CD deploys the chart version pinned in the `eks-gitops` repo.
