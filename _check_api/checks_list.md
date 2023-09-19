---
title: /properties/:property_id/checks
position_number: 1.0
type: get
description: List all verifications completed for the property
parameters:
  - name: tenant_name
    content: (string) Tenant name collected during the verification process.
  - name: approved
    content: (boolean) Verification result.
  - name: valid_until
    content: (number) Timetamp while the verification result is valid (in seconds).
parameters_title: Response data
content_markdown: |-
  No limit on number of the values returned
  {: .info }

  List all verifications completed for the selected property
left_code_blocks:
  - code_block: |-
      var settings = {
        "url": "https://demo.sprove.me/api/1.0//properties/c639a690-5650-4a0b-a91c-cb60d6eca1a8/checks",
        "method": "GET",
        "headers": {
          "Content-Type": "application/json"
        },
      };

      $.ajax(settings).done(function (response) {
        console.log(response);
      });
    title: jQuery
    language: javascript
  - code_block: |-
      import requests

      url = "https://demo.sprove.me/api/1.0//properties/c639a690-5650-4a0b-a91c-cb60d6eca1a8/checks"

      payload = {}
      headers = {
        'Content-Type': 'application/json'
      }

      response = requests.request("GET", url, headers=headers, data = payload)

      print(response.text.encode('utf8'))
    title: Python
    language: python
  - code_block: |-
      var request = require('request');

      var options = {
        'method': 'GET',
        'url': 'https://demo.sprove.me/api/1.0//properties/c639a690-5650-4a0b-a91c-cb60d6eca1a8/checks',
        'headers': {
          'Content-Type': 'application/json'
        }
      };

      request(options, function (error, response) {
        if (error) throw new Error(error);
        console.log(response.body);
      });
    title: Node.js
    language: javascript
  - code_block: |-
      curl --location --request GET 'https://demo.sprove.me/api/1.0//properties/c639a690-5650-4a0b-a91c-cb60d6eca1a8/checks' \
      --header 'Content-Type: application/json'
    title: Curl
    language: bash
right_code_blocks:
  - code_block: |2-
      {
        "checks": [
          {
            "tenant_name": "John Doe",
            "approved": true,
            "valid_until": 1579357302,
            "max_rent": 10000,
            "avg_wage": 25000,
            "current_rent": 8000
          },
          {
            "tenant_name": "Jane Doe",
            "approved": false,
            "valid_until": null,
            "max_rent": 5000,
            "avg_wage": 15000,
            "current_rent": 3500
          },
          {
            "tenant_name": "Olav Nordmann",
            "approved": true,
            "valid_until": 1599357302,
            "max_rent": 18000,
            "avg_wage": 35000,
            "current_rent": 12000
          }
        ],
        "property_id": "c639a690-5650-4a0b-a91c-cb60d6eca1a8"
      }
    title: Response
    language: json
---
