# OCI CIS Cloud Shell

This guide explains how to execute Oracle's [CIS Compliance Script](https://github.com/oci-landing-zones/oci-cis-landingzone-quickstart) inside [Cloud Shell](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/cloudshellintro.htm). The [OCI CIS Benchmark](https://www.cisecurity.org/benchmark/oracle_cloud) is the product of a community consensus process and consists of secure configuration guidelines developed for [Oracle Cloud Infrastructure](https://www.oracle.com/cloud/).

The goal is to quickly download a list of security recommendations for your OCI tenancy and bill of materials (BOMs) exported as CSV.

## Quickstart

This script has no prerequisites. Simply copy/paste the following commands into your [Cloud Shell](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/cloudshellintro.htm) to build a CIS report of your tenancy:   

```bash
# Get the latest official CIS Compliance Script
wget https://raw.githubusercontent.com/oci-landing-zones/oci-cis-landingzone-quickstart/main/scripts/cis_reports.py

# Build the full CIS report
python3 cis_reports.py -dt --all-resources --report-directory cis-report

# Archive the CIS report for downloading
zip -r cis-report.zip cis-report
```

Inside [Cloud Shell](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/cloudshellintro.htm) you should now be able to download the archived report by navigating to "Cog -> Download" (top right) and targeting this file:
```
cis-report.zip
```

Now inspect the `cis_summary_report.html` and all related `raw_data_*.csv` files in that archive.

## Further information

For a list of all available args see [cis_reports.py args](https://github.com/oci-landing-zones/oci-cis-landingzone-quickstart?tab=readme-ov-file#arguments).