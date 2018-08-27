{
  "info": {
    "name": "Open Science Framework Retrieve a citation style",
    "_postman_id": "28d1bd47-c0ff-45fc-b5e2-b3af54a8a18c",
    "description": "Retrieves the details of a citation style.\n#### Returns\nReturns a JSON object with a `data` key containing the representation of the requested citation style, if the request is successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Root",
      "item": [
        {
          "id": "2e5324cd-8431-496e-be7d-ef5bae306496",
          "name": "base_read",
          "request": {
            "url": "http://test-api.osf.io/v2/",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Welcome to the Open Science Framework API. With this API you can access users, projects, components, logs, and files from the [Open Science Framework](https://osf.io/). The Open Science Framework (OSF) is a free, open-source service maintained by the [Center for Open Science](http://cos.io/).\n\n#### Returns\nA JSON object with `meta` and `links` keys.\n\nThe `meta` key contains information such as a welcome message from the API, the specified version of the request, and the full representation of the current user, if authentication credentials were provided in the request.\n\nThe `links` key contains links to the following entity collections: [addons](), [collections](), [institutions](#Institutions_institutions_list), [licenses](#Licenses_license_list), [metaschemas](), [nodes](#Nodes_nodes_list), [registrations](), [users](#Users_users_list)"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "c385e691-dbb7-45e1-9b36-28c9b85056d1"
            }
          ]
        }
      ]
    },
    {
      "name": "Actions",
      "item": [
        {
          "id": "f73a656a-7dcd-4886-90fc-792109464ae9",
          "name": "logs_actions",
          "request": {
            "url": "http://test-api.osf.io/v2/actions/",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "A log can have one of many actions. The complete list of loggable actions (in the format {identifier}: {description}) is as follows:\n* `project_created`: A Node is created\n* `project_registered`: A Node is registered\n* `project_deleted`: A Node is deleted\n* `created_from`: A Node is created using an existing Node as a template\n* `pointer_created`: A Pointer is created\n* `pointer_forked`: A Pointer is forked\n* `pointer_removed`: A Pointer is removed\n* `node_removed`: A component is deleted\n* `node_forked`: A Node is forked\n---\n* `made_public`: A Node is made public\n* `made_private`: A Node is made private\n* `tag_added`: A tag is added to a Node\n* `tag_removed`: A tag is removed from a Node\n* `edit_title`: A Node's title is changed\n* `edit_description`: A Node's description is changed\n* `updated_fields`: One or more of a Node's fields are changed\n* `external_ids_added`: An external identifier is added to a Node (e.g. DOI, ARK)\n* `view_only_link_added`: A view-only link was added to a Node\n* `view_only_link_removed`:  A view-only link was removed from a Node\n---\n* `contributor_added`: A Contributor is added to a Node\n* `contributor_removed`: A Contributor is removed from a Node\n* `contributors_reordered`: A Contributor's position in a Node's bibliography is changed\n* `permissions_updated`: A Contributor`s permissions on a Node are changed\n* `made_contributor_visible`: A Contributor is made bibliographically visible on a Node\n* `made_contributor_invisible`: A Contributor is made bibliographically invisible on a Node\n---\n* `wiki_updated`: A Node's wiki is updated\n* `wiki_deleted`: A Node's wiki is deleted\n* `wiki_renamed`: A Node's wiki is renamed\n* `made_wiki_public`: A Node's wiki is made public\n* `made_wiki_private`: A Node's wiki is made private\n---\n* `addon_added`: An add-on is linked to a Node\n* `addon_removed`: An add-on is unlinked from a Node\n* `addon_file_moved`: A File in a Node's linked add-on is moved\n* `addon_file_copied`: A File in a Node's linked add-on is copied\n* `addon_file_renamed`: A File in a Node's linked add-on is renamed\n* `node_authorized`: An addon is authorized for a project\n* `node_deauthorized`: An addon is deauthorized for a project\n* `folder_created`: A Folder is created in a Node's linked add-on\n* `file_added`: A File is added to a Node's linked add-on\n* `file_updated`: A File is updated on a Node's linked add-on\n* `file_removed`: A File is removed from a Node's linked add-on\n* `file_restored`: A File is restored in a Node's linked add-on\n---\n* `comment_added`: A Comment is added to some item\n* `comment_removed`: A Comment is removed from some item\n* `comment_updated`: A Comment is updated on some item\n---\n* `embargo_initiated`: An embargoed Registration is proposed on a Node\n* `embargo_approved`: A proposed Embargo of a Node is approved\n* `embargo_cancelled`: A proposed Embargo of a Node is cancelled\n* `embargo_completed`: A proposed Embargo of a Node is completed\n* `retraction_initiated`: A Withdrawal of a Registration is proposed\n* `retraction_approved`: A Withdrawal of a Registration is approved\n* `retraction_cancelled`: A Withdrawal of a Registration is cancelled\n* `registration_initiated`: A Registration of a Node is proposed\n* `registration_approved`: A proposed Registration is approved\n* `registration_cancelled`: A proposed Registration is cancelled"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "9647206e-fc9c-4f12-83cf-0943bafb7ef0"
            }
          ]
        }
      ]
    },
    {
      "name": "Addons",
      "item": [
        {
          "id": "73cfa278-2577-4532-934f-1aac63aafa60",
          "name": "addons_list",
          "request": {
            "url": "http://test-api.osf.io/v2/addons/",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "A paginated list of addons configurable with the OSF\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of up to 10 addons. Each resource in the array is a separate addon object.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nThis request should never return an error."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "77e26bd4-f20a-4fb1-a94e-0f83504daf64"
            }
          ]
        }
      ]
    },
    {
      "name": "Citations",
      "item": [
        {
          "id": "8a185131-09d2-4150-8c41-5add86560538",
          "name": "citations_styles_list",
          "request": {
            "url": "http://test-api.osf.io/v2/citations/styles/",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "A paginated list of all standard citation styles available for rendering citations.\n#### Returns\nReturns a JSON object containing `data` and `links` keys.\n\nThe `data` key contains an array of 10 citation styles. Each resource in the array is a separate citation syle and contains the full representation of the citation style object.\n\nThe `links` key contains a dictionary of links that can be used for [pagination](#Introduction_pagination).\n\nThis request should never return an error.\n#### Filtering\nYou can optionally request that the response only include citation styles that match your filters by utilizing the `filter` query parameter, e.g. https://api.osf.io/v2/citations/styles/?filter[title]=open.\n\nCitation styles may be filtered by their `id`, `title`, `short-title`, and `summary`."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "1737248d-4121-47f9-8370-5a1fbcbc6cdb"
            }
          ]
        },
        {
          "id": "ebf5673e-3116-43d9-9b18-3c89019a2810",
          "name": "citations_styles_read",
          "request": {
            "url": {
              "protocol": "http",
              "host": "test-api.osf.io",
              "path": [
                "v2",
                "citations/styles/:style_id/"
              ],
              "variable": [
                {
                  "id": "style_id",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieves the details of a citation style.\n#### Returns\nReturns a JSON object with a `data` key containing the representation of the requested citation style, if the request is successful.\n\nIf the request is unsuccessful, an `errors` key containing information about the failure will be returned. Refer to the [list of error codes](#Introduction_error_codes) to understand why this request may have failed."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "3481baae-d0cd-45ea-a924-35ece295c05f"
            }
          ]
        }
      ]
    }
  ]
}