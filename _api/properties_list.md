---
title: /properties
position_number: 1.0
type: get
description: List all properties
parameters:
  - name: page
    content: (number) Page number. If not specified, first page is displayed.
  - name: per_page
    content: (number) Page limit. Define how many items to display.
  - name: active
    content: (boolean, string) Show only active properties
content_markdown: |-
  This call will return a maximum of 100 properties
  {: .info }

  Lists all the properties you have access to. You can paginate by using the parameters listed above.
left_code_blocks:
  - code_block: |-
      $.ajax({
        url: 'https://demo.sprove.me/api/1.0/properties',
        data: {
          page: 2,
          per_page: 50
        }
        headers: {
          'Authorization': 'Bearer <token>',
          'Content-Type': 'application/json'
        },
        method: 'GET',
        dataType: 'json',
        success: function(data){
          console.log('succes: ' + data);
        }
      });
    title: jQuery
    language: javascript
  - code_block: |-
      r = requests.get("https://demo.sprove.me/api/1.0/properties", headers={ "Authorization": "Bearer <token>", "Content-Type": "application/json" })
      print r.text
    title: Python
    language: python
  - code_block: |-
      var request = require("request");

      function callback (error, response, body) {
        if (!error && response.statusCode == 200) {
          console.log(body);
        }
      }

      request({ url: "https://demo.sprove.me/api/1.0/properties", qs: { page: 2, per_page: 50 }, headers: { "Authorization": "Bearer <token>", "Content-Type": "application/json" }}, callback)
    title: Node.js
    language: javascript
  - code_block: |-
      curl -i -H "Content-Type: application/json" -H "Authorization: Bearer <token>" https://demo.sprove.me/api/1.0/properties?page=2&per_page=50&active=true
    title: Curl
    language: bash
right_code_blocks:
  - code_block: |2-
      {
        "properties": [
          {
            "id": "b685e471-b546-49a7-9fbc-30e3303c46b6",
            "name": "Olav kyres gate 1",
            "active": true,
            "rent_cents": 750000,
            "rent_currency": "NOK",
            "deposit_cents": 1500000,
            "deposit_currency": "NOK",
            "verification_url": "https://demo.sprove.me/properties/b685e471-b546-49a7-9fbc-30e3303c46b6"
          }
        ],
        "page": 1,
        "per_page": 10
      }
    title: Response
    language: json
---
