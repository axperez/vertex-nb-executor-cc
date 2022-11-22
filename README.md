# vertex-nb-executor-cc
Example repo for running a Jupyter notebook on Vertex AI Training with a custom container.


## Docker Build and Push Commands

Run the following steps in a terminal either on a Vertex AI Workbench Managed Notebook, Vertex AI Workbench User-Managed Notebook, or your local terminal where you have installed the gcloud command line sdk and have authenticated a service or user account.

Add your project id, desired image name and tag as inputs:

```bash
PROJECT_ID=
IMAGE_NAME=
TAG=
IMAGE_URI=gcr.io/$PROJECT_ID/$IMAGE_NAME:$TAG
```
Then, run the following commands to build and push the custom container image to Google Container Registry (GCR):
```bash
docker build -t $IMAGE_URI vertex-nb-executor-cc/build/
docker push $IMAGE_URI
```
Note: Make sure your service or user account has the permission to push to your project's GCR (storage.admin role will give you the necessary permissions to push to GCR).
## Vertex AI Workbench Notebook Executor

Run Vertex AI Workbench Notebook Executor from a Vertex AI Workbench Managed Notebook instance as seen in the following screenshots:

<img width="1631" alt="Screen Shot 2022-11-21 at 6 30 10 PM" src="https://user-images.githubusercontent.com/31319618/203205477-5905fa24-e32c-478a-ae40-0b62bd0ee838.png">

Add the custom container uri (IMAGE_URI) in the notebook executor submission form:

<img width="503" alt="image" src="https://user-images.githubusercontent.com/31319618/203202895-e62958a9-dbf6-4e6c-b3e0-c3968bd783df.png">
