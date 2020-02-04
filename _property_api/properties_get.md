---
title: /properties/:id
position_number: 1.2
type: get
description: Get property information
parameters:
  - name: id
    content: (string) Property ID to retrieve.
content_markdown: |-
  Return property information by ID
left_code_blocks:
  - code_block: |-
      var settings = {
        "url": "https://demo.sprove.me/api/1.0//properties/c639a690-5650-4a0b-a91c-cb60d6eca1a8",
        "method": "GET",
        "timeout": 0,
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

      url = "https://demo.sprove.me/api/1.0//properties/c639a690-5650-4a0b-a91c-cb60d6eca1a8"

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
        'url': 'https://demo.sprove.me/api/1.0//properties/c639a690-5650-4a0b-a91c-cb60d6eca1a8',
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
      curl --location --request GET 'https://demo.sprove.me/api/1.0//properties/c639a690-5650-4a0b-a91c-cb60d6eca1a8' \
      --header 'Content-Type: application/json'
    title: Curl
    language: bash
right_code_blocks:
  - code_block: |2-
      {
        "property": {
          "id": "0183c015-d5da-44fb-8228-db50bc6a8380",
          "name": "1-bedroom apartment",
          "address": "Lars Hilles gate 30, 5008 Bergen",
          "rent": 7500,
          "rent_currency": "NOK",
          "deposit": 0,
          "deposit_currency": "NOK",
          "verification_url": "https://demo.sprove.me/properties/0183c015-d5da-44fb-8228-db50bc6a8380"
        }
      }
    title: Response
    language: json
---
