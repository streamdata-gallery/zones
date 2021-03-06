---
swagger: "2.0"
x-collection-name: Hewlett Packard Enterprise (HPE)
x-complete: 0
info:
  title: HPE OneSphere API Delete Zones
  description: Deletes a zone
  termsOfService: http://www.hpe.com/onesphere
  contact:
    name: HPE OneSphere API team
    url: http://www.hpe.com/onesphere
  version: 1.0.0
host: deic02-hpe.hpeonesphere.com
basePath: /rest
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /zones:
    get:
      summary: Get Zones
      description: Returns zones.
      operationId: FindZones
      x-api-path-slug: zones-get
      parameters:
      - in: query
        name: applianceUri
        description: The appliance URI to prune zones by
      - in: query
        name: providerUri
        description: The provider URI to prune zones by
      - in: query
        name: query
        description: Filters the zones returned
      - in: query
        name: regionUri
        description: The region URI to prune zones by
      - in: query
        name: view
        description: 'Return related resources:  * `full` - Include all the details
          of the zones'
      responses:
        200:
          description: OK
      tags:
      - Zones
    post:
      summary: Post Zones
      description: Creates a new zone
      operationId: CreateZone
      x-api-path-slug: zones-post
      parameters:
      - in: body
        name: zone
        description: Add new zone
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Zones
  /zones/{id}:
    delete:
      summary: Delete Zones
      description: Deletes a zone
      operationId: DeleteZone
      x-api-path-slug: zonesid-delete
      parameters:
      - in: query
        name: force
        description: Zones may be in an odd state
      - in: path
        name: id
        description: ID of zone to delete
      responses:
        200:
          description: OK
      tags:
      - Zones
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---