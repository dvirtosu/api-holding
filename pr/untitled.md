# API Client

{% api-method method="put" host="https://api.esempla.srl" path="/v1/organisation" %}
{% api-method-summary %}
PUT Organisation
{% endapi-method-summary %}

{% api-method-description %}
          Acest serviciu, permite inregistrarea unei noi organizatii. De exemplu, dupa inregistrarea unui nou contract in 1C, datele se transmit in regim automat in sistemul OTRS pentru a inregistra organizatia respectiva.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Metoda de autentificare, recomand Bearer token.  
De obicei, noi utilizam JWT Token  
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="idno" type="string" required=true %}
idno-ul organizatiei
{% endapi-method-parameter %}

{% api-method-parameter name="short\_name" type="string" required=true %}
codul organizatiei
{% endapi-method-parameter %}

{% api-method-parameter name="full\_name" type="string" required=true %}
denumire deplina
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=false %}
adresa de email
{% endapi-method-parameter %}

{% api-method-parameter name="phone" type="string" required=false %}
idno-ul onumar de telefonrganizatiei
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Organisation create successfully.
{% endapi-method-response-example-description %}

```bash
{
    "message": "Organisation was created with id X"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
In case if our credentials are expired  or invalid
{% endapi-method-response-example-description %}

```bash
{
    "message": "check your credentials"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
Recomandam TOKEN JWT,  detalii puteti gasi pe RFC 7519 [https://tools.ietf.org/html/rfc7519](https://tools.ietf.org/html/rfc7519)
{% endhint %}

{% api-method method="get" host="https://api.esempla.srl" path="/v1/organisation" %}
{% api-method-summary %}
Get Organisation List
{% endapi-method-summary %}

{% api-method-description %}
Get full list of organisations
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Metoda de autentificare, recomand Bearer token.  
De obicei, noi utilizam JWT Token
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```bash
[
  {
    "id": 1,
    "idno": 200100166321,
    "code": "BMA",
    "title": "Birou Migratie si Azil"
  },
  {
    "id": 2,
    "idno": 200100166322,
    "code": "MBSG",
    "title": "Mobias Banca"
  }
]
  
  
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```bash
{
  "message": "check your credentials
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.esempla.srl" path="/v1/organisation/:id" %}
{% api-method-summary %}
Get Organisation by id
{% endapi-method-summary %}

{% api-method-description %}
get one organisation by id
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Metoda de autentificare, recomand Bearer token.  
De obicei, noi utilizam JWT Token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
id organizatii
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```bash
 {
    "id": 1,
    "idno": 200100166321,
    "code": "BMA",
    "title": "Birou Migratie si Azil"
  }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```bash
{
  "message": "check your credentials
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```bash
{
    "message": "Organisation with this ID is not found
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.esempla.srl" path="/v1/organisation/check" %}
{% api-method-summary %}
Check Organisation
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Metoda de autentificare, recomand Bearer token.  
De obicei, noi utilizam JWT Token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="idno" type="string" required=true %}
idno
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```bash
{
    "message": "true"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

