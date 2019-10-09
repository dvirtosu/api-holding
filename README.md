---
description: API Management
---

# Services

## Scop

      Idea este realizarea interconexiunii a mai multor sisteme informationale . Scopul final este reducerea timpului, privind colectarea dublata a aceasi informatiei in diferite sisteme si de diferite persoane.  
    Realizand un API intre sisteme business, se va ajunge la urmatoarele avantaje:

* Centralizarea informatiei
* Minimizarea numarului de sisteme utilizate pentru fiecare rol \(pentru ca informatia va fi sincronizata , si nu va trebui sa deschizi diferite sisteme informationale pentru a gasi ce trebuie\)
* Documentarea proceselor existente
* Monitorizarea si intervenirea la timp pe acelea segmente , care sunt incarcate sau nu sunt acoperite de loc.

## Sisteme Informationale

<table>
  <thead>
    <tr>
      <th style="text-align:left">Denumirea sistemului</th>
      <th style="text-align:left">Descriere</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p></p>
        <p>OTRS</p>
      </td>
      <td style="text-align:left">
        <p></p>
        <p>Sistem de HelpDesk &amp; ServiceDesk (supportit.md)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Terrasoft</td>
      <td style="text-align:left">Sistem intern de CRM</td>
    </tr>
    <tr>
      <td style="text-align:left">1C</td>
      <td style="text-align:left">Sistem de contabilitate</td>
    </tr>
    <tr>
      <td style="text-align:left">PowerBI</td>
      <td style="text-align:left">Sistem de analiza informatiei &amp; Dashboards</td>
    </tr>
  </tbody>
</table>## Arhitectura

{% tabs %}
{% tab title="Centralizata " %}
Totalitatea apelurilor sunt adresate catre un singur endpoint. La fel sistemul dat nu realizeaza nici o apelare in extern, astfel ne fiind dependent de disponibilitatea sistemelor terte.

```bash
curl -H 'Accept: application/json' -H "Authorization: Bearer ${TOKEN}"
 https://api.esempla.srl/v1/login
```

{% hint style="success" %}
Solutia recomandata, pentru usurarea si standartizarea atat a metodelor de autentificare, cat si a documentare si monitorizarea serviciilor curente
{% endhint %}
{% endtab %}

{% tab title="Hybrid" %}
Varianta Hybrid,  pastreaza apelarea tuturor  serviciilor de pe un singur endpoint, dar in marea parte a sa se comporta ca un proxy API, astfel redirectionand datele sau requesturi catre sistemul destinatie

```bash
curl -H 'Accept: application/json' -H "Authorization: Bearer ${TOKEN}"
 https://api.esempla.srl/v1/login
```

{% hint style="success" %}
Solutia recomandata, pentru usurarea si standartizarea atat a metodelor de autentificare, cat si a documentare si monitorizarea serviciilor curente
{% endhint %}
{% endtab %}

{% tab title="Decentralizata" %}
Se duce evidenta , doar la documentatie centralizat. Implementarea serviciilor disponibile , se realizeaza de catre fiecare sistem in parte.

{% hint style="danger" %}
In asa situatie fiecare implementeaza mecanismul sau de autentificare, configurare de unde apar apelari. La fel va fi greu de monitorizat disponibilitatea serviciilor
{% endhint %}
{% endtab %}
{% endtabs %}

