 ## GCP Label Pivoting – How It Works

In GCP, each resource can have multiple labels stored as key-value pairs. These are grouped by a unique `idd_gcp_label`. This ID is referenced in the `F_GCP_COST` fact table, enabling a direct link between cost data and associated labels.

To simplify analysis, the label pairs (`labels_key`, `labels_value`) are **pivoted** into a single row per `idd_gcp_label`, with each label key as a separate column. This is possible because each label key is expected to occur only once per label group.

The result: you can enrich each cost row with descriptive attributes such as `environment`, `dm-service`, or `owner`—without complex joins or filtering logic.

### Diagram of the Label Pivoting Logic

![Label Creation and Pivot Logic](https://github.com/bredeespelid/TGS_BI/blob/main/idd_label_creation/label_creation.png?raw=true)

