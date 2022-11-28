---
title: sample-block
schema_name: sample-block
category: Other TSVs
all_versions_deprecated: False
exclude_from_index: False
layout: default
---

Related files:

- [📝 Excel template](https://raw.githubusercontent.com/hubmapconsortium/ingest-validation-tools/main/docs/sample-block/sample-block.xlsx): For metadata entry.
- [📝 TSV template](https://raw.githubusercontent.com/hubmapconsortium/ingest-validation-tools/main/docs/sample-block/sample-block.tsv): Alternative for metadata entry.







## Metadata schema

### Field types
- *Boolean* fields can be given as `TRUE`/`FALSE`, `True`/`False`, `true`/`false`, or `1`/`0`.  


<details markdown="1" open="true"><summary><b>Version 1 (current)</b></summary>

<blockquote markdown="1">

[`version`](#version)<br>
[`sample_id`](#sample_id)<br>
[`type`](#type)<br>
[`source_storage_time_value`](#source_storage_time_value)<br>
[`source_storage_time_unit`](#source_storage_time_unit)<br>
[`weight_value`](#weight_value)<br>
[`weight_unit`](#weight_unit)<br>
[`volume_value`](#volume_value)<br>
[`volume_unit`](#volume_unit)<br>
[`pathology_distance_value`](#pathology_distance_value)<br>
[`pathology_distance_unit`](#pathology_distance_unit)<br>
[`preparation_media`](#preparation_media)<br>
[`preparation_temperature`](#preparation_temperature)<br>
[`processing_time_value`](#processing_time_value)<br>
[`processing_time_unit`](#processing_time_unit)<br>
[`storage_media`](#storage_media)<br>
[`storage_temperature`](#storage_temperature)<br>
[`quality_criteria`](#quality_criteria)<br>
[`histological_report`](#histological_report)<br>
[`notes`](#notes)<br>

</blockquote>

<a name="version"></a>
##### [`version`](#version)
The version of the sample metadata specification used in the submission.

| constraint | value |
| --- | --- |
| enum | `1` |
| required | `True` |

<a name="sample_id"></a>
##### [`sample_id`](#sample_id)
The unique Submission ID for the sample assigned by the ingest portal. An example value might be "VAN0010-LK-152-162".

| constraint | value |
| --- | --- |
| required | `True` |

<a name="type"></a>
##### [`type`](#type)
Denotes the type of sample, used to validate the field entries.

| constraint | value |
| --- | --- |
| enum | `block` |
| required | `True` |

<a name="source_storage_time_value"></a>
##### [`source_storage_time_value`](#source_storage_time_value)
The amount of time that elapsed between when the source was generated and this sample was derived from the source. This would, for example, include how long the source was stored in a freezer.

| constraint | value |
| --- | --- |
| type | `number` |
| required | `True` |

<a name="source_storage_time_unit"></a>
##### [`source_storage_time_unit`](#source_storage_time_unit)
Time unit. Leave blank if not applicable.

| constraint | value |
| --- | --- |
| enum | `min`, `hours`, `days`, or `years` |
| required | `False` |
| required if | `source_storage_time_value` present |

<a name="weight_value"></a>
##### [`weight_value`](#weight_value)
Weight of a tissue block. Leave blank if not applicable.

| constraint | value |
| --- | --- |
| type | `number` |
| required | `False` |

<a name="weight_unit"></a>
##### [`weight_unit`](#weight_unit)
Weight unit. Leave blank if not applicable.

| constraint | value |
| --- | --- |
| required | `False` |
| enum | `mg`, `g`, or `kg` |
| required if | `weight_value` present |

<a name="volume_value"></a>
##### [`volume_value`](#volume_value)
The volume of a tissue block. Leave blank if not applicable.

| constraint | value |
| --- | --- |
| type | `number` |
| required | `False` |

<a name="volume_unit"></a>
##### [`volume_unit`](#volume_unit)
Volume unit. Leave blank if not applicable.

| constraint | value |
| --- | --- |
| required | `False` |
| enum | `mm^3` or `um^3` |
| required if | `volume_value` present |

<a name="pathology_distance_value"></a>
##### [`pathology_distance_value`](#pathology_distance_value)
If surgical sample, how far from the pathology was the sample obtained. Typically a number of centimeters. Leave blank if not applicable or unknown. Leave blank if not applicable.

| constraint | value |
| --- | --- |
| type | `number` |
| required | `False` |

<a name="pathology_distance_unit"></a>
##### [`pathology_distance_unit`](#pathology_distance_unit)
Distance unit. Leave blank if not applicable.

| constraint | value |
| --- | --- |
| enum | `mm` or `cm` |
| required | `False` |
| required if | `pathology_distance_value` present |

<a name="preparation_media"></a>
##### [`preparation_media`](#preparation_media)
The media used during preparation of the sample.

| constraint | value |
| --- | --- |
| enum | `PFA (4%)`, `Buffered Formalin (10% NBF)`, `Non-Buffered Formalin (FOR)`, `1 x PBS`, `OCT`, `CMC`, `MACS Tissue Storage Solution`, `RNAlater`, `Methanol`, `Non-aldehyde based without acetic acid (NAA)`, `Non-aldehyde with acetic acid (ACA)`, `PAXgene tissue (PXT)`, `Allprotect tissue reagent (ALL)`, or `None` |
| required | `True` |

<a name="preparation_temperature"></a>
##### [`preparation_temperature`](#preparation_temperature)
The temperature for the preparation process.

| constraint | value |
| --- | --- |
| enum | `Liquid Nitrogen`, `Liquid Nitrogen Vapor`, `Dry Ice`, `-80 Celsius`, `-20 Celsius`, `4 Celsius`, `24 Celsius (Room Temperature)`, or `37 Celsius` |
| required | `True` |

<a name="processing_time_value"></a>
##### [`processing_time_value`](#processing_time_value)
The amount of time that elapsed from beginning of sampling to the first preservation (time from when received in lab to preservation). This would, for example, represent how long it took to cut the tissue and freeze it. Leave blank if not applicable.

| constraint | value |
| --- | --- |
| type | `number` |
| required | `False` |

<a name="processing_time_unit"></a>
##### [`processing_time_unit`](#processing_time_unit)
Time unit. Leave blank if not applicable.

| constraint | value |
| --- | --- |
| required | `False` |
| enum | `min`, `hours`, or `days` |
| required if | `processing_time_value` present |

<a name="storage_media"></a>
##### [`storage_media`](#storage_media)
What was the sample preserved in.

| constraint | value |
| --- | --- |
| enum | `PFA (4%)`, `Buffered Formalin (10% NBF)`, `Non-Buffered Formalin (FOR)`, `1 x PBS`, `OCT Embedded`, `CMC Embedded`, `OCT Embedded Cryoprotected (sucrose)`, `Paraffin Embedded`, `MACS Tissue Storage Solution`, `RNAlater`, `Methanol`, `Tris-EDTA`, `70% ethanol`, `Serum + DMSO`, `DMSO (no serum)`, `PAXgene Tissue Kit (PXT)`, `Allprotect Tissue Reagent (ALL)`, `Sucrose Cryoprotection Solution`, `Carboxymethylcellulose (CMC)`, or `None` |
| required | `True` |

<a name="storage_temperature"></a>
##### [`storage_temperature`](#storage_temperature)
The temperature during storage, after preparation and before the assay is performed.

| constraint | value |
| --- | --- |
| enum | `Liquid Nitrogen (Unspecified)`, `Liquid Nitrogen (Cryotube)`, `Liquid Nitrogen (Straw)`, `Liquid Nitrogen Vapor`, `Dry Ice`, `-80 Celsius (Unspecified)`, `-80 Celsius (Cryotube)`, `-80 Celsius (Straw)`, `-20 Celsius`, `4 Celsius`, `24 Celsius (Room Temperature)`, or `37 Celsius` |
| required | `True` |

<a name="quality_criteria"></a>
##### [`quality_criteria`](#quality_criteria)
For example, RIN: 8.7. For suspensions, measured by visual inspection prior to cell lysis or defined by known parameters such as wells with several cells or no cells. This can be captured at a high level. "OK" or "not OK", or with more specificity such as "debris", "clump", "low clump". Leave blank if not applicable.

| constraint | value |
| --- | --- |
| required | `False` |

<a name="histological_report"></a>
##### [`histological_report`](#histological_report)
histopathological reporting of key variables that are important for the tissue (absence of necrosis, comment on composition, significant pathology description, high level inflammation/fibrosis assessment etc. Leave blank if not applicable.

| constraint | value |
| --- | --- |
| required | `False` |

<a name="notes"></a>
##### [`notes`](#notes)
Notes. Leave blank if not applicable.

| constraint | value |
| --- | --- |
| required | `False` |

</details>
