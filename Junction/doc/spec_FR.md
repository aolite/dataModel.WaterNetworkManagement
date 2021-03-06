Entité : Jonction  
=================  
[Licence ouverte](https://github.com/smart-data-models//dataModel.WaterNetworkManagement/blob/master/Junction/LICENSE.md)  
Description globale : **Cette entité contient une description harmonisée d'une jonction générique faite pour le domaine de la gestion des réseaux d'eau. Cette entité est principalement associée à la gestion verticale des réseaux d'eau et aux applications IdO connexes.**  

## Liste des biens  

- `address`: L'adresse postale.  - `areaServed`: La zone géographique où un service ou un article offert est fourni  - `demandCategory`: Permet d'attribuer les demandes de base et les modèles de temps à d'autres catégories d'utilisateurs.  - `description`: Un texte optionnel qui décrit d'autres informations importantes sur la jonction  - `elevation`: L'élévation au-dessus d'une référence commune de la jonction. Toutes les unités sont acceptées en code [CEFACT](https://www.unece.org/cefact.html)  - `emitterCoefficient`: Coefficient de décharge pour l'émetteur (sprinkler ou buse) placé à la jonction. Toutes les unités sont acceptées en code [CEFACT](https://www.unece.org/cefact.html)  - `initialQuality`: Niveau de qualité de l'eau à la jonction au début de la simulation. Toutes les unités sont acceptées en code [CEFACT](https://www.unece.org/cefact.html)  - `location`:   - `sourceCategory`: Description de la qualité du flux de sources entrant dans le réseau à un nœud spécifique.  - `tag`: Une chaîne de texte facultative utilisée pour classer la pipe dans une catégorie, peut-être en fonction de l'âge ou du matériau  - `type`: Type d'entité NGSI-LD. Il doit s'agir de Junction    
Propriétés requises  
- `elevation`  - `id`  - `location`  - `type`  ## Modèle de données description des biens  
Classement par ordre alphabétique (cliquez pour plus de détails)  
<details><summary><strong>full yaml details</strong></summary>    
```yaml  
Junction:    
  description: 'This entity contains a harmonised description of a generic junction made for the Water Network Management domain. This entity is primarily associated with the water network management vertical and related IoT applications.'    
  properties:    
    address:    
      description: 'The mailing address.'    
      properties:    
        addressCountry:    
          description: 'Property. The country. For example, Spain. Model:''https://schema.org/Text'''    
          type: string    
        addressLocality:    
          description: 'Property. The locality in which the street address is, and which is in the region. Model:''https://schema.org/Text'''    
          type: string    
        addressRegion:    
          description: 'Property. The region in which the locality is, and which is in the country. Model:''https://schema.org/Text'''    
          type: string    
        areaServed:    
          description: 'Property. The geographic area where a service or offered item is provided. Model:''https://schema.org/Text'''    
          type: string    
        postOfficeBoxNumber:    
          description: 'Property. The post office box number for PO box addresses. For example, Spain. Model:''https://schema.org/Text'''    
          type: string    
        postalCode:    
          description: 'Property. The postal code. For example, Spain. Model:''https://schema.org/Text'''    
          type: string    
        streetAddress:    
          description: 'Property. The street address. Model:''https://schema.org/Text'''    
          type: string    
      type: Property    
    areaServed:    
      description: 'The geographic area where a service or offered item is provided'    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Text    
    demandCategory:    
      description: 'Allows base demands and time patterns to be assigned to other categories of users.'    
      properties:    
        baseDemand:    
          description: 'Property. Model:''https://schema.org/Text. Baseline or average demand for the category. A sub-property of the Property ''demandCategory''.'    
          type: string    
        demandPattern:    
          description: 'Relationship. A relationship to the pattern pf the ''demandCategory'' property.'    
          format: uri    
          type: object    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Text    
    description:    
      description: 'An optional text that describes other significant information about the junction'    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Text    
    elevation:    
      description: 'The elevation above some common reference of the junction. All units are accepted in [CEFACT](https://www.unece.org/cefact.html) code'    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
        units: Metre    
    emitterCoefficient:    
      description: 'Discharge coefficient for emitter (sprinkler or nozzle) placed at junction. All units are accepted in [CEFACT](https://www.unece.org/cefact.html) code'    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
        units: 'square metre per second'    
    initialQuality:    
      description: 'Water quality level at the junction at the start of the simulation. All units are accepted in [CEFACT](https://www.unece.org/cefact.html) code'    
      type: Property    
      x-ngsi:    
        model: http://schema.org/Number    
        units: mg/L    
    location:    
      $id: https://geojson.org/schema/Geometry.json    
      $schema: "http://json-schema.org/draft-07/schema#"    
      oneOf:    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                type: number    
              minItems: 2    
              type: array    
            type:    
              enum:    
                - Point    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON Point'    
          type: object    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  type: number    
                minItems: 2    
                type: array    
              minItems: 2    
              type: array    
            type:    
              enum:    
                - LineString    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON LineString'    
          type: object    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    type: number    
                  minItems: 2    
                  type: array    
                minItems: 4    
                type: array    
              type: array    
            type:    
              enum:    
                - Polygon    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON Polygon'    
          type: object    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  type: number    
                minItems: 2    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiPoint    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiPoint'    
          type: object    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    type: number    
                  minItems: 2    
                  type: array    
                minItems: 2    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiLineString    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiLineString'    
          type: object    
        - properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    items:    
                      type: number    
                    minItems: 2    
                    type: array    
                  minItems: 4    
                  type: array    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiPolygon    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiPolygon'    
          type: object    
      title: 'GeoJSON Geometry'    
    sourceCategory:    
      description: 'Description of the quality of source flow entering the network at a specific node.'    
      properties:    
        sourcePattern:    
          description: 'Relationship. A relationship to the pattern pf the sourceCategory property'    
          format: uri    
          type: string    
        sourceQuality:    
          description: 'Property. Model:''https://schema.org/Number''. Units: ''mg/L''. Baseline or average concentration (or mass flow rate) of source. A sub-property of the Property ''sourceCategory''. All units are accepted in [CEFACT](https://www.unece.org/cefact.html) code.'    
          type: number    
        sourceType:    
          description: 'Property. Model:''https://schema.org/Text''. A sub-property of the Property ''sourceCategory'''    
          enum:    
            - CONCEN    
            - MASS    
            - FLOWPACED    
            - SETPOINT    
          type: string    
      required:    
        - type    
        - value    
        - sourceType    
        - sourceQuality    
        - sourcePattern    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Text    
    tag:    
      description: 'An optional text string used to assign the pipe to a category, perhaps one based on age or material'    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Text    
    type:    
      description: 'NGSI-LD Entity Type. It has to be Junction'    
      enum:    
        - Junction    
      type: Property    
  required:    
    - id    
    - type    
    - location    
    - elevation    
  type: object    
```  
</details>    
## Exemples de charges utiles  
#### Jonction NGSI V2 valeurs clés Exemple  
Voici un exemple d'une jonction au format JSON comme valeurs clés. Il est compatible avec NGSI V2 lorsque l'on utilise "options=keyValues" et renvoie les données de contexte d'une entité individuelle.  
```json  
{  
    "id": "63fe7d79-0d4c-4da9-b7d0-3340efa0656a",  
    "type": "Junction",  
    "location": {  
        "type": "Point",  
        "coordinates": [  
            24.30623,  
            60.07966  
        ]  
    },  
    "elevation": 105.8,  
    "demandCategory": {  
        "value": "agriculture demand",  
        "baseDemand": "1.763868462",  
        "demandPattern": "fbcb5fc8-8ca3-4533-a2eb-34bc89262190"  
    },  
    "sourceCategory": {  
        "value": "CategoryX",  
        "sourceType": "MASS",  
        "sourceQuality": 1.2,  
        "sourcePattern": "fbcb5fc8-8ca3-4533-a2eb-34bc89262190"  
    },  
    "tag": "DMA1",  
    "description": "This entity contains a harmonised description of a Junction",  
    "initialQuality": 0.5,  
    "emitterCoefficient": 0.526  
}  
```  
#### Jonction NGSI V2 normalisée Exemple  
Voici un exemple de jonction au format JSON normalisé. Ce format est compatible avec NGSI V2 lorsqu'il n'utilise pas d'options et renvoie les données de contexte d'une entité individuelle.  
```json  
{  
    "id": "63fe7d79-0d4c-4da9-b7d0-3340efa0656a",  
    "type": "Junction",  
    "location": {  
        "type": "geo:json",  
        "value": {  
            "type": "Point",  
            "coordinates": [  
                24.30623,  
                60.07966  
            ]  
        }  
    },  
    "elevation": {  
        "value": 105.8  
    },  
    "demandCategory": {  
        "value": {  
            "value": "agriculture demand",  
            "baseDemand": {  
                "value": "1.763868462"  
            },  
            "demandPattern": {  
                "type": "Relationship",  
                "value": "fbcb5fc8-8ca3-4533-a2eb-34bc89262190"  
            }  
        }  
    },  
    "sourceCategory": {  
        "value": {  
            "value": "CategoryX",  
            "sourceType": {  
                "value": "MASS"  
            },  
            "sourceQuality": {  
                "value": 1.2  
            },  
            "sourcePattern": {  
                "type": "Relationship",  
                "value": "fbcb5fc8-8ca3-4533-a2eb-34bc89262190"  
            }  
        }  
    },  
    "tag": {  
        "value": "DMA1"  
    },  
    "description": {  
        "value": "This entity contains a harmonised description of a Junction"  
    },  
    "initialQuality": {  
        "value": 0.5  
    },  
    "emitterCoefficient": {  
        "value": 0.526  
    }  
}  
```  
#### Jonction NGSI-LD valeurs clés Exemple  
Voici un exemple d'une jonction au format JSON-LD comme valeurs clés. Il est compatible avec le format NGSI-LD lorsqu'il utilise "options=keyValues" et renvoie les données de contexte d'une entité individuelle.  
```json  
{"@context": ["https://schema.lab.fiware.org/ld/context"],  
 "createdAt": "2020-02-20T15:42:00Z",  
 "demandCategory": "agriculture demand",  
 "description": "This entity contains a harmonised description of a Junction",  
 "elevation": 105.8,  
 "emitterCoefficient": 0.526,  
 "id": "urn:ngsi-ld:Junction:63fe7d79-0d4c-4da9-b7d0-3340efa0656a",  
 "initialQuality": 0.5,  
 "location": {"coordinates": [24.30623, 60.07966], "type": "Point"},  
 "modifiedAt": "2020-02-20T15:45:00Z",  
 "sourceCategory": "CategoryX",  
 "tag": "DMA1",  
 "type": "Junction"}  
```  
#### Jonction NGSI-LD normalisée Exemple  
Voici un exemple d'une jonction au format JSON-LD telle que normalisée. Ce format est compatible avec le format NGSI-LD lorsqu'il n'utilise pas d'options et renvoie les données de contexte d'une entité individuelle.  
```json  
{  
    "id": "urn:ngsi-ld:Junction:63fe7d79-0d4c-4da9-b7d0-3340efa0656a",  
    "type": "Junction",  
    "createdAt": "2020-02-20T15:42:00Z",  
    "modifiedAt": "2020-02-20T15:45:00Z",  
    "location": {  
        "type": "GeoProperty",  
        "value": {  
            "type": "Point",  
            "coordinates": [  
                24.30623,  
                60.07966  
            ]  
        }  
    },  
    "elevation": {  
        "type": "Property",  
        "value": 105.8,  
        "unitCode": "MTR"  
    },  
    "demandCategory": {  
        "type": "Property",  
        "value": "agriculture demand",  
        "baseDemand": {  
            "type": "Property",  
            "value": "1.763868462",  
            "unitCode": "MQS"  
        },  
        "demandPattern": {  
            "type": "Relationship",  
            "object": "urn:ngsi-ld:Pattern:fbcb5fc8-8ca3-4533"  
        }  
    },  
    "sourceCategory": {  
        "type": "Property",  
        "value": "CategoryX",  
        "sourceType": {  
            "type": "Property",  
            "value": "MASS"  
        },  
        "sourceQuality": {  
            "type": "Property",  
            "value": 1.2,  
            "unitCode": "M1"  
        },  
        "sourcePattern": {  
            "type": "Relationship",  
            "object": "urn:ngsi-ld:Pattern:fbcb5fc8-8ca3-4533-a2eb-34bc89262190"  
        }  
    },  
   "tag": {  
        "type": "Property",  
        "value": "DMA1"  
    },  
    "description": {  
        "type": "Property",  
        "value": "This entity contains a harmonised description of a Junction"  
    },  
    "initialQuality": {  
        "type": "Property",  
        "value": 0.5,  
        "unitCode":"M1"  
    },  
    "emitterCoefficient": {  
        "type": "Property",  
        "value": 0.526,  
        "unitCode": "S4"  
    },  
    "@context": [  
        "https://schema.lab.fiware.org/ld/context"  
    ]  
}  
```  
