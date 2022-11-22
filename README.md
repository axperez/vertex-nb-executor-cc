# vertex-nb-executor-cc
Example repo for running a Jupyter notebook on Vertex AI Training with a custom container.


## Docker build and push commands

Add your project id, desired image name and tag as inputs:

```bash
PROJECT_ID=
IMAGE_NAME=
TAG=
```
Then, run the following commands to build and push the custom container image to Google Container Registry (GCR):
```bash
IMAGE_URI=gcr.io/$PROJECT_ID/$IMAGE_NAME:$TAG

docker build -t $IMAGE_URI vertex-nb-executor-cc/build/
docker push $IMAGE_URI
```