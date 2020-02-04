---
title: /properties/:id
position_number: 1.4
type: delete
description: Remove a property with defined ID
content_markdown: |-
  Remove the property by the ID.

  Note that there is still possible to get usage statistics after property has been deleted.
  {: .info }
left_code_blocks:
  - code_block: |-
      var settings = {
        "url": "https://demo.sprove.me/api/1.0//properties/c639a690-5650-4a0b-a91c-cb60d6eca1a8",
        "method": "DELETE",
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

      response = requests.request("DELETE", url, headers=headers, data = payload)

      print(response.text.encode('utf8'))
    title: Python
    language: python
  - code_block: |-
      var request = require('request');

      var options = {
        'method': 'DELETE',
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
      curl --location --request DELETE 'https://demo.sprove.me/api/1.0//properties/c639a690-5650-4a0b-a91c-cb60d6eca1a8' \
      --header 'Content-Type: application/json'
    title: Curl
    language: bash
right_code_blocks:
  - code_block: |2-
      No content
    title: Response
    language: json
---
