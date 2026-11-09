# Blodprøve - Lab Implementation Guide v0.1.0

* [**Table of Contents**](toc.md)
* [**Artifacts Summary**](artifacts.md)
* **Blodprøve**

## Resource Profile: Blodprøve 

| | |
| :--- | :--- |
| *Official URL*:https://moekaroline.github.io/FHIR-IG/StructureDefinition/lab-observation-blodprove | *Version*:0.1.0 |
| Draft as of 2025-01-31 | *Computable Name*:LabObservationBlood |

 
Profil for vanlige blodprøver 

**Usages:**

* This Profile is not used by any profiles in this Specification

You can also check for [usages in the FHIR IG Statistics](https://packages2.fhir.org/xig/resource/lab-ig|current/StructureDefinition/StructureDefinition-lab-observation-blodprove.json)

### Formal Views of Profile Content

 [Description of Profiles, Differentials, Snapshots and how the different presentations work](http://build.fhir.org/ig/FHIR/ig-guidance/readingIgs.html#structure-definitions). 

 

Other representations of profile: [CSV](StructureDefinition-lab-observation-blodprove.csv), [Excel](StructureDefinition-lab-observation-blodprove.xlsx), [Schematron](StructureDefinition-lab-observation-blodprove.sch) 



## Resource Content

```json
{
  "resourceType" : "StructureDefinition",
  "id" : "lab-observation-blodprove",
  "url" : "https://moekaroline.github.io/FHIR-IG/StructureDefinition/lab-observation-blodprove",
  "version" : "0.1.0",
  "name" : "LabObservationBlood",
  "title" : "Blodprøve",
  "status" : "draft",
  "date" : "2025-01-31",
  "publisher" : "Karoline Moe",
  "contact" : [{
    "name" : "Karoline Moe",
    "telecom" : [{
      "system" : "url",
      "value" : "https://github.com/MoeKaroline"
    }]
  }],
  "description" : "Profil for vanlige blodprøver",
  "jurisdiction" : [{
    "coding" : [{
      "system" : "urn:iso:std:iso:3166",
      "code" : "NO",
      "display" : "Norway"
    }]
  }],
  "fhirVersion" : "4.0.1",
  "mapping" : [{
    "identity" : "workflow",
    "uri" : "http://hl7.org/fhir/workflow",
    "name" : "Workflow Pattern"
  },
  {
    "identity" : "sct-concept",
    "uri" : "http://snomed.info/conceptdomain",
    "name" : "SNOMED CT Concept Domain Binding"
  },
  {
    "identity" : "v2",
    "uri" : "http://hl7.org/v2",
    "name" : "HL7 v2 Mapping"
  },
  {
    "identity" : "rim",
    "uri" : "http://hl7.org/v3",
    "name" : "RIM Mapping"
  },
  {
    "identity" : "w5",
    "uri" : "http://hl7.org/fhir/fivews",
    "name" : "FiveWs Pattern Mapping"
  },
  {
    "identity" : "sct-attr",
    "uri" : "http://snomed.org/attributebinding",
    "name" : "SNOMED CT Attribute Binding"
  }],
  "kind" : "resource",
  "abstract" : false,
  "type" : "Observation",
  "baseDefinition" : "http://hl7.org/fhir/StructureDefinition/Observation",
  "derivation" : "constraint",
  "differential" : {
    "element" : [{
      "id" : "Observation",
      "path" : "Observation"
    },
    {
      "id" : "Observation.code",
      "path" : "Observation.code",
      "mustSupport" : true
    },
    {
      "id" : "Observation.subject",
      "path" : "Observation.subject",
      "type" : [{
        "code" : "Reference",
        "targetProfile" : ["https://moekaroline.github.io/FHIR-IG/StructureDefinition/lab-patient"]
      }]
    },
    {
      "id" : "Observation.effective[x]",
      "path" : "Observation.effective[x]",
      "slicing" : {
        "discriminator" : [{
          "type" : "type",
          "path" : "$this"
        }],
        "ordered" : false,
        "rules" : "open"
      }
    },
    {
      "id" : "Observation.effective[x]:effectiveDateTime",
      "path" : "Observation.effective[x]",
      "sliceName" : "effectiveDateTime",
      "min" : 0,
      "max" : "1",
      "type" : [{
        "code" : "dateTime"
      }],
      "mustSupport" : true
    },
    {
      "id" : "Observation.value[x]",
      "path" : "Observation.value[x]",
      "slicing" : {
        "discriminator" : [{
          "type" : "type",
          "path" : "$this"
        }],
        "ordered" : false,
        "rules" : "open"
      }
    },
    {
      "id" : "Observation.value[x]:valueQuantity",
      "path" : "Observation.value[x]",
      "sliceName" : "valueQuantity",
      "min" : 0,
      "max" : "1",
      "type" : [{
        "code" : "Quantity"
      }],
      "mustSupport" : true
    }]
  }
}

```
