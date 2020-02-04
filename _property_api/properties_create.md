---
title: /properties
position_number: 1.1
type: post
description: Create a new property
parameters:
  - name: name
    content: (string) Give property a name.
  - name: address
    content: (string) Full or part of the property address. Please, make it easy to tenant to see what property they apply to.
  - name: rent
    content: (number) Rental monthly payment.
  - name: rent_currency
    content: '(string) Currency code: 3-letter following ISO-4217'
  - name: deposit
    content: (number) Deposit amount in currency (optional)
  - name: deposit_currency
    content: '(string) Currency code: 3-letter following ISO-4217 (optional)'
content_markdown: |-
  Please, note that all fields should be put under the 'property' key
  {: .warning }

  Add a new property to the account

  Note that name and address will be visible to a potential tenant.
  {: .info }
left_code_blocks:
  - code_block: |-
      $.ajax({
        url: 'https://demo.sprove.me/api/1.0/properties',
        data: {
          property: {
            name: "1-bedroom apartment",
            address: "Lars Hilles gate 30, 5008 Bergen",
            rent: 7500,
            rent_currency: "NOK",
          }
        }
        headers: {
          'Authorization': 'Bearer <token>',
          'Content-Type': 'application/json'
        },
        method: 'POST',
        dataType: 'json',
        success: function(data){
          console.log('succes: ' + data);
        }
      });
    title: jQuery
    language: javascript
  - code_block: |-
      data = {
        'property': {
          'name': "1-bedroom apartment",
          'address': "Lars Hilles gate 30, 5008 Bergen",
          'rent': 7500,
          'rent_currency': "NOK",
        }
      }

      r = requests.post(url="https://demo.sprove.me/api/1.0/properties", data=data, headers={ "Authorization": "Bearer <token>", "Content-Type": "application/json" })
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

      request.post({ url: "https://demo.sprove.me/api/1.0/properties", json: { property: { name: "1-bedroom apartment", address: "Lars Hilles gate 30, 5008 Bergen", rent: 7500, rent_currency: "NOK" } }, headers: { "Authorization": "Bearer <token>" }}, callback)
    title: Node.js
    language: javascript
  - code_block: |-
      curl -i -X POST -H "Content-Type: application/json" -H "Authorization: Bearer <token>" https://demo.sprove.me/api/1.0/properties -d '{ "property": { "name": "Blekenberg 20", "address":"Blekenberg 20", "rent": 7500, "rent_currency": "NOK" } }'
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
