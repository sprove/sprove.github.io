---
title: Errors
position_number: 5
parameters:
  - name:
    content:
content_markdown: |-
  | Code | Name | Description |
  | --- | --- | --- |
  | 200 | OK | Success |
  | 201 | Created | Creation Successful |
  | 400 | Bad Request | We could not process that action |
  | 401 | Unauthorized | Something wrong with the credentials |
  | 403 | Forbidden | We couldn't authenticate you |
  | 404 | Not Found | This path is not available or requested data not found |

  All errors will return JSON in the following format:
left_code_blocks:
  - code_block: |-
      {
        "error": "error message here"
      }
    title: Response
    language: json
right_code_blocks:
  - code_block:
    title:
    language:
---
