# OCI CIS Cloud Shell

This guide explains how to execute Oracle's [CIS Compliance Script](https://github.com/oci-landing-zones/oci-cis-landingzone-quickstart) inside [Cloud Shell](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/cloudshellintro.htm). The [OCI CIS Benchmark](https://www.cisecurity.org/benchmark/oracle_cloud) is the product of a community consensus process and consists of secure configuration guidelines developed for [Oracle Cloud Infrastructure](https://www.oracle.com/cloud/).

The goal is to quickly download a list of security recommendations for your OCI tenancy and bill of materials (BOMs) exported as CSV. Here's a sample video how this process looks like ([fallback video link](https://objectstorage.eu-frankfurt-1.oraclecloud.com/p/Bd1riNLs1XEmsCF_1YMbeDtSpGA4PLj5IvjGvHmLAx5PsuzMd64FydyF8UCcSA_O/n/frnhkcj2u67r/b/mranftl_shared/o/oci-tenancy-review/cis-report-intro-1080p-social.mp4)): 

<p align="center" width="100%">
<video src="https://github.com/user-attachments/assets/eb954ca5-7ae1-4b30-bf82-f1be7b795a30" width="80%" controls></video>
</p>

## Quickstart

This script has no prerequisites. Simply copy/paste the following commands into your [Cloud Shell](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/cloudshellintro.htm) to build a CIS report of your tenancy:   

```bash
# All files live in the cis directory in your home dir
mkdir -p ~/cis
cd ~/cis

# Remove previous report files within our current dir
rm -rf report report.zip > /dev/null

# Get the latest official CIS Compliance Script
wget https://raw.githubusercontent.com/oci-landing-zones/oci-cis-landingzone-quickstart/main/scripts/cis_reports.py

# Build the full CIS report
python3 cis_reports.py -dt --all-resources --report-directory report

# Archive all CIS report files for downloading
zip -r report.zip report

```

Inside [Cloud Shell](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/cloudshellintro.htm) you should now be able to download the archived report by navigating to "Cog -> Download" (top right) and targeting this file:
```
cis/report.zip
```

Now extract that downloaded `report.zip` and inspect the `cis_summary_report.html` and for a BOM all `raw_data_*.csv` files in that archive.

## Further information

For further information refer to the [official CIS Compliance Script repository](https://github.com/oci-landing-zones/oci-cis-landingzone-quickstart).