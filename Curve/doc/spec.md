Entity: Curve  
=============  
[Open License](https://github.com/smart-data-models//dataModel.WaterNetworkManagement/blob/master/Curve/LICENSE.md)  
Global description: **This entity contains a harmonised description of a generic curve made for the Water Network Management domain. This entity is primarily associated with the water management vertical and related IoT applications.**  

## List of properties  

- `curveType`: Entity's curve type.  - `description`: An optional text that describes other significant information about the junction  - `tag`: An optional text string used to assign the pipe to a category, perhaps one based on age or material  - `type`: NGSI-LD Entity Type. It must be equal to Curve.  - `xData`: X data points for the curve  - `yData`: Y data points for the curve    
Required properties  
- `curveType`  - `id`  - `type`  - `xData`  - `yData`    
Text to be included between overall title and description.  
## Data Model description of properties  
Sorted alphabetically (click for details)  
<details><summary><strong>full yaml details</strong></summary>    
```yaml  
Curve:    
  description: 'This entity contains a harmonised description of a generic curve made for the Water Network Management domain. This entity is primarily associated with the water management vertical and related IoT applications.'    
  properties:    
    curveType:    
      description: 'Entity''s curve type.'    
      enum:    
        - FLOW-HEAD    
        - FLOW-EFFICIENCY    
        - FLOW-HEADLOSS    
        - LEVEL-VOLUME    
      type: Property    
    description:    
      description: 'An optional text that describes other significant information about the junction'    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Text    
    tag:    
      description: 'An optional text string used to assign the pipe to a category, perhaps one based on age or material'    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Text    
    type:    
      description: 'NGSI-LD Entity Type. It must be equal to Curve.'    
      enum:    
        - Curve    
      type: Property    
    xData:    
      description: 'X data points for the curve'    
      items:    
        type: number    
      type: Property    
    yData:    
      description: 'Y data points for the curve'    
      items:    
        type: number    
      type: Property    
  required:    
    - id    
    - type    
    - curveType    
    - xData    
    - yData    
  type: object    
```  
</details>    
Text to be included after list of properties  
## Example payloads    
#### Curve NGSI V2 key-values Example    
Here is an example of a Curve in JSON format as key-values. This is compatible with NGSI V2 when  using `options=keyValues` and returns the context data of an individual entity.  
```json  
{  
  "id": "fAM-8ca3-4533-a2eb-12015",  
  "type": "Curve",  
  "curveType": {  
    "type": "Property",  
    "value": "FLOW-HEAD"  
  },  
  "xData": {  
    "type": "Property",  
    "value": [  
      0.5692,  
      0.4647  
    ]  
  },  
  "yData": {  
    "type": "Property",  
    "value": [  
      0.5692,  
      0.4647  
    ]  
  },  
  "description": {  
    "type": "Property",  
    "value": "Free Text"  
  },  
  "tag": {  
    "type": "Property",  
    "value": "DMA1"  
  }  
}  
```  
#### Curve NGSI V2 normalized Example    
Here is an example of a Curve in JSON format as normalized. This is compatible with NGSI V2 when not using options and returns the context data of an individual entity.  
```json  
{  
    "id": "fAM-8ca3-4533-a2eb-12015",  
    "type": "Curve",  
    "dateCreated": {  
        "type": "DateTime",  
        "value": "2020-02-16T17:43:00Z"  
    },  
    "dateModified": {  
        "type": "DateTime",  
        "value": "2020-02-16T17:43:00Z"  
    },  
    "curveType": {  
        "value": "FLOW-HEAD"  
    },  
    "xData": {  
        "value": [  
            0.5692,  
            0.4647  
        ]  
    },  
    "yData": {  
        "value": [  
            0.5692,  
            0.4647  
        ]  
    },  
    "description": {  
        "value": "Free Text"  
    },  
    "tag": {  
        "value": "DMA1"  
    }  
}  
```  
#### Curve NGSI-LD key-values Example    
Here is an example of a Curve in JSON-LD format as key-values. This is compatible with NGSI-LD when  using `options=keyValues` and returns the context data of an individual entity.  
```json  
{  
  "@context": [  
    "https://schema.lab.fiware.org/ld/context"  
  ],  
  "id": "fAM-8ca3-4533-a2eb-12015",  
  "type": "Curve",  
  "curveType": {  
    "type": "Property",  
    "value": "FLOW-HEAD"  
  },  
  "xData": {  
    "type": "Property",  
    "value": [  
      0.5692,  
      0.4647  
    ]  
  },  
  "yData": {  
    "type": "Property",  
    "value": [  
      0.5692,  
      0.4647  
    ]  
  },  
  "description": {  
    "type": "Property",  
    "value": "Free Text"  
  },  
  "tag": {  
    "type": "Property",  
    "value": "DMA1"  
  }  
}  
```  
#### Curve NGSI-LD normalized Example    
Here is an example of a Curve in JSON-LD format as normalized. This is compatible with NGSI-LD when not using options and returns the context data of an individual entity.  
```json  
{  
    "id": "urn:ngsi-ld:Curve:fAM-8ca3-4533-a2eb-12015",  
    "type": "Curve",  
    "createdAt": "2020-02-16T17:43:00Z",  
    "modifiedAt": "2020-02-16T17:43:00Z",  
    "curveType":{  
        "type": "Property",  
        "value": "FLOW-HEAD"  
    },  
    "xData": {  
        "type": "Property",  
        "value": [0.5692, 0.4647],  
        "unitCode":"C62"  
    },  
    "yData": {  
        "type": "Property",  
        "value": [0.5692, 0.4647],  
        "unitCode":"C62"  
    },  
    "description": {  
        "type": "Property",  
        "value": "Free Text"  
    },  
    "tag": {  
        "type": "Property",  
        "value": "DMA1"  
    },  
    "@context": [  
        "https://schema.lab.fiware.org/ld/context"  
    ]  
}  
```  
Text after  all  
