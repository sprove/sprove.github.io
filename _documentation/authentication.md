---
title: Authentication
position_number: 4
subtitle: /auth
subtitle_type: post
headers:
  - name: Client-ID
    content: client_id you've got from us
  - name: Secret-Key
    content: secret_key you've got from us
content_markdown: |-
  You need to be authenticated to make API calls. Please, reach out to us to get credentials to try APIs.

  You can generate a token using this request.

  Please, keep in mind that token is valid for a limited time
  {: .info }

  Nothing will work unless you generate an API token
  {: .error}
left_code_blocks:
  - code_block:
    title:
    language:
right_code_blocks:
  - code_block: |2-
      $.ajax({
        url: 'https://demo.sprove.me/api/1.0/auth',
        headers: {
            'Client-ID': '<client_id>',
            'Secret-Key': '<secret_key>',
            'Content-Type': 'application/json'
        },
        method: 'POST',
        dataType: 'json',
        success: function(data){
          console.log('succes: ' + data);
        }
      });
    title: JQuery
    language: javascript
  - code_block: |2-
      curl -X POST -i -H "Content-Type: application/json" -H "Client-ID: <client_id>" -H "Secret-Key: <secret_key>" https://demo.sprove.me/api/1.0/auth
    title: Curl
    language: bash
---
