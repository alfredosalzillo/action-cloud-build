# Github Action for Google Cloud Build

An GitHub Action for building using Google Cloud Build.

## Usage

In your actions workflow insert this:

```bash
- name: Build on Cloud Build
  uses: alfredosalzillo/action-cloud-build@master
  with:
    image: gcr.io/[your-project]/[image]
    service key: ${{ secrets.GCLOUD_AUTH }}
```

Your `GCLOUD_AUTH` secret (or whatever you name it) must be a base64 encoded
gcloud service key with the following permissions:
- Service Account User
- Cloud Run Admin
- Storage Admin

The image must be "pushable" to one of Google's container registries, i.e. it
should be in the `gcr.io/[project]/[image]` or `eu.gcr.io/[project]/[image]`
format.
