## GCP Label Pivoting – How It Works

In GCP billing exports, labels are typically ingested as an array of key-value pairs per resource (often as a JSON object). Each group of labels is assigned a unique `idd_gcp_label`, which is referenced from the `F_GCP_COST` fact table.

To make these labels usable in structured analysis:
1. The array is first exploded (unnested) so that each label becomes a separate row containing `labels_key` and `labels_value`.
2. This long-format table is then pivoted into a wide-format view with one row per `idd_gcp_label`, and separate columns for each relevant label key such as `environment`, `owner`, and `dm-service`.
3. The resulting pivoted table is joined back to the cost fact table using `idd_gcp_label`, allowing each cost row to be enriched with standardized, easily filterable label dimensions.

Because each `labels_key` is expected to occur only once per label group, the pivot operation is valid and results in a clean dimensional representation.

### Diagram: From Label Array to Structured Columns

![Label Creation and Pivot Logic](https://github.com/bredeespelid/TGS_BI/blob/main/idd_label_creation/label_creation.png?raw=true)
