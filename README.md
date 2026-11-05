# open-data-examples

Example notebooks and tutorials for a **proposed independent copy of public data sourced from the NASA Planetary Data System (PDS) Geosciences Node**, proposed for [AWS Open Data](https://opendata.aws/). The copy\'s operator is **WashU EEPS (Washington University in St. Louis Department of Earth, Environmental, and Planetary Sciences)**. This independent copy is **not operated or endorsed by NASA or PDS**.

The source Geosciences Node at Washington University in St. Louis archives data on the surfaces and interiors of terrestrial planetary bodies (Mars, the Moon, Venus, Mercury, and related missions). The independent copy\'s content and coverage are not fixed; it is not a complete mirror. The bucket has not been provisioned, and these resource values are unverified placeholders:

| Field | Value |
|-------|--------|
| Bucket | `pds-geosciences` (unverified placeholder; unprovisioned) |
| Region | `us-west-2` (unverified placeholder) |
| ARN | `arn:aws:s3:::pds-geosciences` (unverified placeholder) |
| Access | Proposed anonymous (unsigned) read; not live |
| Update schedule | To be determined |

Source archive documentation: [https://pds-geosciences.wustl.edu/](https://pds-geosciences.wustl.edu/)

## Get to know the dataset

The introductory tutorial lives at [`pds-geosciences/get-to-know-a-dataset.ipynb`](pds-geosciences/get-to-know-a-dataset.ipynb). It follows the [AWS Open Data “Get to know a dataset” template](https://github.com/awslabs/open-data-docs/tree/main/get-to-know-a-dataset) and covers:

- Listing and browsing a verified public bucket with **boto3** and **s3fs** (no AWS credentials), using `s3://pds-geosciences/` only as a placeholder
- Opening representative Mars or Moon products when present, with a simple plot
- Graceful behavior when the bucket is not yet published or is empty

### Run locally

```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r pds-geosciences/requirements.txt
jupyter notebook pds-geosciences/get-to-know-a-dataset.ipynb
```

Alternatives: [JupyterLab](https://jupyter.org/), [VS Code](https://code.visualstudio.com/) with the Jupyter extension, [Amazon SageMaker Studio Lab](https://studiolab.sagemaker.aws/), or SageMaker Studio. No AWS account is required for anonymous read access if enabled. Confirm the operator-published bucket name, region, and available content before running S3 cells; a response from a placeholder bucket does not verify its ownership or provenance.

### Run in the cloud (optional)

Once verified resource details are published, the same unsigned boto3/s3fs code can be used from an EC2 instance or SageMaker notebook in the confirmed bucket region. Check applicable compute and data-transfer pricing before use; **us-west-2** is currently an unverified placeholder.

## Community challenge

**How does surface texture at 10–100 m scales differ between ancient Noachian highlands and younger Amazonian volcanic plains on Mars**, using orbital products streamed from S3 without downloading the full archive?

See the [Community challenge](pds-geosciences/get-to-know-a-dataset.ipynb) section in the notebook for a suggested workflow (AOI selection, texture metrics, PDS citation). Share results via a GitHub issue or pull request in this repository.

## Repository status

This repo is a **draft** for a proposed independent copy on AWS Open Data (registry YAML, documentation, and tutorial). The bucket is unprovisioned; publication, resource details, content, coverage, and update schedule are not yet confirmed. The notebook includes handling for missing or unavailable resources.

## License

See [LICENSE](LICENSE) for this repository. Attribute source data to NASA PDS and the relevant data producers; consult source product documentation for applicable usage terms and cite datasets per [Geosciences Node guidance](https://pds-geosciences.wustl.edu/faq.html).
