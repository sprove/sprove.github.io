---
title: /properties/:id
position_number: 1.3
type: put
description: Update a property with defined ID
parameters:
  - name: name
    content: (string) Update a name.
  - name: address
    content: (string) Full or part of the property address. Please, make it easy to tenant to see what property they apply to.
  - name: rent
    content: (number) Rental monthly payment.
  - name: rent_currency
    content: '(string) Currency code: 3-letter following ISO-4217.'
  - name: deposit
    content: (number) Deposit amount in currency/
  - name: deposit_currency
    content: '(string) Currency code: 3-letter following ISO-4217.'
content_markdown: |-
  Please, note that at least one field should be set under the 'property' key
  {: .warning }

  Update the property by the ID.

  You can also use <span style="color: green; font-weight: bold;">PATCH</span> request type for this request
  {: .success }

  Note that name and address will be visible to a potential tenant.
  {: .info }
left_code_blocks:
  - code_block: |-
      var settings = {
        "url": "https://demo.sprove.me/api/1.0//properties/c639a690-5650-4a0b-a91c-cb60d6eca1a8",
        "method": "PUT",
        "timeout": 0,
        "headers": {
          "Content-Type": "application/json"
        },
        "data": JSON.stringify({"property":{"name":"My secret spot","address":"Norway","rent":100000,"rent_currency":"NOK"}}),
      };

      $.ajax(settings).done(function (response) {
        console.log(response);
      });
    title: jQuery
    language: javascript
  - code_block: |-
      import requests

      url = "https://demo.sprove.me/api/1.0//properties/c639a690-5650-4a0b-a91c-cb60d6eca1a8"

      payload = {
        "property": {
          "name": "2-bedroom apartment",
          "address": "Daniel Hilsens gate 20, 5008 Bergen",
          "rent": 12000,
          "rent_currency": "NOK"
        }
      }

      headers = {
        'Content-Type': 'application/json'
      }

      response = requests.request("PUT", url, headers=headers, data = payload)

      print(response.text.encode('utf8'))
    title: Python
    language: python
  - code_block: |-
      var request = require('request');

      var options = {
        'method': 'PUT',
        'url': 'https://demo.sprove.me/api/1.0//properties/c639a690-5650-4a0b-a91c-cb60d6eca1a8',
        'headers': {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify({"property":{"name":"2-bedroom apartment","address":"Daniel Hilsens gate 20, 5008 Bergen","rent":12000,"rent_currency":"NOK"}})

      };

      request(options, function (error, response) {
        if (error) throw new Error(error);
        console.log(response.body);
      });
    title: Node.js
    language: javascript
  - code_block: |-
      curl --location --request PUT 'https://demo.sprove.me/api/1.0//properties/c639a690-5650-4a0b-a91c-cb60d6eca1a8' \
      --header 'Content-Type: application/json' \
      --data-raw '{
        "property": {
          "name": "2-bedroom apartment",
          "address":"Daniel Hilsens gate 20, 5008 Bergen",
          "rent": 12000,
          "rent_currency": "NOK"
        }
      }'
    title: Curl
    language: bash
right_code_blocks:
  - code_block: |2-
      No content
    title: Response
    language: json
---
