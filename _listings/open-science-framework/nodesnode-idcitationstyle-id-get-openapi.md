---
swagger: "2.0"
x-collection-name: Open Science Framework
x-complete: 0
info:
  title: Open Science Framework Retrieve a styled citation
  description: |-
    The citation for a node in a specific style.
    #### Returns
    Returns a JSON object with a `data` key that contains the representation of the node citation, in the requested style.
  contact:
    name: OSF
    url: https://osf.io/support
    email: support@osf.io
  version: "2.0"
host: test-api.osf.io
basePath: /v2
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /citations/styles/:
    get:
      summary: List all citation styles
      description: |-
        A paginated list of all standard citation styles available for rendering citations.
        #### Returns
        Returns a JSON object containing `data` and `links` keys.

        The `data` key contains an array of 10 citation styles. Each resource in the array is a separate citation syle and contains the full representation of the citation style object.

        The `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).

        This request should never return an error.
        #### Filtering
        You can optionally request that the response only include citation styles that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/citations/styles/?filter[title]=open.

        Citation styles may be filtered by their `id`, `title`, `short-title`, and `summary`.
      operationId: citations_styles_list
      x-api-path-slug: citationsstyles-get
      responses:
        200:
          description: OK
      tags:
      - Citations
      - Styles
  /citations/styles/{style_id}/:
    get:
      summary: Retrieve a citation style
      description: |-
        Retrieves the details of a citation style.
        #### Returns
        Returns a JSON object with a `data` key containing the representation of the requested citation style, if the request is successful.

        If the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.
      operationId: citations_styles_read
      x-api-path-slug: citationsstylesstyle-id-get
      parameters:
      - in: path
        name: style_id
        description: The unique identifier of the citation style
      responses:
        200:
          description: OK
      tags:
      - Citations
      - Styles
      - Style
  /registrations/{registration_id}/citations/:
    get:
      summary: List all citation styles
      description: |-
        A paginated list of the registration's alternative citation styles

        #### Returns
        Returns a JSON object containing `data` and `links` keys.

        The `data` key contains an array of up to 10 citation styles. Each resource in the array is a separate citation styles object.

        The `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).
        #### Filtering
        You can optionally request that the response only include citation styles that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/registrations/wucr8/citations/?filter[title]=open.

        Citation styles may be filtered by their `id`, `title`, `short-title`, and `summary`.
      operationId: registrations_citations_list
      x-api-path-slug: registrationsregistration-idcitations-get
      parameters:
      - in: path
        name: registration_id
        description: The unique identifier of the registration
      responses:
        200:
          description: OK
      tags:
      - Registrations
      - Registration
      - Citations
  /registrations/{registration_id}/citations/{citation_id}/:
    get:
      summary: Retrieve a citation
      description: |-
        Retrieves the citation style details for a registration, in CSL format.
        #### Returns
        Returns a JSON object with a `data` key that contains the representation of the details necessary for the citation style.
      operationId: registrations_citation_read
      x-api-path-slug: registrationsregistration-idcitationscitation-id-get
      parameters:
      - in: path
        name: citation_id
        description: The unique identifier of the citation
      - in: path
        name: registration_id
        description: The unique identifier of the registration
      responses:
        200:
          description: OK
      tags:
      - Registrations
      - Registration
      - Citations
      - Citation
  /nodes/{node_id}/citation/:
    get:
      summary: Retrieve citation details
      description: |-
        The citation details for a node, in CSL format.
        #### Returns
        Returns a JSON object with a `data` key that contains the representation of the details necessary for the node citation.
      operationId: nodes_citation_list
      x-api-path-slug: nodesnode-idcitation-get
      parameters:
      - in: path
        name: node_id
        description: The unique identifier of the node
      responses:
        200:
          description: OK
      tags:
      - Nodes
      - Node
      - Citation
  /nodes/{node_id}/citation/{style_id}/:
    get:
      summary: Retrieve a styled citation
      description: |-
        The citation for a node in a specific style.
        #### Returns
        Returns a JSON object with a `data` key that contains the representation of the node citation, in the requested style.
      operationId: nodes_citation_read
      x-api-path-slug: nodesnode-idcitationstyle-id-get
      parameters:
      - in: path
        name: node_id
        description: The unique identifier of the node
      - in: path
        name: style_id
        description: The unique identifier of the citation style
      responses:
        200:
          description: OK
      tags:
      - Nodes
      - Node
      - Citation
      - Style
  /preprints/{preprint_id}/citation/:
    get:
      summary: Retrieve citation details
      description: |-
        The citation details for a preprint, in CSL format.
        #### Returns
        Returns a JSON object with a `data` key that contains the representation of the details necessary for the preprint citation.
      operationId: preprints_citation_list
      x-api-path-slug: preprintspreprint-idcitation-get
      parameters:
      - in: path
        name: preprint_id
        description: The unique identifier of the preprint whose citation you wish
          to retrieve
      responses:
        200:
          description: OK
      tags:
      - Preprints
      - Preprint
      - Citation
  /preprints/{preprint_id}/citation/{style_id}/:
    get:
      summary: Retrieve a styled citation
      description: |-
        The citation for a preprint in a specific style.
        #### Returns
        Returns a JSON object with a `data` key that contains the representation of the preprint citation, in the requested style.
      operationId: preprints_citation_read
      x-api-path-slug: preprintspreprint-idcitationstyle-id-get
      parameters:
      - in: path
        name: preprint_id
        description: The unique identifier of the preprint
      - in: path
        name: style_id
        description: The unique identifier of the citation style
      responses:
        200:
          description: OK
      tags:
      - Preprints
      - Preprint
      - Citation
      - Style
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