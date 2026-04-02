# OCI CIS Cloud Shell

This guide explains how to execute Oracle's [CIS Compliance Script](https://github.com/oci-landing-zones/oci-cis-landingzone-quickstart) inside [Cloud Shell](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/cloudshellintro.htm). The goal is to quickly download a list of security recommendations and bill of materials (BOMs) exported as CSV without any local prerequisites. 

## Quickstart

Copy/paste the following commands inside your [Cloud Shell](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/cloudshellintro.htm) to get a full CIS report of your tenancy:   

```bash
wget https://raw.githubusercontent.com/oci-landing-zones/oci-cis-landingzone-quickstart/main/scripts/cis_reports.py
python3 cis_reports.py -dt --all-resources --report-directory report
tar -czvf report.tar.gz report
```

Inside [Cloud Shell](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/cloudshellintro.htm) you should now be able to download the archived report by navigating to "Cog -> Download" (top right) and targeting this file:
```
report.tar.gz
```

Now inspect the `cis_summary_report.html` and all related `raw_data_*.csv` files in that archive.

## Further information

For a list of all available args see [cis_reports.py args](https://github.com/oci-landing-zones/oci-cis-landingzone-quickstart?tab=readme-ov-file#arguments).