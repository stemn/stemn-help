# Search

{% api-method method="get" host="https://stemn.com" path="/api/v1/search" %}
{% api-method-summary %}
Search
{% endapi-method-summary %}

{% api-method-description %}
Search for entities
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="page" type="number" required=false %}
The page number
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" required=true %}
Entity type to search for. project \| user \| field
{% endapi-method-parameter %}

{% api-method-parameter name="size" type="number" %}
The number of results to return  
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Search completed successfully.
{% endapi-method-response-example-description %}

```javascript
[
  // Array of entity objects
]
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Configuration error.
{% endapi-method-response-example-description %}

```javascript
{
    "error": "You must supply a type!"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



