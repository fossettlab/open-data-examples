# open-data-examples

Example notebooks and tutorials for the **NASA Planetary Data System (PDS) Geosciences Node** planetary science archive on [AWS Open Data](https://opendata.aws/).

The Geosciences Node at Washington University in St. Louis archives data on the surfaces and interiors of terrestrial planetary bodies (Mars, the Moon, Venus, Mercury, and related missions). When onboarding completes, the public S3 bucket will be:

| Field | Value |
|-------|--------|
| Bucket | `pds-geosciences` |
| Region | `us-west-2` |
| ARN | `arn:aws:s3:::pds-geosciences` |
| Access | Anonymous (unsigned) read |

Official documentation: [https://pds-geosciences.wustl.edu/](https://pds-geosciences.wustl.edu/)

## Get to know the dataset

The introductory tutorial lives at [`pds-geosciences/get-to-know-a-dataset.ipynb`](pds-geosciences/get-to-know-a-dataset.ipynb). It follows the [AWS Open Data “Get to know a dataset” template](https://github.com/awslabs/open-data-docs/tree/main/get-to-know-a-dataset) and covers:

- Listing and browsing `s3://pds-geosciences/` with **boto3** and **s3fs** (no AWS credentials)
- Opening representative Mars or Moon products when present, with a simple plot
- Graceful behavior when the bucket is not yet published or is empty

### Run locally

```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r pds-geosciences/requirements.txt
jupyter notebook pds-geosciences/get-to-know-a-dataset.ipynb
```

Alternatives: [JupyterLab](https://jupyter.org/), [VS Code](https://code.visualstudio.com/) with the Jupyter extension, [Amazon SageMaker Studio Lab](https://studiolab.sagemaker.aws/), or SageMaker Studio. No AWS account is required for read access once the bucket is public.

### Run in the cloud (optional)

From an EC2 instance or SageMaker notebook in **us-west-2**, the same unsigned boto3/s3fs code applies. Staying in-region avoids cross-region data transfer charges when the archive is large.

## Community challenge

**How does surface texture at 10–100 m scales differ between ancient Noachian highlands and younger Amazonian volcanic plains on Mars**, using orbital products streamed from S3 without downloading the full archive?

See the [Community challenge](pds-geosciences/get-to-know-a-dataset.ipynb) section in the notebook for a suggested workflow (AOI selection, texture metrics, PDS citation). Share results via a GitHub issue or pull request in this repository.

## Repository status

This repo is a **draft** for AWS Open Data onboarding (registry YAML, documentation, and tutorial). The `pds-geosciences` bucket may not exist on S3 until later onboarding steps complete; the notebook detects that case and prints guidance instead of failing with an opaque error.

## License

See [LICENSE](LICENSE). PDS data are public domain; cite datasets per [Geosciences Node guidance](https://pds-geosciences.wustl.edu/faq.html).
